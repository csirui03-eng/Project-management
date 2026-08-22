---
apdl: "*AFUN"
method: afun
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.parameter_definition.ParameterDefinition.afun
generated: 2026-08-22
tags: [mapdl-command]
---

# *AFUN

PyMAPDL: `mapdl.afun(lab='', **kwargs)`

Specifies units for angular functions in parameter expressions.

## Parameters

**lab**

Specifies the units to be used:

- `RAD` - Use radians for input and output of parameter angular functions (default).
- `DEG` - Use degrees for input and output of parameter angular functions.
- `STAT` - Show current setting (DEG or RAD) for this command.

## Notes

### Argument descriptions

- `lab : str` - Specifies the units to be used:
  - `RAD` - Use radians for input and output of parameter angular functions (default).
  - `DEG` - Use degrees for input and output of parameter angular functions.
  - `STAT` - Show current setting (DEG or RAD) for this command.

Use radians for input or output of parameter angular functions.

Only the SIN, COS, TAN, ASIN, ACOS, ATAN, ATAN2, ANGLEK, and ANGLEN functions ( [[starset|*SET]], [[vfun|*VFUN]] ) are affected by this command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AFUN.html
