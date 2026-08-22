---
apdl: "EDPL"
method: edpl
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edpl
generated: 2026-08-22
tags: [mapdl-command]
---

# EDPL

PyMAPDL: `mapdl.edpl(ldnum='', **kwargs)`

Plots a time dependent load curve in an explicit dynamic analysis.

## Parameters

**ldnum**: Load number.

## Notes

EDPL invokes an ANSYS macro which produces a load vs. time graph for a load defined with the EDLOAD command. Only one load curve can be plotted at a time. Use EDLOAD,LIST to obtain a list of loads and corresponding load numbers.

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
