---
apdl: "MPREAD"
method: mpread
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.mpread
generated: 2026-08-22
tags: [mapdl-command]
---

# MPREAD

PyMAPDL: `mapdl.mpread(fname='', ext='', lib='', **kwargs)`

PyMAPDL overrides `mapdl.mpread` with its own wrapper, so the signature above is not what `mapdl.mpread` runs. Reach the APDL command as text: `mapdl.run("MPREAD,...")`.

Reads a file containing material properties.

## Parameters

**fname**

File name and directory path (248 characters maximum, including directory). If you do not specify the `LIB` option, the default directory is the current working directory. If you specify the `LIB` option, the default is the following search path: the current working directory, the user's home directory, MPLIB_DIR (as specified by the [[mplib|/MPLIB]],READ, `PATH` command) and `/ansys_dir/matlib` (as defined by installation). If you use the default for your directory, you can use all 248 characters for the file name.

The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). If you omit the default extension is MP. extension is units_MPL, where units is the system of units currently in use. (See the description of the [[units|/UNITS]] command.) For example, if [[units|/UNITS]] is set to SI, the extension defaults to SI_MPL.

**lib**

Reads material library files previously written with the [[mpwrite|MPWRITE]] command. (See the description of the LIB option for the [[mpwrite|MPWRITE]] command.) The only allowed value for LIB is LIB.

The LIB field indicates that the specified file was written by [[mpwrite|MPWRITE]] using the LIB option, and that the file is consistent with the material library file format. When the **MPREAD** command executes, Mechanical APDL reads material properties defined in the specified file into the current Mechanical APDL working database. The currently selected material, as defined by the [[mat|MAT]] command ( [[mat|MAT]],MAT), determines the material number used when reading the material properties. The LIB option for **MPREAD** and [[mpwrite|MPWRITE]] supports storing and retrieving both linear and nonlinear properties.

## Notes

Material properties written to a file without the LIB option do not support nonlinear properties. Also, properties written to a file without the LIB option are restored in the same material number as originally defined. To avoid errors, use **MPREAD** with the LIB option only when reading files written using [[mpwrite|MPWRITE]] with the LIB option.

If you omit the LIB option for **MPREAD**, this command supports only linear properties.

Material numbers are hardcoded. If you write a material file without specifying the LIB option, then read that file in via the **MPREAD** command with the LIB option, Mechanical APDL does not write the file to a new material number; instead, it writes the file to the old material number (the number specified on the [[mpwrite|MPWRITE]] command that created the file.)

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MPREAD.html
