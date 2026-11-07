# Motion review log

## msci-2026 — 18 October 2026

Approved direction: storyboard v3, data first, small selective mascot. The user explicitly requested production after storyboard review. A native 30-shot board was rendered and all seven scene sheets opened before switching from static board mode to motion. This execution continued under that approval.

Scores are director judgments from opened images, strips and encoded-file evidence. Sound assessment is based on verified speech, measured alignment and loudness; it does not claim a subjective listening review.

| Round | Hook | Phone reading | Motion | Variety | Composition | Brand | Sound sync |
|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | 8 | 7 | 7 | 8 | 8 | 9 | 7 |
| 2 | 8 | 8 | 7.5 | 8 | 7.5 | 9 | 7.5 |
| 3 | 8 | 8 | 7.5 | 8 | 7.5 | 9 | 8 |
| Final evidence | 8.5 | 8 | 8 | 8 | 8 | 9 | 8.5 |

### Round 1

Opened native scene sheets s1–s7 and out/msci-2026-contact-r1.png at phone cell width 360.

1. 42.5–44.05: October loss graphic appeared while Brad was still saying the proposal was only a consultation. Moved the internal cut to 44.375, after the proposal take; revealed high at 48.75 with the corresponding sentence.
2. 69–72: full desktop network labels were too small. Increased camera focus from 3.1× to 4.8× around the BBCA ownership chain; source UI remained intact.
3. 3–6 and 17–19: end dots appeared before the price traces reached them. Replaced them with moving heads on the actual trace and delayed final endpoint emphasis.

### Round 2

Opened out/tmp/strip-msci-oct-r2.png, full-resolution product stills at 69.8/71.5, and encoded out/tmp/msci-oct-r2.mp4 evidence.

1. 71.5: the closer UI crop cut through the upper names. Adjusted the vertical focal point using the actual source screenshot; preserved readable Bambang/Robert Budi, PT Dwimuria and BBCA.
2. 17–19: the closing-price comparison needed explicit dates. Added 27 JAN and 28 JAN below the line so it reads as a dated close comparison.
3. Audio master first measured −0.9 dBTP at −14 LUFS. Lowered limiter ceiling and remeasured: −14 LUFS, −1.3 dBTP before AAC.

### Round 3

Opened the updated seven scene sheets, phone stills at 0.9/19.9/49.5/71.5/74, and the every-frame hook strip 0.65–1.05.

1. 0.75–0.85: the incoming percentage momentarily encroached on its supporting basis label. Moved SEJAK 2 JANUARI down 27 px; the fresh hook strip confirms separation throughout the entrance.
2. 20–25: a bare TRADING HALT label next to −7.35% could imply that was the halt trigger. Changed it to SEMPAT TRADING HALT and added an explicit closing-change versus intraday-halt note with ANTARA attribution.
3. 71.5: upper owner icons were tight to the crop edge. Measured the source screenshot and set the final focal center to y1440, keeping the main ownership names and company chain readable.

### Final evidence and checks

Opened out/msci-2026-contact-mp4.png, out/msci-2026-phone.png and out/msci-2026-poster.png from the actual encoded master. Also opened the refreshed phone stills at 0.8, 21.7 and 71.5, and out/tmp/strip-msci-hook-final.png. No new blocking visual issue appeared.

- Price series: 188 actual daily observations; no invented intraday trajectory.
- Mascot: only opening and closing lockup, approximately 13.5% width.
- Voice: all 13 Brad takes PASS speech check; 1,027 generated characters. Captions and vowel mouth cues use provider alignment.
- Final lockup hold scan: last frame differing from the end is 4498, t74.9833; no premature full-frame freeze.
- Two identical 0–5 s / sub1 renders: SHA-256 b252a5c62c0f84473cbabc05d8418c45d91d8c52e85f7856bccfec1cd85434b4.
- Full render: 4,500 frames, sub4, SHA-256 c43732b290b1adf51981129597a3ae060f98caf721ac690b9545b70d8ad26e28.
- ffprobe decoded all 4,500 video frames: H.264, yuv420p, 1080×1920, 60/1, AAC stereo 48 kHz, 75.000 s.
- Market Intel main was checked again before full render: 88877c7, unchanged from capture.

The longer film exceeded the practical memory budget of the original bulk QA frame arrays. QA now streams frames while retaining only beat samples. Original and streaming versions produced byte-for-byte identical JSON metrics on the same six-second encoded preview. Complete master QA is recorded in the delivery note after measurement finishes.

Acceptable limits: tiny supporting source labels and secondary UI text are not the primary reading layer at phone size. Quiet pauses allow price reading. The mascot uses a light cutout mouth animation rather than a full facial rig. Further polish, if requested, would first connect chart transitions more continuously across scenes.

Final master QA: 75.000 s, 4,500 frames, −14.1 LUFS, −1.3 dBTP, no decode errors. 113/120 beats show detected picture change in the first 0.2 s. Longest low-motion reading hold: 35.67–37.48 (1.81 s), after the June comparison is complete and before the next chapter. Other detected pauses are under 0.62 s. These are reading/breathing holds, not omitted footage. Aggregate audio/picture correlation peaks at −2 frames; this is a coarse envelope measurement, not a phoneme lip-sync score. Speech onsets dominate the automatic tempo estimate, so the measured 103.36 BPM does not redefine the authored 96 BPM score grid.

Delivered file SHA-256: 4dda27123c1dc36d4d73a97f6479d9350d0a1415b964e396882131b97238b566; 6201846 bytes. Full QA JSON and delivery manifest are saved in film/msci-2026/.

---

## launch — OpenView Market Intel launch film (9:16, 66.0 s), 2026-10-18

Evidence each round: per-scene strips (one frame per beat, `out/tmp/launch-strip-r*-s*.png`), stills at the
clicks, a 16-frame strip at phone width (360 px), determinism hashes. Scores: hook · phone readability · motion ·
variety · composition · brand · sound sync.

**Round 1** — 6 · 7 · 6 · 8 · 7 · 8 · 8
1. 46.1–46.5: the cursor clicked empty space; the NETWORK tab (CSS 1059, 145) sat outside the window (camera
   centre 560 at scale 1.04 shows CSS 75–1045). Fix: centre 600, scale 1.0, cursor on the tab.
2. 53.6–54.0: the button framing showed "Registers & source dates / Monthly holdings register" (rule: crop out
   register lines). Fix: centre y 940.
3. 0–1.9: the hook held still until the roll. Fix: a slow push on the figure from frame 0 to the slam.
Also found: `tools/contact.mjs` shared its frame files across processes; a parallel film's frames landed in
this film's strip. Fixed with per-run file names.

**Round 2** — 7.5 · 7 · 7.5 · 8 · 7 · 8 · 8 (origin/main moved to `df7af48`: all UI recaptured, S5 re-aimed)
1. 56.6–57.5: the tally reached 127, not 138, before the close. Fix: tally at min(S6 − 0.9, "every" + 1.5),
   faster count.
2. 45.0–46.6: the real Answer card too small to read. Fix: open at scale 1.17 on the Answer line, back out before
   the click.
