# motion-reel

Claude Code skill for making motion videos rendered from code (canvas + `window.seek(t)`, Playwright, ffmpeg, synthesized sound).

## Install

Copy `.claude/skills/motion-reel/` into your project's `.claude/skills/` (or `~/.claude/skills/` for all projects).

## Contents

- `.claude/skills/motion-reel/` — the skill: `SKILL.md`, `story.md`, `build.md`, `evals/`
- `CLAUDE.md` — studio rules the skill assumes (render contract, look, sound, voice-over)
- `docs/` — briefs, motion vocabulary, review log and retros the skill links to

## Not included

The studio's `tools/`, `lib/`, `assets/` and film-specific shot lists live in a private repo. The skill references them (`node tools/*.mjs`, `lib/fx.js`, ...). Without them, use it as a workflow and story guide, or rebuild the tooling to the render contract in `CLAUDE.md`. Voice-over needs your own `ELEVENLABS_API_KEY`.
