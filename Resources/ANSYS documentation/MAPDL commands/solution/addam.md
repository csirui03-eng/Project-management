---
apdl: "ADDAM"
method: addam
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.addam
generated: 2026-08-22
tags: [mapdl-command]
---

# ADDAM

PyMAPDL: `mapdl.addam(af='', aa='', ab='', ac='', ad='', amin='', **kwargs)`

Specifies the acceleration spectrum computation constants for the analysis of shock resistance of shipboard structures.

## Parameters

**af**: Direction-dependent acceleration coefficient for elastic or elastic-plastic analysis option (default = 0).

**aa**, **ab**, **ac**, **ad**: Coefficients for the DDAM acceleration spectrum equations. Default for these coefficients is zero.

**amin**: Minimum acceleration value. It defaults to 6g, where g is the acceleration due to gravity.

## Notes

This command specifies acceleration coefficients to analyze shock resistance of shipboard equipment. These coefficients are used to compute mode coefficients according to the equations given in [Dynamic Design Analysis Method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc7.html#eq1bf15231-590e-4b5a-a30a-aa31e15bf78f) [[vddam|VDDAM]] and [[sed|SED]] commands, is used with the spectrum ( [[antype|ANTYPE]],SPECTR) analysis as a special purpose alternative to the [[sv|SV]], [[freq|FREQ]], and [[svtyp|SVTYP]] commands.

In order to perform a DDAM spectrum analysis using a units system other than BIN (default), you must specify the units system complying with the mass and length units of the model using the [[units|/UNITS]] command. Issue the [[units|/UNITS]] command before defining the shock spectrum computation constants ( **ADDAM** ). The **ADDAM** command is not supported with the user-defined unite system ( `Label` = USER on [[units|/UNITS]] ).

[[ddaspec|DDASPEC]] may alternatively be used to calculate spectrum coefficients.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ADDAM.html
