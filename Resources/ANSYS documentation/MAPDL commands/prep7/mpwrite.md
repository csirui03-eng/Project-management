---
apdl: "MPWRITE"
method: mpwrite
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.mpwrite
generated: 2026-08-22
tags: [mapdl-command]
---

# MPWRITE

PyMAPDL: `mapdl.mpwrite(fname='', ext='', lib='', mat='', **kwargs)`

Writes linear material properties in the database to a file (if the LIB option is not specified) or writes both linear and nonlinear material properties (if LIB is specified) from the database to a file.

## Parameters

**fname**

File name and directory path (248 characters maximum, including directory). If you do not specify the `LIB` option, the default directory is the current working directory. If you specify `LIB` and you have specified a material library directory (via the [[mplib|/MPLIB]] command), that directory is the default. Otherwise, the default is the current working directory. If you use the default for your directory, you can use all 248 characters for the file name.

The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). If you omit the `LIB` option, the default extension is MP. If you specify the `LIB` option, the default extension is units_MPL, where units is the system of units currently in use. (See the description of the [[units|/UNITS]] command.) For example, if [[units|/UNITS]] is set to BIN, the extension defaults to BIN_MPL.

**lib**

The only value allowed for this field is the string "LIB."

The LIB option indicates that you wish to have properties associated with the material (MAT) written to the specified material library file using the material library file format. The material library file format is ASCII-text-based Mechanical APDL command input. Certain commands associated with this format have been modified to interpret the string "\_MATL" to mean the currently selected material. This feature makes the material library file independent of the material number in effect when the file was written; this enables you to restore the properties into the Mechanical APDL database using the material number of your choice. The LIB option also enables you to save both linear and nonlinear properties. If you omit the LIB option, you can save linear properties only.

**mat**: Specifies the material to be written to the named material library file. There is no default; you must either specify a material or omit the `MAT` argument. Even if you specify a `MAT` value, Mechanical APDL ignores it if the LIB argument is not specified.

## Notes

Writes linear material properties currently in the database to a file. The file is rewound before and after writing.

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MPWRITE.html
