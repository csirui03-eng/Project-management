---
apdl: "VGEN"
method: vgen
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.volumes.Volumes.vgen
generated: 2026-08-22
tags: [mapdl-command]
---

# VGEN

PyMAPDL: `mapdl.vgen(itime='', nv1='', nv2='', ninc='', dx='', dy='', dz='', kinc='', noelem='', imove='', **kwargs)`

Generates additional volumes from a pattern of volumes.

## Parameters

**itime**: Do this generation operation a total of `ITIME` s, incrementing all keypoints in the given pattern automatically (or by `KINC` ) each time after the first. `ITIME` must be \> 1 for generation to occur.

**nv1**, **nv2**, **ninc**: Generate volumes from pattern beginning with `NV1` to `NV2` (defaults to `NV1` ) in steps of `NINC` (defaults to 1). If `NV1` = ALL, `NV2` and `NINC` are ignored and the pattern is all selected volumes ( [[vsel|VSEL]] ). If `NV1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NV1` ( `NV2` and `NINC` are ignored).

**dx**, **dy**, **dz**: Keypoint location increments in the active coordinate system (-, Dθ, DZ for cylindrical, -, Dθ, - for spherical).

**kinc**: Keypoint increment between generated sets. If zero, the lowest available keypoint numbers are assigned ( [[numstr|NUMSTR]] ).

**noelem**

Specifies if elements and nodes are also to be generated:

- `0` - Generate nodes and elements associated with the original volumes, if they exist.
- `1` - Do not generate nodes and elements.

**imove**

Specifies whether to redefine the existing volumes:

- `0` - Generate additional volumes as requested with the `ITIME` argument.
- `1` - Move original volumes to new position retaining the same keypoint line, and area numbers ( `ITIME`, `KINC`, and `NOELEM` are ignored). Corresponding meshed items are also moved if not needed at their original position.

## Notes

Generates additional volumes (and their corresponding keypoints, lines, areas and mesh) from a given volume pattern. The MAT, TYPE, REAL, and ESYS attributes are based upon the volumes in the pattern and not upon the current settings of the pointers. End slopes of the generated lines remain the same (in the active coordinate system) as those of the given pattern. For example, radial slopes remain radial, etc. Generations which produce volumes of a size or shape different from the pattern (that is, radial generations in cylindrical systems, radial and phi generations in spherical systems, and theta generations in elliptical systems) are not allowed. Note that solid modeling in a toroidal coordinate system is not recommended. Volume, area, and line numbers are automatically assigned (beginning with the lowest available values ( [[numstr|NUMSTR]] )).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VGEN.html
