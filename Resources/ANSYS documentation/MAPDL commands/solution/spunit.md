---
apdl: "SPUNIT"
method: spunit
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.spunit
generated: 2026-08-22
tags: [mapdl-command]
---

# SPUNIT

PyMAPDL: `mapdl.spunit(tblno='', type_='', gvalue='', keyinterp='', **kwargs)`

Defines the type of multi-point response spectrum.

## Parameters

**tblno**: Input table number.

**type_**

Label identifying the type of spectrum:

- `DISP` - Displacement spectrum ( [[spval|SPVAL]] values interpreted as displacements with units of length).
- `VELO` - Velocity spectrum ( [[spval|SPVAL]] values interpreted as velocities with units of length/time).
- `ACEL` - Acceleration spectrum ( [[spval|SPVAL]] values interpreted as accelerations with units of length/time <sup>2</sup> ).
- `ACCG` - Acceleration spectrum ( [[spval|SPVAL]] values interpreted as accelerations with units of g/time <sup>2</sup> ).
- `FORC` - Force spectrum.
- `PRES` - Pressure spectrum.

**gvalue**: Value of acceleration due to gravity in any arbitrary units for Type=ACCG table. Default is 386.4 in/sec <sup>2</sup>.

**keyinterp**

Key to activate or deactivate the linear interpolation between input response spectrum points and input response spectrum curves:

- `0 (OFF or NO)` - Deactivate linear and use logarithmic interpolation. This value is the default.
- `1 (ON or YES)` - Activate linear interpolation.

## Notes

Defines the type of multi-point response spectrum defined by the [[spfreq|SPFREQ]] and [[spval|SPVAL]] commands.

Force ( **FORC** ) and pressure ( **PRES** ) type spectra can be used only as a nodal excitation.

`GVALUE` is valid only when `Type` = ACCG is specified. A zero or negative value cannot be used. A parameter substitution can also be performed.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SPUNIT.html
