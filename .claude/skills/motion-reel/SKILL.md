---
name: motion-reel
description: Make a motion video rendered from code in this studio (canvas + window.seek(t), Playwright, ffmpeg, synthesized sound). Use when the user asks for a launch video, showreel, Reels, TikTok or Story content, animated explainer or motion ad, hands over a draft or carousel to turn into a video, or wants "a new film" in the motion studio repo; `/motion-reel build <film>` builds a film whose board is approved.
---

# Motion reel

Build a new film in this repo's own engine. Do not switch to Remotion or HyperFrames unless
the user names them; the repo's render contract is in `CLAUDE.md` and wins over this file.

A film runs in two sessions, cut at the owner's one OK on shot list and board together:

- **Pre-production** (this file): brief, story, assets, voice, beat grid, shot list, board.
- **Build** (`/motion-reel build <film>`): read [build.md](build.md) and follow it; skip this file.

The cut keeps the build in a fresh context. Pre-production fills the window with references, takes and
board images, and every later turn pays for all of it.

## 1. Settle the brief
Run `node tools/brief.mjs --in=<draft.md>` on the owner's draft (`--film=<film>` once the project exists: it writes
`brief/original.md` without the embedded base64). It prints the header, the VO words against the budget and what the draft
leaves open. Without a draft, fill the header fields of `docs/brief-template.md` from the request and propose a default
for each gap: the owner answers with one "oke" or a correction.

Ask what is still open in one message, before touching code and before quoting credits; answers already in
`brief/decisions.md` stand. Add what the tool cannot see:
- Overlap: a past film on the same subject or pillar (`projects.json`). Say which, and what this one adds. A remake keeps
  the old folder untouched and asks which of its `decisions.md` answers still stand.
- Product + URL (or topic). For OpenView films, the pillar and formula from `docs/content-map.md`.
- Brand: OpenView films use `lib/brand.js`. Other brands: colors, fonts, one accent, real logo.
- A reference: frame, video, or image folder. Or "none" (then say so; no default look).
- Music: a supplied track (measure it) or "synthesize" (default).
- Voiceover: needs `ELEVENLABS_API_KEY` in `.env`. If empty, stop and name the variable.

The brief is settled when language, voice, duration, ratio, subject (tickers included), data source (app, kit or
illustration) and energy are fixed. Each of these moved after the first take on a past film, and `mi-demo-40` paid for its
VO three times. Record the answers in `<project>/brief/decisions.md`.

A package from another tool (storyboard, zip, handoff): copy it untouched to `<project>/references/<tool>-<date>/`, which
stays out of the commit, and run `tools/brief.mjs` on its brief alone. Open another of its files only when a decision
needs that file. Its shot list and script are material, like a draft's order.

Limits: words, figures or facts the brief or legal rules off screen go in `<src>/forbid.json` (`tools/forbid-lib.mjs`):
`tools/vo.mjs` refuses them before spending credits, `tools/check.mjs` fails on them on screen. A limit no pattern can see
(a name that never carries a percentage) goes in `brief/decisions.md`, read against every board and review sheet.

Pick a film slug (`[a-z0-9-]+`). Everything below is named by it: `<film>`.

**Project layout.** A new film gets its CONTENT project folder (`CLAUDE.md` "New video project folders") and a line
`"<film>": "CONTENT/<n>. <Title> (<date>)"` in `projects.json`; the tools then find it there (`tools/paths.mjs`):
shot list and brief in `<project>/brief/` (`shotlist.md`), code in `<project>/src/` (`film.js`, `timeline.js`,
`vo-lines.json`, `beats.json`, `sfx-<film>.mjs`), takes and media in `<project>/assets/`, boards, sheets and renders
in `<project>/output/`. Older films keep `docs/<film>-shotlist.md`, `film/<film>/`, `assets/<film>/` and `out/`.
Below, `<shotlist>`, `<src>`, `<assets>` and `<output>` mean whichever applies.

## 2. Pre-production
1. **Assets.** Into `<assets>/`, listed before any animation.
   - OpenView logo and symbol: drawn only through `lib/brand.js`; never copy the SVGs into the film.
   - OpenView mascot: the code rig in `lib/mascot/` (API in the header and exports of `lib/mascot/index.js`).
   - OpenView Market Intel: figures and names from the latest `origin/main`, the picture drawn in code with
     the Market Intel UI kit. Capture the running app only when the brief asks for the real app; then follow
     "Market Intel source" in `CLAUDE.md`; choose bands from `capture_mi.mjs --review` and draw with `lib/proof.js`.
   - Another product with a URL: capture real screenshots, logo, colors, fonts with Playwright.
2. **Visual world.** Read `REFERENCES/motion/visual-grammar-2026-10.md`, then write `## World` at the top of `<shotlist>`
   before any shot: one place, its objects, who stands in it, what the light does, and how each figure and relation in the
   brief becomes a thing you can point at. Draw it with `lib/world.js`. The design system stays on the product's own screens.
   **Style guide.** If a reference exists, measure it first:
   `uv run --python 3.11 --with librosa --with numpy tools/ref_probe.py refs/<film>/ref.mp4 refs/<film>/analysis.json`
   then write `docs/<film>-style_guide.md`: palette (hex), type, shot lengths, transitions, camera moves,
   texture, how text enters and exits. Take the grammar, never the content. The house look is `CLAUDE.md`
   "Look" plus `docs/motion-vocab.md`; other films' style guides record those films, not the house.
