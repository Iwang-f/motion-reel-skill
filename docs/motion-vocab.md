# Motion vocabulary

The studio's catalogue of moves. Every move below is an export of [`lib/fx.js`](../lib/fx.js), a pure function of
time that draws on a canvas 2D context, so a film reaches showreel density by combining moves instead of inventing
them. Every move is on screen in the demo, [`film/fx-demo/film.js`](../film/fx-demo/film.js)
(`node render.mjs --film=fx-demo --format=9x16`); the last column of each table gives its time there.

## Pace

- Cut, or bring in a new idea, every 1–1.5 s (60–90 frames). At 120 BPM that is every 2 or 3 beats.
- Put motion on every beat: a hit, a swap, a punch, a line that draws, a camera move.
- Use at least 5 different moves in the first 3 s (recipe A). The demo uses eleven.
- Land hits on the beat grid (`beats.json`). A slam's impact comes 5 frames after it starts, so start it 5 frames
  early (`t - beat + fr(5)`).
- Let the frame rest once, at the end: 0.4–0.8 s held on the end card.

## Timing numbers

Craft from @flxrnc and `kelano86/what-if-animation`, not measured here (`REFERENCES/motion/reels-study-2026-11.md`).

- One hero per shot. Secondary moves travel 50–70 % of its distance and start 100–200 ms later; ambient motion stays under 5 %.
- Enter on ease-out; exit on ease-in, 40–50 % shorter. Position may overshoot; opacity settles without a bounce.
- Hold text 0.3 s per word plus 0.5 s, with a 2 % push running through the hold.
- A visual hit lands 1 frame before its sound. A pop on a spoken word covers the word: land it in the pause right after.
- Every cut arrives on a frame that already holds something. Whatever touches the ground gets a contact shadow; props sit darker
  than the character.
- Turn notes into numbers: "make it pop" is scale 1.0 → 1.08 → 1.0 over 6 frames; "too busy" is remove 30 % of the moves.

## Conventions

- `u` is seconds since the move starts; `u < 0` draws nothing (or the "before" state). Give each move its own
  `u = t - start` and the moves compose freely.
- Write lengths in frames with `fr(n)` (`fr(6)` = 0.1 s). At 120 BPM a beat is 30 frames and a half beat 15.
- Text style: `{ font: FONT.display | FONT.ui, px, ls (em), c }`. `FONT.display` is Space Grotesk 700 and
  `FONT.ui` is JetBrains Mono 500, the house's two faces. `fitPx(s, st, width)` gives the px that makes a word
  exactly `width` wide.
- Springs come from `lib/motion.js` (`TYPE` for type, `DOT` for dots and nodes, `SOFT` for long travel, `SNAP`) plus
  two in `fx.js`: `SLAM` (one 16 % overshoot, settled in about 21 frames) and `ROLL` (digit reels, about 36 frames).
  Use `EASE.*` with `prog(u, dur, ease)` for moves of fixed length (wipes, pushes, draw-ons).
- Post moves (`rgbSplit`, `smear`) read a finished frame. Draw the scene into `layer('<name>', W, H)` and composite
  it. Give every nested use its own layer name. The library already uses `fx-whip` and `fx-rgb0..2`.
- Paint backgrounds oversized (`fillRect(-300, -300, W + 600, H + 600)`) so shakes and tilts never show an edge.
- The render already averages 4 subframes over a 0.5 shutter, so anything fast gets real motion blur. Add `smear`
  only for the 1–3 fastest frames of a whip.

## Kinetic type

