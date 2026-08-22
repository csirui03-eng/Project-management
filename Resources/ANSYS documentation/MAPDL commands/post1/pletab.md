---
apdl: "PLETAB"
method: pletab
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.element_table.ElementTable.pletab
generated: 2026-08-22
tags: [mapdl-command]
---

# PLETAB

PyMAPDL: `mapdl.pletab(itlab='', avglab='', **kwargs)`

Displays element table items.

## Parameters

**itlab**: User-defined label, as specified with the [[etable|ETABLE]] command, of item to be displayed.

**avglab**

Averaging operation:

- `NOAV` - Do not average element items at common nodes (default).
- `AVG` - Average the element items at common nodes.

## Notes

Displays items stored in the table defined with the [[etable|ETABLE]] command for the selected elements. For display purposes, items are assumed to be constant over the element and assigned to each of its nodes. Contour display lines (lines of constant value) are determined by linear interpolation within each element from the nodal values. These nodal values have the option of being averaged (values are averaged at a node whenever two or more elements connect to the same node) or not averaged (discontinuous). The discontinuity between contour lines of adjacent elements is an indication of the gradient across elements.

For [reinforcing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_compreinfdirectemb.html) elements, this command displays the results of reinforcing member (individual reinforcing) selected via the [[layer|LAYER]], `N` command (where `N` is a given reinforcing member). [[layer|LAYER]],0 (default) or [[layer|LAYER]],1 selects the first reinforcing member.

Portions of this command are not supported by PowerGraphics ( [[graphics|/GRAPHICS]],POWER).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLETAB.html
