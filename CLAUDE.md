# Lancer Campaign

This repo is a running LANCER (Massif Press mecha TTRPG) tabletop campaign. Claude runs as GM for one player.

## Player & Squad
- **Lee "Envy" Cadar** (the player character) — full sheet in `characters/lee-cadar.md`.
- **Squad** (GM-run allies) — `characters/squad.md` is an index into `voss-amara.md` (Doc), `kessa-draye.md` (Bull), `jonas-achebe.md` (Riot).

## Reference material
- `talents-reference.md`, `triggers-reference.md` — full core-rulebook text, used when leveling up or picking new options.
- `gm-reference.md` — core rules quick-reference (turn order, actions, tags) for mid-session lookup.
- `gm-reminders.md` — ruling mistakes that got corrected more than once; check before running a scene if something feels like a repeat.
- `bestiary.md` — enemy stat blocks encountered or prepped so far.
- `campaign-log.md` — source of truth for what's happened: setting primer, house rules, and a session-by-session log ending in "Open Threads."

## Working conventions
- **Resuming:** read the tail of `campaign-log.md` (recent hits + Open Threads) and `characters/lee-cadar.md` before picking play back up — don't ask the player to re-summarize what's already recorded here.
- **Combat:** check `gm-reminders.md` first — it exists specifically to stop the same rulings from being gotten wrong twice.
- **Character changes** (level-ups, gear, injuries): edit the relevant character file directly, don't just narrate it and leave the sheet stale.
- **Commit and push after updates** — this repo, including git history, is the durable record of the campaign.
- Campaign state belongs in these files, not in Claude's cross-session memory — memory is only for things like "where does this repo live," not campaign content that already lives here.
