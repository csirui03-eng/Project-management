---
apdl: "AGEN"
method: agen
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.agen
generated: 2026-08-22
tags: [mapdl-command]
---

# AGEN

PyMAPDL: `mapdl.agen(itime='', na1='', na2='', ninc='', dx='', dy='', dz='', kinc='', noelem='', imove='', **kwargs)`

Generates additional areas from a pattern of areas.

## Parameters

**itime**: Do this generation operation a total of `ITIME` s, incrementing all keypoints in the given pattern automatically (or by `KINC` ) each time after the first. `ITIME` must be more than 1 for generation to occur.

**na1**, **na2**, **ninc**: Generate areas from the pattern of areas `NA1` to `NA2` (defaults to `NA1` ) in steps of `NINC` (defaults to 1). If `NA1` = ALL, `NA2` and `NINC` are ignored and the pattern is all selected areas ( [[asel|ASEL]] ). If `NA1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI). A component name may also be substituted for `NA1` ( `NA2` and `NINC` are ignored).

**dx**, **dy**, **dz**: Keypoint location increments in the active coordinate system (-, D θ, DZ for cylindrical; -, D θ, - for spherical).

**kinc**: Keypoint number increment between generated sets. If zero, the lowest available keypoint numbers are assigned ( [[numstr|NUMSTR]] }.

**noelem**

Specifies if elements and nodes are also to be generated:

- `0` - Generate nodes and elements associated with the original areas, if they exist.
- `1` - Do not generate nodes and elements.

**imove**

Specifies whether to redefine the existing areas:

- `0` - Generate new areas as requested with the `ITIME` argument.
- `1` - Move original areas to new position, retaining the same keypoint numbers ( `ITIME`, `KINC`, and `NOELEM` are ignored). If the original areas are needed in the original position (for example, they may be attached to a volume), they are not moved, and new areas are generated instead. Meshed items corresponding to moved areas are also moved if not needed at their original position.

## Notes

Generates additional areas (and their corresponding keypoints, lines and mesh) from a given area pattern. The MAT, TYPE, REAL, ESYS, and SECNUM attributes of the new areas are based upon the areas in the pattern and not upon the current settings of the pointers. End slopes of the generated lines remain the same (in the active coordinate system) as those of the given pattern. For example, radial slopes remain radial. Generations which produce areas of a size or shape different from the pattern (that is, radial generations in cylindrical systems, radial and phi generations in spherical systems, and theta generations in elliptical systems) are not allowed. Solid modeling in a toroidal coordinate system is not recommended. Area and line numbers are automatically assigned, beginning with the lowest available values ( [[numstr|NUMSTR]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AGEN.html
