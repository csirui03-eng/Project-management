---
apdl: "DDASPEC"
method: ddaspec
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.ddaspec
generated: 2026-08-22
tags: [mapdl-command]
---

# DDASPEC

PyMAPDL: `mapdl.ddaspec(keyref='', shptyp='', mountloc='', deftyp='', amin='', **kwargs)`

Specifies the shock spectrum computation constants for DDAM analysis.

## Parameters

**keyref**

Key for reference catalog:

- `1` - The spectrum computation constants are based on NRL-1396 (default). For more information, see [Dynamic Design Analysis Method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc7.html#eq1bf15231-590e-4b5a-a30a-aa31e15bf78f)

**shptyp**

Select the ship type:

- `SUBM` - Submarine
- `SURF` - Surface ship

**mountloc**

Select the mounting location:

- `HULL` - Hull mounting location. These structures are mounted directly to basic hull structures like frames, structural bulkheads below the water line, and shell plating above the water line.
- `DECK` - Deck mounting location. These structures are mounted directly to decks, non-structural bulkheads, or to structural bulkheads above the water line.
- `SHEL` - Shell plating mounting location. These structures are mounted directly to shell plating below the water line without intervening foundations.

**deftyp**

Select the deformation type:

- `ELAS` - Elastic deformation (default)
- `PLAS` - Elastic-plastic deformation

**amin**: Minimum acceleration value. It defaults to 6g, where g is the acceleration due to gravity.

## Notes

The excitation along one of the fore and aft, vertical or athwartship directions is required to calculate the spectrum coefficients. Issue the [[sed|SED]] command before issuing **DDASPEC**. For example, if you want to apply the excitation along the fore and aft direction, you should specify `SEDX` = 1.0 on [[sed|SED]]. Similarly, for excitation along vertical or athwartship direction, specify `SEDY` = 1.0 or `SEDZ` = 1.0, respectively, on [[sed|SED]].

[[addam|ADDAM]] and [[vddam|VDDAM]] may alternatively be used to calculate spectrum coefficients.

In order to perform a DDAM spectrum analysis using a units system other than BIN (default), you must specify the units system complying with the mass and length units of the model using the [[units|/UNITS]] command. Issue the [[units|/UNITS]] command before defining the shock spectrum computation constants ( **DDASPEC** ). The DDASPEC command is not supported with the user-defined units system ( `Label` = USER on [[units|/UNITS]] ).

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DDASPEC.html
