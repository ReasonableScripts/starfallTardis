TARDIS HQ V12

Six-pane window repair
----------------------
The window texture is NOT repaired pane-by-pane anymore.

The OBJ was inspected to recover the physical left-to-right order of all
window panes. If a lower six-pane row contained flat panes, the corresponding
GOOD upper six-pane row from that same side was copied onto it in physical
left-to-right order.

Rows replaced:
- X+ lower six: replaced as a complete ordered set (detected 2 flat panes)
- Y+ lower six: replaced as a complete ordered set (detected 6 flat panes)

This preserves:
- pane order
- border/corner orientation
- the original artist's grime
- matching BaseColor / Normal / Emissive data

Emissive
--------
Material.003 uses VertexLitGeneric with:
- $selfillum flag enabled
- $selfillum = 1
- $selfillummask = the supplied emissive texture
- $selfillumtint = [1 1 1]

This makes the windows/signs appear lit even in darkness.

IMPORTANT: Source self-illumination does NOT cast light onto nearby walls or
the ground. A Starfall dynamic light can be added separately if actual light
spill is desired.

Use with:
- custommodellib_lite_v7.txt
- tardis_model_hq_sixpane_emissive_v12.txt
