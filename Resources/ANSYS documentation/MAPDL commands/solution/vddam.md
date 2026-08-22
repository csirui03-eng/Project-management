---
apdl: "VDDAM"
method: vddam
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.vddam
generated: 2026-08-22
tags: [mapdl-command]
---

# VDDAM

PyMAPDL: `mapdl.vddam(vf='', va='', vb='', vc='', **kwargs)`

Specifies the velocity spectrum computation constants for the analysis of shock resistance of shipboard structures.

## Parameters

**vf**: Direction-dependent velocity coefficient for elastic or elastic-plastic analysis option (Default = 0).

**va**, **vb**, **vc**: Coefficients for the DDAM velocity spectrum equations. See [Dynamic Design Analysis Method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc7.html#eq1bf15231-590e-4b5a-a30a-aa31e15bf78f)

## Notes

This command specifies velocity coefficients to analyze shock resistance of shipboard equipment. These coefficients are used to compute mode coefficients according to the equations given in [Dynamic Design Analysis Method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc7.html#eq1bf15231-590e-4b5a-a30a-aa31e15bf78f) [[addam|ADDAM]] and [[sed|SED]] commands, is used with the spectrum ( [[antype|ANTYPE]],SPECTR) analysis as a special purpose alternative to the [[sv|SV]], [[freq|FREQ]], and [[svtyp|SVTYP]] commands.

In order to perform a DDAM spectrum analysis using a units system other than BIN (default), you must specify the units system complying with the mass and length units of the model using the [[units|/UNITS]] command. Issue the [[units|/UNITS]] command before defining the shock spectrum computation constants ( **VDDAM** ). The **VDDAM** command is not supported with the user-defined units system ( `Label` = USER on the [[units|/UNITS]] command).

[[ddaspec|DDASPEC]] may alternatively be used to calculate spectrum coefficients.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VDDAM.html
