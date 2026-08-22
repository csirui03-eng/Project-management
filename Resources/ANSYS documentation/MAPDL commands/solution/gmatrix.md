---
apdl: "GMATRIX"
method: gmatrix
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.gmatrix
generated: 2026-08-22
tags: [mapdl-command]
---

# GMATRIX

PyMAPDL: `mapdl.gmatrix(symfac='', condname='', numcond='', matrixname='', **kwargs)`

Performs electric field solutions and calculates the self and mutual conductance between multiple conductors.

## Parameters

**symfac**: Geometric symmetry factor. Conductance values are scaled by this factor which represents the fraction of the total device modeled. Defaults to 1.

**condname**: Alphanumeric prefix identifier used in defining named conductor components.

**numcond**: Total number of components. If a ground is modeled, it is to be included as a component.

**matrixname**: Array name for computed conductance matrix. Defaults to GMATRIX.

## Notes

To invoke the **GMATRIX** macro, the exterior nodes of each conductor must be grouped into individual components using the [[cm|CM]] command. Each set of independent components is assigned a component name with a common prefix followed by the conductor number. A conductor system with a ground must also include the ground nodes as a component. The ground component is numbered last in the component name sequence.

A ground conductance matrix relates current to a voltage vector. A ground matrix cannot be applied to a circuit modeler. The lumped conductance matrix is a combination of lumped "arrangements" of voltage differences between conductors. Use the lumped conductance terms in a circuit modeler to represent conductances between conductors.

Enclose all name-strings in single quotes in the **GMATRIX** command line.

**GMATRIX** works with the following elements:

- `SOLID5` (KEYOPT(1) = 9)
- `SOLID98` (KEYOPT(1) = 9)
- `LINK68`
- `PLANE230`
- `SOLID231`
- `SOLID232`

This command is available from the menu path shown below only if existing results are available.

This command does not support multiframe restarts Distributed-Memory Parallel (DMP) Restriction This command is not supported in a DMP solution.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GMATRIX.html
