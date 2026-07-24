# Combat Display Rules

How combat gets presented to the player. Established 2026-07-22.

## Battle State Block
At the top of each round (and again right after any change — damage, status, position), show a compact state block alongside the prose, not instead of it:

| Combatant | HP | Status | Notes |
|---|---|---|---|
| Lee / Ungoliant | 13/13 | — | |
| Bull / Drake | 13/13 | — | |
| Raider Captain | 12/12 | — | |

Include HP/Structure, active statuses (HIDDEN, IMMOBILIZED, etc.), and anything positional that matters (engaged, in cover, prone). Drop rows once a combatant is destroyed/removed rather than leaving dead entries cluttering the table.

## Dice Rolls
Show full breakdown on every roll — every die involved (base d20, each Accuracy/Difficulty d6, damage dice) and every bonus contributing to the total (Grit, talent bonuses, ACCURATE tag, etc.) — not just the final number.

## Turn Order
No explicit round/turn tracker called out in the text. Keep following the actual turn-order rules in [`gm-reference.md`](gm-reference.md) (player-chosen order, strict hostile/ally alternation, one action per character per round) — just don't narrate the bookkeeping ("Round 2, Bull has not yet acted") unless something about it is actually in question.

## Battle Map (visual layer)
For fights where positioning is doing real work — multi-room layouts, elevation, hazards, chokepoints, multiple frame sizes navigating the same space — publish or update the interactive battle map (`tools/combat-map/battle-map.html`, see its README for the authoring workflow) alongside the text and state block, not instead of them. Redeploy it via the Artifact tool whenever positions or terrain change enough to matter, not on every single micro-move. Skip it for simple, spatially-trivial skirmishes where the state block already covers everything relevant — it's an added layer for fights where "where everyone is standing" is actually part of the tactics, not a replacement for the default text presentation.
