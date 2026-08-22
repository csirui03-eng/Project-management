---
apdl: "SBCTRAN"
method: sbctran
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.misc_loads.MiscLoads.sbctran
generated: 2026-08-22
tags: [mapdl-command]
---

# SBCTRAN

PyMAPDL: `mapdl.sbctran(**kwargs)`

Transfers solid model loads and boundary conditions to the FE model.

## Notes

Causes a manual transfer of solid model loads and boundary conditions to the finite element model. Loads and boundary conditions on unselected keypoints, lines, areas, and volumes are not transferred. Boundary conditions and loads will not be transferred to unselected nodes or elements. The **SBCTRAN** operation is also automatically done upon initiation of the solution calculations ( [[solve|SOLVE]] ).

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SBCTRAN.html
