---
apdl: "HBMAT"
method: hbmat
group: aux2
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux2.binary_file_manipulation.BinaryFileManipulation.hbmat
generated: 2026-08-22
tags: [mapdl-command]
---

# HBMAT

PyMAPDL: `mapdl.hbmat(fname='', ext='', form='', matrx='', rhs='', mapping='', **kwargs)`

Writes an assembled global matrix in Harwell-Boeing format.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. Defaults to the current Jobname if left blank.

**ext**: Filename extension (eight-character maximum). Defaults to `.matrix` if left blank.

**form**

Specifies format of output matrix file:

- `ASCII` - Write output matrix file in ASCII form.
- `BIN` - Write output matrix file in binary form.

**matrx**

Specify which matrix to write to the output matrix file:

- `STIFF` - Write stiffness matrix to output matrix file. Valid for all types of analyses that write a `.full` file.
- `MASS` - Write mass matrix to output matrix file. Valid for buckling, substructure, and modal analyses. If `.full` file was generated in a buckling analysis, then this label will write stress stiffening matrix to output matrix file.
- `DAMP` - Write damping matrix to output matrix file. Only valid for damped modal analyses.

**rhs**

Specifies whether to write the right-hand side vector to output matrix file:

- `YES` - Write right-hand side vector to output matrix file.
- `NO` - Do not write right-hand side vector to output matrix file.

**mapping**

Specifies whether to write the mapping file. This file is always named `Fnamemapping`.

- `YES` - Write the mapping file.
- `NO` - Do not write the mapping file (default).

## Notes

This command copies a matrix from the assembled global matrix file ( `.full` file) or from the superelement matrix file ( `.sub` file) as specified on the [[fileaux2|FILEAUX2]] command and write it in Harwell-Boeing format to a new file named `Jobname.matrix`. The Harwell-Boeing format is widely used by other applications that deal with matrices.

The assembled global matrix file is created during solution depending on the analysis type, equation solver, and other solution options. By default, the assembled global matrix file is never deleted at the end of solution. For most analysis types, the Sparse direct solver and the ICCG solver will write a `.full` file. All mode extraction methods used for buckling and modal analyses will write a properly formatted `.full` file to be used with the **HBMAT** command. However, when using distributed-memory parallel (DMP) processing, a majority of analyses will write a distributed (or local) form of the `.full` file which is not currently supported by the **HBMAT** command.

When dumping the stiffness matrix for transient and harmonic analyses, be aware that the element mass matrix values (and possibly element damping matrix values) are incorporated into the globally assembled stiffness matrix. Thus, the globally assembled stiffness matrix represents more than the stiffness of the model for these analysis types. Please refer to the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html) for more details.

When dumping a `.full` file, the rows and columns corresponding to specified constraints (for example, [[d|D]] commands) are eliminated from the system of equations and therefore are not written to the `.matrix` file. Also, rows and columns corresponding to eliminated (dependent) degrees of freedom from coupling and/or constraint equations (for example, [[ce|CE]], [[cp|CP]] commands) are also eliminated from the system of equations and are not written to the `.matrix` file. The DOFs that are eliminated from any coupling and/or constraint equations are determined internally by the solution code and may not match what you specified via the [[ce|CE]] / [[cp|CP]] (or similar) commands.

When dumping a `.sub` file, the full `n` x `n` matrix will be written to the `.matrix` file for either symmetric or unsymmetric matrices, regardless of whether any of the matrix coefficients are zero-valued. When dumping a `.full` file, only the lower triangular part of the matrix will be written to the `.matrix` file if the matrix is symmetric; the full matrix is written if the matrix is unsymmetric. Only matrix coefficients that are greater than zero will be written.

The Harwell-Boeing format is column-oriented. That is, non-zero matrix values are stored with their corresponding row indices in a sequence of columns. However, because the Mechanical APDL matrix files are stored by row and not column, when the **HBMAT** command is used with a non-symmetric matrix, the transpose of the matrix is, in fact, written.

The [[wrfull|WRFULL]] command, used with the [[solve|SOLVE]] command, generates the assembled global matrix file and eliminate the equation solution process and results output process.

The mapping file can be used to map the matrix equation numbers found in the `.matrix` file directly to the corresponding node numbers and degrees of freedom.

When dumping a CMS `.sub` file, the last rows/columns of the matrix are non-physical degrees of freedom added internally by the [CMS process](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/advcms.html#advcmsunderstand) and cannot be mapped directly to a node number or particular degree of freedom.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_HBMAT.html