| Move | Export | Use it for | Length @ 60 fps | Combine with | Demo |
|---|---|---|---|---|---|
| Word slam | `slam(ctx, u, s, { x, y, st, from, sp, rot })` | The loudest word of a scene, on a downbeat. Starts at `from` × (2.4–2.8) and lands on `SLAM` | impact at 5 f, settled by 21 f | shake + RGB split + punch on the impact; invert on the third slam of a run | 0.0 MOVE, 12.0 ALL, 12.5 OUT. |
| Per-letter stagger | `stagger(ctx, u, s, { each, order, mode, out })` | Second lines, lower-case asides, names. `mode` rise / drop / scale / spin; `order` ltr / rtl / center / edges / seeded | 2 f per letter + 15 f to settle | under a slam (half a beat later); a line drawn under it | 0.5 every frame. |
| Mask reveal | `maskReveal(ctx, u, lines, { lh, each, out })` | Headline blocks and labels: each line rises from its own baseline inside a clip, and leaves upward the same way | 15 f per line, 5 f between lines; exit 12 f | punch on the next beat; venetian bars or a diagonal into the scene | 3.1 TYPE THAT LANDS., every mono label |
| Split-flap | `splitFlap(ctx, u, s, { cw, ch, each, flips, flip })` | Numbers and codes that should feel mechanical: counts, tickers, timecodes | 3 f per flap × 6–8 flaps, cells 3–4 f apart | a mono line under it; a dots wipe in | 10.66 900 FRAMES |
| Number roll | `numberRoll(ctx, u, { to, from, turns, each, sp })` | Any figure that matters. Each digit column spins to its target, right column first | 24 f (`[16, 1]`) to 36 f (`ROLL`) | counter ticks around it; punch when it lands | 1.06 60, 6.08 24 |
| Fill-the-frame type | `fillType(ctx, u, s, { fit, fill, s0, anchor })` | One short word that becomes the whole picture; anchor on a stem to push through it next | 30–36 f to fill | `push` + `camera` through a stroke (match cut on its ink) | 4.56 BIG |
| Swap in place | `swapWord(ctx, u, keys, o)` | A sentence with one changing word (ON THE BEAT → CUT. → HIT.). Returns the slot width for what follows | 12–15 f per swap; swap at most every 15 f | a small shake + RGB split on each swap | 2.0–3.0 |

## Matte transitions

Run any matte with `transition(ctx, k, matte, o, drawA, drawB, lead)`. `k` is the eased progress. `lead: { c, lag }`
sends a colour band ahead of B, which makes a 10-frame wipe read as designed: use the accent or the other room's
colour. Each matte only adds subpaths, so it can also clip or fill anything else.

| Move | Export | Use it for | Length | Combine with | Demo |
|---|---|---|---|---|---|
| Iris | `iris(ctx, k, { cx, cy })` | Out of a round thing on screen (the O of a word, a node, a dot) into the next room | 12–14 f, `inOutCubic` | lime lead band (`lag` 0.16) | 1.0 from the O of MOVE |
| Bars / venetian | `bars(ctx, k, { n, dir, style, each, order })` | Changing rooms on a downbeat with a rhythm of its own. `venetian` thickens each band; `slide` runs them across | 14–16 f, linear k (each bar eases itself) | a white or paper lead band; mask reveal in B | 3.0 onto the lime field |
| Diagonal wipe | `diagonal(ctx, k, { angle })` | A fast, directional change; the edge angle carries the energy of the cut | 10–14 f | the outgoing room's colour as the lead band | 4.5 |
| Shape morph | `morph(ctx, k, { a, b })`, `mixShape`, `fillShape`, `rectShape`, `circleShape` | Rect ↔ circle ↔ rounded card. As a graphic: a bar becomes a node. As a matte: a node opens into the next room | matte 10–12 f; graphic 20–30 f on a spring, 3 f stagger | connectors from the morphed nodes; punch on arrival | 7.5 bars → nodes, 8.9 hub → frame |
| Halftone-dot wipe | `dots(ctx, k, { pitch, angle, from, soft })` | Print texture without a texture: dots grow along a direction (or from a point) and merge | 18–24 f, linear k | split-flap or big type in B | 10.5 |
| Radial sweep | `sweep(ctx, k, { cx, cy, a0, dir, blades })` | Out of something that turns or scans: a radar beam, a dial, a clock hand (one wedge from `a0`); a rotor or fan (`blades` 2–4, each opening its share of the turn). Centre it on the thing that turns | 14–20 f; `inOutCubic`, or linear k for a radar's constant beam | accent lead band (`lag` 0.12–0.16), so a lit edge leads the wedge; B's first move as the wedge passes it | 11.8 onto ALL |

