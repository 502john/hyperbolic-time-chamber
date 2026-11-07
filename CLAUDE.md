# Hyperbolic Time Chamber

A local interview practice app. I walk into a small world, pick a room, practice with Claude, and the world updates from the session report. This is a learning project: I make the design decisions, and I learn the stack by reading and questioning what you build.

## Read first

- `starting_resources/context.md`: the plan of record (decisions, stack, MCP tools and rules, build stages). If a decision changes it, propose the edit.
- `starting_resources/initial_design.html`: the current world and visual direction. Keep this look. It also defines the session report format to stay compatible with.
- `.claude/output-styles/SKILL.md`: how we work together (design checkpoints, predict-first, explain-back). Follow it even if the output style is not switched on.

## Stack

Tauri (Rust) shell, Three.js world, embedded Excalidraw, local Whisper via whisper.cpp, Rust MCP server on localhost while the app runs. Claude Code is the interviewer.

## Current stage

Stage 1: the loop. Tauri shell, current world, embedded Excalidraw, and MCP with `get_next_drill`, `get_board`, and `log_session`. Done when one Design Hall mock goes from start to a logged report and the world updates. Do not start later stages until I say so.

## Rules

- **Private data stays local.** Reports, transcripts, recordings, drill cards, content packs, and my Career Canvas record live in a private data folder outside this repo. Never commit them. Demo and tests use fictional data only.
- **Narrow MCP tools.** No general file-writing tool. Reports are append-only and validated against the schema. A skill cannot be marked demonstrated without an evidence string.
- **No gamification.** No XP, streaks, or points.
- **Never use em dashes**, in code comments, docs, commit messages, or chat.

## Git

- `main` is stable. Never commit or push to it directly.
- `dev` is the integration branch. Branch from it as `feat/<short-name>` or `fix/<short-name>`.
- Commit in small, focused steps with clear messages. 
- Open a PR into `dev`. `dev` merges into `main` only through a PR, when I say a stage is done.
- Ask me before merging anything.

## My journal

I keep a handwritten journal. You never write it for me. At the end of each stage, give me a one-line nudge to write my entry: what we built, the design call I made and why, one concept in my own words, and what confused me. At the start of a session, ask if I have anything from my journal to bring back.
