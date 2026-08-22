---
apdl: "CURR2D"
method: curr2d
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.magnetics_calculations.MagneticsCalculations.curr2d
generated: 2026-08-22
tags: [mapdl-command]
---

# CURR2D

PyMAPDL: `mapdl.curr2d(**kwargs)`

Calculates current flow in a 2D conductor.

## Notes

**CURR2D** invokes a macro which calculates the total current flowing in a conducting body for a 2D planar or axisymmetric magnetic field analysis. The currents may be applied source currents or induced currents (eddy currents). The elements of the conducting region must be selected before this command is issued. The total current calculated by the macro is stored in the parameter TCURR. Also, the total current and total current density are stored on a per-element basis in the element table ( [[etable|ETABLE]] ) with the labels TCURR and JT, respectively. Use the [[pletab|PLETAB]] and [[pretab|PRETAB]] commands to plot and list the element table items.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CURR2D.html
