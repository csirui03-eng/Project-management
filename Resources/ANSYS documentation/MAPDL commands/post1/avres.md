---
apdl: "AVRES"
method: avres
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.controls.Controls.avres
generated: 2026-08-22
tags: [mapdl-command]
---

# AVRES

PyMAPDL: `mapdl.avres(key='', opt='', **kwargs)`

Specifies how results data will be averaged when PowerGraphics is enabled.

## Parameters

**key**

Averaging key.

- `1` - Average results at all common subgrid locations.
- `2` - Average results at all common subgrid locations except where material type ( [[mat|MAT]] ) discontinuities exist. (Default.)
- `3` - Average results at all common subgrid locations except where real constant ( [[real|REAL]] ) discontinuities exist.
- `4` - Average results at all common subgrid locations except where material type ( [[mat|MAT]] ) or real constant ( [[real|REAL]] ) discontinuities exist.

**opt**

Option to determine how results data are averaged.

- `(blank)` - Average surface results data using only the exterior element faces (default).
- `FULL` - Average surface results data using the exterior face and interior element data.

## Notes

The **AVRES** command specifies how results data will be averaged at subgrid locations that are common to 2 or more elements. The command is valid only when PowerGraphics is enabled (via the [[graphics|/GRAPHICS]],POWER command).

With PowerGraphics active ( [[graphics|/GRAPHICS]],POWER), the averaging scheme for surface data with interior element data included ( **AVRES**,,FULL) and multiple facets per edge ( [[efacet|/EFACET]] ,2 or [[efacet|/EFACET]],4) will yield differing minimum and maximum contour values depending on the Z-Buffering options ( [[slashtype|/TYPE]],,6 or [[slashtype|/TYPE]],,7). When the Section data is not included in the averaging schemes ( [[slashtype|/TYPE]],,7), the resulting absolute value for the midside node is significantly smaller.

PowerGraphics does not average your stresses across discontinuous surfaces. The normals for various planes and facets are compared to a tolerance to determine continuity. The `ANGLE` value you specify in the [[edge|/EDGE]] command is the tolerance for classifying surfaces as continuous or "coplanar."

The command affects nodal solution contour plots ( [[plnsol|PLNSOL]] ), nodal solution printout ( [[prnsol|PRNSOL]] ), and subgrid solution results accessed through the Query Results function (under General Postprocessing) in the GUI.

The command has no effect on the nodal degree of freedom solution values (UX, UY, UZ, TEMP, etc.).

For cyclic symmetry mode-superposition harmonic solutions, **AVRES**,,FULL is not supported. Additionally, averaging does not occur across discontinuous surfaces, and the `ANGLE` value on the [[edge|/EDGE]] command has no effect.

The section-based ( [[mat|MAT]] ) discontinuity in shells is accommodated via [[eshape|/ESHAPE]].

The command is also available in [[slashsolu|/SOLU]].

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AVRES.html
