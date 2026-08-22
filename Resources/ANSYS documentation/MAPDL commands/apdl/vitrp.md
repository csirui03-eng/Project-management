---
apdl: "*VITRP"
method: vitrp
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.array_parameters.ArrayParameters.vitrp
generated: 2026-08-22
tags: [mapdl-command]
---

# *VITRP

PyMAPDL: `mapdl.vitrp(parr='', part='', pari='', parj='', park='', **kwargs)`

Forms an array parameter by interpolation of a table.

## Parameters

**parr**: The name of the resulting array parameter. See [[starset|*SET]] for name restrictions.

**part**: The name of the TABLE array parameter. The parameter must exist as a dimensioned array of type TABLE ( [[dim|*DIM]] ).

**pari**: Array parameter vector of I (row) index values for interpolation in `ParT`.

**parj**: Array parameter vector of J (column) index values for interpolation in `ParT` (which must be at least 2D).

**park**: Array parameter vector of K (depth) index values for interpolation in `ParT` (which must be 3D).

## Notes

Forms an array parameter (of type ARRAY) by interpolating values of an array parameter (of type TABLE) at specified table index locations according to: `ParR` = f( `ParT`, `Parl`, `ParJ`, `ParK` )

where `ParT` is the type TABLE array parameter, and `ParI`, `ParJ`, `ParK` are the type ARRAY array parameter vectors of index values for interpolation in `ParT`. See the [[dim|*DIM]] command for TABLE and ARRAY declaration types. Linear interpolation is used. The starting array element number for the TABLE array ( `ParT` ) is not used (but a value must be input). Starting array element numbers must be defined for each array parameter vector if it does not start at the first location. For example, **\*VITRP**,R(5),TAB(1,1),X(2),Y(4) uses the second element of X and the fourth element of Y as index values (row and column) for a 2D interpolation in TAB and stores the result in the fifth element of R. Operations continue on successive array elements ( [[vlen|*VLEN]], [[vmask|*VMASK]] ) with the default being all successive elements. Absolute values and scale factors may be applied to the result parameter ( [[vabs|*VABS]], [[vfact|*VFACT]] ). Results may be cumulative ( [[vcum|*VCUM]] ). See the [[voper|*VOPER]] command for details.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VITRP.html
