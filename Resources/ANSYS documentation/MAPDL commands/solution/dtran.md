---
apdl: "DTRAN"
method: dtran
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_constraints.SolidConstraints.dtran
generated: 2026-08-22
tags: [mapdl-command]
---

# DTRAN

PyMAPDL: `mapdl.dtran(**kwargs)`

Transfers solid model DOF constraints to the finite element model.

## Notes

Constraints are transferred only from selected solid model entities to selected nodes. The **DTRAN** operation is also done if the [[sbctran|SBCTRAN]] command is issued, and is automatically done upon initiation of the solution calculations ( [[solve|SOLVE]] ).

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DTRAN.html
