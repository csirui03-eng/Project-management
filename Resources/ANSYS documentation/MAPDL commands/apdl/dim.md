---
apdl: "*DIM"
method: dim
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.parameter_definition.ParameterDefinition.dim
generated: 2026-08-22
tags: [mapdl-command]
---

# *DIM

PyMAPDL: `mapdl.dim(par='', type_='', imax='', jmax='', kmax='', var1='', var2='', var3='', csysid='', **kwargs)`

Defines an array parameter and its dimensions.

## Parameters

**par**: Name of parameter to be dimensioned. See [[starset|*SET]] for name restrictions.

**type_**

Array type:

- `ARRAY` - Arrays are similar to standard FORTRAN arrays (indices are integers) (default). Index numbers for the rows, columns, and planes are sequential values beginning with one. Used for 1-, 2-, or 3D arrays.
- `ARR4` - Same as ARRAY, but used to specify 4-D arrays.
- `ARR5` - Same as ARRAY, but used to specify 5-D arrays.
- `CHAR` - Array entries are character strings (up to 8 characters each). Index numbers for rows, columns, and planes are sequential values beginning with one.
- `TABLE` - Array indices are real (non-integer) numbers which must be defined when filling the table. Index numbers for the rows and columns are stored in the zero column and row "array elements" and are initially assigned a near-zero value. Index numbers must be in ascending order and are used only for retrieving an array element. When retrieving an array element with a real index that does not match a specified index, linear interpolation is done among the nearest indices and the corresponding array element values ( [[starset|*SET]] ). Used for 1-, 2-, or 3D tables.
- `TAB4` - Same as TABLE, but used to specify 4-D tables.
- `TAB5` - Same as TABLE, but used to specify 5-D tables.
- `STRING` - Array entries are character strings (up to IMAX each). Index numbers for columns and planes are sequential values beginning with 1. Row index is character position in string.

**imax**: Extent of first dimension (row). (For `Type` = STRING, `IMAX` is rounded up to the next multiple of eight and has a limit of 248). Default = 1.

**jmax**: Extent of second dimension (column). Default = 1.

**kmax**: Extent of third dimension (plane). Default = 1.

**var1**: Variable name corresponding to the first dimension (row) for `Type` = TABLE, TAB4, or TAB5. Default = Row.

**var2**: Variable name corresponding to the second dimension (column) for `Type` = TABLE, TAB4, or TAB5. Default = Column.

**var3**: Variable name corresponding to the third dimension (plane) for `Type` = TABLE, TAB4, TAB5. Default = Plane.

**csysid**: An integer corresponding to the coordinate system ID number. Default = 0 (global Cartesian).

## Notes

### Argument descriptions

- `par : str` - Name of parameter to be dimensioned. See [[starset|*SET]] for name restrictions.
- `type_ : str` - Array type:
  - `ARRAY` - Arrays are similar to standard FORTRAN arrays (indices are integers) (default). Index numbers for the rows, columns, and planes are sequential values beginning with one. Used for 1-, 2-, or 3D arrays.
  - `ARR4` - Same as ARRAY, but used to specify 4-D arrays.
  - `ARR5` - Same as ARRAY, but used to specify 5-D arrays.
  - `CHAR` - Array entries are character strings (up to 8 characters each). Index numbers for rows, columns, and planes are sequential values beginning with one.
  - `TABLE` - Array indices are real (non-integer) numbers which must be defined when filling the table. Index numbers for the rows and columns are stored in the zero column and row "array elements" and are initially assigned a near-zero value. Index numbers must be in ascending order and are used only for retrieving an array element. When retrieving an array element with a real index that does not match a specified index, linear interpolation is done among the nearest indices and the corresponding array element values ( [[starset|*SET]] ). Used for 1-, 2-, or 3D tables.
  - `TAB4` - Same as TABLE, but used to specify 4-D tables.
  - `TAB5` - Same as TABLE, but used to specify 5-D tables.
  - `STRING` - Array entries are character strings (up to IMAX each). Index numbers for columns and planes are sequential values beginning with 1. Row index is character position in string.
- `imax : str` - Extent of first dimension (row). (For `Type` = STRING, `IMAX` is rounded up to the next multiple of eight and has a limit of 248). Default = 1.
- `jmax : str` - Extent of second dimension (column). Default = 1.
- `kmax : str` - Extent of third dimension (plane). Default = 1.
- `var1 : str` - Variable name corresponding to the first dimension (row) for `Type` = TABLE, TAB4, or TAB5. Default = Row.
- `var2 : str` - Variable name corresponding to the second dimension (column) for `Type` = TABLE, TAB4, or TAB5. Default = Column.
- `var3 : str` - Variable name corresponding to the third dimension (plane) for `Type` = TABLE, TAB4, TAB5. Default = Plane.
- `csysid : str` - An integer corresponding to the coordinate system ID number. Default = 0 (global Cartesian).

