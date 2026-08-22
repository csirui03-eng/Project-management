---
apdl: "*ULIB"
method: ulib
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.macro_files.MacroFiles.ulib
generated: 2026-08-22
tags: [mapdl-command]
---

# *ULIB

PyMAPDL: `mapdl.ulib(fname='', ext='', **kwargs)`

Identifies a macro library file.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name.

**ext**: Filename extension (eight-character maximum).

## Notes

Identifies a macro library file for the [[use|*USE]] command.

A library of macros allows blocks of often-used commands to be stacked and executed from a single file. The macro blocks must be enclosed within block identifier and terminator lines as shown in this example: **Example: Macro Blocks**

> ``` apdl
> ABC! Any valid alphanumeric name (32 characters maximum)
> !  identifying this data block
> ---! Mechanical APDL data-input commands
> ---
> ---
> /EOF! Terminator for this data block
> XYZ! Identify another data block (if desired)
> ---! Mechanical APDL data-input commands
> ---
> ---
> /EOF! Terminator for this data block
> (etc.)
> ```

To add comment lines to a macro block, place them anywhere within the macro block, including directly on the lines where the macro block identifier and the macro block terminator appear as shown in the example. Do not place comment lines (or any other lines) outside of a macro block.

The name of the macro library file is identified for reading via **\*ULIB**. The name of the macro block is identified via [[use|*USE]].

Commands within the macro block are copied to a temporary file (of the macro block name) during the [[use|*USE]] operation and executed as if a macro file of that name had been created. The temporary file is deleted after it has been used.

Macro block names should be acceptable file names (system-dependent) and should not match user- created macro file names, as the user-created macro file is used first (if it exists) before the library file is searched.

Macro blocks may be stacked in any order. Branching ( `*GO` or `*IF` ) external to the macro block is not allowed.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ULIB.html
