---
apdl: "MSTOLE"
method: mstole
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.special_purpose.SpecialPurpose.mstole
generated: 2026-08-22
tags: [mapdl-command]
---

# MSTOLE

PyMAPDL: `mapdl.mstole(method='', namesurf='', namefluid='', **kwargs)`

Adds two extra nodes from `FLUID116` elements to `SURF151` or `SURF152` elements for convection analyses.

## Parameters

**method**

Mapping method:

- `0` - Hybrid method (default).
- `1` - Projection method.
- `2` - Minimum centroid distance method.

**namesurf**: Component name for a group of `SURF151` or `SURF152` elements. The component name must be 32 characters or less, and it must be enclosed in single quotes (for example, 'COM152') when the **MSTOLE** command is manually typed in.

**namefluid**: Component name for a group of `FLUID116` elements. The component name must be 32 characters or less, and it must be enclosed in single quotes (for example, 'COM116') when the **MSTOLE** command is manually typed in.

## Notes

For convection analyses, the **MSTOLE** command adds two extra nodes from `FLUID116` elements to `SURF151` or `SURF152` elements by employing the specified mapping method. In the hybrid method, the projection method is tried first and if it fails the centroid distance method is used. The `SURF151` or `SURF152` elements and the `FLUID116` elements must be grouped into components and named using the [[cm|CM]] command.

The `SURF151` or `SURF152` extra node option must be set for two extra nodes (KEYOPT(5) = 2).

For more information, see [Using the Surface Effect Elements](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_the/Hlp_G_THE2_5.html#) in the [Thermal Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_the/Hlp_G_THE4.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MSTOLE.html
