---
apdl: "PFACT"
method: pfact
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.pfact
generated: 2026-08-22
tags: [mapdl-command]
---

# PFACT

PyMAPDL: `mapdl.pfact(tblno='', excit='', parcor='', **kwargs)`

Calculates participation factors for the PSD or multi-point response spectrum table.

## Parameters

**tblno**: Input PSD (Power Spectral Density) table number for which participation factors are to be calculated.

**excit**

Label defining the location of excitation:

- `BASE` - Base excitation (default).
- `NODE` - Nodal excitation.

**parcor**

Label defining excitation type (applies only to [[spopt|SPOPT]],PSD analysis). Used only when partially correlated excitation is due to wave propagation or spatial correlation. Defaults to partially correlated excitation as defined by [[coval|COVAL]] and [[qdval|QDVAL]] commands.

- `WAVE` - Excitation defined by [[psdwav|PSDWAV]] command.
- `SPAT` - Excitation defined by [[psdspl|PSDSPL]] command.

## Notes

Calculates the participation factors for a particular PSD or multi-point response spectrum table defined with the [[psdval|PSDVAL]] or [[spval|SPVAL]] command. The `Jobname.DB` file must contain modal solution data in order for this command to calculate the participation factor. There must be a **PFACT** command for each excitation spectrum. You are limited to 300 excitations.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PFACT.html