## Camera

| Move | Export | Use it for | Length | Combine with | Demo |
|---|---|---|---|---|---|
| Whip pan + smear | `whipPan(ctx, u, { dir, dur, smear }, drawA, drawB)`; parts `whip(u, dur)`, `smear(ctx, src, dx, dy, n)` | Joining two frames side by side as one move. The smear is as long as the frame's own travel | 8–12 f; the smear peaks on the middle 2–3 | a swap word that keeps going after the landing | 2.0 |
| Push / pull | `push(u, s0, s1, dur, ease)` → scale, applied with `camera(ctx, cam, cx, cy)` | A slow push (1 → 1.05 over a scene) to keep a hold alive; a push-through (1 → 30, `inCubic`) to dive into a shape and cut on its colour | 30–60 f; push-through 40 f | `fillType` anchored on a stem | 5.32 into the I of BIG |
| Parallax | `parallax(ctx, cam, cx, cy, [{ z, draw }])` | Depth on flat type: a far outline word (z 3), the message (z 1), a near ruler or labels (z 0.5) | the whole shot | `remap` on the camera | 9.0–10.5 |
| Time remap | `remap(t, [[t, speed], …])` → media time; `speedAt(t, keys)` | Speed ramps: fast, freeze-frame crawl, fast again. Feed any move with media time instead of `t` | ramps of 10–15 f between speeds; a 0.5 s crawl reads as a stop | parallax; a speed readout | 9.3–10.2 |

## Beat hits

Sum overlapping hits (shake offsets add, RGB amounts add) so a run of beats stacks instead of resetting.

| Move | Export | Use it for | Length | Combine with | Demo |
|---|---|---|---|---|---|
| RGB split | `rgbSplit(ctx, src, amt, { angle, mode })` with `env(u, frames)` | The impact frame of a slam or a swap. `radial` mode for a centred hit | 6–8 f envelope, 14–30 px at the hit | shake, slam | 0.08, 2.5, 12.0 |
| Flash / invert | `flash(ctx, u, { frames, mode, c })` | One frame that marks the hardest beat. Invert keeps the picture readable; flash wipes it white | 1–2 f | the third hit of a run; never twice in a row | 0.08, 13.0 |
| Shake | `shake(u, { amp, decay, hz, rot, seed })` → offsets, applied with `jolt(ctx, sh, cx, cy)` | Weight on impact. Seeded, decays | visible for 6–10 f (`decay` 0.1 s), 10–34 px | slam, punch | every slam |
| Scale punch | `punch(u, amt, omega)` → scale, applied with `scaleAt(ctx, s, cx, cy)` | A beat on something already settled: a number that landed, a node, the end card | peak at 2.5 f, back by 12 f, 5–12 % | number roll, nodes, end card | 1.5, 4.0, 8.5, 13.0, 14.5 |

## Graphic

| Move | Export | Use it for | Length | Combine with | Demo |
|---|---|---|---|---|---|
| Line draw / trim path | `trace(ctx, pts, a, b, o)`, `bezier()`, `polyLen()`, `pointAt()` | Underlines, baselines, routes. Draw on with `b` rising; trim off with `a` rising | draw 12–18 f `outExpo`, trim 10 f `inCubic` | stagger above it; any reveal | 0.5 under every frame., 6.0 bar baseline |
| Connector | `connector(ctx, u, a, b, { style, bend, r, dur })` | Relations: hub to node, label to point. The line draws itself and a dot pops at each end | 14 f, 4 f apart per connector | morph nodes; mask-reveal labels as each lands | 8.0 |
| Counter with ticks | `counter(ctx, u, { to, dur, ticks, major, line \| arc, label })` | A value with a scale: the ruler builds, then lights up behind the head | ruler 10–15 f, count 28–55 f | number roll for the figure, punch on landing | 1.06 the 60-tick arc |
| Data burst into a form | `burst(ctx, u, { pts, src \| from, spread, by, curl })` with `textPoints()`, `rectPoints()` | Dots that become a chart, a word or a logo shape, from a scatter field or from the points of the previous shape | 30–50 f (spread 0.3 s + spring) | a 4-frame swap to the solid form once landed | 6.0 bars, 13.45 ALL OUT. → fx.js |

