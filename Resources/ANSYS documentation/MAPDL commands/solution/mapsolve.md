---
apdl: "MAPSOLVE"
method: mapsolve
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.rezoning.Rezoning.mapsolve
generated: 2026-08-22
tags: [mapdl-command]
---

# MAPSOLVE

PyMAPDL: `mapdl.mapsolve(maxsbstep='', **kwargs)`

Maps solved node and element solutions from an original mesh to a new mesh.

## Parameters

**maxsbstep**: The maximum number of substeps for rebalancing the residuals. The default value is 5.

## Notes

Used during the [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html) process, the **MAPSOLVE** command maps solved node and element solutions from the original mesh to the new mesh and achieves equilibrium based on the new mesh.

Additional substeps are necessary to reduce the residuals to zero.

During the rebalancing stage, the external loads and time remain unchanged.

The **MAPSOLVE** command is valid only for rezoning ( [[rezone|REZONE]] ). Distributed-Memory Parallel (DMP) Restriction This command is not supported in a DMP solution.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MAPSOLVE.html
