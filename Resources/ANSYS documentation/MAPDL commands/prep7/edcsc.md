---
apdl: "EDCSC"
method: edcsc
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edcsc
generated: 2026-08-22
tags: [mapdl-command]
---

# EDCSC

PyMAPDL: `mapdl.edcsc(key='', **kwargs)`

Specifies whether to use subcycling in an explicit dynamics analysis.

## Parameters

**key**

Subcycling key:

OFF - Do not use subcycling (default).

ON - Use subcycling.

## Notes

Subcycling can be used to speed up an analysis when element sizes within a model vary significantly. Relatively small elements will result in a small time step size. When subcycling is on, the minimum time step size is increased for the smallest elements.

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
