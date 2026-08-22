---
apdl: "PSDUNIT"
method: psdunit
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.psdunit
generated: 2026-08-22
tags: [mapdl-command]
---

# PSDUNIT

PyMAPDL: `mapdl.psdunit(tblno='', type_='', gvalue='', **kwargs)`

Defines the type of input PSD.

**Command default:**

Acceleration (ACEL) spectrum (acceleration <sup>2</sup> /Hz).

## Parameters

**tblno**: Input table number.

**type_**

Label identifying the type of spectrum:

- `DISP` - Displacement spectrum (in terms of displacement <sup>2</sup> /Hz ).
- `VELO` - Velocity spectrum (in terms of velocity <sup>2</sup> /Hz ).
- `ACEL` - Acceleration spectrum (in terms of acceleration <sup>2</sup> /Hz ).
- `ACCG` - Acceleration spectrum (in terms of g <sup>2</sup> /Hz ).
- `FORC` - Force spectrum (in terms of force <sup>2</sup> /Hz ).
- `PRES` - Pressure spectrum (in terms of pressure <sup>2</sup> /Hz ).

**gvalue**: Value of acceleration due to gravity in any arbitrary units for Type=ACCG. Default is 386.4 in/sec <sup>2</sup>.

## Notes

Defines the type of PSD defined by the [[psdval|PSDVAL]], [[coval|COVAL]], and [[qdval|QDVAL]] commands.

Force (FORC) and pressure (PRES) type spectra can be used only as a nodal excitation.

`GVALUE` is valid only when type ACCG is specified. A zero or negative value cannot be used. A parameter substitution can also be performed.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSDUNIT.html
