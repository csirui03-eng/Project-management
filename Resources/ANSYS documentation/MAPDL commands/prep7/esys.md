---
apdl: "ESYS"
method: esys
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.esys
generated: 2026-08-22
tags: [mapdl-command]
---

# ESYS

PyMAPDL: `mapdl.esys(kcn='', **kwargs)`

Sets the element coordinate system attribute pointer.

**Command default:**

Use element coordinate system orientation as defined (either by default or by KEYOPT setting) for the element (default).

## Parameters

**kcn**

Coordinate system number:

- `0` - Use element coordinate system orientation as defined (either by default or by KEYOPT setting) for the element (default).
- `N` - Use element coordinate system orientation based on local coordinate system N (where N must be greater than 10). For global system 0, 1, or 2, define a local system N parallel to appropriate system with the [[local|LOCAL]] or [[cs|CS]] command (for example: [[local|LOCAL]],11,1).

## Notes

Identifies the local coordinate system to be used to define the element coordinate system of subsequently defined elements. Used only with area and volume elements. For non-layered volume elements, the local coordinate system N is simply assigned to be the element coordinate system. For shell and layered volume elements, the x and y axes of the local coordinate system N are projected onto the shell or layer plane to determine the element coordinate system. See [Understanding the Element Coordinate System](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_3.html#elemESYSchange) for more details. N refers to the coordinate system reference number ( `KCN` ) defined using the [[local|LOCAL]] (or similar) command. Element coordinate system numbers may be displayed( [[pnum|/PNUM]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ESYS.html
