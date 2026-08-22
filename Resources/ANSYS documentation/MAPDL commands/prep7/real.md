---
apdl: "REAL"
method: real
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.real
generated: 2026-08-22
tags: [mapdl-command]
---

# REAL

PyMAPDL: `mapdl.real(nset='', **kwargs)`

Sets the element real constant set attribute pointer.

## Parameters

**nset**: Assign this real constant set number to subsequently defined elements (defaults to 1).

## Notes

Identifies the real constant set number to be assigned to subsequently defined elements. This number refers to the real constant set number ( `NSET` ) defined with the real constant sets ( [[r|R]] ). Real constant set numbers may be displayed ( [[pnum|/PNUM]] ). If the element type requires no real constants, this entry is ignored. Elements of different type should not refer to the same real constant set.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_REAL.html
