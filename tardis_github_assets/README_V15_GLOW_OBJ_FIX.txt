TARDIS HQ V15 glow OBJ fix

V14 parse failure
-----------------
The generated OBJ contained:

  o Material.003_glow_q00

but that object had ZERO faces.

StarfallEx mesh.createFromObj() does not handle this empty object transition
cleanly and errored with:

  Expected a multiple of 3 vertices for the mesh's triangles.

V15 completely omits every zero-face OBJ group.

Glow groups actually present:
  Material.003_glow_q10
  Material.003_glow_q01
  Material.003_glow_q11

There is no q00 glow mesh/material/texture allocation in the test script.

Use:
  custommodellib_lite_v7.txt
  tardis_hq_flight_v15.txt

Upload all files in this folder to:
  tardis_github_assets/
