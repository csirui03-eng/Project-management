---
apdl: "VDGL"
method: vdgl
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.volumes.Volumes.vdgl
generated: 2026-08-22
tags: [mapdl-command]
---

# VDGL

PyMAPDL: `mapdl.vdgl(nv1='', nv2='', ninc='', **kwargs)`

Lists keypoints of a volume that lie on a parametric degeneracy.

## Parameters

**nv1**, **nv2**, **ninc**: List keypoints that lie on a parametric degeneracy on volumes from `NV1` to `NV2` (defaults to `NV1` ) in steps of `NINC` (defaults to 1). If `NV1` = ALL (default), `NV2` and `NINC` will be ignored and keypoints on all selected volumes ( [[vsel|VSEL]] ) will be listed. If `NV1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). You may also substitute a component name for `NV1` (ignore `NV2` and `NINC` ).

## Notes

See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for details about parametric degeneracies.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VDGL.html
