---
apdl: "/TEE"
method: slashtee
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.macro_files.MacroFiles.slashtee
generated: 2026-08-22
tags: [mapdl-command]
---

# /TEE

PyMAPDL: `mapdl.slashtee(label='', fname='', ext='', **kwargs)`

Writes a list of commands to a specified file at the same time that the commands are being executed.

## Parameters

**label**

Specifies how Mechanical APDL is to interpret this **/TEE** command:

- `NEW` - Signals the beginning of the command text that is to be written to `Fname`. If `Fname` already exists, specifying NEW causes the contents of `Fname` to be overwritten.
- `APPEND` - Indicates that you want to append to `Fname` the command text that follows.
- `END` - Signals the end of the command text that is to be written to or appended to `Fname`.

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name.

**ext**: Filename extension (eight-character maximum). If you plan to execute the file as if it were a Mechanical APDL command, use the extension `.mac`.

## Notes

### Argument descriptions

- `label : str` - Specifies how Mechanical APDL is to interpret this **/TEE** command:
  - `NEW` - Signals the beginning of the command text that is to be written to `Fname`. If `Fname` already exists, specifying NEW causes the contents of `Fname` to be overwritten.
  - `APPEND` - Indicates that you want to append to `Fname` the command text that follows.
  - `END` - Signals the end of the command text that is to be written to or appended to `Fname`.

\* `fname : str` - File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. \* `ext : str` - Filename extension (eight-character maximum). If you plan to execute the file as if it were a Mechanical APDL command, use the extension `.mac`.

You can use the **/TEE** command to record a macro to a specified file at the same time that the macro is being executed. It is similar to the Linux **tee** command.

For more information about the **/TEE** command, see the of the [Ansys Parametric Design Language Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_apdl/apdlxpl.html).

The following example illustrates the use of the **/TEE** command. If you issue these commands:

``` apdl
/tee,new,myfile,mac
et,1,42,0,0,1
ex,1,3e7
/tee,end
/tee,append,myfile,mac
n,1,8
n,5,11
fill
ngen,5,5,1,5,1,0,1
/tee,end
```

the content of **myfile.mac** is:

``` apdl
et,1,42,0,0,1
ex,1,3e7
n,1,8
n,5,11
fill
ngen,5,5,1,5,1,0,1
```

This command is valid in any processor, but only during an interactive run.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TEE_sl.html
