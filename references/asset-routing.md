# Asset Routing

Use this reference when a game task touches generated or integrated 2D visual assets.

## Route By Asset Type

- Sprite workflow: characters, creatures, NPCs, props, summons, projectiles, impacts, UI-adjacent icons, FX, and animation sheets.
- Map workflow: overworld maps, rooms, levels, stages, tactical arenas, battle backgrounds, side-scroller scenes, parallax layers, tilemaps, collision zones, walkable areas, exits, triggers, and camera bounds.
- Runtime integration: keep generated art, import metadata, animation clips, collision, and scene wiring explicit instead of hiding everything in one baked image.

## Sprite Rules

- Use built-in image generation for raw visible art. Do not replace requested sprite assets with code-drawn placeholders.
- For transparent extraction or chroma-key sprite workflows, request a solid green `#00FF00` background first.
- Use solid magenta `#FF00FF` only when green conflicts with the subject palette, vegetation/map art, edge cleanup, or the generated output fails green-key processing.
- Keep a single raw generated sheet to one coherent action family, continuous sequence, directional locomotion set, or compact prop pack.
- For controllable heroes and high-value player assets, generate separate action sheets first, QA each action, then assemble final runtime atlases deterministically.
- Keep wide slash arcs, muzzle flashes, projectiles, dust, and impact bursts separate from body sheets unless the runtime explicitly supports wider cells and per-action origins.
- Prefer compact multi-row grids for animated bodies: `2x2`, `2x3`, `2x4`, `3x3`, `3x4`, or `4x4`.
- Avoid raw single-row body sheets for characters, creatures, NPCs, enemies, summons, or animated props. Build strips later after QA if the engine needs them.

## Sprite Prompt Essentials

Every raw sprite prompt should state:

- exact grid shape or single asset requirement
- solid green background first, or magenta fallback if green is unsafe for the subject
- stable identity, silhouette, palette, and scale across frames
- subject centered in each cell
- full body or asset inside the safe area
- no frame crossing cell edges
- no guide marks, labels, borders, shadows, or background scenery unless requested

## Map Rules

- Do not ship a single baked image as a playable map unless the user only asked for a flat background.
- Playable maps should expose geometry through layers, props, tiles, object metadata, collision shapes, walkable zones, triggers, exits, and camera bounds.
- Keep runtime-controlled objects out of the baked base map.
- For layered maps, use this order: base/background, in-world mockup, separate props/objects, collision and metadata, preview.
- For side-scroller scenery-only parallax, separate background layers from platforms, hazards, exits, collision, and camera hooks.
- Save prompts, dimensions, layer list, collision assumptions, and import notes near the generated assets.

## Asset QA

Check and record:

- dimensions and expected grid/cell count
- alpha or chroma-key cleanup quality
- edge touching, cropping, or unwanted cutoffs
- frame-to-frame scale drift
- anchor consistency, especially feet/bottom anchor
- runtime import settings
- animation clip metadata
- collision or walkable-zone metadata for maps
- preview image or GIF when useful
