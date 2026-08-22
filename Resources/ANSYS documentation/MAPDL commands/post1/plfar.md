---
apdl: "PLFAR"
method: plfar
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.plfar
generated: 2026-08-22
tags: [mapdl-command]
---

# PLFAR

PyMAPDL: `mapdl.plfar(lab='', option='', var1b='', var1e='', nvar1='', var2b='', var2e='', nvar2='', val1='', val2='', val3='', val4='', val5='', ldstep='', substep='', freqb='', freqe='', plottype='', logopt='', **kwargs)`

Plots pressure far fields and far-field parameters.

## Parameters

**lab**

Parameters to plot :

- `PRES` - Acoustic parameters
- `PROT` - Acoustic parameters with the y-axis rotated extrusion (not valid for 2D elements)
- `PLAT` - Acoustic parameters radiated by a vibrating structural panel (not valid for 2D elements)

**option**

Plot option, based on the specified plot parameter type:

(table not available in the PyMAPDL source, see the Ansys help page)

**var1b**, **var1e**

Starting and ending values for the first variable associated with `PlotType` as described below.

When `PlotType` = blank (default) or SPHR: Starting and ending phi (φ) angles (in degrees) in the spherical coordinate system. Defaults to 0.

When `PlotType` = PLXY: Starting and ending x value in the Cartesian coordinate system. Defaults to 0.

When `PlotType` = PLYZ: Starting and ending y value in the Cartesian coordinate system. Defaults to 0.

When `PlotType` = PLXZ: Starting and ending x value in the Cartesian coordinate system. Defaults to 0.

**nvar1**: Number of divisions between the starting and ending `VAR1` values for data computations. Defaults to 0.

**var2b**, **var2e**

Starting and ending values for the second variable associated with `PlotType` as described below.

When `PlotType` = blank (default) or SPHR: Starting and ending theta (θ) angles (in degrees) in the spherical coordinate system. Defaults to 0 for a 3D model and 90 for a 2D extrusion model.

When `PlotType` = PLXY: Starting and ending y value in the Cartesian coordinate system. Defaults to 0.

When `PlotType` = PLYZ: Starting and ending z value in the Cartesian coordinate system. Defaults to 0.

When `PlotType` = PLXZ: Starting and ending z value in the Cartesian coordinate system. Defaults to 0.

**nvar2**: Number of divisions between the starting and ending `VAR2` values for data computations. Defaults to 0.

**val1**

`VAL1` is additional input. Its meaning depends on the `PlotType` argument as described below.

When `PlotType` = blank (default) or SPHR: Radius of the sphere surface.

When `PlotType` = PLXY: Fixed z value for an X-Y plane in the Cartesian coordinate system. Defaults to 0.

When `PlotType` = PLYZ: Fixed x value for a Y-Z plane in the Cartesian coordinate system. Defaults to 0.

When `PlotType` = PLXZ: Fixed y value for an X-Z plane in the Cartesian coordinate system, Defaults to 0.

**val2**

When `Option` = SPLC, SPLP, SPAC, or SPAP: Reference rms sound pressure. Defaults to 2x10 <sup>-5</sup> Pa.

When `Option` = PWL: Reference sound power. Defaults to 1x10 <sup>-12</sup> watts.

**val3**

When `Lab` = PRES: Thickness of 2D model extrusion in the z direction (no default).

When `Lab` = PROT: Angle of the y-axis rotated extrusion model (no default).

**val4**: When `Lab` = PLAT: Mass density of acoustic fluid.

**val5**: When `Lab` = PLAT: Sound speed in acoustic fluid.

**ldstep**

Specified load step. Defaults to the load step number specified on the [[set|SET]] command, or defaults to 1 if [[set|SET]] has not been issued.

- `n` - Load step number.
- `ALL` - All load steps.

**substep**

Specified substep. Defaults to the substep number specified on the [[set|SET]] command, or defaults to ALL (all substeps at the specified load step) if [[set|SET]] has not been issued.

- `n` - Substep number.
- `ALL` - All substeps.

**freqb**

Frequency value representing one of the following:

- Beginning frequency of the frequency range ( `FREQB` to `FREQE` ) for the defined load step(s) and substeps ( `SUBSTEP` = ALL). If a `SUBSTEP` value is specified, `FREQB` is invalid.
- Central frequency of octave bands, used when `LogOpt` = OB1, OB2, OB3, OB6, OB12, or OB24 and `FREQE` is blank.

**freqe**: Ending frequency of the frequency range ( `FREQB` to `FREQE` ) for the defined load step(s) and substeps ( `SUBSTEP` = ALL). If blank, `FREQE` is set to `FREQB`. If a `SUBSTEP` value is specified, `FREQE` is invalid.

**plottype**

Type of plot:

- `ANGX` - x-y chart with angle as the x-axis variable (default).
- `FRQX` - x-y chart with frequency as the x-axis variable.
- `CONT` - Waterfall diagram of a field parameter with variables (frequency, angle).
- `MRPM` - Waterfall diagram of a field parameter with variables (frequency, RPM).
- `PLXY` - Contour plot on an X-Y plane.
- `PLYZ` - Contour plot on a Y-Z plane.
- `PLXZ` - Contour plot on an X-Z plane.
- `SPHR` - Contour plot on a sphere surface.

**logopt**

Octave bands (used only when Option = SPLC, SPLP, SPAC, SPAP, or PWL) :

- `OB0` - Narrow bands (default).
- `OB1` - Octave bands.
- `OB2` - 1/2 octave bands.
- `OB3` - 1/3 octave bands.
- `OB6` - 1/6 octave bands.
- `OB12` - 1/12 octave bands.
- `OB24` - 1/24 octave bands.

## Notes

The **PLFAR** command plots pressure far fields and far-field parameters as determined by the equivalent source principle. Use this command to plot pressure and acoustic parameters. See the [[hfsym|HFSYM]] command for the model symmetry and the [[hfang|HFANG]] command for spatial radiation angles.

Plotting acoustic parameters radiated by a vibrating structural panel ( `Lab` = PLAT) is supported by elements `SOLID185`, `SOLID186`, `SOLID187`, `SHELL181`, `SHELL281`, and `SOLSH190`. The vibration surface of the panel must be flagged by the [[sf|SF]],,MXWF command.

A maximum of ten curves can be plotted on a 2D chart.

The waterfall diagram is plotted only in Cartesian coordinates.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLFAR.html
