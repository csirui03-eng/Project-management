---
apdl: "TBFIELD"
method: tbfield
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.data_tables.DataTables.tbfield
generated: 2026-08-22
tags: [mapdl-command]
---

# TBFIELD

PyMAPDL: `mapdl.tbfield(type_='', value='', **kwargs)`

Defines values of field variables for material data tables.

## Parameters

**type_**

Field variable type:

- `CYCLE` - A healing cycle number is to be specified in `Value`.
- `FREQ` - A frequency is to be specified in `Value`.
- `NPRES` - A normal pressure is to be specified in `Value`.
- `PLSR` - An equivalent plastic strain rate is to be specified in `Value`.
- `PPRE` - Pressure degree of freedom is to be specified in `Value`.
- `SLDA` - A total sliding distance (algebraic) is to be specified in `Value`.
- `SLDI` - A total sliding distance (absolute) is to be specified in `Value`.
- `SLRV` - A sliding velocity is to be specified in `Value`.
- `SRAT` - Stress ratio of fatigue load cycle is to be specified in `Value`.
- `TEMP` - A temperature is to be specified in `Value`.
- `TIME` - A time is to be specified in `Value`.
- `UFXX` - [User-defined](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_fielduserdef.html#) field variable (UF01,UF02,..., UF09).
- `UX / UY / UZ` - Displacements in the global/local X, Y, or Z coordinate system, respectively, are to be specified in `Value`.
- `XCOR / YCOR / ZCOR` - X, Y and Z locations, respectively, are to be specified in `Value`..

**value**: The field value to be referenced.

## Notes

Define your data tables as field-variable-dependent (via the appropriate [[tb|TB]] command), then issue **TBFIELD** to define the field values.

Issue this command multiple times to enter values for different field variables.

Define data values in ascending order for all field quantities. If a field value is to be held constant, define it only once; subsequent definitions are ignored.

No limit exists on the number of values that you can specify. The specified field value remains active until the next **TBFIELD** command is input.

After you have defined the field value(s), define your data for the data tables ( [[tbdata|TBDATA]] ).

For more information about the interpolation scheme used for field-dependent material properties, see [Understanding Field Variables](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/matexampFVinterp.html)

For more information about using **TBFIELD** with [[tb|TB]],ELASTIC or [[tb|TB]],SDAMP, see [Full Harmonic Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR4_5.html#sect2_lfd_wk5_2v)

The TEMP (temperature) predefined field variable is available for all material models defined via [[tb|TB]], `Lab`.

Several other field variables are available for use with some material models (when used with specific element types), such as TIME (time), PPRE (pore-pressure), XCOR / YCOR / ZCOR (location), UX / UY / UZ (displacement), and UF01 - UF09 ( [user-defined](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_fielduserdef.html#) ).

The field variables can be defined in the global coordinate system or in any local or user-defined coordinate system.

For more information, see [Predefined Field Variables](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/matpredeffieldvars.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TBFIELD.html
