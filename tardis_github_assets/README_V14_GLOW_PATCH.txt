TARDIS HQ V14 proper emissive patch

Why V12/V13 looked fullbright
-----------------------------
$selfillum was enabled on the entire Material.003 exterior.
With Starfall URL/render-target backed dynamic materials, the intended
$selfillummask path did not behave reliably, so the whole main exterior could
appear self-lit.

V14 architecture
----------------
Base exterior:
  VertexLitGeneric
  BaseColor + Normal only
  receives normal world/dynamic/flashlight lighting

Glow overlay:
  UnlitGeneric + additive
  separate tiny geometry overlay, offset 0.025 units
  black outside authored emissive pixels
  only windows/signs/lamp add visible glow

Overlay triangles:
  Material.003_glow_q10: 111
  Material.003_glow_q01: 199
  Material.003_glow_q11: 437
  Material.003_glow_q00: 0

RT use
------
Main exterior:
  4 base + 4 normal = 8 RTs
Secondary materials:
  4 RTs
Glow:
  4 RTs

Total = 16 RTs, same general budget as before and below the 20-RT bank.

Flight/camera
-------------
Use tardis_hq_flight_v14.txt with custommodellib_lite_v7.txt.

V14 also restores the old V4-style external camera trace and adds an explicit
server pilot-state message so camera activation no longer depends entirely on
the client resolving the exact seat entity first.
