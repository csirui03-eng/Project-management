---
apdl: "SCOPT"
method: scopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.scopt
generated: 2026-08-22
tags: [mapdl-command]
---

# SCOPT

PyMAPDL: `mapdl.scopt(tempdepkey='', mappingkey='', **kwargs)`

Specifies System Coupling options.

## Parameters

**tempdepkey**

Temperature-dependent behavior key based on the convection coefficient:

- `YES` - A negative convection coefficient, - `N`, is assumed to be a function of temperature and is determined from the HF property table for material `N` ( [[mp|MP]] command). This is the default behavior.
- `NO` - A negative convection coefficient, - `N`, is used as is in the convection calculation.

**mappingkey**

Controls whether midside nodes of higher-order elements are used for mapping on System Coupling interfaces:

- `YES` - Both corner and midside nodes are used (default).
- `NO` - Only corner nodes are used.

## Notes

By default in the Mechanical APDL program, a negative convection coefficient value triggers temperature- dependent behavior. In some one-way CFD to Mechanical APDL thermal simulations, it is desirable to allow convection coefficients to be used as negative values. To do so, issue the command **SCOPT**,NO.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SCOPT.html
