---
apdl: "MSHPATTERN"
method: mshpattern
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.mshpattern
generated: 2026-08-22
tags: [mapdl-command]
---

# MSHPATTERN

PyMAPDL: `mapdl.mshpattern(key='', **kwargs)`

Specifies pattern to be used for mapped triangle meshing.

## Parameters

**key**

Key indicating triangle pattern to be used (the figures below illustrate the pattern that will be used for each value of `KEY` ):

- `0` - Allow Mechanical APDL choose the pattern (default). The program maximizes the minimum angle of the triangular-shaped elements that are created.
- `1` - Unidirectional split at node I.
- `2` - Unidirectional split at node J.

## Notes

"Mapped triangle meshing" refers to the Mechanical APDL program's ability to take a map-meshable area and mesh it with triangular elements, based on the value of **MSHPATTERN**, `KEY`. This type of meshing is particularly useful for analyses that involve the meshing of rigid contact elements.

This command is valid only when you have specified that Mechanical APDL use triangle-shaped elements ( [[mshape|MSHAPE]],1,2D)-or you are meshing with an element that supports only triangles- and you have specified mapped meshing ( [[mshkey|MSHKEY]],1) to mesh an area.

For details about mapped meshing with triangles, see the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MSHPATTERN.html
