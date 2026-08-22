---
apdl: "EDDUMP"
method: eddump
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.eddump
generated: 2026-08-22
tags: [mapdl-command]
---

# EDDUMP

PyMAPDL: `mapdl.eddump(num='', dt='', **kwargs)`

Specifies output frequency for the explicit dynamic restart file

(d3dump).

## Parameters

**num**: Number of d3dump (restart) files written during the analysis (defaults to 1). When you specify NUM, the time interval between restart files is TIME / NUM, where TIME is the analysis end-time specified on the TIME command.

**dt**: Time interval at which the d3dump (restart) files are written. If NUM is input, DT is ignored.

## Notes

You can use NUM or DT to specify the time interval at which d3dump restart files will be written. You should not specify both quantities; if both are input, NUM will be used. The restart files are written sequentially as d3dump01, d3dump02, etc.

In LS-DYNA, the restart file output is specified in terms of number of time steps. Because the total number of time steps is not known until the LS-DYNA solution finishes, Mechanical APDL calculates an approximate number of time steps for the solution, and then uses NUM or DT to calculate the required LS-DYNA input. This approximated number of time steps may be different from the total number reached in LS-DYNA after the solution finishes. Therefore, the number of restart dump files or the output interval may differ slightly from what you requested using NUM or DT.

In an explicit dynamic small restart (EDSTART,2) or full restart analysis (EDSTART,3), the EDDUMP setting will default to the NUM or DT value used in the original analysis. You can issue EDDUMP in the restart to change this setting.

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
