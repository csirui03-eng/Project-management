---
apdl: "LFSURF"
method: lfsurf
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.lfsurf
generated: 2026-08-22
tags: [mapdl-command]
---

# LFSURF

PyMAPDL: `mapdl.lfsurf(sline='', tline='', **kwargs)`

Generates surface elements overlaid on the edge of existing solid elements and assigns the extra node as the closest fluid element node.

## Parameters

**sline**: Component name for the surface lines of the meshed solid areas. The component name must be 32 characters or less.

**tline**: Component name for the target lines meshed with fluid elements. The component name must be 32 characters or less.

## Notes

This command macro is used to generate surface effect elements overlaid on the surface of existing plane elements and, based on proximity, to determine and assign the extra node for each surface element. The underlying areas of the solid region and the fluid lines must be meshed prior to calling this command macro. The active element type must be `SURF151` with appropriate settings for KEYOPT(4), KEYOPT(5), KEYOPT(6), and KEYOPT(8).

The surface lines of the solid and the target lines of the fluid are grouped into components and named using the [[cm|CM]] command. The names must be enclosed in single quotes (for example, ' `SLINE` ') when the **LFSURF** command is manually typed in.

When using the GUI method, node and element components are created through the picking dialog boxes associated with this command.

The macro is applicable for the `SURF151` and `FLUID116` element types.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LFSURF.html
