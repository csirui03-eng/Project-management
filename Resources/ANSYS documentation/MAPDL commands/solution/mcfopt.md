---
apdl: "MCFOPT"
method: mcfopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.mcfopt
generated: 2026-08-22
tags: [mapdl-command]
---

# MCFOPT

PyMAPDL: `mapdl.mcfopt(format_='', type_='', norm='', **kwargs)`

Specifies options for the Modal Coordinates File ( `Jobname.mcf` ).

## Parameters

**format_**

`Jobname.mcf` file format:

- `0` - ASCII with wrap for more than 25 values (harmonic analysis) or 50 values (transient analysis) (default).
- `1` - ASCII.

**type_**

Output form of the complex modal coordinates - Only supported for `Format` = 1:

- `0` - Real and imaginary parts (default).
- `1` - Amplitude and phase angle in degree.

**norm**

Mode shape normalization for the calculation of the modal coordinates - Only supported for `Format` = 1:

- `0` - The modes are mass normalized (default).
- `1` - The modes are normalized to unity.

## Notes

Options specified with **MCFOPT** are processed when a request is made to write the `Jobname.mcf` file by issuing [[trnopt|TRNOPT]] or [[hropt|HROPT]] with `MCFwrite` = ON.

If you specify normalized to unity for the modal coordinates ( `Norm` = 1), the generalized mass must be available (see ). Note that this option is independent from the normalization of the modes specified during the modal analysis ( `NrmKey` on [[modopt|MODOPT]] command).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MCFOPT.html
