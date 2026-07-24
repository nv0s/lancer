# Lancer Combat Map

A self-contained interactive battle map (`battle-map.html`) for fights where position actually matters — multi-room layouts, elevation, hazards, chokepoints. It's published via Claude's Artifact tool and redeployed as a fight evolves; there's no server or build step, just one HTML file with inline CSS/JS and a `MAP` data object.

## When to use it

Publish/update the map for fights where positioning is doing real work — dungeon crawls, elevation, hazards, multiple frame sizes needing to navigate the same space. Skip it for simple, spatially-trivial skirmishes where the text state block (`reference/combat-display.md`) already covers everything that matters.

## Workflow

1. Open `battle-map.html`, edit the `MAP` object near the top of the `<script>` block.
2. Publish via the Artifact tool, pointing at this file's path — republishing the same path keeps the same URL, so the player can leave one tab open all session.
3. Redeploy whenever positions or terrain change enough to matter, not necessarily every single micro-move.

## Data model

```js
const MAP = {
  meta: { name, sub, round },
  grid: { cellPx },              // cols/rows are NOT set here -- see "Grid sizing" below
  tiles: [ { x, y, w, h, elevation?, terrain?, note?, cover? }, ... ],
  tokens: [ { id, name, faction, x, y, elevation, size, hp, maxHp, statuses, notes?, stats?, loadout?, spotted? }, ... ]
};
```

- `terrain`: `"wall"` | `"difficult"` | `"hazard"` | `"pit"` | `"void"` | omit for open floor.
- `faction`: `"friendly"` | `"neutral"` | `"hostile"`.
- `size`: the token's actual Lancer size (0.5, 1, 2, 3, 4) — determines its footprint and how much room it needs.
- `spotted`: hostiles show only a qualitative condition (NOMINAL/DAMAGED/CRITICAL) and no stat block until this is `true` — matches the real Spotter/Lock On rules (you don't know a hostile's exact Evasion/E-Defense/Armor/Speed/HP without spotting them).

## Authoring rules (learned the hard way — don't relearn these)

1. **Stats come from the actual files, every time.** Copy HP/Evasion/E-Defense/Armor/Speed straight from `characters/*.md` and `reference/bestiary.md` at the moment you build the map. Never invent numbers — this is a static page with no way to read those files live, so it's on whoever's authoring the map (you, GM) to keep it honest.
2. **Grid sizing is automatic — don't hand-set `cols`/`rows`.** A `fitGridToContent()` step scans every tile/token (ignoring the void catch-all), finds their bounding box, and sizes the grid to that plus a small margin, rebasing coordinates to start right at the margin. Author coordinates near the origin for readability; a bigger map just means more rooms, and the grid grows to match — there's no size to pick in advance.
3. **Tile lookup returns the *first* matching entry per cell**, so array order matters: specific terrain (walls, hazards, elevation, pits) first, then generic room/hallway floor-fill rectangles, then a single oversized void catch-all (`{x:0,y:0,w:9999,h:9999,terrain:"void"}`) *last*. That catch-all is what carves an actual dungeon shape — rooms and hallways cut out of nothing — instead of a rectangle with obstacles scattered on open ground.
4. **A cell needing two properties (e.g. a wall with cover) needs them merged into one entry**, not two separate ones — `{x,y,w:1,h:1,terrain:"wall",cover:{...}}`. Two separate entries for the same cell means the first-match rule silently drops whichever one loses.
5. **Corridor thickness has to clear the largest frame size that actually needs to move through it.** Lancer fields multiple sizes (0.5–4) in the same fight — a Size 2 mech needs a 2-wide hallway, not a 1-wide one. Check every hallway against your roster's largest *moving* frame. A stationary boss (e.g. a Size 3+ artillery piece that never leaves its room) doesn't force the rest of the map's corridors wider — only the room it sits in needs to fit its footprint.
6. **Vary terrain shapes.** L-shapes, zigzags, scattered clusters read as a real space; an occasional clean rectangular room/arena is fine, but the map as a whole should look like rooms and hallways, not boxes dropped on an open field.

## Interaction (once published)

- Drag anywhere on the map to pan, at any zoom level.
- Ctrl+scroll (or trackpad pinch) to zoom, toward the cursor.
- Drag the bar between the map and the sidebar to resize it.
- Hover a tile or token for a cursor-following tooltip.
- Click a tile or token to pin it to the sidebar for comparison — pin several at once; click again (or its ×) to unpin.
- The Sensor Key at the bottom of the sidebar is collapsible (click the "Sensor Key" bar) and independently resizable (drag that same bar).
