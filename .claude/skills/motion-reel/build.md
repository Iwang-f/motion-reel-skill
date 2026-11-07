# Motion reel: build

The second session of a film: the owner approved the board in pre-production, and this session animates,
scores, critiques and renders it. `<film>` is the slug after `build`.

## Where the film lives
A film in `projects.json` lives in its CONTENT project folder: shot list `<project>/brief/shotlist.md`, code in
`<project>/src/` (`film.js`, `timeline.js`, `vo-lines.json`, `beats.json`, `sfx-<film>.mjs`), takes in
`<project>/assets/vo/`, renders and sheets in `<project>/output/` (`tools/paths.mjs`). Older films keep
`docs/<film>-shotlist.md`, `film/<film>/`, `assets/<film>/` and `out/`. Below, `<shotlist>`, `<src>` and `<output>`
mean whichever applies.

## Read
Exactly these, once each, and nothing else:
- `<shotlist>`, its `## Build brief` (and the shots it names). It is the contract: shots, times, approved decisions.
- `<src>/film.js` (the board stage) and `<src>/timeline.js` (the scene list) if the film has VO.
- `docs/motion-vocab.md`.

Tools are run, not read: `node tools/<tool>.mjs --help` (and `tools/qa.py --help`) prints the usage. A library
(`lib/fx.js`, `lib/motion.js`, `lib/vo-clock.js`, `lib/synth.mjs`, `lib/brand.js`, `lib/proof.js`, `lib/mascot/`) is looked up one
function at a time (Grep, or Read with offset/limit), never read whole. Other films' modules and style guides stay
closed: the house look is `CLAUDE.md` "Look" and `docs/motion-vocab.md`.
If the build brief is missing or a decision in it is still open, ask the owner before building.

## Working rules (every call re-reads the whole context: keep it small)
- Change files with Edit: small exact replacements. Never rewrite a whole file to change part of it, and do not
  re-read a file after editing it.
- Long commands (a master render, a hash-only run) run with `run_in_background`; wait for the completion notice.
  No `sleep`, no `Monitor` or polling loops, no reading the output file while it runs.
- Mechanical problems come from numbers, not from looking: `tools/round.mjs` prints the seek sweep, determinism,
  font px and layout lints and `qa.py` density. Images are for looks only: one review sheet per round, over 18 shots its pages (the `review`
  line), a phone page or a strip only where a number or that sheet points. Every image stays in context to the end.
- No ad-hoc analysis scripts. A number the tools do not give is added to the tool (with its `--help`), once.
- Send independent reads and edits of a step in one message: every extra message re-reads the whole context.
- State lives in `<shotlist>` and `docs/review_log.md`: log each round as it ends, so a compaction loses nothing.

## Steps
1. **Build** `<src>/film.js`: `async bootFilm(fmt, lang)` returning `W, H, duration, draw(ctx, t)`, plus
   `beats`, `board`, and `lockup` from `lib/brand.js` when the film ends on the logo. Use `lib/motion.js` springs
   (`track`, `swapAlpha`, `DOT/SOFT/TYPE/SNAP`), `lib/fx.js` effects and `film/layout.js`, so 9:16, 1:1, 16:9 are
   reframed, never cropped. VO films take the clock, word cues and captions from `lib/vo-clock.js` (`timeline.js`
   is only the scene list; captions are `buildCaptions` / `drawCaptions`, model: iata-55, one line and centred unless
   the brief says otherwise: `maxLines: 1`, `align: 'center'`). Seeded noise only. Font sizes are integer px; animate a
   size with a scale transform. Build each scene to its shot list's density on the first pass, its holds alive and its
   beats answered: moves added later are decoration, moves planned with the scene carry the story.
   `node tools/check.mjs --film=<film>` passes before the first critique.
2. **Sound.** `node tools/prepare.mjs --film=<film>` (takes checked, clock into `beats.json`), then
   `node <src>/sfx-<film>.mjs`: the film's cue list on `lib/synth.mjs` (model: iata-55's `src/sfx-iata-55.mjs`),
   score and SFX on the beat grid, VO mixed in, -14 LUFS.
3. **Critique.** Rounds of `node tools/round.mjs --film=<film> [--strips=a:b,…]`, following
   `prompts/critique-pass.txt`: score, fix the 3 worst, next round. **Two rounds by default: one to find, one to verify.** A third
   only when round 2 leaves a score under 8 the eye can see, or a new visible fault; never for a `qa.py` number alone. Then render the master
   and report the remaining gaps (each score under 8 with its timestamp and cause) to the owner. Log each round in
   `docs/review_log.md`.
4. **Master**, one background command: `node tools/master.mjs --film=<film> --format=9x16 --poster=<t>` (then `1x1`, `16x9`
   if requested). It runs the pre-flight first (check, end-card logo, Market Intel moved?) because every fault found after
   a master costs a second master; recent films ran up to six. `STOP` names what to fix. Exit 2 is a stall:
   close what you can and rerun with the `--workers` it prints. Close the session's other heavy work before it starts:
   the machine has 8 GB.
5. **Deliver** `<output>/<film>-final*.mp4`, the contact sheet, the poster, a loop check if it is a loop, and `<output>/<film>-post.md`:
   the title in the oddity form (story.md "Topic"), the cover frame's time, the caption with sources and disclaimer, the pinned
   question that feeds the next film. Add the film's row to `docs/results.md`. Say what you would improve next, and say plainly
   that nobody has listened to it or watched it in motion. Commit source, not the output.

Done when `tools/master.mjs` exits 0 in every requested format (a density miss is printed and reported, and fails nothing), the post
file and the `docs/results.md` row exist, and the owner has the files.
