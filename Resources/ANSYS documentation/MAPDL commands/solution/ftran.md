---
apdl: "FTRAN"
method: ftran
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_forces.SolidForces.ftran
generated: 2026-08-22
tags: [mapdl-command]
---

# FTRAN

PyMAPDL: `mapdl.ftran(**kwargs)`

Transfers solid model forces to the finite element model.

## Notes

Forces are transferred only from selected keypoints to selected nodes. The **FTRAN** operation is also done if the [[sbctran|SBCTRAN]] command is issued or automatically done upon initiation of the solution calculations ( [[solve|SOLVE]] ).

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FTRAN.html
