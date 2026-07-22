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
- `campaign-log.md` — top-level index: setting primer, house rules, and a list of story arcs with status and links. Not the source of narrative detail itself — that lives under `arcs/`.
- `open-threads.md` — campaign-wide, not per-arc: every unresolved plot thread, with a link back to the job that raised it. A thread raised in one arc often gets pulled on or resolved in a later one, so it isn't duplicated into each arc file.
- `arcs/NN-arc-slug/arc.md` — one story arc's hook, summary, and job list. An arc is the overarching story; it's marked **Active** or **Complete**.
- `arcs/NN-arc-slug/jobs/NN-job-slug.md` — one job (a mission/contract) within that arc, usually made up of several distinct fights/scenes as sections within the same file. Usually many jobs make up an arc, but a single long job can be the whole arc — don't split individual fights within one job into separate job files.

## Working conventions
- **Resuming:** find the most recent **Active** arc in `campaign-log.md`, read its `arc.md` (summary), its latest job file, `open-threads.md`, and `characters/lee-cadar.md`, before picking play back up — don't ask the player to re-summarize what's already recorded here.
- **New arc:** when the story's overarching focus shifts (a new contract, a new antagonist, an open thread spinning up the next hook), create a new `arcs/NN-arc-slug/` folder with an `arc.md` and a `jobs/` subfolder, and add it to the list in `campaign-log.md`.
- **New job:** each mission/contract within the current arc gets its own file under that arc's `jobs/` folder, added to the job list in the arc's `arc.md`. Multiple fights within the same job are sections in that one file, not separate job files.
- **Open threads:** add new ones to `open-threads.md` as they come up, with a link back to the job that raised them. When one resolves, move it from Active to Resolved with a link to where that happened — don't just delete it.
- **Closing an arc:** update its `arc.md` status to Complete.
- **Combat:** check `gm-reminders.md` first — it exists specifically to stop the same rulings from being gotten wrong twice.
- **Character changes** (level-ups, gear, injuries): edit the relevant character file directly, don't just narrate it and leave the sheet stale.
- **Commit and push after updates** — this repo, including git history, is the durable record of the campaign.
- Campaign state belongs in these files, not in Claude's cross-session memory — memory is only for things like "where does this repo live," not campaign content that already lives here.
