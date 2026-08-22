---
apdl: "LSREAD"
method: lsread
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_operations.LoadStepOperations.lsread
generated: 2026-08-22
tags: [mapdl-command]
---

# LSREAD

PyMAPDL: `mapdl.lsread(lsnum='', **kwargs)`

Reads load and load step option data into the database.

> [!WARNING]
> This command must be run using `non_interactive <ansys.mapdl.core.Mapdl.non_interactive>`. Please visit [Unsupported Interactive Commands](https://mapdl.docs.pyansys.com/version/stable/user_guide/mapdl.html#unsupported-interactive-commands) for further information.

## Parameters

**lsnum**: Identification number of the load step file to be read. Defaults to 1 + highest number read in the current session. Issue **LSREAD**,STAT to list the current value of `LSNUM`. Issue **LSREAD**,INIT to reset `LSNUM` to 1. The load step files are assumed to be named `Jobname.Sn`, where `n` is a number assigned by the [[lswrite|LSWRITE]] command (01- 09,10,11, etc.). On systems with a 3-character limit on the extension, the S is dropped for `LSNUM` \> 99.

## Notes

Reads load and load step option data from the load step file into the database. **LSREAD** will not clear the database of all current loads. However, if a load is respecified with **LSREAD**, then it will overwrite the existing load. See the [[lswrite|LSWRITE]] command to write load step files, and the [[lsdele|LSDELE]] command to delete load step files. **LSREAD** removes any existing [[sfgrad|SFGRAD]] specification.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSREAD.html
