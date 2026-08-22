---
apdl: "EDHTIME"
method: edhtime
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edhtime
generated: 2026-08-22
tags: [mapdl-command]
---

# EDHTIME

PyMAPDL: `mapdl.edhtime(nstep='', dt='', **kwargs)`

Specifies the time-history output interval for an explicit dynamics

analysis.

## Parameters

**nstep**: Number of steps at which output is written to the time-history file, Jobname.HIS, and the ASCII output files. Defaults to 1000. The time increment between output is TIME / NSTEP, where TIME is the analysis end-time specified on the TIME command.

**dt**: Time interval at which output is written to the time-history file, Jobname.HIS, and the ASCII output files. If NSTEP is input, DT is ignored.

## Notes

EDHTIME controls the number of steps at which output will be written to the time-history file, Jobname.HIS (see the EDHIST command), and any ASCII files requested on the EDOUT command. You can use NSTEP or DT to specify the output interval. You should not specify both quantities; if both are input, NSTEP will be used.

In an explicit dynamic small restart (EDSTART,2) or full restart analysis (EDSTART,3), the EDHTIME setting will default to the NSTEP or DT value used in the original analysis. You can issue EDHTIME in the restart to change this setting.

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
