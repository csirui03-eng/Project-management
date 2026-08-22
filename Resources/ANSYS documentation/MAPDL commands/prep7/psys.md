---
apdl: "PSYS"
method: psys
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.artificially_matched_layers.ArtificiallyMatchedLayers.psys
generated: 2026-08-22
tags: [mapdl-command]
---

# PSYS

PyMAPDL: `mapdl.psys(kcn='', **kwargs)`

Sets the PML element coordinate system attribute pointer.

**Command default:**

The PML element coordinate system orientation defaults to the global Cartesian system.

## Parameters

**kcn**

Coordinate system number:

- `0` - Use the global Cartesian coordinate system as the PML element coordinate system (default).
- `N` - Set the PML element coordinate system orientation based on a local Cartesian coordinate system N (where N must be greater than 10) defined by the [[local|LOCAL]] or [[cs|CS]] command (for example: [[local|LOCAL]],11,0).

## Notes

This command identifies the local coordinate system used to define the PML (perfectly matched layers) coordinate system of subsequently defined PML elements. It is only applicable to volume elements that support PML. The use of PML coordinate systems is similar to element coordinate systems, as discussed in [Understanding the Element Coordinate System](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_3.html#elemESYSchange) `KCN` ) defined using the [[local|LOCAL]] (or similar) command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSYS.html
