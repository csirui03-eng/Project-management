---
apdl: "EDCTS"
method: edcts
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edcts
generated: 2026-08-22
tags: [mapdl-command]
---

# EDCTS

PyMAPDL: `mapdl.edcts(dtms='', tssfac='', **kwargs)`

Specifies mass scaling and scale factor of computed time step for an

explicit dynamics analysis.

## Parameters

**dtms**: Time step size for mass scaled solutions (defaults to 0).

**tssfac**: Scale factor for computed time step. Defaults to 0.9; if high explosives are used, the default is lowered to 0.67.

## Notes

If DTMS is positive, the same time step size will be used for all elements and mass scaling will be done for all elements. Therefore, positive values should only be used if inertial effects are insignificant.

If DTMS is negative, mass scaling is applied only to elements whose calculated time step size is smaller than DTMS. Negative values should only be used in transient analyses if the mass increases are insignificant.

In order to use mass scaling in an explicit dynamic small restart analysis (EDSTART,2) or full restart analysis (EDSTART,3), mass scaling must have been active in the original analysis. The time step and scale factor used in the original analysis will be used by default in the restart. You can issue EDCTS in the restart analysis to change these settings.

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
