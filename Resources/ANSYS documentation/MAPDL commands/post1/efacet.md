---
apdl: "/EFACET"
method: efacet
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.controls.Controls.efacet
generated: 2026-08-22
tags: [mapdl-command]
---

# /EFACET

PyMAPDL: `mapdl.efacet(num='', **kwargs)`

Specifies the number of facets per element edge for PowerGraphics displays.

**Command default:**

As stated above.

## Parameters

**num**

Number of facets per element edge for element plots.

- `1` - Use 1 facet per edge (default for h-elements).
- `2` - Use 2 facets per edge.
- `4` - Use 4 facets per edge.

## Notes

**/EFACET** is valid only when PowerGraphics is enabled ( [[graphics|/GRAPHICS]],POWER), except that it can be used in FULL graphics mode for element `CONTA174`. (See the [[graphics|/GRAPHICS]] command and element `CONTA174` in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html) for more information.) The **/EFACET** command is only applicable to element type displays.

**/EFACET** controls the fineness of the subgrid that is used for element plots. The element is subdivided into smaller portions called facets. Facets are piecewise linear surface approximations of the actual element face. In their most general form, facets are warped planes in 3D space. A greater number of facets will result in a smoother representation of the element surface for element plots. **/EFACET** may affect results averaging. See [Contour Displays](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_3.html#) in the [Basic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS19.html) for more information.

For midside node elements, use `NUM` = 2; if `NUM` = 1, no midside node information is output. For non-midside node elements, `NUM` should be set to 1. See the [[plnsol|PLNSOL]] and [[prnsol|PRNSOL]] commands for more information.

With PowerGraphics active ( [[graphics|/GRAPHICS]],POWER), the averaging scheme for surface data with interior element data included ( [[avres|AVRES]],,FULL) and multiple facets per edge ( **/EFACET** ,2 or **/EFACET**,4) will yield differing minimum and maximum contour values depending on the Z-Buffering options ( [[slashtype|/TYPE]],,6 or [[slashtype|/TYPE]],,7). When the Section data is not included in the averaging schemes ( [[slashtype|/TYPE]],,7), the resulting absolute value for the midside node is significantly smaller.

For cyclic symmetry mode-superposition harmonic solutions, only `NUM` = 1 is supported in postprocessing.

> [!WARNING]
> If you specify **/EFACET**,1, PowerGraphics does not plot midside nodes. You must use **/EFACET**,2 to make the nodes visible.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EFACET.html
