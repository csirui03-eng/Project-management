---
apdl: "TBIN"
method: tbin
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.data_tables.DataTables.tbin
generated: 2026-08-22
tags: [mapdl-command]
---

# TBIN

PyMAPDL: `mapdl.tbin(oper='', par1='', par2='', par3='', par4='', **kwargs)`

Sets parameters used for [interpolation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_loginterpscal.html#) of the material data tables.

## Parameters

**oper**

Operation to perform:

- ALGO - Specifies the interpolation algorithm to use for the subtable (or table if the material data table has only one subtable) being defined.
- BNDS - Specifies the maximum and minimum bounds for individual field variables.
- CACH - Enables or disables caching of interpolated data for better performance.
- DEFA - Specifies the default value of the user-defined field variable used for interpolation (if no value was specified).
- EXTR - Controls extrapolation options.
- NORM - Scales the field variables before interpolation.
- SCALE - Interpolates [[tb|TB]] -based material parameters in the linear- or natural-log scale.

**par1**, **par2**, **par3**, **par4**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TBIN.html) for further information.

## Notes

For a list of the supported material data tables ( [[tb|TB]] ), see [Logarithmic Interpolation and Scaling](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_loginterpscal.html#)

`Oper` = DEFA, BNDS, NORM and CACH are supported for the [linear multivariate](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/matexampFVinterp.html#exlinmult4) ( **TBIN**,ALGO,LMUL) interpolation algorithm only.

### Command Specifications

**Interpolation Parameters for Oper= ALGO**

- `Par1` - Interpolation algorithm:

  - [LINEAR](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/matexampFVinterp.html#ansmatexampl)
    - Linear 1D / 2D (default).
  - [LMUL](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/matexampFVinterp.html#exlinmult4)
    - Linear-multivariate interpolation (multidimensional).

  `Par1` = LINEAR is available for all material models. The remaining options are limited to a subset of material models. For more information, see.

**Interpolation Parameters for Oper= BNDS**

- `Par1` - The field variable on which the operation is being applied.
- `Par2` - Lower bound of the field variable.
- `Par3` - Upper bound of the field variable.

**Interpolation Parameters for Oper= CACH**

- `Par1` - Reserved for future use.

\* `Par2` - Enable or disable caching of interpolated material parameters. Enable for better performance.

> - OFF - Disable (default).
> - ON - Enable.

**Interpolation Parameters for Oper= DEFA**

- `Par1` - The field variable on which the operation is being applied.
- `Par2` - Default value of the field variable for which an initial value was not specified.

**Interpolation Parameters for Oper= EXTR**

- `Par1` - Reserved for future use.
- `Par2` - Set extrapolation/projection options for interpolating material parameters.
  - OFF / BBOX- Projects to the hyper-rectangular bounding box (default). An error occurs if query points exist outside the convex hull of points but inside the hyper-rectangular bounding box.
  - PHULL - Projects to the convex hull of points if a point is located outside the convex hull surface.

**TBIN**,EXTR is supported for the [linear multivariate](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/matexampFVinterp.html#exlinmult4) interpolation algorithm only.

**Interpolation Parameters for Oper= NORM**

- `Par1` - Reserved for future use.
- `Par2` - Enable or disables field-variable normalization for interpolation.
  - OFF - Disable.
  - ON - Enable (default).

**Interpolation Parameters for Oper= SCALE**

- `Par1` - Independent variable, which can be any field variable specified via the [[tbfield|TBFIELD]] command.
- `Par2` - Index of any material parameter specified via the [[tbdata|TBDATA]] command.
- `Par3` - Scale to use for the independent variable. Valid options are LINEAR (linear) or LOG (logarithmic).
- `Par4` - Scale to use for the dependent variable (the material parameter specified via `Par2` ). Valid options are LINEAR (linear) or LOG (logarithmic).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TBIN.html
