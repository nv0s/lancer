# Lancer Campaign

This repo is a running LANCER (Massif Press mecha TTRPG) tabletop campaign. Claude runs as GM for one player.

## Player & Squad
- **Lee "Envy" Cadar** (the player character) — full sheet in `characters/lee-cadar.md`.
- **Squad** (GM-run allies) — `characters/squad.md` is an index into `voss-amara.md` (Doc), `kessa-draye.md` (Bull), `jonas-achebe.md` (Riot).

## Reference material (`reference/`)
- `reference/talents-reference.md`, `reference/triggers-reference.md` — full core-rulebook text, used when leveling up or picking new options.
- `reference/gm-reference.md` — core rules quick-reference (turn order, actions, tags) for mid-session lookup.
- `reference/gm-reminders.md` — ruling mistakes that got corrected more than once; check before running a scene if something feels like a repeat.
- `reference/combat-display.md` — how combat is presented to the player (battle-state block, dice-roll detail, turn-order style). Follow this for every fight.
- `reference/loot-display.md` — how loot/salvage gets listed and allocated after a fight or search.
- `reference/interrogation-resolution.md` — the two-roll (gate, then benefit) system for interrogating captured NPCs.
- `reference/downtime-resolution.md` — the structured downtime-action menu and outcome tiers.
- `reference/reward-negotiation.md` — how negotiating a job's payout works, including when it's a free-form ask vs. an actual roll.
- `reference/leveling-presentation.md` — when level-ups get offered and how much detail to front-load vs. let the player ask for.
- `reference/bestiary.md` — enemy stat blocks encountered or prepped so far.
- `reference/Lancer - Free Version.pdf` — the core rulebook itself.

## Story (`story/`)
- `story/campaign-log.md` — top-level index: setting primer, house rules, and a list of story arcs with status and links. Not the source of narrative detail itself — that lives under `story/arcs/`.
- `story/open-threads.md` — campaign-wide, not per-arc: every unresolved plot thread, with a link back to the job that raised it. A thread raised in one arc often gets pulled on or resolved in a later one, so it isn't duplicated into each arc file.
- `story/arcs/NN-arc-slug/arc.md` — one story arc's hook, summary, and job list. An arc is the overarching story; it's marked **Active** or **Complete**.
- `story/arcs/NN-arc-slug/jobs/NN-job-slug.md` — one job (a mission/contract) within that arc, usually made up of several distinct fights/scenes as sections within the same file. Usually many jobs make up an arc, but a single long job can be the whole arc — don't split individual fights within one job into separate job files.

## Working conventions
- **Resuming:** find the most recent **Active** arc in `story/campaign-log.md`, read its `arc.md` (summary), its latest job file, `story/open-threads.md`, and `characters/lee-cadar.md`, before picking play back up — don't ask the player to re-summarize what's already recorded here.
- **New arc:** when the story's overarching focus shifts (a new contract, a new antagonist, an open thread spinning up the next hook), create a new `story/arcs/NN-arc-slug/` folder with an `arc.md` and a `jobs/` subfolder, and add it to the list in `story/campaign-log.md`.
- **New job:** each mission/contract within the current arc gets its own file under that arc's `jobs/` folder, added to the job list in the arc's `arc.md`. Multiple fights within the same job are sections in that one file, not separate job files.
- **Open threads:** add new ones to `story/open-threads.md` as they come up, with a link back to the job that raised them. When one resolves, move it from Active to Resolved with a link to where that happened — don't just delete it.
- **Closing an arc:** update its `arc.md` status to Complete.
- **Combat:** check `reference/gm-reminders.md` first — it exists specifically to stop the same rulings from being gotten wrong twice. Present it per `reference/combat-display.md`.
- **Character changes** (level-ups, gear, injuries): edit the relevant character file directly, don't just narrate it and leave the sheet stale.
- **Commit and push after updates** — this repo, including git history, is the durable record of the campaign.
- Campaign state belongs in these files, not in Claude's cross-session memory — memory is only for things like "where does this repo live," not campaign content that already lives here.
