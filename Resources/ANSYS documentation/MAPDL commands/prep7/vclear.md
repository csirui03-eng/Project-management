---
apdl: "VCLEAR"
method: vclear
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.vclear
generated: 2026-08-22
tags: [mapdl-command]
---

# VCLEAR

PyMAPDL: `mapdl.vclear(nv1='', nv2='', ninc='', **kwargs)`

Deletes nodes and volume elements associated with selected volumes.

## Parameters

**nv1**, **nv2**, **ninc**: Delete mesh for volumes `NV1` to `NV2` (defaults to `NV1` ) in steps of `NINC` (defaults to 1). If `NV1` = ALL, `NV2` and `NINC` are ignored and mesh for all selected volumes ( [[vsel|VSEL]] ) is deleted. If `NV1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NV1` ( `NV2` and `NINC` are ignored).

## Notes

Deletes all nodes and volume elements associated with selected volumes (regardless of whether the nodes or elements are selected). Nodes shared by adjacent meshed volumes and nodes associated with non-volume elements will not be deleted. Attributes assigned as a result of [[vatt|VATT]] are maintained. In the program's response to the command, if a volume, area, line, or keypoint is tallied as "cleared," it means either its node or element reference was deleted.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VCLEAR.html
