---
apdl: "PDRAG"
method: pdrag
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.piping.Piping.pdrag
generated: 2026-08-22
tags: [mapdl-command]
---

# PDRAG

PyMAPDL: `mapdl.pdrag(px1='', py1='', pz1='', h1='', px2='', py2='', pz2='', h2='', kcord='', **kwargs)`

Defines the external fluid drag loading for a piping run.

## Parameters

**px1**, **py1**, **pz1**: External fluid drag pressure (global Cartesian components) at height `H1`.

**h1**: Height (along `Kcord` coordinate) for first drag pressure.

**px2**, **py2**, **pz2**: External fluid drag pressure (global Cartesian components) at height `H2`.

**h2**: Height (along `Kcord` coordinate) for second drag pressure.

**kcord**

Coordinate direction for height value (in the global Cartesian coordinate system):

- `X` - X coordinate.
- `Y` - Y coordinate (default).
- `Z` - Z coordinate.

## Notes

Defines the external fluid drag loading (pressure) as a function of height for a piping run. (See the RUN command description in [Archived Commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_arch/Hlp_C_VALVE.html).) The element drag pressure is determined from the centroid height and linear interpolation. Pressures are assigned to the elements as they are generated.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PDRAG.html
