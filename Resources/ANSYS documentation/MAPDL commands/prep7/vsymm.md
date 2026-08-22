---
apdl: "VSYMM"
method: vsymm
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.volumes.Volumes.vsymm
generated: 2026-08-22
tags: [mapdl-command]
---

# VSYMM

PyMAPDL: `mapdl.vsymm(ncomp='', nv1='', nv2='', ninc='', kinc='', noelem='', imove='', **kwargs)`

Generates volumes from a volume pattern by symmetry reflection.

## Parameters

**ncomp**

Symmetry key:

- `X` - X symmetry (default).
- `Y` - Y symmetry.
- `Z` - Z symmetry.

**nv1**, **nv2**, **ninc**: Reflect volumes from pattern beginning with `NV1` to `NV2` (defaults to `NV1` ) in steps of `NINC` (defaults to 1). If `NV1` = ALL, `NV2` and `NINC` are ignored and the pattern is all selected volumes ( [[vsel|VSEL]] ). If `NV1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NV1` ( `NV2` and `NINC` are ignored).

**kinc**: Keypoint increment between sets. If zero, the lowest available keypoint numbers are assigned ( [[numstr|NUMSTR]] ).

**noelem**

Specifies whether nodes and elements are also to be generated:

- `0` - Generate nodes and elements associated with the original volumes, if they exist.
- `1` - Do not generate nodes and elements.

**imove**

Specifies whether volumes will be moved or newly defined:

- `0` - Generate additional volumes.
- `1` - Move original volumes to new position retaining the same keypoint numbers ( `KINC` and `NOELEM` are ignored). Corresponding meshed items are also moved if not needed at their original position.

## Notes

Generates a reflected set of volumes (and their corresponding keypoints, lines, areas and mesh) from a given volume pattern by a symmetry reflection (see analogous node symmetry command, [[nsym|NSYM]] ). The MAT, TYPE, REAL, and ESYS attributes are based upon the volumes in the pattern and not upon the current settings. Reflection is done in the active coordinate system by changing a particular coordinate sign. The active coordinate system must be a Cartesian system. Volumes in the pattern may have been generated in any coordinate system. However, solid modeling in a toroidal coordinate system is not recommended. Volumes are generated as described in the [[vgen|VGEN]] command.

See the [[esym|ESYM]] command for additional information about symmetry elements.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VSYMM.html
