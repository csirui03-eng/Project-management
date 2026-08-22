---
apdl: "ADAMS"
method: adams
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.adams
generated: 2026-08-22
tags: [mapdl-command]
---

# ADAMS

PyMAPDL: `mapdl.adams(nmodes='', kstress='', kshell='', **kwargs)`

Performs solutions and writes flexible body information to a modal neutral file ( `Jobname.MNF` ) for use in an ADAMS analysis.

## Parameters

**nmodes**: Number of normal modes to be written to `Jobname.MNF` file (no default).

**kstress**

Specifies whether to write stress or strain results:

- `0` - Do not write stress or strain results (default).
- `1` - Write stress results.
- `2` - Write strain results.
- `3` - Write both stress and strain results.

**kshell**

Shell element output location. This option is valid only for shell elements.

- `0, 1` - Shell top surface (default).
- `2` - Shell middle surface.
- `3` - Shell bottom surface.

## Notes

**ADAMS** invokes a predefined Mechanical APDL macro that solves a series of analyses and then writes the modal neutral file, `Jobname.MNF`. This file can be imported into the ADAMS program in order to perform a rigid body dynamics simulation. For detailed information about how to use the **ADAMS** command macro to create a modal neutral file, see [Rigid Body Dynamics and the Ansys- Adams Interface](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/advmeth2402.html)

Before running the **ADAMS** command macro, you must specify the units with the [[units|/UNITS]] command. The interface points should be the only selected nodes when the command macro is initiated. (Interface points are nodes where constraints may be applied in ADAMS.) Only selected elements will be considered in the calculations.

By default, stress and strain data is transferred to the ADAMS program for all nodes, as specified by the `KSTRESS` value. If you want to transfer stress/strain data for only a subset of nodes, select the desired subset and create a node component named STRESS before running the **ADAMS** command macro. For example, you may want to select exterior nodes for the purpose of visualization in the ADAMS program.

The default filename for the modal neutral file is `Jobname.MNF`. In interactive (GUI) mode, you can specify a filename other than `Jobname.MNF`. In batch mode, there is no option to change the filename, and the modal neutral file is always written to `JobnameMNF`.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ADAMS.html
