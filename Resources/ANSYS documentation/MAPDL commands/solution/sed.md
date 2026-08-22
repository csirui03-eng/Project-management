---
apdl: "SED"
method: sed
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.sed
generated: 2026-08-22
tags: [mapdl-command]
---

# SED

PyMAPDL: `mapdl.sed(sedx='', sedy='', sedz='', cname='', **kwargs)`

Defines the excitation direction for response spectrum and PSD analyses.

## Parameters

**sedx**, **sedy**, **sedz**: Global Cartesian coordinates of a point that defines a line (through the origin) corresponding to the excitation direction. For example: 0.0, 1.0, 0.0 defines global Y as the spectrum direction.

**cname**: The component name corresponding to the group of excited nodes. Only applies to base excitation multi-point response spectrum analysis ( [[spopt|SPOPT]], MPRS) and power spectral density analysis ( [[spopt|SPOPT]], PSD). Defaults to no component.

## Notes

In single-point response spectrum analysis ( [[spopt|SPOPT]],SPRS), the excitation direction without rocking ( [[rock|ROCK]] ) is normalized to one so that the `SEDX`, `SEDY`, and `SEDZ` values do not scale the spectrum. The excitation direction with rocking is not normalized. The `SEDX`, `SEDY`, and `SEDZ` values must be consistent with the linear components of `OMX`, `OMY`, and `OMZ` values on the [[rock|ROCK]] command. The calculated direction then scales the spectrum. For more information, see [Participation Factors and Mode Coefficients](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc7.html#eqe483f2f2-aaa1-4080-a835-10c0e1e18f57).

In multi-point response spectrum analysis ( [[spopt|SPOPT]],MPRS) and power spectral density analysis ( [[spopt|SPOPT]],PSD), the excitation direction is normalized to one so that the `SEDX`, `SEDY`, and `SEDZ` values do not scale the spectrum. The component name ( `Cname` ) is required. The constraints corresponding to the excitation direction are applied to the component nodes.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SED.html
