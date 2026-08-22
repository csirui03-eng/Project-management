---
apdl: "MONITOR"
method: monitor
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.monitor
generated: 2026-08-22
tags: [mapdl-command]
---

# MONITOR

PyMAPDL: `mapdl.monitor(var='', node='', lab='', **kwargs)`

Controls contents of variable fields in the nonlinear solution monitor file.

## Parameters

**var**: One of four variable field numbers in the monitor file whose contents can be specified by the Lab field. Valid arguments are integers 1, 2, 3, or 4. See Notes section for default values.

**node**: The node number for which information is monitored in the specified `VAR` field. In the GUI, if `Node` = P, graphical picking is enabled. If blank, the monitor file lists the maximum value of the specified quantity (Lab field) for the entire structure.

**lab**: The solution quantity to be monitored in the specified `VAR` field. Valid labels for solution quantities are UX, UY, and UZ (displacements); ROTX, ROTY, and ROTZ (rotations); and TEMP (temperature). Valid labels for reaction force are FX, FY, and FZ (structural force) and MX, MY, and MZ (structural moment). Valid label for heat flow rate is HEAT. For defaults see the Notes section.

## Notes

The monitor file always has an extension of **.mntr**, and takes its file name from the specified `Jobname`. If no `Jobname` is specified, the file name defaults to `file`.

You must issue this command once for each solution quantity you want to monitor at a specified node at each load step. You cannot monitor a reaction force during a linear analysis. The variable field contents can be redefined at each load step by reissuing the command. The monitored quantities are appended to the file for each load step.

Reaction forces reported in the monitor file may be incorrect if the degree of freedom of the specified node is involved in externally defined coupling ( [[cp|CP]] command) or constraint equations ( [[ce|CE]] command), or if the program has applied constraint equations internally to the node.

The following example shows the format of a monitor file. Note that the file only records the solution substep history when a substep is convergent.

font TypeSize="8pt"? SOLUTION HISTORY INFORMATION FOR JOB: file.mntr LOAD SUB- NO. NO. TOTL INCREMENT TOTAL VARIAB 1 VARIAB 2 VARIAB 3 VARIAB 4 STEP STEP ATTMP ITER ITER TIME/LFACT TIME/LFACT MONITOR MONITOR MONITOR MONITOR Wall MxDs FY MxRe 1 1 1 5 5 0.36000E-01 0.36000E-01 0.0000 -0.47242E-01 -0.13783E-01 0.22670E-04 1 2 1 3 8 0.36000E-01 0.72000E-01 0.0000 -0.91552E-01 -0.27269E-01 0.38849E-03 1 3 1 4 12 0.54000E-01 0.12600 0.0000 -0.15161 -0.43972E-01 0.25235E-03 1 4 1 3 15 0.81000E-01 0.20700 0.0000 -0.22926 -0.65119E-01 0.11131E-03 1 5 1 5 20 0.12150 0.32850 0.0000 -0.34188 -0.93242E-01 0.12267E-02 1 6 1 4 24 0.12150 0.45000 0.0000 -0.46860 -0.11992 0.22689E-02 1 7 1 5 29 0.18000 0.63000 0.0000 -0.65720 -0.16217 0.12111E-03 1 8 2 7 38 0.63000E-01 0.69300 0.0000 -0.72594 -0.46582 0.67121E-02 1 9 1 11 49 0.63000E-01 0.75600 0.0000 -0.79976 -1.1070 0.29302E-02 1 10 1 10 59 0.63000E-01 0.81900 0.0000 -0.87073 -1.8708 0.95828E-02 1 11 1 18 77 0.81000E-01 0.90000 0.0000 -0.90000 -269.31 0.73911/\_font? The following details the contents of the various fields in the monitor file:

- `LOAD STEP` - The current load step number.
- `SUBSTEP` - The current substep (time step) number.
- `NO. ATTEMPT` - The number of attempts made in solving the current substep. This number is equal to the number of failed attempts (bisections) plus one (the successful attempt).
- `NO. ITER` - The number of iterations used by the last successful attempt.
- `TOTL. ITER` - Total cumulative number of iterations (including each iteration used by a bisection).
- `INCREMENT` -
- `TIME/LFACT` - Time or load factor increments for the current substep.
- `TOTAL TIME/LFACT` - Total time (or load factor) for the last successful attempt in the current substep.
- `VARIAB 1` - Variable field 1. By default, this field lists the elapsed (or wall clock) times used up to (but not including) the current substep.
- `VARIAB 2` - Variable field 2. In this example, the field is reporting the MZ value. By default, this field lists the maximum displacement in the entire structure.
- `VARIAB 3` - Variable field 3. In this example, the field is reporting the FY value of a certain node. By default, this field reports the maximum equivalent plastic strain increment in the entire structure.
- `VARIAB 4` - Variable field 4. By default, this field reports the maximum residual force in the entire structure.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MONITOR.html
