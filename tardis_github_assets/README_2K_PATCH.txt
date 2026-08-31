TARDIS Starfall 2K tile patch

Upload every file in this folder to the existing:
  ReasonableScripts/starfallTardis/tardis_github_assets/

New model:
  Tardis_Starfall_2K.obj

New Material.003 tiles:
  Material003_BaseColor_q00/q10/q01/q11.png
  Material003_Normal_q00/q10/q01/q11.png
  Material003_Emissive_q00/q10/q01/q11.png

qXY is UV-space:
  X = U half (0 left, 1 right)
  Y = V half (0 bottom, 1 top)

The OBJ was clipped at U/V = 0.5 where required, so triangles crossing tile
boundaries were actually split rather than stretched into the wrong tile.

Use with:
  custommodellib_lite_v7.txt
  tardis_model_hq_2k_test_v8.txt
