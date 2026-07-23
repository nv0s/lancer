---
description: Sync against the repo and recap where the LANCER campaign left off before playing
---

Before doing anything else this session, run the resume checklist from `CLAUDE.md`'s "Resuming" convention — do this even if it's already been done earlier in this conversation, since the user is explicitly asking for a fresh sync:

1. Run `git pull` in the repo root, then `git log --oneline -10` and `git status`. If `git pull` brings down new commits, or `git log` shows commits you don't already have full context on, that's a sign any carried-over conversation summary is stale — trust the repo over the summary.
2. Read `story/campaign-log.md` to find the most recent **Active** arc (if more than one shows Active, flag that as a possible stale status rather than guessing which is current).
3. Read that arc's `arc.md` and its latest job file under `jobs/`.
4. Read `story/open-threads.md` in full.
5. Read `characters/lee-cadar.md` in full (and `characters/squad.md` plus any squad member files if their gear/state seems relevant to what's next).

Then report back a concise "where we left off" recap to the player:
- Current arc and job, one line each on status.
- Anything in progress mid-scene (a fight, a negotiation, a downtime action) that was left unresolved.
- Any open threads that look ripe to pull on next.
- Anything that looks inconsistent or stale (e.g. a job file marked Active that reads as narratively finished) — flag it, don't silently fix it.

Keep the recap tight — a few bullet points, not a re-narration of the whole session. End by asking what the player wants to do next, unless the mid-scene state makes the next step obvious (e.g. resuming a fight already in progress).
