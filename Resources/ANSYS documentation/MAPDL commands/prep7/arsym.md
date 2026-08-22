---
apdl: "ARSYM"
method: arsym
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.arsym
generated: 2026-08-22
tags: [mapdl-command]
---

# ARSYM

PyMAPDL: `mapdl.arsym(ncomp='', na1='', na2='', ninc='', kinc='', noelem='', imove='', **kwargs)`

Generates areas from an area pattern by symmetry reflection.

## Parameters

**ncomp**

Symmetry key:

- `X` - X symmetry (default).
- `Y` - Y symmetry.
- `Z` - Z symmetry.

**na1**, **na2**, **ninc**: Reflect areas from pattern beginning with `NA1` to `NA2` (defaults to `NA1` ) in steps of `NINC` (defaults to 1). If `NA1` = ALL, `NA2` and `NINC` are ignored and the pattern is all selected areas ( [[asel|ASEL]] ). If `Ncomp` = P, use graphical picking to specify areas and ignore `NL2` and `NINC`. A component name may also be substituted for `NA1` ( `NA2` and `NINC` are ignored).

**kinc**: Keypoint increment between sets. If zero, the lowest available keypoint numbers are assigned ( [[numstr|NUMSTR]] ).

**noelem**

Specifies whether nodes and elements are also to be generated:

- `0` - Generate nodes and elements associated with the original areas, if they exist.
- `1` - Do not generate nodes and elements.

**imove**

Specifies whether areas will be moved or newly defined:

- `0` - Generate additional areas.
- `1` - Move original areas to new position retaining the same keypoint numbers ( `KINC` and `NOELEM` are ignored). Valid only if the old areas are no longer needed at their original positions. Corresponding meshed items are also moved if not needed at their original position.

## Notes

Generates a reflected set of areas (and their corresponding keypoints, lines and mesh) from a given area pattern by a symmetry reflection (see analogous node symmetry command, [[nsym|NSYM]] ). The MAT, TYPE, REAL, ESYS, and SECNUM attributes are based upon the areas in the pattern and not upon the current settings. Reflection is done in the active coordinate system by changing a particular coordinate sign. The active coordinate system must be a Cartesian system. Areas in the pattern may have been generated in any coordinate system. However, solid modeling in a toroidal coordinate system is not recommended. Areas are generated as described in the [[agen|AGEN]] command.

See the [[esym|ESYM]] command for additional information about symmetry elements.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ARSYM.html
