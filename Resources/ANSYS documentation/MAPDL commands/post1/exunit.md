---
apdl: "EXUNIT"
method: exunit
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.exunit
generated: 2026-08-22
tags: [mapdl-command]
---

# EXUNIT

PyMAPDL: `mapdl.exunit(ldtype='', load='', untype='', name='', **kwargs)`

Specifies the interface data unit labels to be written to the profile file from Mechanical APDL to Ansys CFX transfer.

## Parameters

**ldtype**

Load type:

- `SURF` - Surface load.
- `VOLU` - Volumetric load.

**load**

Surface loads:

- `DISP` - Displacement in a static analysis. Mode shape in a modal analysis.
- `TIME` - Time. The unit for frequency is the inverse of the unit for time.
- `MASS` - Mass.
- `TEMP` - Temperature.
- `HFLU` - Heat flux.

Volumetric loads:

- `DISP` - Displacement.
- `FORC` - Force
- `HGEN` - Heat generation

**untype**

Unit type:

- `COMM` - Predefined unit
- `USER` - User-specified unit

**name**

Commonly used predefined unit name or user-specified unit name.

- `SI` - International System of units (meter-kilogram-second) (default)
- `FT` - English System of units (feet-pound-second)

In the SI system, surface loads are in units of m for DISP, degrees K for TEMP, and W/m <sup>2</sup> for HFLU; volumetric loads are in units of m for DISP, N/m <sup>3</sup> for FORC, and W/m <sup>3</sup> for HGEN.

In the English system, surface loads are in units of ft for DISP, degrees F for TEMP, and BTU/sec-ft <sup>2</sup> for HFLU; volumetric loads are in units of ft for DISP, pdl/ft <sup>3</sup> for FORC, and BTU/sec-ft <sup>3</sup> for HGEN. A pdl is a poundal, and 32.174 pdl = 1 lbf.

## Notes

This command only specifies which unit labels are to be written to the file when the [[exprofile|EXPROFILE]] is issued. It does not perform unit conversions.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EXUNIT.html
