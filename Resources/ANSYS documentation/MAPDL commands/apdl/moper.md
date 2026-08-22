---
apdl: "*MOPER"
method: moper
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.array_parameters.ArrayParameters.moper
generated: 2026-08-22
tags: [mapdl-command]
---

# *MOPER

PyMAPDL: `mapdl.moper(parr='', par1='', oper='', val1='', val2='', val3='', val4='', val5='', val6='', **kwargs)`

Performs matrix operations on array parameter matrices.

## Parameters

**parr**: The name of the resulting array parameter matrix. See [[starset|*SET]] for name restrictions.

**par1**: First array parameter matrix input to the operation.

**oper**

Matrix operations. Usage of the `Val1` through `Val6` arguments varies for each operation, as described below:

- `INVERT` - ( **\*MOPER**, `ParR`, `Par1`, INVERT)

  Square matrix invert: Inverts the n x n matrix in Par1 into ParR. The matrix must be well conditioned.

  > [!WARNING]
  > Non-independent or ill-conditioned equations can cause erroneous results.

  For large matrices, use the APDL Math operation [[lsfactor|*LSFACTOR]] for efficiency (see [APDL Math](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_apdl/apdlmathex.html)

- `MULT` - ( **\*MOPER**, `ParR`, `Par1`, MULT, `Par2` )

  Matrix multiply: Multiplies `Par1` by `Par2`. The number of rows of `Par2` must equal the number of columns of `Par1` for the operation. If `Par2` is input with a number of rows greater than the number of columns of `Par1`, matrices are still multiplied. However, the operation only uses a number of rows of `Par2` equal to the number of columns of `Par1`.

- `COVAR` - ( **\*MOPER**, `ParR`, `Par1`, COVAR, `Par2` )

  Covariance: The measure of association between columns of the `Par1` input matrix. `Par1` of size m runs (rows) by n data (columns) is first processed to produce a row vector containing the mean of each column, which is transposed to the output column vector `Par2` of n array elements. The `Par1` and `Par2` operation then produces `ParR`, a resulting n x n matrix of covariances (with the variances as the diagonal terms).

- `CORR` - ( **\*MOPER**, `ParR`, `Par1`, CORR, `Par2` )

  Correlation: The correlation coefficient between columns of the `Par1` input matrix. `Par1` of size m runs (rows) by n data (columns) is first processed to produce a row vector containing the mean of each column, which is then transposed to the output column vector `Par2` of n array elements. The `Par1` and `Par2` operation then produces `ParR`, a resulting n x n matrix of correlation coefficients (with a value of 1.0 for the diagonal terms).

- `SOLV` - ( **\*MOPER**, `ParR`, `Par1`, SOLV, `Par2` )

  Solution of simultaneous equations: Solves the set of `n` equations of `n` terms of the form a<sub>n1</sub> x<sub>1</sub> + a<sub>n2</sub> x<sub>2</sub> + <sup>...</sup> + a<sub>nn</sub> x<sub>n</sub> = b<sub>n</sub> where `Par1` contains the matrix of a-coefficients, `Par2` contains the vector(s) of b-values, and `ParR` contains the vector(s) of x-results. `Par1` must be a square matrix. The equations must be linear, independent, and well conditioned.

  > [!WARNING]
  > Non-independent or ill-conditioned equations can cause erroneous results.

  For large matrices, use the APDL Math operation [[lsfactor|*LSFACTOR]] for efficiency (see [APDL Math](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_apdl/apdlmathex.html)

- `SORT` - ( **\*MOPER**, `ParR`, `Par1`, SORT, `Par2`, `n1`, `n2`, `n3` )

  Matrix sort: Sorts the columns of matrix `Par1` according to sort vector `Par2` and places the result back into `Par1`. Rows of `Par1` are moved to the corresponding positions indicated by the values of `Par2`. `Par2` may be a column of `Par1` (in which case it will also be reordered). Alternatively, you may specify the column of `Par1` to sort using `n1` (leaving `Par2` blank). A secondary sort can be specified by column `n2`, and a third sort using column `n3`. `ParR` is the vector of initial row positions (the permutation vector). Sorting `Par1` according to `ParR` should reproduce the initial ordering.

- `NNEAR` - ( **\*MOPER**, `ParR`, `Par1`, NNEAR, `Toler` )

  Nearest Node: Finds the nodes nearest to the given set of points in `Par1`, where `Par1` is an n x 3 array of coordinate locations. `ParR` is a vector of the nearest selected nodes, or 0 if no nodes are nearer than `Toler`. `Toler` defaults to 1 and is limited to the maximum model size.

- `ENEAR` - ( **\*MOPER**, `ParR`, `Par1`, ENEAR, `Toler` )

  Nearest Element: Finds the elements nearest to the given set of points in `Par1`, where `Par1` is an n x 3 array of coordinate locations. `ParR` is a vector of the nearest selected elements, or 0 if no element centroids are nearer than `Toler`. `Toler` defaults to 1 and is limited to the maximum model size.

- `MAP` - ( **\*MOPER**, `ParR`, `Par1`, MAP, `Par2`, `Par3`, `kDim`, `--`, `kOut`, `LIMIT` )

  Maps the results from one set of points to another. For example, you can map pressures from a CFD analysis onto your model for a structural analysis.

  `Par1` is the Nout x 3 array of points that will be mapped to. `Par2` is the Nin x M array that contains M values of data to be interpolated at each point and corresponds to the Nin x 3 points in `Par3`. The resulting `ParR` is the Nout x M array of mapped data points.

  For each point in the destination mesh, all possible triangles in the source mesh are searched to find the best triangle containing each point. It then does a linear interpolation inside this triangle. You should carefully specify your interpolation method and search criteria in order to provide faster and more accurate results (see `LIMIT`, below).

  `kDim` is the interpolation criteria. If `kDim` = 2 or 0, two dimensional interpolation is applied (interpolate on a surface). If `kDim` = 3, three dimensional interpolation is applied (interpolate on a volume).

  `kOut` specified how points outside of the domain are handled. If `kOut` = 0, use the value(s) of the nearest region point for points outside of the region. If `kOut` = 1, set results outside of the region to zero.

  `LIMIT` specifies the number of nearby points considered for interpolation. The default is 20, and the minimum is 5. Lower values will reduce processing time; however, some distorted or irregular sets of points will require a higher `LIMIT` value to encounter three nodes for triangulation.

  Output points are incorrect if they are not within the domain (area or volume) defined by the specified input points. Also, calculations for out-of-bound points require much more processing time than do points that are within bounds. Results mapping is available from the command line only.

- `INTP` - ( **\*MOPER**, `ParR`, `Par1`, INTP, `Par2` )

  Finds the elements that contain each point in the array of n x 3 points in `Par1`. `Par2` will contain the set of element ID numbers and `ParR` will contain their n x 3 set of natural element coordinates (values between -1 and 1). `Par1` must be in global Cartesian coordinates.

- `SGET` - ( **\*MOPER**, `ParR`, `Par1`, SGET, `Par2`, `Label`, `Comp` )

  Gets the nodal solution item corresponding to `Label` and `Comp` (see the [[plnsol|PLNSOL]] command) and interpolates it to the given element locations. `Par1` contains the n x 3 array of natural element coordinates (values between -1 and 1) of the n element ID numbers in `Par2`. `Par1` and `Par2` are usually the output of the **\*MOPER**,,,INTP operation. `ParR` contains the n interpolated results.

**val1**, **val2**, **val3**, **val4**, **val5**, **val6**: Additional input used in the operation. The meanings of `Val1` through `Val6` vary depending on the specified matrix operation. See the description of `Oper` for details.

## Notes

Each starting array element number must be defined for each array parameter matrix if it does not start at the first location. For example, **\*MOPER**,A(2,3),B(1,4),MULT,C(1,5) multiplies submatrix B (starting at element (1,4)) by submatrix C (starting at element (1,5)) and puts the result in matrix A (starting at element (2,3)).

The diagonal corner elements for each submatrix must be defined: the upper left corner by the array starting element (on this command), the lower right corner by the current values from the [[vcol|*VCOL]] and [[vlen|*VLEN]] commands. The default values are the (1,1) element and the last element in the matrix. No operations progress across matrix planes (in the 3rd dimension). Absolute values and scale factors may be applied to all parameters ( [[vabs|*VABS]], [[vfact|*VFACT]] ). Results may be cumulative ( [[vcum|*VCUM]] ). Array elements should not be skipped with the [[vmask|*VMASK]] and the `NINC` value of the [[vlen|*VLEN]] specifications. See the [[voper|*VOPER]] command for details.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MOPER.html
