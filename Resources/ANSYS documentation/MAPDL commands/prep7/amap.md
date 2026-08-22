---
apdl: "AMAP"
method: amap
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.amap
generated: 2026-08-22
tags: [mapdl-command]
---

# AMAP

PyMAPDL: `mapdl.amap(area='', kp1='', kp2='', kp3='', kp4='', **kwargs)`

Generates a 2D mapped mesh based on specified area corners.

## Parameters

**area**: Area number of area to be meshed. If `AREA` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI).

**kp1**, **kp2**, **kp3**, **kp4**: Keypoints defining corners of the mapped mesh. Three or four corners may be specified, and may be input in any order.

## Notes

Only one area at a time can be meshed with this command. The program internally concatenates all lines between the specified keypoints, then meshes the area with all quadrilateral elements. If line divisions are set, the mesh will follow the rules for mapped meshing (see [Meshing Your Solid Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD7_5.html#modmeshvaidck31400) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html)).

If the area being meshed has concatenated lines, the program will ask if those concatenations should be removed (in batch, the concatenations will automatically be removed). Nodes required for the generated elements are created and assigned the lowest available node numbers. If a mapped mesh is not possible due to mismatched line divisions or poor element shapes, the meshing operation is aborted.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AMAP.html
