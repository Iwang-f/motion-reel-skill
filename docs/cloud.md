# Cloud sessions

The repo carries everything a Claude Code cloud session needs to continue a film: `CLAUDE.md`, the `motion-reel` skill in
`.claude/skills/`, the tools, libraries, shared assets, and each film's brief, source and voice takes. Rendered files
(`out/`, `CONTENT/*/output/`) stay on the local machine; regenerate them with the tools.

`tools/cloud-setup.sh` runs at session start through the hook in `.claude/settings.json`. It installs Node dependencies,
Chromium, ffmpeg and uv. It does nothing on a local machine.

## Set once in the cloud environment

- `ELEVENLABS_API_KEY` as an environment variable, only for new voice takes. `tools/vo.mjs` reads the process environment
  when there is no `.env`. Takes already committed need no key.
- Network access that allows `api.elevenlabs.io`, only for new voice takes. The setup script also needs npm, the Playwright
  browser download and the apt mirrors.

## What differs from local

- **Market Intel source.** `tools/mi_sync.mjs`, `mi_dev.mjs`, `capture_mi.mjs` and `master.mjs` default to a clone at
  `D:/AI/Openview/repos/platform-market-intel`, and the session must have access to that private repo. Without it, do
  Market Intel sync and capture locally, commit the result, and continue in the cloud. Do not invent figures.
- **Getting a render out.** `output/` is ignored. To review a preview, commit that one file on the session's branch or
  publish it another way the owner chooses, and pull the final render locally.
- **Moving work back.** The session pushes a branch; merge it into `main` and pull locally.
