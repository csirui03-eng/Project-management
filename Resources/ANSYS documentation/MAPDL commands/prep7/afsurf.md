---
apdl: "AFSURF"
method: afsurf
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.afsurf
generated: 2026-08-22
tags: [mapdl-command]
---

# AFSURF

PyMAPDL: `mapdl.afsurf(sarea='', tline='', **kwargs)`

Generates surface elements overlaid on the surface of existing solid elements and assigns the extra node as the closest fluid element node.

## Parameters

**sarea**: Component name for the surface areas of the meshed solid volumes. The component name must be 32 characters or less.

**tline**: Component name for the target lines meshed with fluid elements. The component name must be 32 characters or less.

## Notes

This command macro is used to generate surface effect elements overlaid on the surface of existing solid elements and, based on proximity, to determine and assign the extra node for each surface element. The underlying volumes of the solid region and the fluid lines must be meshed prior to calling this command macro. The active element type must be `SURF152` with appropriate settings for KEYOPT(4), KEYOPT(5), KEYOPT(6), and KEYOPT(8).

The surface areas of the solid and the target lines of the fluid are grouped into components and named using the [[cm|CM]] command. The names must be enclosed in single quotes (for example, ' `SAREA` ') when the **AFSURF** command is manually typed in.

When using the GUI method, node and element components are created through the picking dialog boxes associated with this command.

The macro is applicable for the `SURF152` and `FLUID116` element types.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AFSURF.html
