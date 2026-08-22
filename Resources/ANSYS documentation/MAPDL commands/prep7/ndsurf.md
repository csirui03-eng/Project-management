---
apdl: "NDSURF"
method: ndsurf
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.ndsurf
generated: 2026-08-22
tags: [mapdl-command]
---

# NDSURF

PyMAPDL: `mapdl.ndsurf(snode='', telem='', dimn='', **kwargs)`

Generates surface elements overlaid on the edge of existing elements and assigns the extra node as the closest fluid element node.

## Parameters

**snode**: Component name for the surface nodes of the solid elements. The component name must be 32 characters or less.

**telem**: Component name for the target fluid elements. The component name must be 32 characters or less.

**dimn**

Model dimensionality:

- `2` - 2D model.
- `3` - 3D model.

## Notes

This command macro is used to generate surface effect elements ( `SURF151` or `SURF152` ) overlaid on the surface of existing plane or solid elements and, based on proximity, to determine and assign the extra node ( `FLUID116` ) for each surface element. The active element type must be `SURF151` or `SURF152` with appropriate settings for KEYOPT(4), KEYOPT(5), KEYOPT(6), and KEYOPT(8).

The surface nodes of the plane or solid elements must be grouped into a node component and the fluid elements must be grouped into an element component and named using the [[cm|CM]] command. The names must be enclosed in single quotes (for example, 'NOD') when the **NDSURF** command is manually typed in.

When using the GUI method, node and element components are created through the picking dialog boxes associated with this command.

The macro is applicable for the `SURF151`, `SURF152`, and `FLUID116` element types.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NDSURF.html
