---
apdl: "SFTRAN"
method: sftran
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_surface_loads.SolidSurfaceLoads.sftran
generated: 2026-08-22
tags: [mapdl-command]
---

# SFTRAN

PyMAPDL: `mapdl.sftran(**kwargs)`

Transfer the solid model surface loads to the finite element model.

## Notes

Surface loads are transferred only from selected lines and areas to all selected elements. The **SFTRAN** operation is also done if the [[sbctran|SBCTRAN]] command is issued or automatically done upon initiation of the solution calculations ( [[solve|SOLVE]] ).

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFTRAN.html
