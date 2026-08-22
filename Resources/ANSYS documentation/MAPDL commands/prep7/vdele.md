---
apdl: "VDELE"
method: vdele
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.volumes.Volumes.vdele
generated: 2026-08-22
tags: [mapdl-command]
---

# VDELE

PyMAPDL: `mapdl.vdele(nv1='', nv2='', ninc='', kswp='', **kwargs)`

Deletes unmeshed volumes.

## Parameters

**nv1**, **nv2**, **ninc**: Delete volumes from `NV1` to `NV2` (defaults to `NV1` ) in steps of `NINC` (defaults to 1). If `NV1` = ALL, `NV2` and `NINC` are ignored and all selected volumes ( [[vsel|VSEL]] ) are deleted. If `NV1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NV1` ( `NV2` and `NINC` are ignored).

**kswp**

Specifies whether keypoints, lines, and areas are also deleted:

- `0` - Delete volumes only (default).
- `1` - Delete volumes, as well as keypoints, lines, and areas attached to the specified volumes but not shared by other volumes.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VDELE.html