## Recipes

### A. A 3-second hook with 5+ moves (demo 0.0–3.0)
1. Frame 0: the key word starts a slam at 2.8× (`slam`, fitted to the frame width with `fitPx`). Frame 0 is a
   giant crop of it, which makes a strong thumbnail.
2. Frame 5, the impact: shake 34 px, RGB split 30 px (7-frame envelope), one inverted frame.
3. Half a beat later (0.5 s): the second line staggers up letter by letter, with its key word in the accent, and a
   line draws under it (`trace`, 18 f), then trims off before the cut.
4. 1.0 s: an iris opens out of a round letter of the word, with an accent band leading, into the other room.
5. Inside: a number rolls in on reels while a tick arc builds and lights up behind it. Punch when it lands on the
   beat.
6. 2.0 s: a whip pan to the next frame (10 f, smeared), where one word swaps in place on each half beat with a small
   hit.

That is 11 moves in 3 s, one new thing every 0.25–0.5 s.

### B. A scene transition in under 0.3 s
Pick the matte from what is on screen: an iris from a round shape, a morph from a card or node, a diagonal for
plain energy, bars on a hard downbeat, a radial sweep from anything that turns or scans. Run it for 10–14 frames (`inOutCubic`; bars and dots linear) with a lead band
in the accent or the outgoing room's colour (`lag` 0.14–0.25). Put the new scene's first move 4–8 frames after the
matte starts, so B is already moving as it opens. A whip pan does the same in 10 frames and needs no matte. A
push-through (40 frames, `inCubic`, ×30) into a stroke of a fill-the-frame word is a match cut on its ink: the next
room is that colour.

### C. A data reveal (demo 6.0–9.0)
1. Mono eyebrow (mask reveal), then the headline figure rolls in on reels (`numberRoll`) with its unit beside it.
2. A baseline draws (`trace`). Dots burst from a scatter field into the bars (`burst` on `rectPoints`, `by: 'x'` so
   they land left to right), then the bars go solid with a 4-frame swap.
3. Labels and values mask-reveal bar by bar, 2–3 frames apart.
4. Next idea, 1.5 s later: each bar morphs into a node (staggered 3 frames), a hub slams in, connectors draw out
   4 frames apart, and each node punches as its line arrives.
5. Exit with the hub: it morphs into the full frame as the matte to the next room.
Show only real figures. The demo's counts are the library's own exports per family.

### D. An end card
Bring the previous scene's shape into it: its letters break into dots that fly into the final word (`burst` with
`src` = `textPoints` of the old word, `pts` = `textPoints` of the new one). Swap to solid in 4 frames, mask-reveal one
mono line under it, punch once on the next beat, then hold still for 0.4–0.8 s. Keep the end card on the film's grid
(left at the margin, like the rest of the film). For the logo, call `drawLockup()` from `lib/brand.js`; never redraw
it.

## Combinations that work

- **Slam + shake + RGB split + punch** on one beat; **invert** only on the strongest beat of a run.
- **Fill-type + push-through + hard cut** on the ink colour.
- **Iris from a letter**, or **morph from a node**: the transition comes out of something already on screen.
- **Parallax + time remap**: depth makes a speed ramp legible, because the layers crawl at three different speeds.
- **Burst + 4-frame swap**: the dots land, then the solid form replaces them before anyone notices the dots stopped.
- **Swap word + small hit** on half beats: the sentence holds still while one word keeps changing.
