---
apdl: "LAYER"
method: layer
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.controls.Controls.layer
generated: 2026-08-22
tags: [mapdl-command]
---

# LAYER

PyMAPDL: `mapdl.layer(num='', **kwargs)`

Specifies the element layer for which data are to be processed.

## Parameters

**num**

Layer-processing mode:

- `N` - The layer number to process. The default value is 0.
- `FCMAX` - Processes the layer with the largest failure criteria.

## Notes

Specifies the element layer for which results data are to be listed, plotted, or otherwise processed.

Applies to stress and strain data for layered elements `SHELL181`, `SHELL281`, `ELBOW290`, `SOLID185`, `SOLID186`, `SOLSH190`, `SHELL208`, `SHELL209`, `REINF264`, and `REINF265` ; heat flux and heat gradient for `SHELL131` and `SHELL132`.

For [reinforcing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_compreinfdirectemb.html) elements, `N` is a given reinforcing member (individual reinforcing). Specifying `N` = 0 (default) or `N` = 1 selects the first reinforcing member.

The [[shell|SHELL]] command can then be used (with shell elements) to specify a location (TOP, MID, BOT) within the layer for output. (The [[shell|SHELL]] command does not apply to thermal shell elements `SHELL131` and `SHELL132`.) Transverse shear stresses for MID are linearly averaged from TOP and BOT, and do not reflect a parabolic distribution. Setting KEYOPT(8) = 2 for `SHELL181`, `SHELL281`, `SHELL208`, `SHELL209`, and `ELBOW290` writes the mid-surface values directly to the results file and yields more accurate values than linear averaging.

Because energy is a per-element quantity, you cannot use this command for energy output.

When using the **LAYER** command with `SHELL181`, `SOLID185`, `SOLID186`, `SOLSH190`, `SHELL208`, `SHELL209`, `SHELL281`, and `ELBOW290`, KEYOPT(8) must be set to 1 (or 2 for `SHELL181`, `SHELL281`, `ELBOW290`, `SHELL208`, and `SHELL209` ) in order to store results for all layers.

When `NUM` = FCMAX, you must provide the failure criterion input. If specifying input via the [[fc|FC]] command, all structural elements are processed. For more information, see the documentation for the [[fc|FC]] command.

Use this command with [[rsys|RSYS]],LSYS to display results in the layer coordinate system for a particular layer.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LAYER.html
