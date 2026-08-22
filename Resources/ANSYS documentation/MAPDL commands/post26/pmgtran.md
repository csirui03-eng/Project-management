---
apdl: "PMGTRAN"
method: pmgtran
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.special_purpose.SpecialPurpose.pmgtran
generated: 2026-08-22
tags: [mapdl-command]
---

# PMGTRAN

PyMAPDL: `mapdl.pmgtran(fname='', freq='', fcnam1='', fcnam2='', pcnam1='', pcnam2='', ecnam1='', ccnam1='', **kwargs)`

Summarizes electromagnetic results from a transient analysis.

## Parameters

**fname**: File name (8 characters maximum) to which tabular data and plot files will be written. Must be enclosed in single quotes when the command is manually typed in. Defaults to MG_TRNS. The data file extension is `.OUT` and the plot file extension is. `PLT`.

**freq**: Frequency of solution output. Defaults to 1. Every `FREQ` th solution on the results file is output.

**fcnam1**, **fcnam2**: Names of element components for force calculation. Must be enclosed in single quotes when the command is manually typed in.

**pcnam1**, **pcnam2**: Names of element components for power loss calculation. Must be enclosed in single quotes when the command is manually typed in.

**ecnam1**, **ccnam1**: Names of element components for energy and total current calculations, respectively. Must be enclosed in single quotes when the command is manually typed in.

## Notes

**PMGTRAN** invokes a Mechanical APDL macro which calculates and summarizes electromagnetic results from a transient analysis. The results are summarized by element components and listed on the screen as well as written to a file ( `Fname.OUT` ).

You can select two components for the summary of electromagnetic forces, two for power loss, and one each for stored energy (see [[senergy|SENERGY]] ) and total current (see [[curr2d|CURR2D]] ). See the referenced commands for other restrictions.

**PMGTRAN** is restricted to MKSA units.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PMGTRAN.html