Up to three dimensions (row, column, and plane) may be defined using ARRAY and TABLE. Use ARR4, ARR5, TAB4, and TAB5 to define up to five dimensions (row, column, plane, book, and shelf). An index number is associated with each row, column, and plane. For array and table type parameters, element values are initialized to zero. For character and string parameters, element values are initialized to (blank). A defined parameter must be deleted ( [[starset|*SET]] ) before its dimensions can be changed. Scalar (single valued) parameters should not be dimensioned. **\*DIM**,A,,3 defines a vector array with elements A(1), A(2), and A(3). **\*DIM**,B,,2,3 defines a 2x3 array with elements B(1,1), B(2,1), B(1,2), B(2,2), B(1,3), and B(2,3). Use [[starstatus|*STATUS]], `Par` to display elements of array `Par`. You can write formatted data files (tabular formatting) from data held in arrays through the [[vwrite|*VWRITE]] command.

If you use table parameters to define boundary conditions, then `Var1`, `Var2`, and/or `Var3` can either specify a primary variable (listed in *\*DIM - Primary Variables* ) or can be an independent parameter. If specifying an independent parameter, then you must define an additional table for the independent parameter. The additional table must have the same name as the independent parameter and may be a function of one or more primary variables or another independent parameter. All independent parameters must relate to a primary variable.

Tabular load arrays can be defined in both global Cartesian (default), cylindrical, spherical, or local (see below) coordinate systems by specifying `CSYSID`, as defined in [[local|LOCAL]]. Coordinate system `CSYSID` must exist prior to issuing the **\*DIM** command.

**The following constraints apply when specifying a local coordinate system for your tabular loads:**

- Only Cartesian, cylindrical and spherical coordinate systems are supported
- Angle values for Y in cylindrical or spherical coordinate systems must be input in degrees and must be positive values between 0 and 360 degrees (0 (equation omitted) Y (equation omitted) 360)
- Angle values for Z in spherical coordinate system must be input in degrees and must be positive values between -90 and +90 ( -90 (equation omitted) Z (equation omitted) 90)

If specifying a 4- or 5-D array or table, four additional fields ( `LMAX`, `MMAX`, `Var4`, and `Var5` ) are available. Thus, for a 4-D table, the command syntax would be:

``` apdl
*DIM,Par,Type,IMAX,JMAX,KMAX,LMAX,Var1,Var2,Var3,Var4,CSYSID
```

For a 5-D table, the command syntax is:

``` apdl
*DIM,Par,Type,IMAX,JMAX,KMAX,LMAX,MMAX,Var1,Var2,Var3,Var4,Var5,CSYSID
```

You cannot create or edit 4- or 5-D arrays or tables via the GUI.

For more information, see [Array Parameters](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_apdl/Hlp_P_APDL3_11.html#ansys.guide.apdl.ch3.s11.9)

#### \*DIM - Primary Variables

| Primary Variable | Label for `Var1, Var2, Var3, Var4, Var5` |
|----|----|
| Time | TIME |
| Frequency | FREQ |
| X-coordinate location | X |
| Y-coordinate location | Y |
| Z-coordinate location | Z |
| Temperature | TEMP |
| Velocity | VELOCITY |
| Pressure | PRESSURE |
| Geometric gap/penetration | GAP |
| Cyclic sector number | SECTOR |
| Amplitude of the rotational velocity vector | OMEGS |
| Eccentricity | ECCENT |
| Phase shift | THETA |
| Element number | ELEM |
| Node number | NODE |
| Concentration | CONC |

Specify PRESSURE as the independent variable (not PRES).

The X, Y, and Z coordinate locations listed above are valid in global Cartesian, or local (Cartesian, cylindrical and spherical) coordinate systems. The VELOCITY label is applicable only to the calculated fluid velocity in element `FLUID116`.

When using PRESSURE as a primary variable, the underlying element must have the pressure DOF associated with it, or it must be a supported contact element.

The gap/penetration label (GAP) is only used for defining certain contact element real constants.

The frequency label (FREQ) is valid for harmonic analyses only.

The node and element labels (NODE and ELEM) allow you to use node and element numbers as primary variables, and their axis values should be integers.

The OMEGS, ECCENT, and THETA primary variables only apply to the `COMBI214` element. The amplitude of the rotational velocity (OMEGS) is an absolute value, so only positive values of OMEGS are valid. The eccentricity (ECCENT) and phase shift (THETA) labels are only valid for nonlinear analyses.

If you use table parameters to define boundary conditions, the table names ( `Par` ) must not exceed 32 characters.

In thermal analyses, if you apply tabular loads as a function of temperature but the rest of the model is linear (for example, includes no temperature-dependent material properties or radiation ), you should turn on Newton-Raphson iterations ( [[nropt|NROPT]],FULL) to evaluate the temperature- dependent tabular boundary conditions correctly.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DIM.html
