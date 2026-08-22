---
apdl: "BFTRAN"
method: bftran
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_body_loads.SolidBodyLoads.bftran
generated: 2026-08-22
tags: [mapdl-command]
---

# BFTRAN

PyMAPDL: `mapdl.bftran(**kwargs)`

Transfers solid model body-force loads to the finite element model.

## Notes

Body loads are transferred from selected keypoints and lines to selected nodes and from selected areas and volumes to selected elements. The **BFTRAN** operation is also done if the [[sbctran|SBCTRAN]] command is either explicitly issued or automatically issued upon initiation of the solution calculations ( [[solve|SOLVE]] ).

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BFTRAN.html