3. **Story.** Read [story.md](story.md), put the subject through its Topic ladder, and write its spine table at the top of
   `<shotlist>`, before any script. The spine is done when every row is filled and the script tests at the end of that file
   pass on the first line and the outline; the draft's order is material here,
   not a script, and a draft's `ALUR CERITA` and `KANDIDAT HOOK` (`docs/brief-prompt.md`) are its first version. Show the
   spine with the VO quote: it is the cheapest moment to change the film. From a draft, the same message names what the draft
   covers and the script drops, with both word counts: `pandu-supra-80` came back as "ga selengkap draft" after its first
   film, and the extension took three more sessions.
4. **Voice-over** (if the brief has VO): follow "Voice-over" in `CLAUDE.md`. Write the script from the spine in the investigator
   voice (story.md "The viewer"), up to the word budget, counting figures as they are spoken: its Indonesian 1,7 is what six films ran
   at 1.12 (1,65–1,75 words a film-second), so a full budget lands near the brief's seconds. `character` defaults to
   `calm, fair narrator, talking to one person`. Then `<src>/vo-lines.json` and the last section of story.md, until
   `tools/script.mjs` passes; its `credits` line is the quote. Generate with `tools/vo.mjs`, pass `--check`. Definitions and legal terms need a source in
   `references/sources.md` like any figure; R-120 keeps register names off screen, not out of the sources file.
   The takes set the scene lengths: `<src>/timeline.js` is the scene list on `lib/vo-clock.js` (`sceneTimeline`;
   model: iata-55), and `node tools/prepare.mjs --film=<film>` checks the takes and writes the clock to `beats.json`.
5. **Beat grid.** Supplied track: measure BPM/beats/downbeats/hits (librosa) into `<src>/beats.json`.
   Synthesized: pick BPM, write `<src>/sfx-<film>.mjs`, a cue list on `lib/synth.mjs` (model: iata-55's
   `src/sfx-iata-55.mjs`), so it emits `beats.json` and `<output>/<film>-audio.wav` at -14 LUFS.
6. **Shot list.** Write `<shotlist>` on the beat grid: every shot with frames, camera, on-screen
   text, SFX, its spine beat, the effect from `docs/motion-vocab.md` it uses, and the reason for its cut into the next shot (next
   step, same position, cause and effect, time jump, callback, change of size). A shot with no reason to cut joins the next one as
   a camera move. Plan the way into the product as one move, a world object becoming the screen, named in the shots on both sides
   of the cut: it drew the owner's only creative revision at build on `delisting-18-80` (45–50 s). Plan the density here, scene by scene:
   the moves each hold will carry, because the first build of every recent film scored 4–5 on density and spent its rounds
   adding them. List the decisions that need the owner's OK. No stop here: the shot list goes to the owner with the board.
7. **Board.** Draw the film's widest and closest shots first in `<src>/film.js` (export `board: [{ t, shot, note }]`) and look at
   that pair alone (`node tools/board.mjs --film=<film> --only=<wide>,<close>`, its `-view.jpg`): they show how much the world has to
   hold and whether its figures survive close up, while a redraw costs two shots. Then draw one still per shot.
   Run `node tools/board.mjs --film=<film>`. Its text is the mechanical review: fix every `warn … mid-move` line
   (move `t` to the settled frame) and every `layout` finding (text outside the safe area, in the caption band,
   overlapping, too small), then run it once more to confirm the text is clean.
   Read only the board's `-view.jpg` overview, or over 18 shots the `pages` it prints, each once, for looks: fix what reads wrong in one pass, no
   look-patch-rerender loop, no per-scene sheets (`--scenes` exists for the owner, not for this review).
   The look test, on that overview: mute it and follow the story from pictures alone; a stranger sees a place, people and
   things, not slides. Besides the caption, a shot holds at most 6 words, on objects; proof plates and lines the brief
   requires in full are the only exceptions. Failing this means redrawing the shot, not trimming the text.
8. **Owner review (the one gate).** Show the shot list and the board (`<output>/<film>-board.png`) together, with
   the decisions that need an OK, and wait for that single OK. **No motion or sound before it.**
9. **Hand-off.** When the owner OKs the review, write a `## Build brief` section at the top of
   `<shotlist>`: what is approved, what is still open, and the files the build needs (film module,
   takes, beats, sfx script). Then start the build in a fresh context:
   - Desktop app: start a new session with fresh context (not a fork), prompt `/motion-reel build <film>`.
   - Terminal: tell the owner to run `/clear`, then `/motion-reel build <film>`.

   Pre-production ends here: the owner's OK on shot list and board is the completion criterion, and the build
   belongs to the new session.

## 3. Hard rules
- Pure function of time: `seek(t)` only. No `Math.random`, no timers, no CSS transitions,
  no `requestAnimationFrame` in render mode, no state between frames.
- Open the `-view.jpg` previews; full-resolution images only as a `--crop` of one detail. Images are for looks;
  mechanical checks are the tools' numbers (`node tools/check.mjs --film=<film>`: seek sweep, determinism, font px,
  layout lint).
- Context is the cost, and turns multiply it: a turn at 300k costs what three cost at 100k, and two thirds of recent
  messages carried one tool. Send every independent read, search and edit of a step in one message. Tools are run, not
  read (`--help` gives the usage); edit with Edit, never rewrite a whole file; long commands run in the background and you
  wait for the notice, with no `sleep` or polling loops.
- Another film's source is not a template: films share 3–16 % of their code. Look up the one function you need (Grep, or
  Read with offset/limit) and leave its `film.js` closed.
- State lives in files: `brief/decisions.md`, `references/sources.md`, `<shotlist>`, `docs/review_log.md`. The project
  auto-compacts at 250k, so a fact held only in the conversation can vanish mid-film.
- Secrets only from `.env`. Never print, log, or paste a key.
- One session per brand: the engine, synth, and export pipeline are reused, not rebuilt.
