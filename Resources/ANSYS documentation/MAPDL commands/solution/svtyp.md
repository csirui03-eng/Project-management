---
apdl: "SVTYP"
method: svtyp
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.svtyp
generated: 2026-08-22
tags: [mapdl-command]
---

# SVTYP

PyMAPDL: `mapdl.svtyp(ksv='', fact='', keyinterp='', **kwargs)`

Defines the type of single-point response spectrum.

## Parameters

**ksv**

Response spectrum type:

- `0` - Seismic velocity response spectrum loading (SV values interpreted as velocities with units of length/time).
- `1` - Force response spectrum loading (SV values interpreted as force amplitude multipliers).
- `2` - Seismic acceleration response spectrum loading (SV values interpreted as accelerations with units of length/time <sup>2</sup> ).
- `3` - Seismic displacement response spectrum loading (SV values interpreted as displacements with units of length).

**fact**: Scale factor applied to spectrum values (defaults to 1.0). Values are scaled when the solution is initiated ( [[solve|SOLVE]] ). Database values remain the same.

**keyinterp**

Key to activate or deactivate the linear interpolation between input response spectrum points and input response spectrum curves:

- `0 (OFF, or NO)` - Deactivate linear and use logarithmic interpolation. This value is the default.
- `1 (ON, or YES)` - Activate linear interpolation.

## Notes

Defines the type of single-point response spectrum ( [[spopt|SPOPT]] ). The seismic excitation direction is defined with the [[sed|SED]] command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SVTYP.html