3. 56.1–57.5: the pull back at scale 0.62 left empty panel either side of the app. Fix: cut in tight on the ring
   (1.4), pull back to 0.9 (the app's full width).
Also: `rbh-ring` had a hover card in it (mouse left on the node); `capture_mi.mjs` now waits after moving away.

**Round 3** — 8 · 8 · 8 · 8 · 8 · 8 · 8
1. ✕ list ~10.7 px at phone width → 38 px (34 px for the long third row).
2. S3 node labels ~12 px at phone width → 42 / 28 px.
3. Sound: the tally's sounds moved with the new tally time (`sfx-launch.mjs` uses the same formula).
Determinism: `render.mjs --hash-only --from=0 --to=3 --sub=1` twice → `e2b00a9b…ae03d` both times.
Mix: −14.0 LUFS, −1.3 dBTP, voice 12.8 dB over the ducked music while speaking.

---

## msci-40 — MSCI timeline 2026 (9:16, 40.0 s, Indonesian), build, 2026-10-19

Evidence each round: contact sheet (one frame per beat), phone sheet (`--cell=360`), every-frame strips over the
seven joins (4.74–5.12, 10.7–11.1, 16.72–17.08, 23.22–23.5, 27.6–27.98, 31.56–32.1, 37.15–37.85), the halt
(9.6–10.6), the caption page change (14.95–15.45), the opening lips (0.28–1.48), stills of each changed shot, and
`qa.py` on a full `--sub=1` render (`output/tmp/r*-sub1.mp4`). Scores: hook · phone readability · motion · density ·
composition · brand · sound sync. Sound is scored from measurement only: nobody listened in this session.

Baseline (board-stage motion, before the build): qa density fail — 4 moves in the first 3 s; gaps 0.03–1.88,
3.05–4.9, 6.13–7.8, 19.83–21.58, 34.15–36.05; quiet beats 36, 37, 41, 46, 54, 61, 67.

**Round 1** (first build pass, `r2-sub1`) — 8 · 6 · 7 · 9 · 7 · 9 · not assessed by ear
(qa: density pass, 7 moves in 3 s, max gap 1.44 s, 0 quiet beats; event→onset median 40.7 ms, p90 162 ms;
−14.0 LUFS, −1.3 dBTP; check_logo 0 differing pixels; determinism 0–5 s `d84ca39a…0e6e` twice)
1. 11.0–12.0 (3a): the four MSCI classes in 30 px mono (≈10 px on a phone) in an otherwise empty frame.
   Fix: display 52 px, inactive classes in `control`, IHSG marker 34 px.
2. 17.0–18.8 (4a): the year line in `line` (#303741) disappears at 360 px. Fix: `control`.
3. 37.7–38.4 (5d): the close's caption sat under the landed lockup (the brand twice, the card not clean).
   Fix: the l05 caption leaves at "OpenView." + 0.35 s.

**Round 2** (transition strips, stills) — 8 · 7 · 7 · 9 · 7.5 · 9 · not assessed by ear
1. 27.7–28.0 (4f): labels drawn inside the ×2.6 pull showed clipped fragments at the top of frame. Fix: labels
   start once the pull is within 15 % of rest (u 0.45).
2. 5.0–5.15, 10.95–11.1, 16.98–17.1: the rooms opened empty behind their mattes. Fix: B moves under the matte —
   the whole year carries across the diagonal and trims away as January reframes; classes and date start at
   S3 − 0.14; rail and year line at S4 − 0.12.
3. 13.22–13.55 still run (qa) and the 5a arrival ring crossing the BBCA label. Fix: slow push in scene 3; the ring
   moved to b65 with the punch, 44 px of travel. 5a also opens close on the emiten (×1.35) and pulls back on "kenali".

**Round 3** (`r3-sub1` + partial renders, phone sheet) — 8 · 7 · 8 · 8 · 7.5 · 9 · not assessed by ear
(qa on `r3-sub1`: density FAIL, gap 15.15–16.88 — the scene-3 push raised the local median so the −3,81 % roll no
longer stood out; partial render 13–19 s after the fix: events 15.17, 15.93, 16.88, no gap)
1. 15.15–16.88 (3d): no new idea for 1.7 s. Fix: the push ends on "Pasar"; the roll keeps its ROLL spring (its first
   frame is the peak); punch + thunk when it has landed.
2. Eyebrows and row labels at 26–28 px mono (≈9 px on a phone) carry the meaning of the figures. Fix: 32 px.
3. 25.3–27.7 (4d/4e): lower half empty while the levels sat high; −11,57 % touched the 16 Okt candle; its 5 and 7
   landed after their spoken words. Fix: levels 90 px lower; the change at 150 px (60 px clear); reels for 5 and 7
   on springs that reach 99.5 % on "lima" and "tujuh".

**Round 4** (the master, `output/msci-40-final-9x16.mp4`, sub 4; tiles from the mp4 and the stills above) —
8 · 8 · 8 · 9 · 8 · 9 · not assessed by ear
- Hook 8: 7 measured events in 3 s (frame-0 slam + shake + RGB, mascot pop, b1 punch, month ticks, line trace,
  5.185,10 glitch, mascot swap). Readability 8: figures 52–170 px, captions 54 px, eyebrows and row labels 32 px;
  holder names (≈29 px on screen) and inline sources (26 px) are the secondary layer. Motion 8: only two 0.2 s holds
  (20.78, 22.78), each covered by the rail's beat ring. Density 9. Composition 8. Brand 9: `drawLockup`, check_logo
  0 of 290,048 px differ, mascot outside the clear space.
- Sound sync not assessed by ear. Measured: event→onset median 37.7 ms, p90 145.6 ms (56 events); onsets to the
  32nd grid median 13.9 ms; sound-to-picture lag +2 frames; −14.0 LUFS, −1.3 dBTP; voice 14.2 dB over the ducked
  music; music silent 9.90–10.41 and 30.70–31.95 (the second visible as a clean gap in the spectrogram). Voice
  delivery not assessed (pre-production takes, `--check` passed then; not regenerated).
- qa: density pass (62 events, 15.5 per 10 s, max gap 1.43 s, 0 quiet beats), 11 hard cuts. Determinism 0–5 s:
  `1b98a1cd…eea1c` twice. Master sha256 `19920a87…b37e`, 40.000 s, 1080×1920, 60 fps, H.264 yuv420p + AAC 48 kHz.
- Market Intel: `node tools/mi_sync.mjs` before the render — still `1c2b99d` (no re-read needed).

**Owner revision, 19 Okt (v2)** — voice Zephlyn (`3mAVBNEqop5UbHtD8oxQ`), IHSG `i-ha-es-ge`, MSCI `Em-Es-Si-Ai` (picked
from 8 samples), KSEI line removed, the main narrator rig (narrator_base + blink + vector mouth) without card, moving
after the owner's reference (host bust cut by the frame edge, bubble, zoom and side changes, knocked out by the slam).
l04 kept: STT hears "IHGS" on its second IHSG in every take (3 tries); owner to judge by ear. Film now 39.5 s (the
takes set the clock). Master: qa density pass (5 moves in 3 s, max gap 1.49 s, 0 quiet beats), check_logo 0 px,
determinism `6cd7e05c…e6cd7` twice, −14.0 LUFS, −1.8 dBTP, voice 12.6 dB over music. Sound and voice delivery not
assessed by ear. ElevenLabs credits this revision: ~2,379 (takes 1,630, samples 639, STT extra).

**Owner revision, 19 Okt (v3)** — owner heard "IHGS" at 24 s and a wrong MSCI. l04 rebuilt from owner-approved pieces
(no credits): MSCI from sample `s-msci-c`, "Besoknya, i-ha-es-ge" from `s-ihsg-b`, the rest from take 3 (kept in
`output/tmp/l04-take3.*`); STT now hears "MSCI" and "IHSG" (its "1998" for "sembilan puluh delapan" is the only
mismatch). Error on my side: a full `vo.mjs` run regenerated l02, l03, l05 (~423 credits, not approved; old takes
overwritten); the new ones pass `--check`. Film 39.0 s. Master: qa density pass (5 moves in 3 s, max gap 1.49 s, 0 quiet
beats), check_logo 0 px, −14.0 LUFS, −1.9 dBTP, voice 13.2 dB over music.

**Owner revision, 20 Okt (v4, CTA)** — 3 s CTA after the close ("TEMUKAN DI / openview.id →", no voice): a lime dot
morphs into the button, the address pops in, the arrow beats, the narrator ducks out and drops in above the logo's
clear space, his cursor comes down the right margin (x > 952, outside the clear space) and clicks (press, ripple), the
product line returns. Close hold 1.9 → 0.25 s so the CTA follows the lockup (a 1.6 s gap failed qa); `MAX_SECONDS` 43
(owner asked for the extra time). Film 40.5 s. Master: qa density pass (5 moves in 3 s, max gap 1.49 s, 0 quiet beats),
check_logo 0 px on the last frame (the lockup never moves), determinism 36–40.5 s `5144d368…071e` twice, −14.1 LUFS,
−1.8 dBTP. No credits. Sound not assessed by ear.

## OpenView pay per report — build, 20 October 2026

Owner approved the 29-shot board and Brad pilots (“oke continue”). Project: CONTENT/2. LinkedIn Video_Launching OpenView 2 (26 Okt 26); slug openview-pay-per-report-40. Full findings and limitations: brief/build-review.md in that project.

Round 1: hook 8; primary phone readability 6; composition 7; canonical brand 10. Corrected real-recording crop coordinates (26–32 s), caption background on lime (18.6–19.7 s), and measured score level. The initial video crop included padded gray canvas; corrected crops retain genuine app pixels. Score now measures 13.8 dB below voice during speech, WAV −14.2 LUFS / −1.5 dBTP.

Round 2: hook 8; primary phone readability 8; composition 8; brand 10. Cut loading time from the real expanded-network action (30.5–32 s), focused the fan and selected identity, and explicitly labelled the monthly chart line OPENVIEW (33.5–35 s). Animatic r2 density pass: 7 events in first 3 s, max gap 0.58 s, motion in 80/80 beats. Two 0–3 s hashes match: 9d10ed427073aeb21f66350d2c6e6c2561c7173d42f8b44d4a4387d712b742fe.

Round 3: same observed still scores. Removed only a clipped repeated floating identity tag from the map crop; complete genuine identity and substantive dataset caveat remain. Opened latest beat sheets, 360 px stills, every-frame strips (hook, product turn, expanded map); rendered affected 30.5–32 s. Animatic r3 density pass: 99 events, 7 in first 3 s, max gap 0.58 s, zero quiet beats; AAC −14.2 LUFS / −1.4 dBFS, measured envelope lag −2 frames. Code check passes 51 seeks + 22 tool tests; logo 0/290048 pixels differ. Latest Market Intel origin/main still 1c2b99ddacf40329d4178a544b0fcb7e9ba8bbd2.

Motion performance, real-time pacing, voice expression and sound synchronization are not scored: strips and automatic measurements are not real-time viewing or audible audition. The owner accepted the two pilots; all nine takes pass transcript checking. The subjective all-categories-8+ gate is not claimed. Final master technical results are recorded after encoding in the project delivery report.

**Final encoded master, OpenView pay per report (20 October):** output/openview-pay-per-report-40-final-9x16.mp4; 10,249,047 bytes; SHA256 64400476828fd84aa512b1b4224be814daee89f367a3038c2691e237a926388c. Exactly 40.000 s, 1080×1920, 60 fps, 2400 H.264 yuv420p frames, AAC stereo 48 kHz; both stream durations 40 s. Studio renderer sub 4, CRF 16. Independent ffprobe and full QA decode passed. Final density: 96 events; 6 in first 3 s; max gap 0.58 s; 80/80 beats with motion; zero quiet beats. Measured −14.2 LUFS / −1.4 dBFS. Canonical canvas logo differs in 0 of 290048 pixels. Two product-range 30.5–32 s renders match 6c1c638216a24b205cdd77c8e0192de9b417c8d6e12100dc2ef1d5e01f23e1e2; final 35/35 discontinuous seeks match. Opened encoded-MP4 beat and phone sheets and poster; no new layout defect found in those sampled images. No real-time/audible subjective pass is claimed. File checks, nine checked take hashes and 162 extracted-frame hashes are saved in project brief/delivery-report.json. Dedicated capture server stopped after production.

## iata-55 — Saham IATA, "Ganti Nama, Ganti Tuan" (9:16, 55.0 s, Indonesian), build, 23 Okt 2026

Contract: `CONTENT/3. Saham IATA (23 Okt 26)/brief/shotlist.md` (Build brief). Evidence each round: contact sheet (one
frame per beat, 110), 360 px phone stills (`output/tmp/phone-*.png`), every-frame or 15–30 fps strips over the joins
(whip 1.8–2.4, flap 4.85–5.2, plate → bar 10.9–11.9, chip push 19.45–20.25, bar → disc 28.1–29.3, pull 37.8–38.9,
rings → rows 41.45–42.3, lock push and iris 44.4–45.8, burst 50.25–51.15) and `qa.py` on a full `--sub=1` render
(`output/tmp/r*-sub1.mp4`). Scores: hook · phone readability · motion · density · composition · brand · sound sync.
Sound is scored from measurement only: nobody listened in this session.

**Round 1** (first build pass, `r1-sub1`) — 7 · 6 · 7 · 6 · 7 · 9 · 7 (measured)
(qa: density FAIL — 4 moves in 3 s; gaps 8.0–9.52, 16.8–18.32, 21.02–23.02, 29.12–30.72, 38.07–40.85; 0 quiet
beats; −14.1 LUFS, −1.9 dBTP; event→onset median 63.9 ms, p90 277 ms; lag −2 frames)
1. Density: the board's moves between cues were too soft to read as events (stagger at 0.5, crack, plate fills 8.5
   and 9.06, the lime bar's entry 21.5–22.5, the link climb 28.9–30.4, the ring burst 38.8–39.7). Fix: punch on
   IATA at 0.5, a hit on the split, a punch as each plate fills, punches on 22.0, 29.5/30.0 (root disc), the hub on
   "Namanya" and the ring on 39.5, a shake on "turun".
2. Phone (360 px): mono labels at 22–30 px (7–10 px on a phone): years, plate periods, bar scales, history marks,
   layer names, network labels; network labels crossed links at 34.9 and 48.4. Fix: eyebrows 36 px, labels 28–34 px,
   KODE/PEMILIK moved under the card; network labels drawn as the app draws them (canvas halo, `miLabel`).
3. 37.95–38.15: the retracting links left their head beads as debris. Fix: no bead while the scene exits.

**Round 2** (`r2-sub1`, 360 px phone stills, strips over the joins) — 8 · 7.5 · 7.5 · 7 · 7 · 9 · 7 (measured)
(qa: density FAIL — 6 moves in 3 s; one gap 21.02–23.02; 0 quiet beats; −14.0 LUFS, −1.9 dBTP; event→onset median
64.6 ms, p90 298 ms (quiet ticks under the voice give no onset); lag −2 frames)
1. 21.02–23.02 (4b): the punch on the rolling 50,50 % did not stand out from the shrink and the roll. Fix: a small
   hit (shake 10, RGB 8) on 22.0, the beat after "Karya", with the lime motif under it.
2. 45.6–47.4 (7a): the desk opened as a thin search bar at the top of an empty frame for 1.8 s. Fix: the search
   opens mid-frame and rises to the top as the network builds under it (SOFT, from "emiten" − 0.45 s).
3. 37.95–38.8 (5e → 6a): one-segment link stubs stayed as dots after the exit, then the person sat alone for 0.6 s.
   Fix: exits snap to nothing at 96 %; his name travels from beside the disc to under it, where scene 6 keeps it.
Also: CTA network labels 26 → 28 px; Karya Pacific Investama's label moved left of its disc (it stacked on Karya
Bumi Energi's).

**Round 3** (`r3-sub1`, phone stills of scenes 5–7, chip push rendered at sub 4) — 8 · 8 · 8 · 7 · 7.5 · 9 · 7 (measured)
(qa: density FAIL — 6 moves in 3 s; gaps 21.02–23.02, 46.58–48.25; quiet beat 77 (38.5); −14.0 LUFS, −1.9 dBTP;
event→onset median 65.6 ms; lag −2 frames; check_logo 0 of 290,048 px differ; determinism 0–5 s `30c34dd4…82fa`
twice)
1. 21.02–23.02 (4a→4b) and 46.58–48.25 (7a): long SOFT moves (the date block shrinking, the search rising) raise the
   local median, so the hit on 22.0 and the punch on 47.0 do not stand out. Fix: both moves on a critically damped
   [16, 1] spring (about 0.4 s), so each is a short burst of its own and the beats after it read.
2. 38.5 (6a): the name's travel settles exactly on the beat; the frame holds 38.5–38.8. Fix: a punch on the hub on 38.5.
3. 35.4–37.0 (5d/5e): "PEMILIK MANFAAT" twice on screen (layer name and his role). Fix: his role label leaves as the
   layer names arrive.

**Round 4** (`r4-sub1`, strips 21.35–22.2 and 47.2–48.3) — 8 · 8 · 8 · 7.5 · 8 · 9 · 8 (measured)
(qa: density FAIL — 6 moves in 3 s; one gap 47.38–49.07; 0 quiet beats; −14.0 LUFS, −1.9 dBTP. The faster shrink and
lift read as single moves; 22.0 now an event.)
1. 47.38–49.07 (7b): the network builds in small pieces (discs, thin links, labels); no frame stood out. Fix: the
   whole network punches on 48.0 (5 %), with a tick.
2. Market Intel `origin/main` moved 9dfa377 → 2fb61d5 ("remove search google for group"): the kit's theme, skin and
   glyph files are unchanged (empty diff), so the drawn UI stands. `tools/mi_sync.mjs` refuses to move the capture
   worktree (Next.js rewrote its `next-env.d.ts`); this film does not use it, so it was left untouched.
3. Composition holds in 3a–3c (lower third empty until the prices come in) as approved on the board; not changed.

**Round 5** (`r5-sub1`) — 8 · 8 · 8 · 8 · 8 · 9 · 8 (measured)
(qa: density pass — 87 events, 15.8 per 10 s, 6 moves in 3 s, max gap 1.50 s, 0 quiet beats; −14.0 LUFS, −1.9 dBTP;
event→onset median 65.9 ms, p90 298 ms (named ticks under the voice give no onset); onsets to the 32nd grid median
14 ms; lag −2 frames; 9 hard cuts)
The pass had no margin: four gaps at 1.42–1.50 s (35.57–37.07, 25.03–26.52, 38.07–39.52, 44.08–45.5), and the
master averages 4 subframes, which lowers peaks. Fixes before the master: the network punches 4 % on 36.5; the
tags punch as the Rp1 bracket lands; the 18 rings burst 1.2 frames apart instead of 3 (one burst, not a trickle);
the push into the lock starts with a 5 % kick on 44.5.

**Round 6** (first sub-4 master, `output/iata-55-final-9x16.mp4`, discarded) — 8 · 8 · 8 · 7.5 · 8 · 9 · 8 (measured)
1. qa density FAIL on the master: gap 13.70–15.28 (motion blur lowered the 14.02 step below the event threshold);
   other gaps at 1.38–1.45 s. Fix: a hit (shake 10, RGB 8) and a 10 % punch on the figure at the second step; the
   18 rings burst together (0.4 frame apart); the ring punches on 40.0 and 40.5 too; the push's kick 5 → 9 %.
2. Determinism: four full sub-4 runs gave four different sha256. A per-frame comparison of two fresh runs found 12
   frames, all 16.73–17.17 (3d): the price tags were drawn at fractional font sizes (34 → 40 px while landing), which
   the render's Chromium rasterizes differently from run to run. Fix: one font size and a scale transform for the tags,
   for the name's travel into scene 6, and for the root disc's pop and exit (its ticker's size follows its radius).
   Frames 16.67–17.20 now match across two fresh runs.
3. Process: the first master attempt ran twice at once into the same file (a stray background job); the file was
   corrupt and was deleted. Masters now render one at a time.
Owner answers recorded (decisions 12–14): plain MNC / IATA (no retake), the three draft readings confirmed, logos
cleared for publication.

**Round 7** (the master, `output/iata-55-final-9x16.mp4`, sub 4; tiles from the mp4, beat sheet, poster) —
8 · 8 · 8 · 8 · 8 · 9 · 8 (measured; not assessed by ear)
- Hook 8: 6 measured events in 3 s (frame-0 crop slam + shake + RGB + invert, IATA punch, card pop, crack and tear
  hit, whip, Karya stamp). Readability 8: figures 120–220 px, names 40–92 px, captions 54 px, eyebrows 36 px, labels
  28–34 px; bar scales, history marks and network labels (26–30 px) are the secondary layer. Motion 8: springs
  throughout; every scene leaves through a move (whip, full-frame flap, plate → bar, push into the date, bar → root
  disc, the name's travel, rings → rows, push into the shackle and iris, burst into the lockup). Density 8. Composition
  8 (3a–3c keep the approved board's empty lower third until the prices arrive). Brand 9: `drawLockup`, check_logo
  0 of 290,048 px differ.
- qa: density pass (88 events, 16.0 per 10 s, 6 moves in 3 s, max gap 1.38 s, 0 quiet beats, 110/110 beats with
  motion); −14.0 LUFS, −1.9 dBTP; voice 14.4 dB over the ducked music; event→onset median 65.9 ms, p90 298 ms;
  onsets to the 32nd grid median 14.6 ms; sound-to-picture lag −2 frames. The end card rests 54.53–55.0 after the
  caret's last blink.
- Determinism: the master render and a separate full `--hash-only` run both give frame sha256 `9887e24a…47ba`
  (3300 frames, sub 4).
- Master: 55.000 s, 1080×1920, 60 fps, H.264 yuv420p + AAC 48 kHz stereo, 12.8 MB, file sha256 `eeab0cf3…6395`.
  Poster `output/iata-55-poster.png` (4.45 s, "WARDONO ASNIM ?"). Contact sheets `output/iata-55-contact-9x16.png`
  (one frame per beat, drawn) and `output/iata-55-contact-mp4.png` (from the mp4).
- Market Intel kit checked against `origin/main` `2fb61d5` before the render: theme, skin and glyph files unchanged.
- Next, if asked: a sound pass by ear (nobody listened); scene 3's lower third before the prices land; mono labels in
  the CTA network at 28 px read small on a phone.

## heli-55 — Saham HELI, "Tak Ada di Manifest" (9:16, 55.0 s, Indonesian), build, 24 Okt 2026

Contract: `CONTENT/4. Saham HELI (24 Okt 26)/brief/shotlist.md` (Build brief). Evidence each round: `node tools/round.mjs
--film=heli-55` (check, sub-1 540 px preview, `qa.py --events`, review sheet). New in `lib/fx.js`: `sweep` (radial sweep
matte; demo 11.8 in `film/fx-demo`). Scores: hook · phone readability · motion · density · composition · brand · sound
sync. Sound is scored from measurement only: nobody listened in this session.

**Round 1** (first build pass) — 6 · 8 · 7 · 5 · 7 · 9 · 7 (measured)
(qa: density FAIL — 64 events, 4 moves in 3 s; gaps 3.40–4.93, 8.57–11.97, 35.75–37.38, 41.15–42.92, 46.68–48.58,
48.58–51.43; quiet beats 16.5, 17.5, 27.5, 37.0, 53.0, 54.0, 54.5; −14.1 LUFS, −1.9 dBTP; lag −2 frames)
1. 8.57–11.97 (2b–2d): the turning rotor (4.2 rev/s) and the helicopter's settle kept the frame's median change high,
   so the swaps and the network (grown from 0 on DOT) never stood out. Fix: rotor 1.6 rev/s, root and Komala slam in
   from 1.6×, a punch on the helicopter at 10.5.
2. Hook and holds: only 4 detectable moves in 3 s; the card held 3.4–4.9; the CTA network grew softly (46.7–51.4).
   Fix: punches on HELI at 1.0 and 2.0, on the card at 4.0; result row, root and people slam in; the network pulses on
   "pemegang" and 51.0; the orbit pulses at 42.0.
3. 35.75–37.38 and the quiet beats: the price underline was too thin to read as the "same price" beat. Fix: both
   stubs flood lime on "harga" (ink text, ink underline) and punch at 37.0; punches on the stamp (16.0, 16.5), Edwin
   (17.5), his disc (27.5); a caret after the address on 53.0–54.5.

**Round 2** — 7.5 · 8 · 7.5 · 7 · 7 · 9 · 7 (measured)
(qa: density FAIL — 77 events, 5 moves in 3 s; one gap 11.97–13.97; quiet beats 53.0, 54.0; −14.1 LUFS, −1.7 dBTP;
event→onset p90 193 ms; lag −2 frames)
1. 11.97–13.97 (2d → 3a): the lift-off (cubic climb) and the camera tilt are steady motion, no event. Fix: a hit on
   the lift-off (12.5) and a hit with RGB as the tilt lands (13.55).
2. 47.0–48.3 (7a): the desk opened as a thin search bar at the top of an empty frame, the root alone below. Fix: the
   search opens mid-frame and rises to the top as the network builds (SOFT, from "siapa" − 0.45 s).
3. 53.0, 54.0 quiet: the caret switched on the frame before qa's beat window. Fix: it blinks 2 frames after the beat.

**Round 3** (strips: rotor sweep 6.8–7.2, row → card 20.3–21.1, burst 51.4–52.1) — 8 · 8 · 8 · 7 · 7.5 · 9 · 7 (measured)
(qa: density FAIL — 81 events, 5 moves in 3 s; one gap 42.92–45.22; 0 quiet beats; −14.1 LUFS, −1.9 dBTP;
event→onset p90 197 ms; lag −2 frames). The strips: the two lime rotor blades read as designed; row 03 rounds into
the card while the manifest drops (mid-grey for 0.2 s); the burst forms the lockup left to right.
1. 42.92–45.22 (6b → 6c): the fold and the lime lock (events in round 2) sat inside the rings' pour, the disc's move
   and the rows' reveals, so neither stood 2× above the second around it. Fix: a hit on the fold (43.71), a heavier
   hit on "tertutup" (22 px, RGB 16), the lime lock slams from 2.8×.
2. Sound sync p90 197 ms: quiet ticks under the voice (stagger, scan, eyebrows, caret, ring ticks, the rotor's first
   pulse at zero gain) were named events with no audible onset. Fix: only audible cues are named events.
3. 51.6–51.9: the burst's dots straggled in a loose cloud. Fix: spread 0.2 s, faster spring, less curl.

**Round 4** (strip: fold 43.6–44.6) — 8 · 8 · 8 · 8 · 7.5 · 9 · 7 (measured). The cap: master rendered, gaps reported.
(qa: density PASS — 85 events, 5 moves in 3 s, max gap 1.45 s, 0 quiet beats; −14.1 LUFS, −1.9 dBTP; event→onset
p90 204 ms; lag −2 frames). The fold reads: eight rings open into rows while the other 28 pour into the +29 lock.
Remaining under 8:
- Composition 7.5: 24.4–25.9 (4c) the network sits in the lower half with the top empty until the radar's ping;
  48.3–51.4 (7b–7c) the CTA network's 24 px mono labels are small on a phone.
- Sound sync 7 (measured only): event→onset p90 204 ms, the quiet cues under the voice give no onset; nobody has
  listened to the mix.
Market Intel `origin/main` still `2fb61d5` (`tools/mi_sync.mjs`, before the master): kit tokens unchanged.

## trial-55 — OpenView Market Intel free-trial waitlist, "Dari Nama PT ke Pemiliknya" (9:16, 55.0 s, Indonesian), build, 24 Okt 2026

Scores: hook · readability · motion · density · composition · brand · sound.

**Round 1** — 6 · 7 · 7 · 4 · 7 · 8 · 7 (measured)
(qa: density FAIL — 68 events, 3 moves in 3 s, 6 gaps over 1.5 s (max 2.97 s), 10 quiet beats; −14 LUFS, −1.9 dBTP;
event→onset p90 83 ms; lag −2 frames. Check: seek sweep, determinism and layout lint clean.) Built over the board stage:
the 1.6 exit (IATA's card, ring and title leave upward), the match cut onto the card's real position, the dot wipe into
scene 4, the 4.6 exit (panel A out, B's chain pushes), the burst sources tied to panel B's discs, the "?" ring that waits
for the person in 4.1–4.2, the 2.2 landing rings, the 2.7 arrival ring and pill on the beat, scene 3 rows on the cues.
1. 1.5–4.2, 13.7–16.7, 32.7–34.6, 35.8–37.9, 42.5–45.0, 45.7–47.8: no event; the holds carried only steady push or
   small marks. Fix: the list, the cards, the network, both panels and the chain punch on every beat in their holds; a
   large ring leaves the root on "dari".
2. First 3 s had 3 moves: beat punches on the list from 1.95 add the other two.
3. Cue bugs in the board stage: `c('l02','ke')` matched "kepemilikan," (14.7 s instead of 16.6) and `c('l05','openview')`
   matched the first "OpenView" (the URL rose at 47.9 instead of 51.3). Both now take the second word.

**Round 2** — 7 · 7 · 7 · 7 · 7 · 8 · 8 (measured)
(qa: density FAIL by one quiet beat only — 104 events, 5 moves in 3 s, max gap 1.44 s, 0 gaps, 1 quiet beat (9.0 s);
−14 LUFS; p90 83 ms.) The review sheet reads as the board does; labels are the weak part.
1. 9.0–9.2 (1e): the question settles and nothing moves for 0.26 s. Fix: the beat punch starts at 8.95.
2. Readability: network labels, panel A's rows, SUMBER and the person captions at 24–26 px are small on a phone. Fix: 28–30 px
   (labels wrap at 340 px).
3. 52.5–54.5 end hold: the button pulses on every beat (the brief lists 5.5 among the holds that move); the last 0.3 s rests.

**Round 3** (strips: match cut 11.4–12.0, dot wipe 34.4–34.9, burst 47.7–48.6) — 7 · 8 · 8 · 8 · 7 · 8 · 8 (measured)
(qa: density PASS — 103 events, 5 moves in 3 s, max gap 1.42 s, 0 quiet beats; −14 LUFS, −1.9 dBTP; p90 83 ms; lag −2
frames.) The strips: the card contracts into the PT disc while the HELI disc drops to the root; lime dots lead the wipe
into the two panels; the burst leaves panel B's discs left to right and the lockup is solid at 48.5.
1. Composition 4a–4c (36.6–42.5): panel B's chain is small and sits at the panel's foot, with 200 px of nothing under
   its title. Fix: discs 92 / 64 / 72 px, the chain centred in the panel (y 1226); the burst sources follow the radii.
2. Hook 7 (0–3 s): the rows landed with no weight. Fix: two small hits (6 px, RGB 4) on rows one and three, 0.85 and 1.25.
3. Phone page 2: labels read at 28–30 px; nothing else to fix there.

**Round 4** (strips: hook 0–1.6, 4.6 exit 42.4–43.2) — 8 · 8 · 8 · 8 · 7.5 · 8 · 7.5 (measured). The cap: master rendered, gaps reported.
(qa: density PASS — 105 events, 6 moves in 3 s, max gap 1.45 s, 0 quiet beats; −14 LUFS, −1.9 dBTP; p90 83 ms; lag −2
frames. Check: seek sweep, determinism 10/10, layout lint 0 / 0 / 0 / 0.) Panel A leaves upward while B's chain pushes
and its frame and labels go; the chain is the ghost the burst starts from.
Remaining under 8:
- Composition 7.5: 36.3–38.0 (4a) panel B is a dim frame with three faint discs and a "?" until "Di OpenView"; 52.9–55.0
  (5d) the form column ends at y 1398 and leaves y 1420–1600 to the captions only.
- Sound sync 7.5 (measured only): event→onset p90 83 ms and lag −2 frames pass, but nobody has listened to the mix.
- Shot 5.5 deviates from the shot list: it says nothing else moves; the build brief asks for motion on every beat inside
  the holds, so the button pulses (3.5 %) on every beat until 54.6 and the frame rests for the last 0.4 s.
Market Intel `origin/main`: not re-synced in this build (`tools/mi_sync.mjs` before the master, see below).

## mi-demo-40 (25 Okt 2026, build)

**Round 1** — hook 8 · readability 6 · motion 7 · density 4 · composition 7 · brand 9 · sound sync 7
(qa: density FAIL — 36 events, 11 moves in 3 s, max gap 4.95 s, 8 gaps over 1.5 s, quiet beats 9.0 12.5 27.0 31.0 33.5
38.5; −14.1 LUFS, −2 dBTP; event→onset p90 131 ms; lag −3 frames. Check: determinism 10/10, layout lint 0 / 0 / 0 / 0.)
1. Density: the card's arrivals are small (24 px labels, 14–40 px discs), so 3.78–5.33, 8.72–11.93, 13.32–16.33,
   17.30–19.92, 23.65–25.58, 26.47–28.68 and 31.38–36.33 carry no new idea the eye (or qa) can see. Fix: the app's
   selection tint (`selected`, multiplied) over what each line names (layer columns, Dwimuria, each person, the two
   Danantara discs, "Uji coba gratis", the field); the search field focuses on "Ketik"; all three tabs open on 9.0;
   the bars (36 px) fill together on "punya" and the figures roll on "satu"; the list gets its recessed panel; the
   CTA field draws on 33.5 and turns dark (active) as the address types; the caret blinks on the beat grid.
2. Readability 3b (11.8–13.0): INDONESIA INVESTMENT AUTHORITY collides with the Danantara label in rows 2–3; BBCA and
   Danantara labels at 24–26 px. Fix: IIA in its own column (x 870, three lines); holder 28 px, persons 30 px,
   Danantara name 28 px.
3. 4c (15.8–17.0): the 50 % line runs through the overlines and holder names. Fix: drawn in the gaps between each
   row's text lines. Also a cue bug: `openview` matched the brand word "OpenView" (30.3), so the address was already
   typed when the field drew; now the second match (35.5), in film and sfx.

**Round 2** (strip: card into the wall 29.9–31.3) — hook 8 · readability 7 · motion 7 · density 6 · composition 7 · brand 9 · sound sync 7.5
(qa: density FAIL — 53 events, 11 moves in 3 s, max gap 1.4 s, 0 gaps over 1.5 s, quiet beats 9.0 31.5 37.0–39.5;
−14.1 LUFS, −2 dBTP; event→onset p90 103 ms; lag +1 frame.) The strip: the card shrinks onto its wall slot while the
wall fades in, the wall scatters out of frame, the lockup rises into its box.
1. Quiet beats: the tabs flip exactly on 9.0 (the change lands in the frame before qa's window); 31.13–32.13 holds
   still after "Market Intel"; the end hold (37–40) only blinks off-grid. Fix: tab changes ramp over 4 frames from
   1 frame after the edge; a short muted rule draws under "Market Intel" on 31.5; the caret blinks 2 frames after
   every beat (the last 0.47 s rests).
2. Composition 6a–6c (22.0–27.3): the two state banks sit in a band at y 550–850 with 500 px of empty card under
   them until the list. Fix: the network is centred (+220 px) and rises on the beat after "Danantara" (27.0) as the
   recessed panel opens under it; roots 50 px, owners 44, merged 52; tickers 28 px.
3. Sound sync p90 103 ms: soft named ticks (0.05–0.07) sit under the voice. Fix: every named transient at 0.09–0.1;
   "market" follows the picture to "Market" (30.86); a tick for the rule.

**Round 3** (strip: the network rises for the list 26.9–27.8) — hook 8 · readability 7.5 · motion 8 · density 6 · composition 7.5 · brand 9 · sound sync 7.5
(qa: density FAIL — 51 events, 11 moves in 3 s, 1 gap 26.47–28.68, 0 quiet beats; −14.1 LUFS, −2 dBTP; event→onset p90
101 ms; lag +1 frame.) The strip: centred network, rise on 27.0, the panel opens under it.
1. Gap 26.47–28.68: the rise (SOFT, 0.6 s from 27.0) is still moving at 27.37, so the panel's arrival no longer
   stands out from its half second. Fix: the rise on DOT (settled by 27.35); the panel in one frame.
2. Readability 3a–4b: the state banks' holder label at 24 px; the figures still spinning at 15.4. Fix: holder labels
   26 px, the state banks' in three lines (clear of the root disc and the IIA column); the roll on [16, 1] (read by 15.35).
3. Composition 5a (17.0–18.2): BBCA's chain sits in the bottom third, the top half empty for 1.2 s. Fix: it builds
   200 px higher and steps down on "berujung" (DOT), leaving the room above for the two people.

**Round 4** (strip: BBCA steps down 18.0–18.9) — hook 8 · readability 7.5 · motion 8 · density 8.5 · composition 8 · brand 9 · sound sync 7.5. The cap: master rendered, gaps reported.
(qa: density PASS — 53 events, 11 moves in 3 s, max gap 1.4 s, 0 quiet beats; −14.1 LUFS, −2 dBTP; event→onset p90
101 ms; lag −2 frames. Check: seek sweep, determinism 10/10, layout lint 0 / 0 / 0 / 0.) The network rises at 27.08 and
the panel lands at 27.38 as two events; BBCA builds centred and steps down on "berujung".
Remaining under 8:
- Readability 7.5: 3a–3b (9.97–13.0) network labels at 24–26 px and 6e–6f (27.4–30.0) the thirteen list rows at 24 px
  read small on a phone; the card is 940 px wide and the app's names are long. The figures, titles and captions read.
- Sound sync 7.5 (measured only): lag −2 frames passes; event→onset p90 101 ms (iata-55 passed at 83); nobody has
  listened to the mix.
Market Intel `origin/main` moved 59a7717 → 298d090 ("change ahu to kemenkum", "fix obs"): the kit's source files and
the film's labels are unchanged (register names are not on screen, R-120). The capture worktree was not moved (a
generated `next-env.d.ts` change); the figures were not re-read from the running app in this build.
Master (full size, sub 4): qa found what the 540 px preview did not — a gap 30.55–32.17 (the lockup and "Market Intel"
rise are smeared by the shutter, no single frame stands out) and a quiet beat on 14.5. Fix from the numbers, no new
round: "Market Intel" lights on "Intel." (31.26) with the selection tint; a stake mark drops at each bar's end on 14.5.
Re-rendered: density PASS (50 events, 9 moves in 3 s, max gap 1.4 s, 0 quiet beats), −14.0 LUFS, −2 dBTP, lag −2 frames,
event→onset p90 120 ms; check pass (determinism 10/10, layout 0 / 0 / 0 / 0); check_logo 0 differing pixels.
Market Intel re-check (owner's go, same day): the capture worktree's generated `next-env.d.ts` stashed, `mi_sync` moved it
to `791e3d2`; kit files unchanged; every figure, name and label the film shows read again from the running app and
unchanged (`references/sources.md`, "Re-check before the master"). No re-render.

## check-email-16 — OpenView Market Intel Instagram Story "Check your email" (9:16, 16.0 s, Indonesian, no VO), build, 25 Okt 2026

Approved on 25 Okt 2026 (shot list and board, lime `#d4ff3a`). Scores are director judgments from the review sheet, the phone pages and `tools/round.mjs` numbers; the sound score is measured (event→onset, lag), nobody has listened to the mix.

**Round 1** — hook 6 · readability 7 · motion 7 · density 4 · composition 7.5 · brand 9 · sound sync 5
(qa: density FAIL — 21 events, 3 moves in the first 3 s, gaps 1.12–3.00 / 6.50–9.00 / 10.43–12.00, still runs 1.87–2.12, 10.73–11, 11.62–11.98; −14 LUFS, −2.1 dBTP; event→onset p90 247 ms.)
1. Density: the calm moves (logo, hairline, bars, push, underline-free tell) change under 0.5 % of the frame, so the detector counts none of them. Fix: small hits (4–7 px) on each, plus new moves in the quiet stretches: a network heartbeat on 2.5, an underline under "email" on 7.2, the letter reading on at 7.6, a tuck and shut hit at 8.4 / 8.7, a punch on the Spam and Promosi. markers at 10.75, a logo breath at 11.5, an echo pass on the hairline at 13.55, a hit on each of the three pulses at 14.0 / 14.5 / 15.0; the network drifts faster so no frame is dead.
2. Sound sync: soft named cues (0.035–0.07) were under the pad, so their events had no onset. Fix: only transients that carry a hit are named, at gain 0.1–0.14; ambience is unnamed.
3. Layering: the envelope's hop passed over CHECK on 3.0–3.4. Fix: the envelope is drawn under the type.

**Round 2** — hook 7.5 · readability 7 · motion 8 · density 8 · composition 7.5 · brand 9 · sound sync 8.5
(qa: density PASS — 34 events, 5 moves in the first 3 s, max gap 1.17 s, 0 still runs; −14 LUFS, −1.9 dBTP; event→onset p90 25 ms, lag −2 frames.)
1. Readability 3a–5c: the instruction (36 px) and the reminder (mono 32 px) are the information the viewer must act on and read small on a phone. Fix: 40 / 38 px, sign-off 34 px (`TELL_Y` 1330 → 1322); the lines stay inside the margins (layout lint 0 / 0 / 0 / 0).
2. Hook: exactly 5 detected moves, 0.3 (logo) and 2.0 (push) not seen. Fix: a tap on 2.0 and 0.5.
3. Sign-off size, see 1.

**Round 3** — hook 7.5 · readability 8 · motion 8 · density 8 · composition 7.5 · brand 9 · sound sync 8.5
(qa: density PASS — 34 events, 5 moves in the first 3 s; p90 25 ms.) The quick-push attempt (5 % in 0.5 s) was a camera move, not an event, so 2.0 stayed undetected. Fix: back to a slow 8 % creep with a 7 % punch on 2.0 and 0.5, ring + thump named on both.

**Round 4** (cap) — hook 8 · readability 8 · motion 8 · density 8.5 · composition 7.5 · brand 9 · sound sync 8.5
(qa: density PASS — 35 events, 6 moves in the first 3 s, max gap 1.17 s, 0 quiet beats; −14 LUFS, −2 dBTP; event→onset p90 18.7 ms, lag −2 frames. Check: seek sweep, determinism 10/10, layout lint 0 / 0 / 0 / 0.)
Master (`output/check-email-16-final-9x16.mp4`, sha256 `2294ff50a0bef3fc…`): density pass, 33 events, 6 moves in 3 s, max gap 1.17 s, p90 18.7 ms, −14.0 LUFS, −2.0 dBTP; still runs 12.62–12.82 (0.2 s) and 15.57–15.98 (the rest, by design).
Remaining under 8:
- Composition 7.5: from 4.9 s on, the lower 27 % of the frame (y 1410–1920) holds only the dim network. It is the approved decision 4 (the reply bar) and 7 (network at 12 % alpha); lowering the block or lifting the network is the owner's call.
- Not scored: the 0.3 logo rise and the 0.5 ring register as no event in `qa.py` (the hook counts 6 of 8 designed moves); sound has never been listened to.
Deviations from the approved board, all readability: instruction 36 → 40 px, reminder 32 → 38 px, sign-off 30 → 34 px, instruction baseline 1330 → 1322; the envelope is drawn under the type; the shot list's quiet stretches filled as above. Copy, colours, the layout of the headline block and the sound plan are as approved.
`tools/check_logo.mjs` needs `film.lockup` (an end card); this film draws the logo small at the top and exports none, per the build brief. Not run.

## aspi-55 — Saham ASPI, "Siapa di Balik Kenaikan ASPI?" (9:16, 55.0 s, Indonesian), build, 25 Okt 2026

Approved on 25 Okt 2026 (shot list and board, decisions 1–14). Built on the board stage: the joins the board cut
(row 01 → PT disc with the table falling away, one navy room 3 → 4 with the lock opening into the record, the chain
re-forming as the network 4 → 5, PO out of the chip, the chart's points bursting into the split 6 → 7, the split's discs
travelling back into the network 7 → 8, the network's dots bursting into the lockup with a 4-frame swap), exits for
every label, and the score: a new piano voice in `lib/synth.mjs` (hammered strings, felt, prepared string, scrape,
key clicks, dampers, a room) and `src/sfx-aspi-55.mjs`, piano only. Scores are director judgments from the review sheet
and `tools/round.mjs` numbers; the sound score is measured (event→onset, lag, levels), nobody has listened to the mix.

**Round 1** — hook 6 · readability 7.5 · motion 7 · density 4 · composition 8 · brand 9 · sound sync 6
(qa: density FAIL — 59 events, 3 moves in the first 3 s, max gap 4.56 s, 8 gaps over 1.5 s, 19 quiet beats; −14.1 LUFS,
−2 dBTP; event→onset p90 156 ms, lag −2 frames. Check: determinism 10/10, layout lint 0 / 0 / 0 / 0.)
1. Density: the holds between word cues are smooth springs (line draw, card unfold, recentre, reveals), which the
   detector does not count, and the dark-on-dark card is invisible to it. Gaps 0.72–2.80, 5.90–7.53, 12.73–15.95,
   17.97–19.57, 23.78–25.55, 32.68–34.20, 35.37–39.93, 43.68–45.50. Fix: one punctual move per gap on the words — a hit
   on "naik", +135,78 % slams in on "seratus", the line dims on "tiga"; the scan stops on row 01 with a lime flash; a wide
   amber pulse on "Biasanya", a small hit as the "?" lands; a lime read-scan down the opened record; a hit and a second
   ring on "Nama yang sama"; scene 6 stays calm (no hit on a figure): the day's column as a lime band behind the marker
   (it brightens once on 37.5), a highlighter under ≈ Rp852 JUTA, 24.000 LOT steps back to muted on "juta"; a highlighter
   under "DATA,".
2. Quiet beats 7.0, 13.0–14.5, 20.5, 29.0–29.5, 36.5–39.0, 45.0–47.0, 49.0, 51.0, 54.0–54.5: motion on the beat — the
   amber ring beats with the score, a sheen along the redaction bar once a beat, Pilarmas' selection pings each beat,
   a clock ring from the 11 Jun point each beat, the client rings drift, the network recedes later, the lockup's lines
   come in on 51.0, the end card breathes in (5 % over the last 2 s; the logo is outside it).
3. Sound sync: reversed notes were named at their end (an offset, no onset) and quiet clicks and grace notes were
   named under the voice. Fix: only transients that carry a picture move are named; the new picture moves get their own
   piano cue (chord on "naik", thud on "seratus", ping on the scan stop, prepared thud on the pulse, a rising run under
   the read-scan, pings for the iris, the split, the highlighter).
Market Intel: `mi_sync` moved 6b3c12b → 88aab0b → 7d551ca (dashboard SQL, `en.json`, the network page's ownership
changes; kit sources changed only a comment, "AHU" → "KEMENKUM"). Recaptured at 7d551ca: `aspi-holders.png` is
pixel-identical (ffmpeg md5), so `SEP`, `NAME_X`, `PCT_X` and every figure in scene 2 stand; `aspi-header.png` changed
and is not used by the film.

**Round 2** — hook 7.5 · readability 7.5 · motion 7.5 · density 6.5 · composition 8 · brand 9 · sound sync 7
(qa: density FAIL — 73 events, 5 moves in the first 3 s, max gap 2.15 s, gaps 12.47–14.15, 23.78–25.45, 32.68–34.20,
35.37–37.52, quiet beats 7.0 and 52.0; −14.1 LUFS, −1.9 dBTP; event→onset p90 118 ms, lag −2 frames. Check pass.)
`tools/qa.py --events` now also prints the eight sound events farthest from an onset (round.mjs relays the line).
1. Density: the "Nama yang sama" hit fell inside the 4 → 5 travel (everything moves, nothing stands out); the marker band
   and the ≈ Rp852 highlighter grew over 3–30 frames, too gradual for a 320 px detector. Fix: the hit and the thick ring
   move to "sama" (24.82, network settled); the day's column snaps in over 2 frames at full height; ≈ Rp852 JUTA in display
   56 px with a 2-frame highlighter; a first amber pulse on 13.0 (the closed company sounds out twice).
2. Quiet beats: the push into row 01 now starts as the scan stops (6.95), so 7.0 moves; the disclaimer arrives on 52.0
   (up 3 s before the end, as the shot list says) and fills that beat.
3. Sound sync, worst events: iris 655 ms (the ping sat under the reversed swell's peak), shrink 335, tilt 311, dashes 294,
   pan 178, answer 161. Fix: the swell and the scrape end 40–60 ms before the iris and the iris gets a clear ping and dyad;
   louder first notes for shrink and dashes; a D5 over the low landing on the tilt; "pan" and "answer" unnamed (passing
   notes, not hits).

**Round 3** — hook 7.5 · readability 8 · motion 8 · density 7.5 · composition 7.5 · brand 9 · sound sync 7
(qa: density FAIL — 77 events, 5 moves in the first 3 s, max gap 1.68 s, one gap 12.47–14.15, 0 quiet beats; −14.1 LUFS,
−2 dBTP; event→onset p90 99.5 ms, lag −2 frames; worst iris 782, shrink 335, tilt 311, dashes 294, clock 253 ms. Check pass.)
1. Density: the first amber pulse (13.0, 7 px) is two pixels wide at the detector's 320 px and is not counted. Fix: both
   pulses 11 px.
2. Sound sync: the detector finds 221 onsets in 55 s; next to the narrator's consonants a felt or soft note is no onset
   (the falling run into the tilt shows none at all), and the iris ping followed the reversed swell by 40 ms, inside its
   peak. Fix: a named call is a hit and the key's action is heard under it (a click, a fingernail for a pluck); the swell and
   the scrape stop 120 ms before the iris hit (the suck, then the hit), which also gets a prepared thud; the passing cues
   (climb, shrink, fall, dashes, clock) are unnamed.
3. Composition 2c (8.99): the capture's own heading, "Pemegang Saham (Laporan 1%)", sits right under the amber name and
   reads as a second title. Fix: the table's heading band steps back (ink 70 %) as the row lights; the falling band keeps it.

**Round 4** (cap) — hook 7.5 · readability 8 · motion 8 · density 7.5 · composition 8 · brand 9 · sound sync 8
(qa: density FAIL — 77 events, 5 moves in the first 3 s, max gap 1.66 s, one gap 12.47–14.13, 0 quiet beats; −14.1 LUFS,
−2 dBTP; event→onset p90 64 ms (iris fixed), worst tilt 311, logo 111, card 98 ms; lag −2 frames. Check pass.)
The 13.0 pulse is drawn (strip 12.9–13.1) but, at 0.7 s, is steady motion to the detector: its peak frame (4,406 px
at 320 px) is under twice the second's median. The falling run into the tilt still shows no onset.
Master, fixes from the numbers, no round 5: both amber pulses run 0.45 s; the run stops 120 ms before the tilt and the
tilt hit gets a D5 and a D6 over the thud. First master: −14.0 LUFS, −1.9 dBTP, p90 61.8 ms, density FAIL on one new gap
25.45–27.13 (the full-size, sub-4 render smooths the node pops that the 540 px preview counted at 26.08). Fix: the lime
highlighter runs under "4 PERUSAHAAN" on "pemilik" (26.30), with a ping.
Master (`output/aspi-55-final-9x16.mp4`, 1080×1920, H.264 yuv420p, 60 fps, 55.000 s): density PASS — 73 events, 5 moves in
the first 3 s, max gap 1.37 s, 0 quiet beats; −14.1 LUFS, −2.0 dBTP; event→onset median 16.7 ms, p90 61.6 ms, lag −2 frames;
voice 13.3 dB over the ducked score while speaking; check pass (seek sweep 3,300 frames, determinism 10/10, layout lint
0 / 0 / 0 / 0, unit tests 33); `check_logo` 0 differing pixels; whole-film hash-only renders (1 and 4 workers) both
sha256 `1e51905fac897039…`; file sha256 `3ea66b66d0e5c337…`. Market Intel `origin/main` 7d551ca at the master (= the
capture).
Remaining under 8:
- Hook 7.5: exactly 5 detected moves in the first 3 s (0.10, 0.72, 1.28, 1.63, 2.80); the logo pop at 0.9, the line draw
  and the readout are designed moves the detector does not count.
- Sound: nobody has listened to the score. Worst sync events are soft by design — logo ping 111 ms (under the open low
  octave), the rolled card arpeggio 98 ms (its low first note), "siapa" 87 ms.
Deviations from the approved board (no claim, figure or source changed): ≈ Rp852 JUTA in display 56 px with a lime
highlighter (was mono 40 px); lime highlighters under "4 PERUSAHAAN" and "DATA,"; the capture's own heading dims under
the amber name at 2c; "KETERBUKAAN MENUNJUKKAN" leaves as the lockup lands, so the end reads "SIAPA." over OpenView; the
disclaimer arrives at 52.0 as the shot list says (the board stage drew it at 51.9); board stills 2b, 4e, 6e, 7d moved to settled
frames. Added moves: hits on "naik", "seratus" (+135,78 % slams in), "sama", a hit as the "?" lands; the scan's stop flash;
two amber pulses and a beating ring; the read-scan down the record; a sheen on the redaction bar; Pilarmas' beat pings;
the day's column and clock rings in scene 6; drifting client rings; the end card's 5 % breath.

### aspi-55 Revisi 1 — scenes 6–8 on the new clock, 26 Okt 2026

Owner's revisi 1 (`brief/revisi-1.md`, decisions 15–17): l07 "Apakah kebetulan?", l08 gains "Telusuri sendiri di
OpenView.", edges 41 · 46 (were 41 · 47.5). Built: scene 7 keeps the split and the client fan, with its caveat read
before the question (fan at 41.75, "Order lewat broker bisa milik nasabahnya" at 42.2); DATA, / BUKAN TUDUHAN. are gone;
KEBETULAN? (display 84 px, the "?" in lime 0.35 s later) rises on "kebetulan", calm; the question is held 2.2 s with a
4 % push anchored on the margin (eased out as the discs travel into scene 8) and one path pulse from his disc on 44.5.
Scene 8 from 46.0: the network re-forms and pulses once on 46.5, recedes over "menunjukkan" into APA; the disclaimer is
up from 50.0; "Telusuri sendiri di openview.id" lights lime on "Telusuri" (51.85); the end card breathes 7 % over the
last 3 s. Score: scene 7 thinner (two voices), then suspended — a B♭ lydian chord under "Apakah", a high E6 left hanging
on the "?", the path pulse as a low string ping; it resolves to D minor on "Keterbukaan"; the call and answer on "apa"
and "siapa" at the new cues; a soft key on "Telusuri"; D minor add9 struck again on the last "OpenView." and faded by 55.
Levels: scene 7 −28 dB RMS, the held suspension −34 dB before the resolve (by design), voice 13.3 dB over the ducked score.

**Revision round** (round.mjs round 5) — hook 7.5 · readability 8 · motion 8 · density 7.5 · composition 8 · brand 9 ·
sound sync 7.5 (qa: no gaps, quiet beats 33.0, 34.5, 48.0; layout lint: two texts pushed past the left margin at 44.75 by the
hold's push; event→onset p90 75 ms.)
1. The push scaled about the centre and pushed the caveat and KEBETULAN past x 80. Fix: anchored on the margin.
2. Quiet beats: the new l06 take moved "lewat" to 33.42, leaving 33.0 and 34.5 still; the network had settled by 48.0.
   Fix: the 11 Jun clock ring beats from 32.5 (with the score's A); the network recedes from 47.45, over "menunjukkan".
3. First revised master: one gap 45.93–47.55. Fix: the re-forming network pulses once from his disc on 46.5.
Master (`output/aspi-55-final-9x16.mp4`, replaces v1; 1080×1920, H.264 yuv420p CRF 16, 60 fps, 55.000 s): density PASS —
77 events, 5 moves in the first 3 s, max gap 1.36 s, 0 quiet beats; −14.0 LUFS, −2.0 dBTP; event→onset median 15.6 ms,
p90 74.9 ms, lag −2 frames; check pass (determinism 10/10, layout lint 0 / 0 / 0 / 0, unit tests 33); `check_logo` 0
differing pixels; hash-only renders (1 and 4 workers) both `22c1dbe6ce7d3e1d…`; file sha256 `6a3efb4a33f38c54…`.
Remaining under 8: hook 7.5 (5 detected moves, unchanged); sound sync 7.5 — worst "apa" 163 ms (the slam lands on the
narrator's soft vowel), the final chord 129 ms (rolled from its low D); nobody has listened.
Market Intel: `origin/main` moved 7d551ca → 5d9adfd. `mi_sync` refuses: the capture worktree has the dev server's
generated `next-env.d.ts` change. The 45-file diff touches no kit source, no company/holders page and no Indonesian
strings, so the 7d551ca capture stands for this render; recapturing needs the generated file restored (owner's go, as on
mi-demo-40).
Re-check (owner's go, 26 Okt 2026): `next-env.d.ts` restored, `mi_sync` moved the worktree to 5d9adfd (= origin/main),
recaptured with `capture_mi.mjs --lang=id`: `aspi-holders.png` and `aspi-header.png` pixel-identical to the 7d551ca
capture (ffmpeg md5), so `SEP`, `NAME_X`, `PCT_X` and every scene 2 figure stand and the master needs no re-render.
`capture.json` now records 5d9adfd; the dev server's regenerated `next-env.d.ts` was restored again after the capture.

## andi-55 · "Siapa di Balik Pengendali Baru ANDI?" (build, 27 Okt 2026)

Build on the approved board (owner, 27 Okt 2026). Before the motion pass: the capture outlines re-measured on full-size
crops of the film's own frames: PSJ "1 nama pemilik manfaat tercatat" (began on "ki", cut "tercatat"), Erik "namanya
muncul di 3 perusahaan privat." (began on "emiten"), the network panel's header row (its sides were clipped by the
plate); the PSJ owner row was already on its text. The fan's middle date sat under the panel's top edge: moved up.
Joins designed: 2b → 2c one pan up the paper; 2c → 2d PSJ's disc carries into the deal; 2 → 3 the room turns navy
while the disc slides to the centre and ANDI recedes; 3 → 4 the held push runs on under the scan; 4 → 5 the PSJ plate
is the same plate (s4 draws it); 5b → 5c a push through the name row (match cut on its ink); 5d a push into the 3;
6a the disc the iris opened from travels to the centre and gives way to the logo plate; 6e → 7 the tiles fold into
DSAP's disc and the web pulls back from it. Market Intel: `mi_sync` already at origin/main 4644d41 (captures stand);
the kit's sources changed 1c2b99d → 4644d41 in comments only (no token, mark or glyph change).

**Round 1** — hook 7 · readability 8 · motion 7 · density 5 · composition 7.5 · brand 9 · sound sync 7
(qa: density FAIL, 65 events, 4 moves in the first 3 s, gaps 9.58–11.52, 15.65–17.20, 18.97–21.18, 26.62–30.62,
9 quiet beats; −14.1 LUFS; event→onset p90 151 ms, worst "siapa" 313 ms; check pass, layout 0/0/0/0.)
1. 26.62–30.62: four seconds of smooth zoom and pan with no event (5a–5b). Fix: snap zoom and snap pan (outExpo,
   0.5 s), the KEMENKUM chip lands with a hit, the selection tint sweeps the phrase.
2. Gaps in 2a and 3a–3c and the quiet beats (6.29, 8.71, 15.0, 16.45, 20.32, 43.55, 44.52, 54.19, 54.68). Fix: the
   camera drops onto the price line on "barunya"; a lime pulse runs the 33 % link to PSJ; 3a's thread rises from PSJ
   with a room punch; the three rings pop, flash lime and send a sonar ring each; the PENGENDALI chip flies off ANDI on
   "Tapi"; the "?" punches as its chip settles; in 6 the tile being said wears the lime selection and pulses on every
   beat; the end card breathes linearly to the last frame.
3. Hook: only 4 detected moves by 3 s (Rp faded in). Fix: Rp slams in on "rupiah" with a hit.

**Round 2** — hook 8 · readability 7 · motion 8 · density 9 · composition 7 · brand 9 · sound sync 7.5
(qa: density PASS, 86 events, 5 moves in the first 3 s, max gap 1.40 s, 0 quiet beats; −14.1 LUFS; event→onset
p90 139 ms, worst cut "ring" 262 ms, "siapa" 242 ms; check pass, determinism 10/10, layout 0/0/0/0.)
1. 34.06 (5d): the lime ring sat over "di", not the "3" (its source point was the board's estimate). Fix: the 3
   measured on the frame (source x 3233), the push into it now centres on it.
2. 32.78 (5c): the beneficial-owner line and the app's "Tidak tercatat memegang saham emiten" were 24 px mono, hard
   to read on a phone. Fix: 28 px, the caveat in paper white.
3. 26.3–27.4 (4c): the logo shrank to half and the plate was a thin strip, both small in a black frame. Fix: the logo
   settles at 72 % on y 560 above the plate. Sound: transients (tick, snap, kick) on the soft cuts at 9.38, 13.12,
   26.11 and 37.01, and a kick under the SIAPA slam.

**Round 3** — hook 8 · readability 8 · motion 8 · density 9 · composition 8 · brand 9 · sound sync 7.5
(qa: density PASS, 86 events, 5 moves in the first 3 s, max gap 1.40 s, 0 quiet beats; −14.1 LUFS; event→onset
p90 120 ms; worst: the cut at 13.12 262 ms, the SIAPA slam at 7.04 242 ms, the keyhole glint 1.07 s (a 0.03 bell in the
silence, by design); check pass, determinism 10/10, layout 0/0/0/0.)
1. 7.04: the SIAPA slam's sound arrives on top of the riser's peak and the bed, so no onset reads at the hit. Fix: the
   riser and the bed end 0.25 s before the slam; the hit lands on air.
2. 13.12: the cut from the paper to the deal is too quiet under the duck (tick 0.12, kick 0.3). Fix: kick 0.6, snap.
3. 32.9–34.2 (5d): the profile plate alone, a thin strip in black, and his photo gone between 5c and 5e. Fix: the
   photo and crown stay, rising and shrinking to where the fan picks them up.

**Round 4** (the cap) — hook 8 · readability 8 · motion 8 · density 9 · composition 8 · brand 9 · sound sync 7.5
(qa: density PASS, 86 events, 5 moves in the first 3 s, max gap 1.40 s, 0 quiet beats; −14.1 LUFS, −2.0 dBTP;
event→onset p90 118 ms, the 13.12 cut now on its onset, SIAPA 218 ms; check pass, determinism 10/10, layout 0/0/0/0.)
Remaining under 8: sound sync 7.5 — the SIAPA slam (7.04) still reads 218 ms from its nearest onset (the narrator's
"siapa" and the hit share the moment); the keyhole glint (22.80) is a 0.03 bell inside the silence, by design; nobody
has listened.
On the master two faults showed that the 540 px previews hid: a gap 11.50–13.13 (the PSJ disc's pop lost prominence
under the full render's motion blur; it now lands with a small hit on 12.59) and `check_logo` 9 % differing pixels (the
end card breathed to 106 % on the last frame, and the burst's lime dots kept drawing under the lockup and fringed its
edges). Fix: the card breathes out 5 % and back to exactly its own size on the last frame; the burst stops once the
solid lockup has swapped in.
Master (`output/andi-55-final-9x16.mp4`; 1080×1920, H.264 yuv420p, 60 fps, 55.000 s, AAC): density PASS — 81 events,
5 moves in the first 3 s, max gap 1.39 s, 0 quiet beats; −14.1 LUFS, −1.9 dBTP; event→onset median 33 ms, p90 121 ms,
lag −2 frames; check pass (determinism 10/10, layout 0/0/0/0, unit tests 35); `check_logo` 0 differing pixels;
hash-only renders (1 and 4 workers) and the master all `a2cdb4c4e7d4f2b5…`; file sha256 `23f358ca0512c6cc…`.
Delivered with `output/andi-55-contact.png` and the poster `output/andi-55-poster.png` (3.44 s: Rp 92,57 MILIAR).
Remaining under 8: sound sync 7.5 (SIAPA 218 ms; the glint by design; nobody has listened). Open for the owner before
publication (brief note 1): a larger photo of Ir. Erik Setiawan, usage permission for the photo and both logos, legal
review.

**Owner revision, 27 Okt 2026 (decision 9)** — 5f without the network panel ("untuk bagian ini gausah ditampilkan ya,
berarti sesuaikan lagi"). The fan no longer moves up: it holds the frame (PSJ's disc back on its board place), its
source line "Sumber: profil Ir Erik Setiawan · OpenView" comes in on 36.24, the camera leans 8 % in about Erik's link
point on 36.0, DSAP lights on 36.76 with a punch and one sonar ring, and the iris opens out of DSAP's disc where the
lean left it; the DSAP room's first disc starts there too. The `erik-network.png` capture is no longer loaded. Sound:
the panel's slide and tick became a source tick, a lean whoosh and a pop on the light.
Round 5 (revision): layout 0/0/0/0, max gap 1.40 s, one quiet beat at 36.77 (the light switched in one frame and held).
Fix: the punch and the sonar ring. Round 6: density PASS, 0 quiet beats.
Master (`output/andi-55-final-9x16.mp4`, replaces the build's): density PASS — 84 events, 5 moves in the first 3 s, max
gap 1.39 s, 0 quiet beats; −14.1 LUFS, −1.9 dBTP; event→onset median 33 ms, p90 121 ms, lag −2 frames; check pass
(determinism 10/10, layout 0/0/0/0, unit tests 35); `check_logo` 0 differing pixels; hash-only renders (1 and 4
workers) and the master all `20c97887c3818bbe…`; file sha256 `3b52b676132abec4…`. Contact sheet redrawn.

## satu-persen-58 (build, 30 Okt 2026)

Board approved the same day ("OK, lanjut build"). Built on `src/film.js` in `CONTENT/10. TikTok_Launching OpenView (30 Okt 26)/`;
sound in `src/sfx-satu-persen-58.mjs`. Cost first: the blurred rows, unverified nodes and branches became sprites and a
quarter-size layer built once, so the full sweep fell from about 29 min to about 3 min. The narrative brief (decision 4) keeps
the film calm: no shake, RGB split or invert; every hit below is light, a ring, a soft punch or a camera step.
The 2 April page was read again before the master: SP 64/OJK/DKPU/IV/2026, 2 April 2026, agenda "Penyediaan data
kepemilikan saham Perusahaan Tercatat di atas 1 persen kepada publik", confirmed.

**Round 1** — hook 6 · readability 8 · motion 6 · density 5 · composition 7 · brand 9 · sound 7.
Density FAIL: 3 moves in 3 s, 9 gaps, 16 quiet beats, long still runs.
1. 0–3 s: the camera's fall hides the moves from the measure. 2. 39.1 s: the map's camera was never restored (board-stage
bug), so title, legend and card zoomed with the map, off the left edge. 3. Holds at 18–23, 29–32, 49–53 s with nothing moving.
Fixes: camera restored and the legend gives way to the card; lamp, line cut and punch in the hook; dust motes, star drift,
lamps coming on, sonar rings on ① ② ③ and the stars, windows dropping and coming on, cards answering the beat.

**Round 2** — hook 6.5 · readability 8 · motion 7.5 · density 6.5 · composition 8 · brand 9 · sound 7.5.
Layout 0/0/0/0, no quiet beats, no still runs; the road → street join and the map fold read in their strips. FAIL: 3 moves, gaps
13.73–15.63, 26.88–28.40, 29.58–31.73. (qa.py ran out of memory beside the sheets; rerun on its own.)
Fixes: lamp click moved to the beat at 0.6 where the fall ends; plate punch on "masukan"; the frame takes the padlock's click;
the two unnamed doors arrive in a breath of fog light.

**Round 3** — hook 6.5 · readability 7.5 · motion 7.5 · density 7 · composition 7 · brand 9 · sound 7.5.
FAIL: 3 moves, one gap 1.60–3.82 (the long pull-back hid the shutters). Eyes: 0–1.1 s far too dark for a hook; 30–34 s the
"PT CONTOH INVESTAMA" label crossed by the dashed arrow and covered by the second door; caption over busy windows.
Fixes: pull-back in two steps (shutters, then crowd), lamp pool warmer and the wall brighter from frame 0, door and arrow moved
clear of the label, caption scrim higher over the street.

**Round 4** — hook 8 · readability 8 · motion 8 · density 8.5 · composition 8 · brand 9 · sound 7.5.
Density PASS: 80 events, 5 moves in the first 3 s, max gap 1.46 s, 0 quiet beats, no still runs; layout 0/0/0/0; determinism
10/10; -14 LUFS, TP -1.9 dBFS, voice 11.1 dB over the music, lag -2 frames, event→onset p90 332 ms (the soft swells and risers
of an ambient score, not the hits).
Under 8: sound sync 7.5 (19.56 truck, 23.71 corner, 10.20 chord have slow onsets by design; nobody has listened yet).
Master (`output/satu-persen-58-final-9x16.mp4`; 1080×1920, H.264 yuv420p, 60 fps, 58.000 s, AAC): density PASS — 76 events,
5 moves in the first 3 s, max gap 1.45 s, 0 quiet beats; −14.0 LUFS, −1.9 dBFS; check pass (determinism 10/10, layout
0/0/0/0); `check_logo` 0 differing pixels (first render 21: stars and motes reached into the clear space by their radius,
so the skip box took 8 px more); render sha256 `4587c88b0a59e827…`, file sha256 `62ac72c7b1e5ee66…`. Delivered with
`output/satu-persen-58-contact.png` and the poster `output/satu-persen-58-poster.png` (4.70 s: DI ATAS 1%).
Render notes: the machine has 8 GB; with Chrome, ChatGPT and other Claude sessions open a 4-worker render hung at 16:14 (CPU 10%,
free RAM under 800 MB, no error) and was stopped; 2 workers took 1,063 s and finished clean.
Remaining under 8: sound sync 7.5 (soft onsets by design; nobody has listened). Open for the owner before publication:
MSCI logo usage permission, waitlist / access status, legal review, a plan with a commercial licence for the voice.
Whole-film determinism: hash-only on 1 worker (1,222 s) gives the master's `4587c88b0a59e827…` (2 workers), so the render does not depend on the worker split.

## pandu-supra-80 (31 Okt 2026)

Motion and score built from the approved board in a fresh session. `film.js` was a stack of stills; every shot now acts out the
shot list on the word cues. A stroke-state leak made 4/10 frames non-deterministic: `lamp()` leaves round caps on the context, so
dashed pills depended on the frames before them; `draw` now resets stroke state each frame, on the whip layer too.

**Round 1** — hook 6.5 · story 8 · readability 7 · motion 7.5 · density 5.5 · composition 8 · brand 9 · sound 6.
Determinism 10/10, layout findings only inside the window at 5.64 and 8.03 (the street seen through the desk window). FAIL: 79 events,
3 moves in 3 s, 15 gaps (9 outside scene 7, waived by decision 11), 5 quiet beats.
Problems: 1.4–2.8 caption over the enlarged list; first 3 s are one steady push, so nothing stands out; voice 20.7 dB over the music.
Fixes: the lamp finds the noticeboard, camera steps on "huruf" and "siaran", the caption band turned to clean paper; the world answers
the gaps (stacks land, windows by row, lens jumps, the scan pings what is on record, the ledger and the phone move in steps); the
silence pulls back in two steps; music 0.22 → 0.5; stars on the end card outside the clear space.

**Round 2** — hook 7 · story 8 · readability 8 · motion 7.5 · density 6.5 · composition 8 · brand 9 · sound 7.5.
Determinism 10/10; voice 13.5 dB over the music; -14.1 LUFS. FAIL: 88 events, 4 moves, gaps outside scene 7 at 8.48–10.43, 11.87–13.42,
32.23–35.13, 67.25–68.87, 69.73–72.38; quiet 35.4 and the end hold.
Problems: slow steps overlap, so qa sees one long move (0.3–1.3, the lens hunt, the phone); the release label covers the logo at 31.2; the
source line is lost on lit windows at 19.6–22.
Fixes: a short camera step on the word (spring 24), lens jumps with rests between, the label at the page foot, sources on a dark strip,
a night skyline with living windows under the end card.

**Round 3** — hook 8 · story 8 · readability 8 · motion 8 · density 7 · composition 8 · brand 9 · sound 7.5.
Determinism 10/10; 93 events, 5 moves in 3 s, -14.1 LUFS. FAIL only on 8.48–10.43 and 11.87–13.42 outside scene 7 (gaps and quiet beats
46–63 are waived, decision 11).
Problems: coins and rising buildings are one steady change, so nothing stands out; the thumb at 70.1–70.9 reads as a stick; the dive at
69.3 goes through the ledger's big type rather than the window.
Fixes: OJK's floodlights stutter on at "saham"; rows rise one at a time on a short spring; a hand with palm and cuff; the book clears the
window before the dive.

**Round 4** — hook 8 · story 8 · readability 8 · motion 8 · density 8 · composition 8 · brand 9 · sound 7.5.
Determinism 10/10; 94 events, 5 moves in 3 s; -14 LUFS, TP -1.6 dBFS, voice 13.6 dB over the music; `mi_sync`: `f3a6eaf` is still origin/main.
Outside scene 7 one gap is left, 69.73–72.28: the hand raised the median, so the screen's steps no longer stand out. Fix before the master:
the street takes a camera step on "OpenView". Under 8: sound sync 7.5 (risers and soft onsets by design, lag -11 frames; nobody has listened).

**Master** (`output/pandu-supra-80-final-9x16.mp4`; 1080×1920, H.264 yuv420p, 60 fps, 76.000 s, 2 workers 554 s): 104 events, 5 moves in the first
3 s; -14 LUFS, -1.6 dBFS, lag 7 frames; check pass, `check_logo` 0 differing pixels; render sha256 `1afeeb50208e4f79`. Poster 2.0 s (the lens on SS).
`qa.py` density FAIL at full size: gaps 46.03–63.00 and quiet-free scene 7 are waived (decision 11); outside it one gap, 21.50–23.72, and one quiet
beat at 45.6. The phone gap is closed. Under 8: sound sync 7.5, nobody has listened.
Owner's call after this film (31 Okt 2026): two critique rounds by default, a third only for a fault the eye can see, because rounds 3–4 here went
mostly on the density number.

### pandu-supra-80 extension, 163.2 s (31 Okt 2026, build)

Shots 10a–17a and 8a–9d animated and scored on the 22 final takes; 1a–7d keep their built motion. `tools/round.mjs` counts on from the 76 s cut, so
extension round 1 is its round 5 and it prints "the cap": the two rounds here are the extension's own.

**Round 1** (tool round 5) — hook 8 · story 8 · readability 7 · motion 7.5 · density 7 · composition 7 · brand 9 · sound 7.5.
Determinism 10/10; 201 events, 12.3 per 10 s, 5 moves in 3 s; -14 LUFS, TP -2 dBFS, voice 14.7 dB over the music. `qa.py` ran out of memory beside the
sheets (2.36 GiB array) and passed when run alone. Layout overlap at 131.05 is false: the lobby's plate under the lime scan, hidden by the clipped list.
- Readability 7: 128.4–137.4, ten names in `U(26)` on a 9 s hold, thin at 360 px.
- Motion 7.5: 153.0–153.9, the pen's exit crosses "Pandu: pasif, pribadi". Density 7: 132.2–136.8 and 142.1–145.0, holds with one event each.
- Composition 7: 147.6–154.2, lamp on the page and its cone across the rows (owner's note, E13); 117–121, Pandu's head covers the `CIO` pill and the key board floats.
- Sound 7.5: cues on their words by the numbers, nobody has listened.
Fixes: (1) the lamp behind the book, a soft pool on the page, the pen draws the rule under the question and leaves below the rows; (2) the `CIO` pill above
head height, a post under the key board; (3) the ten names at `U(30)`, dots and Pandu moved right.

**Round 2** (tool round 6) — hook 8 · story 8 · readability 8 · motion 8 · density 7 · composition 8 · brand 9 · sound 7.5.
Determinism 10/10; 202 events, 12.4 per 10 s, 5 moves in 3 s; `qa.py` again run alone. `mi_sync`: `f3a6eaf` is still origin/main, no recapture. The three fixes hold
on the phone pages; the longest name then sat on its dot, so the ten went to `U(29)` before the master.
- Density 7: `qa.py` FAIL. Scene 7 (46.1–63.0) is waived by decision 11. Thirteen gaps over 1.5 s are left in the extension, longest 142.13–144.97 and 132.17–134.60,
  all under moving pictures, plus quiet beats 214, 225, 227, 260, 262. Reported, not looped.
- Sound 7.5: nobody has listened.
No third round: neither score under 8 is a fault the eye can see.

**Master** (`CONTENT/11. Pandu Sjahrir Supra Sekuritas (31 Okt 26)/output/pandu-supra-80-final-9x16.mp4`; 1080×1920, H.264 yuv420p, 60 fps, 163.200 s, 59.1 MB, 2 workers
855 s): 192 events, 5 moves in the first 3 s, 5 quiet beats, max gap 3.61 s (scene 7); -14.1 LUFS, -1.8 dBFS, lag 3 frames; check pass, `check_logo` 0 differing pixels,
Market Intel `f3a6eaf`; render sha256 `d507fc58c884bbbd`. Poster 2.0 s. Phone stills at 120.3, 134.4, 153.75 and 154.05 hold the round's fixes. Under 8: density 7
(`qa.py` FAIL), sound sync 7.5. l15 and l18 are still unheard.

### tmpo-85 (3 Nov 2026, build)

Board approved 3 Nov 2026 ("OK, lanjut build"); the 22 Zephlyn takes are locked. Built on the board's stills: matte cuts (iris, diagonal, whips) at
the scene edges, pushes and drifts on the holds, punches on the stressed words, the Fortune page lands with a shake, the Mayapada neon staggers on.

**Round 1** — hook 6 · story 8 · readability 8 · motion 7 · density 5 · composition 8 · brand 8 · sound 7.
Determinism 10/10; layout 0 after `PUSH2` (2d and scene 12 push to `{540, -1620, 0.425}`, which holds the roof sign at screen y 230: the sign drops its
letters above y 200, a fault the lint cannot see); 143 events, 11.9 per 10 s; -14 LUFS, TP -2 dBFS, lag -2 frames, event->onset p90 99.9 ms.
- Hook 6: 2 moves in the first 3 s (0.93 BARU, 1.20 thunk). 0–0.9 s is a still card under a slow push; the 1.40 pull-back is a smooth 0.9 s glide.
- Density 5: 18 gaps over 1.5 s; longest 57.12–60.85 (the pull up the tower and the ride, both smooth), 48.50–51.90 (Jaya Raya's hold),
  107.48–111.60 (the four pins, then a 1.4 s glide to the stand); 14 quiet beats.
- Motion 7: holds freeze on beats: 3.88–6.30 (the header), 50.5–51.2 (Jaya Raya), 66.8–67.6 (the penthouse). The whip at 8.70 and the diagonal at
  12.10 read clean on their strips.
- Sound 7: the worst event->onset are swells with slow attacks (drop 70.67, out 10.67, rise 112.69, pull 96.67); nobody has listened.
Fixes: (1) hook: his plate lights alone at 0.06, a snap back at 1.40, the lobby lamp clicks on at 2.0, a snap in to the header at 2.80, then a slow
push on it to 6.30; a whoosh on each snap, a tick on the lamp. (2) dead stretches: Jaya Raya pushes in from 46.90 with a punch on "persen" and a snap
to the yayasan at 51.66; a snap up the tower on "berdiri" (57.53) and a drift (`DRIFT7`, the sign kept at y 230) into scene 8, where the lift and the
camera arrive together on "puncak" (59.79) with a punch; the four pins knock on "mencatat" (108.58) and the camera crashes in to the stand on
"bukan" (110.12), then drifts to the CTA. (3) frozen holds: the header push, Jaya Raya's push, an 8 % push in the penthouse kept under the tablet.

**Round 2** — hook 8 · story 8 · readability 8 · motion 8 · density 7 · composition 8 · brand 8 · sound 7.5.
163 events, 13.5 per 10 s; 5 moves in the first 3 s (0.07 the plate, 1.20, 1.42 the snap back, 2.00 the lamp, 2.83 the snap in); max gap 2.64 s
(was 3.73); -14.1 LUFS, TP -1.9 dBFS.
- Density 7 (qa FAIL): 15 gaps over 1.5 s, all under a moving picture or in scene 9's designed breath: 22.35–24.03, 28.50–30.70, 34.47–36.53,
  42.70–44.30, 45.33–47.05, 54.68–56.82, 57.55–59.53, 70.68–72.92, 77.48–80.12, 88.78–90.40, 91.53–93.23, 93.23–94.75, 97.67–99.80,
  100.32–102.03, 108.58–110.22. Quiet beats 27 (18.0 the tablet), 45 (30.0 the door), 101 (67.33 the penthouse push, 8 % in 3.7 s, under qa's
  threshold), 115/118/119 (scene 9), 139/140 (the street push), 162 (108.0), 180 (the end card). Jaya Raya's push (46.90–51.66) steps its labels a
  pixel at a time, so qa counts an event every 0.13 s in 49.18–51.38: it inflates the count, not the picture.
- Lag: -10 frames after round 2's snap whooshes; with them swapped for the film's own `cutAir` (onset 40 ms before the frame), -12. Not a sync fault:
  the cross-correlation is flat (|xc| <= 0.03 at every lag in ±40 frames, global argmax -37), the only 30 s window with a peak (30–60 s, 0.079)
  gives -2, and the 37 hard cuts sit a median 0 frames from their nearest onset. The VO's onsets swamp the envelope in a 120 s narrated film.
  The cuts at 18.67 and 54.67 carry their cue 0.2 s after by design (the lift's ding, the stone's thunk).
No third round: neither score under 8 is a fault the eye can see (density is a qa number under moving pictures; sound is unheard).

**Master** (`CONTENT/13. Di Balik Saham TMPO (3 Nov 26)/output/tmpo-85-final-9x16.mp4`; 1080×1920, H.264 High yuv420p, 60 fps, AAC 48 kHz stereo, 120.667 s,
32.8 MB, 2 workers 416 s, 583 s in all): 158 events, 13.1 per 10 s, 5 moves in the first 3 s, 8 quiet beats (27, 32, 45, 115, 118, 119, 162, 180), max gap
3.03 s (96.77–99.80: the smooth pull-back to the whole tower, 97.07–98.27, then the 6 % push until the first group lights; the preview's event at 97.67
did not register at full size); -14 LUFS, -1.9 dBFS, lag -12 frames (noise, see round 2); check pass, `check_logo` 0 differing pixels, Market Intel
`b869eda` (origin/main unmoved, no recapture); render sha256 (frame digests) `4423ec64b90b86f5`, file sha256 `89abd127990815dc`. Poster 1.38 s (his plate
lit, BARU, "tercatat" in lime). Exit 1 is the density FAIL only. Under 8: density 7 (`qa.py` FAIL), sound sync 7.5. Nobody has listened to the mix.

## delisting-18-80 (build, 4 Nov 2026)

**Round 1** — hook 7 · story 8 · readability 7 · motion 7 · density 6 · composition 6 · brand 8 · sound 7.
120 events, 17.5 per 10 s; 7 moves in the first 3 s; max gap 1.82 s (30.90–32.72, the plaque filling); quiet beats 71, 87, 101, 102 (the last two the end rest);
-14 LUFS, TP -1.9 dBFS, lag -12 frames (edge of the search range: Eleven v4's alignment leads the audio by about 170 ms on l01 and l07); 38 hard cuts. Check, determinism
10/10 and layout lint clean. Fixed the three worst:
- Density at the Turn: the plaque's first line now fills word by word like the second, the plaque punches on each word, the room, the camera and a wave up the tallest stack
  go on the score's kick (31,33 s + 1,33 n) instead of a sine; ticks on Agung and Muda.
- Composition: 10b started small at the head of an empty frame: the name now fills the frame at y 800 and rises to the head of the graph when the links come. 1b crowded his
  head: 1,02 % and the date stand above the crate and follow it. The plaque's chains crossed "MABA" on the sign: they now hang from the sign's lower edge.
- Readability: disclaimer 28 → 32 px, lighter grey. The split-flap's seam read as a strike through TELE and MABA at ×5: the flap runs 0,55 s, then the plain sign snaps in.
Also beat 87 (58,0): the arm comes up on the comma, 0,25 s before the beam; the push starts with it. The 24,00 % punch at 26,67 s wrapped nothing: it now moves the figure.

**Round 2** — hook 8 · story 8 · readability 8 · motion 8 · density 8 · composition 8 · brand 8 · sound 7.5.
126 events, 18.3 per 10 s; 7 moves in the first 3 s; max gap 1.78 s; quiet beats 101, 102 (the end rest, by design); -14.1 LUFS, TP -1.9 dBFS; 43 hard cuts; layout lint 0.
- Density (qa FAIL, by number only): two gaps over 1.5 s, both under a moving picture: 43.55–45.33 (the dashes crawling down to where they stop short) and 47.88–49.50 (links drawing
  out from the name, thin lines qa does not count).
- Lag -12 frames, unchanged: Eleven v4's alignment leads the audio by 170–190 ms on l01 and l07, so the picture sits slightly ahead of the voice; `hit-open@0.00`, `door-up@0.07` and `rise@36.20`
  are slow or first-frame onsets. Nobody has listened to the mix.
No third round: nothing the eye can see scores under 8; sound is unheard, density is a qa number.

**Master** (`CONTENT/14. Delisting 18 Saham (4 Nov 26)/output/delisting-18-80-final-9x16.mp4`; 1080×1920, H.264 High yuv420p, 60 fps, AAC 48 kHz stereo, 68.667 s, 25.4 MB, 1 worker 736 s, 918 s in all):
123 events, 6 moves in the first 3 s, 3 quiet beats, max gap 1.62 s; -14.1 LUFS, -1.9 dBFS, lag -2 frames; check pass; Market Intel `b869eda` (origin/main unmoved); render sha256 (frame digests)
`264e141e92abb6c3`, file sha256 `3d335e4f131ace2f`. Poster 35.72 s (the plaque, 16,62 %, 30 OKT 2026 over red). The first master stopped at `check_logo` (3.6 % of the box differed): the end card's
slow drift still scaled the lockup 1.6 % on the last frame. The drift now settles to exactly 1 (0.984 → 1); `check_logo` 0 differing pixels. `round.mjs` does not run `check_logo`, so only the master
caught it. Under 8: sound 7.5 (nobody has listened to the mix). Density stays a `qa.py` FAIL on the number; by eye it scored 8.

## delisting-18-80, owner revision of the 45–50 s transition (4 Nov 2026)

Owner: the way into Market Intel at 45–50 s did not connect ("belum oke... lebih nyambung, ada efek transisi, go all out"; "fokus memperbaiki detik 45-50"). A first answer put the app on a phone in the viewer's hand; the owner called it "a little bit strange" and asked for "a desktop view, using a laptop to open the market intel. Don't use a phone".

**What changed, 45,33–47,80 and 49,36–49,82 only** (VO untouched, `vo-lines.json` not touched, no credits spent): one move with no cut. Pull out of MABA past the viewer's shoulder; a laptop shut on a table in the foreground; "Buka" swings the lid (his hand lifts it by the edge, the lid's back turns edge-on, then its face); the desktop wakes; the light from the webcam dot falls on the name hung on MABA's kiosk; on "itu" the plaque flies down the light into the query box. First push: the whole desktop across the frame, the query typed. Second push, on "Intel": through the desktop, rail and panel passing off the frame, the middle column lands exactly on the frame, the result row opens into the canvas and the name flies to the head of the graph. "lima": the same move backwards, the graph back on the laptop, the dashes running from its lid to the five.

- Composition: the laptop stands where the third tier's four dark kiosks are, so MABA, PLAS, UNIT, SUGI and LCGP all stay in sight at "lima". The viewer's head sits below LCGP's floor.
- The desktop canvas is 3120×1920, same height as the frame; the kit is its middle 1080 column, so the seam at full push is pixel exact.
- `lib/mi-kit.js` gained `miDesk` (browser top, rail, header band, empty Detail Node panel, page rows behind the palette). Rail and panel strings are the app's own at `b869eda` (`site/desk-rail.tsx`, `lib/shared/content/site.ts`); the rows and the address bar are shapes with no text or figures.
- Sound: lid lift, swing and stop in place of the phone tap; two pushes in place of one; the `through` thump on the 47,33 beat.

**Round on the revision**: phone version 6 on connection (the owner's word: strange). Laptop, round 1, fixed: the hand as a large ball at the desktop push (it now rests where the push carries it off the frame), the beam's hard wide end at the lid (it now starts narrow from a webcam dot), green light on the table's front under the captions (clipped to the top), the rail's symbol over its text. Round 2 confirmed them on stills and on frames from the MP4. Scores: hook 8, story 9, readability 8, motion 9, density 8, brand 9, sound 7.5 (nobody has listened to the mix).

**Master** (`CONTENT/14. Delisting 18 Saham (4 Nov 26)/output/delisting-18-80-final-9x16.mp4`; 1080×1920, H.264 yuv420p, 60 fps, AAC, 68.667 s, 25.1 MB, 1 worker 677 s, 862 s in all): check pass, `check_logo` 0 differing pixels; 123 events, 6 moves in the first 3 s, 3 quiet beats, max gap 1.79 s (density stays a `qa.py` FAIL on the number); -14.1 LUFS, -1.8 dBFS, lag -2 frames; Market Intel `b869eda` (origin/main unmoved); render sha256 (frame digests) `08dae82ba375c7ba`, file sha256 `bba6caced6b93cb0`. Poster 35.72 s unchanged. Nothing committed.

## anda-ipo-80 (Siapa di Balik IPO ANDA)

**Round 1** (2 workers; 150 events, first 3 s 6 moves, max gap 2.61 s, -14 LUFS, lag 0): hook 8, story 8, phone 7, motion 7, density 6, brand 8, sound 7 (numbers only, nobody can listen tonight). Fixed: gaps in the last third (plates count on the words at 68.7–69.1 and 72.1–72.6, push at 73.3, beats at 78.94, 80.46, 82.13, 88.05, 90.27, the name typed into the search box at 86.6); hook shots sat in the top half (6b, 8c, 9, 10a, 11b, 12, 13a moved to the middle, kamu added under the signs in 8c); network screens too small (tighter crops), Ivan's panel cut at the left, the ring crossed 3 PERUSAHAAN.

**Round 2** (2 workers; 161 events, first 3 s 6 moves, max gap 2 s, gaps over 1.5 s: 38.67–40.32 the held beat, 82.13–84.13 and 86.15–88.05 the question and the typing; -14 LUFS, lag 0): hook 8, story 8, phone 8, motion 8, density 8, brand 8, sound 7 (mix numbers pass, not heard). One new fault, the company's network screen cut its node at the bottom, and the avatar on Ivan's panel: both crops fixed and checked on stills. No third round: no score under 8 the eye can see. `qa.py` still says density FAIL for those three gaps, left on purpose.

**Master** (`CONTENT/15. Siapa di Balik IPO ANDA (5 Nov 26)/output/anda-ipo-80-final-9x16.mp4`; 1080×1920, H.264 yuv420p, 60 fps, AAC, 95.333 s, 34.3 MB, 2 workers 590 s, 780 s in all): check pass, `check_logo` 0 differing pixels; 158 events, 7 moves in the first 3 s, 2 quiet beats (141, 142, the lockup hold), max gap 2 s (density stays a `qa.py` FAIL on the number; 38.67–40.32, 82.13–84.13 and 86.15–88.05 left on purpose); -14 LUFS, -2 dBFS, lag -2 frames; Market Intel `712682c` (origin/main unmoved); render sha256 (frame digests) `c42d709644a1f10f`, file sha256 `ccfdae02e0ec1f5c`. Poster 5.75 s. Still under 8: sound 7, the mix passes on numbers and nobody has heard it. Board gate waived in the owner's words (`brief/decisions.md` row 18). `references/grok-2026-11-05/` (95 MB) stays local, not committed.

## dooh-mto-75 (Saham DOOH, MTO Nihil)

Moved here from another box by the zip `CONTENT/17. Saham-DOOH-MTO-Nihil-6Nov26.zip` (rounds 1 to 3 ran there, their log stayed there; state in `brief/STATUS-build.md`, `brief/AUDIT-2026-11-06.md`). On arrival `vo.mjs --check` failed l02, l03, l04: that box's normalizer equivalences were not in the zip. Ported to `tools/normalize-indonesian.mjs` with two tests (Rp figures as STT writes them; SII, DOOH, BBS as spelled); takes untouched, `beats.json` byte-identical.

**Owner's change mid-render, 6 Nov 2026**: Market Intel on a laptop, not a phone; the picture is free, it need not match the app. The running master was stopped. 7b, 7c, 8a redrawn with `laptop` (`lib/world.js`), two kit additions (`miCursor`, `miEvidence`), VO and clock untouched, no credits spent.
- 7b, Kamu's view: laptop on a kerb cabinet, the street's three cables run into its back and on across the screen as the holders. Click on SII at 59,1.
- 7c: push into the screen (z 1,5), panel `Detail bukti` (the app's word, `holder-ledger.tsx`), source and date on their words, marked on a document.
- 8a: laptop goes back and dim, the holders stand either side of the broker's phone. The phone keeps only the one price.
- Board: first pass flagged 4 safe, 4 overlap (crop of `Market Intel` in 7c, text under the panel); fixed, sleeves dimmed below the band, then layout 0 0 0 0.
- Eye on 16 frames of the master, 55,9–65,65: lid, wake, stagger, click, push, panel, phone all read; no fault to fix. Motion 7, readability 7, brand 8, connection to the world 8 on this scene only.
- Weak: 7b's laptop stands still 56,28–58,98 while only small things move on its screen; `qa.py` sees it as a gap of 2,7 s. Next time a slow push through 7b into 7c's zoom. Not re-rendered: round cap, and a qa number alone is no reason.

**Master** (`CONTENT/17. Saham DOOH MTO Nihil (6 Nov 26)/output/dooh-mto-75-final-9x16.mp4`; 1080×1920, H.264 yuv420p, 60 fps, AAC, 81 s, 51,7 MB, 2 workers 1086 s, 1406 s in all, no stall on this box): check pass, `check_logo` 0 differ, density FAIL on number (151 events, first 3 s 7 moves, max gap 2,7 s, gaps 40,52–43,73 planned turn silence, 44,78–46,40, 51,50–53,03, 56,28–58,98), -14 LUFS, TP -1,9 dBFS, lag -3 fr. Nobody has listened to the mix. Other scenes unchanged from round 3 and not re-scored here.

## byan-82 (Jejak Amran Sulaiman di BYAN)

**Round 1** (2 workers; 99 events, first 3 s 3 moves, max gap 2.57 s, 10 gaps over 1.5 s, -14 LUFS, lag -6 fr): hook 7, story 8, phone 7, motion 7, density 5, composition 7, brand 9, sound 7 (numbers only, nobody can listen tonight).
- Rails read against the sheet: chalk would still run across the quay on the two wide shots 7a (61,0, whose own note says no line) and 8b (68,25), so it could join the two holders' berths. Fixed first: chalk off on both. Nothing else joins them; no price, no Jhonlin Baratama UBOs, no addresses; 4g footnote reads at phone size.
- Score causes. Density 5: soft springs spread every arrival over 20 frames, so holds read as drift (3.75-5.5, 19-21.47, 25.25-27, 52.5-57.5). Hook 7: 3 moves in 3 s. Phone 7: 6d (57,25) Amran's name is a grey bar on the very relation the line is about; 5b (40,5) and 1b a big plate with two bars; 2c (10,75) "30OKT" reads as "300KT". Motion 7: 4f (34,25) the second number is still rolling when the cut takes it; 4b (25,0) the figure rolls until the coal starts. Composition 7: 7b (63,0) grey panels in three corners round the empty bollard. Story 8: 5d (43,75) "+6 perusahaan lain" lasts 0,07 s and the name 0,24 s. Sound 7: lag -6 fr, not heard.
- Fixed: (1) chalk off on 7a and 8b; (2) readability: 6d reframed so both names read, 1b and 5b lift the plate out of frame, 7b clears the cards and dims the sign, flaps get a gap between day and month, 5d holds to 44,7 s (5e shorter) so name and count are read, 4f and 4b land before the cut; (3) density: lights step on words instead of ramping (1c "nama", 3d "Group", 6d each card), barge jolts under the digits (3b, 4c), a key tap answers plate and row (4e, 4f), paper arrives on a faster spring, "?" pops in 1a.
- The render leans most on: a hung card or tile popping on a soft spring, and a slow camera drift with a lantern pool. Round 2's fixes reach for something else.

**Round 2** (2 workers; 117 events, first 3 s 2 moves, max gap 2.07 s, 5 gaps over 1.5 s, -14.1 LUFS, lag -10 fr): hook 7, story 8, phone 8, motion 7, density 6, composition 7, brand 9, sound 7.
- Round 1 fixes verified on the sheets: 7a and 8b carry no chalk, 6d reads both names with the clips apart, 7b's bollard stands alone, the 4g footnote reads at phone size. Rails read against the sheets: no line or rope between the holders or filings on 4e-4g, no price, no Jhonlin Baratama UBOs, no addresses.
- Score causes. Hook 7: the plate sits still from 0,9 to 2,25. Density 6: `qa.py` fails it (gaps 0,63-2,25, 12,95-14,5, 25,25-27, 44,88-46,5, 46,5-48,57), and `tools/master.mjs` exits 1 on that failure. Motion 7: the coal sinks in one slide at 25,5-26,9. Composition 7: a grey bar on the hull under the caption at 44,9-46,5, and one source slip between the two plates on 7a (61,0). Sound 7: lag -10 fr, soft moves peak after their sounds.
- Fixed: (1) the 7a slip is now one per plate, so nothing is shared between them; (2) hook: the lamp catches, the beam drops to the empty frame on "Resources", stepped pushes on "Bayan", "Resources" and "dua"; (3) stepped pushes on 3a, 4c, 5e and 6a, the coal falls twice, no figure on the 5e hull; small sounds added on the new moves. These reach for a stepped push and a light move, not the hung card or the drift. Not yet verified by a render when logged: the master's numbers are the check.

**Master** (9x16, 72,5 s; 123 events, first 3 s 6 moves, max gap 1.42 s, 0 quiet beats, density PASS, -14 LUFS, TP -1.9 dBFS, lag -10 fr, logo ok, sha256 eb580bb777d4e2a2): hook 8, story 8, phone 8, motion 7, density 8, composition 8, brand 9, sound 7.
- First master failed density (max gap 2,25 s: 16,75-19, 28,12-29,73, 37,72-39,57, 52,5-54,17). Stepped pushes on 3c, 4e, 5a and 6d closed them, plus a hand tap on 4e. No separate round 3: the second master was the verifying render.
- Read on one phone sheet of the changed shots, not on a full review sheet: 7a has one slip per plate and no line, 4g's footnote reads, 5e's hull has no bar. Rails hold on those frames. Scores come from stills and numbers; nobody watched the master in motion or listened to it, so motion and sound are the least certain.
- Sound 7: lag -10 fr, soft moves still peak after their sounds. Motion 7: not seen in motion. Next time: time soft arrivals to land on their sound, and plan stepped pushes in the shot list so holds are not patched in rounds.
- For the owner: #35 (Market Intel theme on screens, amber world) is our scope reading; 72,5 s against the 80-85 s target (#36), about 25 more words restore 80 s; legal review before publication, #29 first.
