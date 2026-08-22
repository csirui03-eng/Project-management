---
apdl: "SHELL"
method: shell
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.controls.Controls.shell
generated: 2026-08-22
tags: [mapdl-command]
---

# SHELL

PyMAPDL: `mapdl.shell(loc='', **kwargs)`

Selects a shell element or shell layer location for results output.

## Parameters

**loc**

Location within shell element (or layer) to obtain stress results:

- `TOP` - Top of shell element (or layer) (default).
- `MID` - Middle of shell element (or layer). The default method averages the TOP and BOT values to obtain a mid value. Setting KEYOPT(8) = 2 for `SHELL181`, `SHELL208`, `SHELL209`, `SHELL281`, and `ELBOW290` uses MID results obtained directly from the results file.
- `BOT` - Bottom of shell element (or layer).

## Notes

Selects the location within a shell element (or a shell layer) for results output (nodal stresses, strains, etc.). Applies to POST1 selects, sorts, and output ( [[nsel|NSEL]], [[nsort|NSORT]], [[prnsol|PRNSOL]], [[plnsol|PLNSOL]], [[prpath|PRPATH]], [[plpath|PLPATH]], etc.), and is used for storage with the POST26 [[esol|ESOL]] command. For example, **SHELL**,TOP causes item S of the POST1 [[prnsol|PRNSOL]] command or the POST26 [[esol|ESOL]] command to be the stresses at the top of the shell elements. For layered shell elements, use the [[layer|LAYER]] (POST1) or [[layerp26|LAYERP26]] (POST26) command to select the layer. The **SHELL** command does not apply to the layered thermal shell elements, `SHELL131` and `SHELL132`.

For PowerGraphics ( [[graphics|/GRAPHICS]],POWER), the **SHELL**,MID command affects both the printed output and the displayed results, while the **SHELL** (TOP or BOT) command prints and displays both the top and bottom layers simultaneously. Note that [[cycexpand|/CYCEXPAND]],ON automatically turns on PowerGraphics; however, for cyclic mode-superposition harmonic postprocessing ( [[cycfiles|CYCFILES]] ), the **SHELL** command prints and displays only the requested layer.

In POST26, the [[esol|ESOL]] data stored is based on the active **SHELL** specification at the time the data is stored. To store data at various specifications (for example, stresses at the top and bottom locations), issue a [[store|STORE]] command before each new specification.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SHELL.html
