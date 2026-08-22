---
apdl: "VLIST"
method: vlist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.volumes.Volumes.vlist
generated: 2026-08-22
tags: [mapdl-command]
---

# VLIST

PyMAPDL: `mapdl.vlist(nv1='', nv2='', ninc='', **kwargs)`

Lists the defined volumes.

## Parameters

**nv1**, **nv2**, **ninc**: List volumes from `NV1` to `NV2` (defaults to `NV1` ) in steps of `NINC` (defaults to 1). If `NV1` = ALL (default), `NV2` and `NINC` are ignored and all selected volumes ( [[vsel|VSEL]] ) are listed. If `NV1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NV1` ( `NV2` and `NINC` are ignored).

## Notes

An attribute (TYPE, MAT, REAL, or ESYS) listed as a zero is unassigned; one listed as a positive value indicates that the attribute was assigned with the [[vatt|VATT]] command (and will not be reset to zero if the mesh is cleared); one listed as a negative value indicates that the attribute was assigned using the attribute pointer \[TYPE, MAT, REAL, or ESYS\] that was active during meshing (and will be reset to zero if the mesh is cleared). A "-1" in the "nodes" column indicates that the volume has been meshed but there are no interior nodes. The volume size is listed only if a [[vsum|VSUM]] command has been performed on the volume. Volume orientation attributes (KZ1 and KZ2) are listed only if a [[veorient|VEORIENT]] command was previously used to define an orientation for the volume.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VLIST.html
