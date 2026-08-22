---
apdl: "*VFUN"
method: vfun
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.array_parameters.ArrayParameters.vfun
generated: 2026-08-22
tags: [mapdl-command]
---

# *VFUN

PyMAPDL: `mapdl.vfun(parr='', func='', par1='', con1='', con2='', con3='', **kwargs)`

Performs a function on a single array parameter.

## Parameters

**parr**: The name of the resulting numeric array parameter vector. See [[starset|*SET]] for name restrictions.

**func**

Function to be performed:

- `ACOS` - Arccosine: ACOS( `Par1` ).
- `ASIN` - Arcsine: ASIN( `Par1` ).
- `ASORT` - Par1 is sorted in ascending order. [[vcol|*VCOL]], [[vmask|*VMASK]], [[vcum|*VCUM]], and [[vlen|*VLEN]],,NINC do not apply. [[vlen|*VLEN]],NROW does apply.
- `ATAN` - Arctangent: ATAN( `Par1` ).
- `COMP` - Compress: Selectively compresses data set. "True" ( [[vmask|*VMASK]] ) values of `Par1` (or row positions to be considered according to the `NINC` value on the [[vlen|*VLEN]] command) are written in compressed form to `ParR`, starting at the specified position.
- `COPY` - Copy: `Par1` copied to `ParR`.
- `COS` - Cosine: COS( `Par1` ).
- `COSH` - Hyperbolic cosine: COSH( `Par1` ).
- `DIRCOS` - Direction cosines of the principal stresses ( `n` X9). `Par1` contains the `n` X6 component stresses for the `n` locations of the calculations.
- `DSORT` - `Par1` is sorted in descending order. [[vcol|*VCOL]], [[vmask|*VMASK]], [[vcum|*VCUM]], and [[vlen|*VLEN]],,NINC do not apply. [[vlen|*VLEN]],NROW does apply.
- `EULER` - Euler angles of the principal stresses ( `n` X3). `Par1` contains the `n` X6 component stresses for the `n` locations of the calculations.
- `EXP` - Exponential: EXP( `Par1` ).
- `EXPA` - Expand: Reverse of the COMP function. All elements of `Par1` (starting at the position specified) are written in expanded form to corresponding "true" ( [[vmask|*VMASK]] ) positions (or row positions to be considered according to the `NINC` value on the [[vlen|*VLEN]] command) of `ParR`.
- `LOG` - Natural logarithm: LOG( `Par1` ).
- `LOG10` - Common logarithm: LOG10( `Par1` ).
- `NINT` - Nearest integer: 2.783 becomes 3.0, -1.75 becomes -2.0.
- `NOT` - Logical complement: values (equation omitted) 0.0 (false) become 1.0 (true). Values \> 0.0 (true) become0.0 (false).
- `PRIN` - Principal stresses ( `n` X5). `Par1` contains the `n` X6 component stresses for the `n` locations of the calculations.
- `PWR` - Power function: `Par1` \*\* `CON1` . Exponentiation of any negative number in the vector `Par1` to a non-integer power is performed by exponentiating the positive number and prepending the minus sign. For example, -4\*\*2.3 is -(4\*\*2.3).
- `SIN` - Sine: SIN( `Par1` ).
- `SINH` - Hyperbolic sine: SINH( `Par1` ).
- `SQRT` - Square root: SQRT( `Par1` ).
- `TAN` - Tangent: TAN( `Par1` ).
- `TANH` - Hyperbolic tangent: TANH( `Par1` ).
- `TANG` - Tangent to a path at a point: the slope at a point is determined by linear interpolation half way between the previous and next points. Points are assumed to be in the global Cartesian coordinate system. Path points are specified in array `Par1` (having 3 consecutive columns of data, with the columns containing the x, y, and z coordinate locations, respectively, of the points). Only the starting row index and the column index for the x coordinates are specified, such as A(1,1). The y and z coordinates of the vector are assumed to begin in the corresponding next columns, such as A(1,2) and A(1,3). The tangent result, `ParR`, must also have 3 consecutive columns of data and will contain the tangent direction vector (normalized to 1.0); such as 1,0,0 for an x-direction vector.
- `NORM` - Normal to a path and an input vector at a point: determined from the cross-product of the calculated tangent vector (see TANG) and the input direction vector (with the i, j, and k components input as `CON1`, `CON2`, and `CON3` ). Points are assumed to be in the global Cartesian coordinate system. Path points are specified in array `Par1` (having 3 consecutive columns of data, with the columns containing the x, y, and z coordinate locations, respectively, of the points). Only the starting row index and the column index for the x coordinates are specified, such as A(1,1). The y and z coordinates of the vector are assumed to begin in the corresponding next columns, such as A(1,2) and A(1,3). The normal result, `ParR`, must also have 3 consecutive columns of data and will contain the normal direction vector (normalized to 1.0); such as 1,0,0 for an x-direction vector.
- `LOCAL` - Transforms global Cartesian coordinates of a point to the coordinates of a specified system: points to be transformed are specified in array `Par1` (having 3 consecutive columns of data, with the columns containing the x, y, and z global Cartesian coordinate locations, respectively, of the points). Only the starting row index and the column index for the x coordinates are specified, such as A(1,1). The y and z coordinates of the vector are assumed to begin in the corresponding next columns, such as A(1,2) and A(1,3). Results are transformed to coordinate system `CON1` (which may be any valid coordinate system number, such as 1,2,11,12, etc.). The transformed result, `ParR`, must also have 3 consecutive columns of data and will contain the corresponding transformed coordinate locations.
- `GLOBAL` - Transforms specified coordinates of a point to global Cartesian coordinates: points to be transformed are specified in array `Par1` (having 3 consecutive columns of data, with the columns containing the local coordinate locations (x, y, z or r, θ, z or etc.) of the points). Only the starting row index and the column index for the x coordinates are specified, such as A(1,1). The y and z coordinates (or θ and z, or etc.) of the vector are assumed to begin in the corresponding next columns, such as A(1,2) and A(1,3). Local coordinate locations are assumed to be in coordinate system `CON1` (which may be any valid coordinate system number, such as 1,2,11,12, etc.). The transformed result, `ParR`, must also have 3 consecutive columns of data, with the columns containing the global Cartesian x, y, and z coordinate locations, respectively.

**par1**: Array parameter vector in the operation.

**con1**, **con2**, **con3**: Constants (used only with the PWR, NORM, LOCAL, and GLOBAL functions).

## Notes

Operates on one input array parameter vector and produces one output array parameter vector according to: `ParR` = f( `Par1` )

where the functions (f) are described below. Functions are based on the standard FORTRAN definitions where possible. Out-of-range function results (or results with exponents whose magnitudes are approximately greater than 32 or less than -32) produce a zero value. Input and output for angular functions may be radians (default) or degrees ( [[afun|*AFUN]] ). `ParR` may be the same as `Par1`. Starting array element numbers must be defined for each array parameter vector if it does not start at the first location. For example, **\*VFUN**,A,SQRT,B(5) takes the square root of the fifth element of B and stores the result in the first element of A. Operations continue on successive array elements ( [[vlen|*VLEN]], [[vmask|*VMASK]] ) with the default being all successive elements. Absolute values and scale factors may be applied to all parameters ( [[vabs|*VABS]], [[vfact|*VFACT]] ). Results may be cumulative ( [[vcum|*VCUM]] ). Skipping array elements via [[vmask|*VMASK]] or [[vlen|*VLEN]] for the TANG and NORM functions skips only the writing of the results (skipped array element data are used in all calculations). See the [[voper|*VOPER]] command for details.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VFUN.html
