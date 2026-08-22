---
apdl: "EDRST"
method: edrst
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edrst
generated: 2026-08-22
tags: [mapdl-command]
---

# EDRST

PyMAPDL: `mapdl.edrst(nstep='', dt='', **kwargs)`

Specifies the output interval for an explicit dynamic analysis.

## Parameters

**nstep**: Number of steps at which output is written to the results file (Jobname.RST). Defaults to 100. When you specify NSTEP, NSTEP+2 results are written to the Jobname.RST file. The time interval between output is TIME / NSTEP, where TIME is the analysis end-time specified on the TIME command. Do not specify a value of NSTEP = 0.

**dt**: Time interval at which output is written to the results file (Jobname.RST). If NSTEP is input, DT is ignored.

## Notes

You can use NSTEP or DT to specify the output interval to be used for Jobname.RST. You should not specify both quantities; if both are input, NSTEP will be used.

In an explicit dynamic small restart (EDSTART,2) or full restart analysis (EDSTART,3), the EDRST setting will default to the NSTEP or DT value used in the original analysis. You can issue EDRST in the restart to change this setting.

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
