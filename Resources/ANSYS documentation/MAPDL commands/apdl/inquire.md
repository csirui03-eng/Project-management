---
apdl: "/INQUIRE"
method: inquire
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.parameter_definition.ParameterDefinition.inquire
generated: 2026-08-22
tags: [mapdl-command]
---

# /INQUIRE

PyMAPDL: `mapdl.inquire(strarray='', func='', **kwargs)`

Returns system information to a parameter.

## Parameters

**strarray**: Name of the "string array" parameter that will hold the returned values. String array parameters are similar to character arrays, but each array element can be as long as 248 characters. If the string parameter does not exist, it will be created.

**func**

Specifies the type of file information returned:

- `EXIST` - Returns a 1 if the specified file exists, and 0 if it does not.
- `DATE` - Returns the date stamp of the specified file in the format `yyyymmdd.hhmmss`.
- `SIZE` - Returns the size of the specified file in MB.
- `WRITE` - Returns the status of the write attribute. A 0 denotes no write permission while a 1 denotes write permission.
- `READ` - Returns the status of the read attribute. A 0 denotes no read permission while a 1 denotes read permission.
- `EXEC` - Returns the status of the execute attribute (this has meaning only on Linux). A 0 denotes no execute permission while a 1 denotes execute permission.
- `LINES` - Returns the number of lines in an ASCII file.

## Notes

### Argument descriptions

- `strarray : str` - Name of the "string array" parameter that will hold the returned values. String array parameters are similar to character arrays, but each array element can be as long as 248 characters. If the string parameter does not exist, it will be created.
- `func : str` - Specifies the type of system information returned:
  - `LOGIN` - Returns the pathname of the login directory on Linux systems or the pathname of the default directory (including drive letter) on Windows systems.
  - `DOCU` - Returns the pathname of the Mechanical APDL docu directory.
  - `APDL` - Returns the pathname of the Mechanical APDL APDL directory.
  - `PROG` - Returns the pathname of the Mechanical APDL executable directory.
  - `AUTH` - Returns the pathname of the directory in which the license file resides.
  - `USER` - Returns the name of the user currently logged-in.
  - `DIRECTORY` - Returns the pathname of the current directory.
  - `JOBNAME` - Returns the current `Jobname`.
  - `RSTDIR` - Returns rst directory ( [[file|FILE]] command).
  - `RSTFILE` - Returns rst file name ( [[file|FILE]] command).
  - `RSTEXT` - Returns rst file extension ( [[file|FILE]] command).
  - `PSEARCH` - Returns path used for "unknown command" macro ( [[psearch|/PSEARCH]] command).
  - `OUTPUT` - Returns the current output file name ( [[output|/OUTPUT]] command).

### Returning the Value of an Environment Variable to a Parameter

If `FUNC` =ENV, the command format is **/INQUIRE**, `StrArray`,ENV, `ENVNAME`, `Substring`. In this instance, ENV specifies that the command should return the value of an environment variable. The following defines the remaining fields:

- `envname : str` - Specifies the name of the environment variable.
- `substring : str` - If `Substring` = 1, the first substring (up to the first colon (:)) is returned. If `Substring` = 2, the second substring is returned, etc. For Windows platforms, the separating character is semicolon (;). If this argument is either blank or 0, the entire value of the environment variable is returned.

### Returning the Value of a Title to a Parameter

If `FUNC` = TITLE, the command format is **/INQUIRE**, `StrArray`,TITLE, `Title_num`. In this context, the value of `Title_num` can be blank or 1 through 5. If the value is 1 or blank, the title is returned. If the value is 2 through 5, a corresponding subtitle is returned (2 denoting the first subtitle, and so on).

### Returning Information About a File to a Parameter

The **/INQUIRE** command can also return information about specified files within the file system. For these capabilities, the format is **/INQUIRE**, `Parameter`, `FUNC`,`Fname`, `Ext`, `--`. The following defines the fields:

- `parameter : str` - Name of the parameter that will hold the returned values.
- `func : str` - Specifies the type of file information returned:
  - `EXIST` - Returns a 1 if the specified file exists, and 0 if it does not.
  - `DATE` - Returns the date stamp of the specified file in the format `yyyymmdd.hhmmss`.
  - `SIZE` - Returns the size of the specified file in MB.
  - `WRITE` - Returns the status of the write attribute. A 0 denotes no write permission while a 1 denotes write permission.
  - `READ` - Returns the status of the read attribute. A 0 denotes no read permission while a 1 denotes read permission.
  - `EXEC` - Returns the status of the execute attribute (this has meaning only on Linux). A 0 denotes no execute permission while a 1 denotes execute permission.
  - `LINES` - Returns the number of lines in an ASCII file.

\* `fname : str` - File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. \* `ext : str` - Filename extension (eight-character maximum).

The **/INQUIRE** command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_INQUIRE.html
