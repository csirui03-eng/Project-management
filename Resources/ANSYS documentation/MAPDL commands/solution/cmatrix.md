---
apdl: "CMATRIX"
method: cmatrix
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.cmatrix
generated: 2026-08-22
tags: [mapdl-command]
---

# CMATRIX

PyMAPDL: `mapdl.cmatrix(symfac='', condname='', numcond='', grndkey='', capname='', **kwargs)`

Performs electrostatic field solutions and calculates the self and mutual capacitances between multiple conductors.

## Parameters

**symfac**: Geometric symmetry factor. Capacitance values are scaled by this factor which represents the fraction of the total device modeled. Defaults to 1.

**condname**: Alpha-numeric prefix identifier used in defining named conductor components.

**numcond**: Total Number of Components. If a ground is modeled, it is to be included as a component. If a ground is not modeled, but infinite elements are used to model the far-field ground, a named component for the far-field ground is not required.

**grndkey**

Ground key:

- `0` - Ground is one of the components, which is not at infinity.
- `1` - Ground is at infinity (modeled by infinite elements).

**capname**: Array name for computed capacitance matrix. Defaults to **CMATRIX**.

## Notes

To invoke the **CMATRIX** macro, the exterior nodes of each conductor must be grouped into individual components using the [[cm|CM]] command. Each set of independent components is assigned a component name with a common prefix followed by the conductor number. A conductor system with a ground must also include the ground nodes as a component. The ground component is numbered last in the component name sequence.

A ground capacitance matrix relates charge to a voltage vector. A ground matrix cannot be applied to a circuit modeler. The lumped capacitance matrix is a combination of lumped "arrangements" of voltage differences between conductors. Use the lumped capacitance terms in a circuit modeler to represent capacitances between conductors.

Enclose all name-strings in single quotes in the **CMATRIX** command line.

See the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html) for details.

This command does not support multiframe restarts.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CMATRIX.html
