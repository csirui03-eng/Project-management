---
apdl: "RSOPT"
method: rsopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.radiosity.Radiosity.rsopt
generated: 2026-08-22
tags: [mapdl-command]
---

# RSOPT

PyMAPDL: `mapdl.rsopt(opt='', filename='', ext='', dir_='', **kwargs)`

Creates or loads the radiosity mapping data file for `SURF251` or `SURF252` element types.

## Parameters

**opt**

File option:

- `SAVE` - Write the radiosity mapping data to a file. (Default)
- `LOAD` - Read in the specified mapping data file.

**filename**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RSOPT.html) for further information.

**ext**: Filename extension for radiosity mapping data file (default = `.rsm` ).

**dir_**: Directory path for radiosity mapping data file. If you do not specify a directory path, it will default to your working directory.

## Notes

Use this command to manually create or load a radiosity mapping data file. This command is useful if you want to create the mapping data file without issuing [[save|SAVE]] or [[cdwrite|CDWRITE]], or if you want to specify that the file be located in a directory other than your working directory. Also use this command to manually load an existing mapping data file during a restart. Distributed-Memory Parallel (DMP) Restriction This command is not supported in a DMP solution.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RSOPT.html
