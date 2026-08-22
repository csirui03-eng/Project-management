---
apdl: "*EXPORT"
method: export
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.export
generated: 2026-08-22
tags: [mapdl-command]
---

# *EXPORT

PyMAPDL: `mapdl.export(matrix='', format_='', fname='', val1='', val2='', val3='', **kwargs)`

Exports a matrix to a file in the specified format.

## Parameters

**matrix**: Name of the matrix to export (must be a matrix previously created with [[dmat|*DMAT]] or [[smat|*SMAT]], or a vector previously created with [[vec|*VEC]] ).

**format_**

Format of the output file:

- `MMF` - Export the matrix in the Matrix Market Format.
- `SUB` - Export the matrix in the `SUB` file format.
- `HBMAT` - Export the matrix in the Harwell-Boeing file format.
- `MAT` - Export the matrix in a native format, to be re-imported using the [[dmat|*DMAT]] or [[smat|*SMAT]] command.
- `EMAT` - Export the matrix to an existing `EMAT` file.
- `APDL` - Export the matrix to an APDL array parameter.
- `PS` - Export the matrix profile to a Postscript file.
- `DMIG` - Export the matrix in the `DMIG` file format.
- `CSV` - Export the matrix to an ASCII CSV (comma-separated values) file.

**fname**: Name of the file (case-sensitive, 32-character maximum), or name of the array parameter if `Format` = APDL (no default).

**val1**, **val2**, **val3**: Additional input. The meaning of `Val1` through `Val3` will vary depending on the specified `Format`. See table below for details.

## Notes

Only sparse matrices can be exported to Postscript files. This option plots the matrix profile as a series of dots.

If you want to create a `.SUB` file from several matrices, you need to set `Val3` = WAIT for all matrices but the last, and `Val3` = DONE for the last one. The export will be effective at the last **\*EXPORT** command.

To create a `.SUB` file or `.DMIG` file from scratch, you must supply the row information array. (Specify this array in the `Val2` field for `.SUB` or in the `Val1` field for `.DMIG`.) This must be an `m` x 2 array, where `m` is the size of the matrix. The first column is the node number and the second column is the DOF number corresponding to each row of the matrix.

When exporting an HBMAT file in ASCII format, you can include the matrix type in the header of the file by specifying the matrix type in the `Val2` field. The matrix type is not included in the header if `Val2` is empty. If `Val1` = BINARY, `Val2` is not used.

The **\*EXPORT** command is not applicable to sparse matrices initialized from `.FULL` files by means of the NOD2SOLV option on the [[smat|*SMAT]] command (that is, [[smat|*SMAT]],,,IMPORT,FULL,,NOD2SOLV).

The `.CSV` file format does not support sparse matrices.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EXPORT.html
