TARDIS HQ V11

Window fix
----------
This does NOT procedurally generate replacement window grime.

It finds the large flat #BCBCBC window/end-pane islands from the supplied
Material003_BaseColor texture and pastes resized copies of known-good panes
from the artist's TOP ROW into them.

The same donor regions are copied from:
- BaseColor
- Normal
- Emissive

Large flat islands replaced: 7

Physics fix
-----------
HQ visual bounds:
  min: [-33.061779, -33.241414, -64.900568]
  max: [33.061779, 33.241414, 64.900568]

The previous test's collision hull bottom was around -51 while the visual
bottom is -64.900568, allowing roughly 14 units of the rendered TARDIS to
sink through the floor.

V11 rescales the proven 21-point hull to the actual HQ visual bounds and lets
the collision bottom extend 0.35 units below the visual as a tiny safety lip.

Use:
  custommodellib_lite_v7.txt
  tardis_model_hq_known_good_windows_v11.txt
