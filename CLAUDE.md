# Motion studio rules

## Shared instructions
- This file is the single source of project instructions for Claude Code and Codex; `AGENTS.md` links here.
- For Codex motion planning, implementation, or review, first read [docs/codex-motion-review.md](docs/codex-motion-review.md)
  for the article lessons, evidence requirements, and ownership boundaries from the MSCI retrospective.
- Cloud sessions: what works there and what does not is in [docs/cloud.md](docs/cloud.md).

## New video project folders
- Create every new video project under `CONTENT/` at the repo root, with one folder per project.
- Folder format: `<number>. <Title> (<day> <Indonesian month abbreviation> <two-digit year>)`.
  Examples: `1. OpenView Preview (19 Okt 26)` and `2. MSCI (21 Okt 26)`.
- Before creating a folder, inspect the numbered folders in `CONTENT`; use the highest existing number plus one,
  starting at `1` when none exist. Numbering continues across dates and years.
- Use the production date supplied by the user; otherwise use the project creation date in `Asia/Jakarta`.
  Month abbreviations: `Jan Feb Mar Apr Mei Jun Jul Agu Sep Okt Nov Des`. Keep the original folder date for revisions.
- Inside each project, use `brief/` for the brief, script and storyboard; `references/` for project-specific
  references and source records; `src/` for implementation; `assets/` for project-specific media;
  and `output/` for previews and final exports. Create subfolders when they have content.
- Quote paths containing spaces in commands.
- Existing projects retain their current paths until the user requests migration. The `film/<film>`,
  `assets/<film>`, and `out/` paths below describe the existing tooling layout; for new projects, configure
  project-specific paths under their `CONTENT` folder before production.

## Shared assets and references
- Use the existing lowercase `assets/` directory for shared media. New brand assets go under
  `assets/<Brand>/`, grouped into `logos/`, `fonts/`, or `characters/`; unbranded reusable media goes under
  `assets/shared/`, grouped into `audio/` or `textures/`. Create folders as needed.
- Reuse canonical assets rather than copying them into each video. Record their origin and licence or usage
  permission when known; mark unknown permission for verification before publication. Keep supplied licence files.
- Existing `assets/openview-*.svg` and `assets/fonts/` retain their paths. OpenView logo rendering continues
  through `lib/brand.js`; existing project assets remain in place under the migration rule above.
- Store reusable visual references in `REFERENCES/motion/` or `REFERENCES/character/`; references used only
  by one video belong in that project's `references/`. Record source and timestamp ranges for adopted techniques.
- When finding, adding, or using a GitHub reference, read and update [REFERENCES/github.md](REFERENCES/github.md).
  Each entry records its URL, purpose, useful files or techniques, licence status, and local checkout if present.
  Start with a link; clone when inspection or execution needs it. Keep local reference checkouts in ignored `refs/`.
- For a repository used in production, record the exact commit SHA and files used in the video's `references/`.
  Shared animation code stays in `lib/`, production tools in `tools/`. Check callers and paths before any migration;
  verify loading and the affected tooling before treating a migration as complete.

## Render contract
- Every film is a pure function of time: `window.seek(t)` paints frame t.
- No CSS transitions, no setTimeout, no requestAnimationFrame in render mode,
  no state carried between frames. Seeded noise only (mulberry32), never Math.random.
- Render with `node render.mjs`, encode H.264 yuv420p, CRF 16.

## Look
- Banned defaults: centered title on gradient, everything fading in,
  corner labels and frame borders, glow on UI chrome, generic particle bursts.
- Picture first (owner, 2026-10-31): a film is a drawn world of places, people and objects, not type on a background. At most
  6 words a shot besides the caption, on objects, except proof plates and lines the brief requires in full.
  Grammar: `REFERENCES/motion/visual-grammar-2026-10.md`; drawing: `lib/world.js`. The design system stays on product screens.
- One display face, one UI face. One accent color unless the brief says otherwise.
- Length: 40 s at most unless the brief asks for longer (owner, 2026-10-18).
- Showreel density: at least 5 distinct moves in the first 3 s, a cut or a new idea every 1 to 1.5 s, and
  motion on every beat. Moves come from `docs/motion-vocab.md` and `lib/fx.js`. `tools/qa.py` measures it.
  On a film the VO carries, the number is information: report it, and add a move for the story, never for the number (owner, 2026-11-07).
- OpenView logo and symbol only through `lib/brand.js` (`drawLockup`, `drawSymbol`); `npm run check` enforces it.

## Sound
- Score and SFX are synthesized in code unless a track is supplied.
- Place hits on the measured beat grid (beats.json). Loudness -14 LUFS.

## Market Intel source (every OpenView film)
- Source: the latest `origin/main` of github.com/OpenViewHolding/platform-market-intel, never market-intel-webapp
  or an old screenshot. `node tools/mi_sync.mjs` first (fetch, detached worktree at origin/main, deps); the shot
  list cites the commit SHA.
