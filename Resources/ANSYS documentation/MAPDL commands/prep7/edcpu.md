---
apdl: "EDCPU"
method: edcpu
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edcpu
generated: 2026-08-22
tags: [mapdl-command]
---

# EDCPU

PyMAPDL: `mapdl.edcpu(cputime='', **kwargs)`

Specifies CPU time limit for an explicit dynamics analysis.

## Parameters

**cputime**: CPU time limit (in seconds) for the current phase of the analysis (defaults to 0). If CPUTIME = 0, no CPU time limit is set. CPUTIME values below 0 are not allowed.

## Notes

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
