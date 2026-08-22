---
apdl: "LAYERP26"
method: layerp26
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.controls.Controls.layerp26
generated: 2026-08-22
tags: [mapdl-command]
---

# LAYERP26

PyMAPDL: `mapdl.layerp26(num='', **kwargs)`

Specifies the element layer for which data are to be stored.

## Parameters

**num**

Layer-processing mode:

- `N` - The layer number to process. The default value is 1.

## Notes

Defines the element layer for which results data are to be stored for postprocessing. Applies to stress and strain data for layered elements `SHELL181`, `SOLID185`, `SOLID186`, `SOLSH190`, `SHELL208`, `SHELL209`, `SHELL281`, `REINF265`, and `ELBOW290`.

The [[shell|SHELL]] command can be used (for shell elements) to specify a location (TOP, MID, BOT) within the layer for selection on the [[esol|ESOL]] command. Transverse shear stresses for MID are linearly averaged from TOP and BOT, and do not reflect a parabolic distribution. Setting KEYOPT(8) = 2 for `SHELL181`, `SHELL208`, `SHELL209`, `SHELL281`, and `ELBOW290` writes the mid- surface values directly to the results file and yields more accurate values than linear averaging.

That this command cannot be used for energy output, as energy is a per-element quantity.

When using the **LAYERP26** command with `SHELL181`, `SOLID185`, `SOLID186`, `SOLSH190`, `SHELL208`, or `SHELL209`, KEYOPT(8) must be set to 1 (or 2 for `SHELL181`, `SHELL208`, `SHELL209`, `SHELL281`, and `ELBOW290` ) in order to store results for all layers.

In POST26, the [[esol|ESOL]] data stored is based on the active **LAYERP26** specification at the time the data is stored. To store data at various specifications (for example, layers 2 and 5), issue a [[store|STORE]] command before each new specification.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LAYERP26.html