- Default (owner, 2026-10-18): names and figures from that commit, exactly as the app shows them (read them from
  the running app or its own data). The picture is drawn in code with the Market Intel UI kit (`lib/mi-kit.js`:
  the app's tokens, fonts and components), so it animates freely. Add what the film needs to the kit, not to the film.
  On screen it sits on a laptop, never a phone (owner, 2026-11-06). Its picture may depart from the app's exact UI, from its source and our own ideas; names and figures stay exact.
  Theme and colours stay Market Intel's own, with room to play inside them (owner, 2026-11-07).
- The real app on screen only when the brief asks for it. Then run it with the `market-intel-capture` launch config
  (`tools/mi_dev.mjs`: dev entitlement in the process env only, `.env.local` untouched) and capture with
  `node tools/capture_mi.mjs --film=<film>`: English UI, dark theme unless the brief says light, device scale 3;
  it writes `assets/<film>/ui/capture.json` with the SHA. Run `mi_sync` again before the final render; if
  origin/main moved, recapture and re-check every crop. Crop out the dev badge and register/source lines.
  The dev server's test grid on the network map (`#ovbDevGrid`, dashed cyan) stays out of every capture and screen recording (owner, 2026-11-07): `capture_mi.mjs` hides it; a recording made any other way hides it too.

## Voice-over
- ElevenLabs through `node tools/vo.mjs --film=<film>`. Lines in `film/<film>/vo-lines.json`, one take per line,
  cached by hash, stored in `assets/<film>/vo/` and committed (a take costs credits).
- House narrator, English: Hey Its Brad - Clear Narrator for Documentary (`Dslrhjl3ZpzrctukrQSN`, owner's pick
  2026-10-18), `eleven_v4` (reads audio tags), stability 0.55, similarity 0.8, style 0.12, speaker boost, speed 1.12
  (as on `launch`). It is a library voice: the API refuses it on the Free plan (HTTP 402).
  Indonesian: Zephlyn - Calm, Neutral and Measured (`3mAVBNEqop5UbHtD8oxQ`, owner's pick 2026-10-19 on `msci-40`), same
  model and settings as Brad. Spell abbreviations for it: IHSG as `i-ha-es-ge` (Indonesian letters), MSCI as `Em-Es-Si-Ai`
  (English letters), owner's picks from samples. Change the voice only on the owner's word.
- Text for the voice: PT, Tbk and tickers in capitals so they are spelled (`PT ABC TBK`), numbers as words.
  The `caption` field keeps the written form (`PT ABC Tbk, 45%`). Brand: OpenView, one word.
- Audio tags (Eleven v4 only; `multilingual_v2` cannot read them): never typed into `text`. Each line carries
  `emotion`, `delivery`, `vocal` ([[tag, beforeWord]], non-verbal: `exhales`, `inhales`, `sighs`) and `inline`
  ([[tag, beforeWord]], e.g. `emphasized`); the film carries one `character` persona. `tools/vo.mjs` assembles
  `[character, emotion, delivery] … [tag] word …` and stores the alignment without tags.
- Tag rules learned on `launch` (2026-10-18): describe the voice only. No genre or music words ("documentary",
  "optimistic" on an opening line came back as an outro jingle). No tempo words ("slow", "deliberate"); pace is
  the speed setting. No `[short pause]` (it gave 2 s gaps and an invented word); use the text's own punctuation.
  Tags add expressive pauses: budget about 13 % more speech than untagged. v4 sometimes repeats a short line:
  retake until the check passes.
- Every take passes `node tools/vo.mjs --film=<film> --check` (speech-to-text must match the line) before it is placed.
- The VO sets the clock: scenes are timed from the takes' alignment, never the reverse. If the brief's duration
  cannot hold the lines at the house pace, say so with the numbers and offer cuts. The pace stays 1.12, never faster (owner, 2026-11-07).
- Word budget: (seconds − 2.5) × words per film-second, English 2.0 (Brad v4: 133 words made 66 s), Indonesian
  1.7 (six films of Nov 2026 ran 1.65–1.75; owner, 2026-11-07). A 40 s film holds 75 English or 63 Indonesian words. `tools/vo.mjs` refuses
  a script over budget before spending credits; `maxSeconds` in `vo-lines.json` raises the cap only when the brief does.
- Captions word by word from the alignment, always on (feeds autoplay muted).
- Quote the credits before generating (AI Spend Policy). Publishing needs a plan with a commercial licence.

## Preview before build
- Write the shot list and draw one still per shot in the film's own engine (`board` in the film module); render
  `node tools/board.mjs --film=<film>`. Read only its `-view.jpg` overview (over 18 shots, the `pages` it prints); fix mechanical faults from the layout lint
  and mid-move warnings it prints.
- Show the shot list and the board together and wait for one OK (owner, 2026-10-23). No motion or sound before it;
  then animate, synthesize, critique and render.
- The build runs in a fresh session: `/motion-reel build <film>` (skill `motion-reel`, `build.md`).

## Looking at images
- `tools/board.mjs` and `tools/contact.mjs` print a `-view.jpg` beside every sheet (1280 px long side). Open the
  view; open full resolution only as a `--crop` or `--stills` of one detail. Every image stays in context for the
  rest of the session.

## Secrets
- API keys live in `.env` only (template: `.env.example`). The ElevenLabs key is `ELEVENLABS_API_KEY` in `.env`.
- Read it in Node with `process.loadEnvFile('.env')` then `process.env.ELEVENLABS_API_KEY`. Never inline a real key in code, a prompt, a doc, or a screenshot; use a placeholder.
- Never print, log, or commit `.env`. If a key is missing, say which variable and stop.

## Loop before you show me anything
1. Make the round's evidence with `node tools/round.mjs --film=<film>` (checks, preview, density, sheets) and
   LOOK at its review sheet. Mechanical faults come from its numbers, not from the eye.
2. Score it 1-10 on: hook in the first 3 s, story (the spine in the skill's `story.md`), readability at phone size,
   motion quality, density, brand accuracy, sound sync.
3. Fix the 3 worst problems, then one round to verify: two rounds by default (owner, 2026-10-31). A third only when round 2
   leaves a score under 8 the eye can see, or a new visible fault; never for a `qa.py` number alone. After it, render and
   report the remaining gaps instead of looping.
4. Only then do the full render.
