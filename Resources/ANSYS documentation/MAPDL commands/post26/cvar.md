---
apdl: "CVAR"
method: cvar
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.special_purpose.SpecialPurpose.cvar
generated: 2026-08-22
tags: [mapdl-command]
---

# CVAR

PyMAPDL: `mapdl.cvar(ir='', ia='', ib='', itype='', datum='', name='', **kwargs)`

Computes covariance between two quantities.

## Parameters

**ir**: Arbitrary reference number assigned to the resulting variable (2 to `NV` ( [[numvar|NUMVAR]] )). If this number is the same as for a previous variable, the previous variable will be overwritten with this result.

**ia**, **ib**: Reference numbers of the two variables to be operated on. If only one, leave `IB` blank.

**itype**

Defines the type of response PSD to be calculated:

- `0,1` - Displacement (default).
- `2` - Velocity.
- `3` - Acceleration.

**datum**

Defines the reference with respect to which covariance is to be calculated:

- `1` - Absolute value.
- `2` - Relative to base (default).

**name**: Thirty-two character name for identifying the variable on listings and displays. Embedded blanks are compressed upon output.

## Notes

This command computes the covariance value for the variables referenced by the reference numbers `IA` and `IB`. If `DATUM` = 2, the variable referenced by `IR` will contain the individual modal contributions (that is, the dynamic or relative values). If `DATUM` = 1, the variable referenced by `IR` will contain the modal contributions followed by the contributions of pseudo- static and covariance between dynamic and pseudo-static responses. `File.PSD` must be available for the calculations to occur.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CVAR.html
