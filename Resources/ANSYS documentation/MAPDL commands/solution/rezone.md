---
apdl: "REZONE"
method: rezone
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.rezoning.Rezoning.rezone
generated: 2026-08-22
tags: [mapdl-command]
---

# REZONE

PyMAPDL: `mapdl.rezone(option='', ldstep='', sbstep='', **kwargs)`

Initiates the rezoning process, sets rezoning options, and rebuilds the database.

## Parameters

**option**

The [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html) method to employ:

- `MANUAL` - Manual rezoning. You decide when to use rezoning, what region(s) to rezone, and what remeshing method to use on the selected region(s). This method is currently the default and only option.

**ldstep**: The load step number at which rezoning should occur. The default value is the highest load step number found in the `Jobname.Rnnn` files (for the current jobname and in the current directory).

**sbstep**: The substep number of the specified load step ( `LDSTEP` ) at which rezoning should occur. The default value is the highest substep number found in the specified load step in the `Jobname.Rnnn` files (for the current jobname and in the current directory).

## Notes

The **REZONE** command rebuilds the database ( `.db` file) based on the specified load step and substep information, and updates nodes to their deformed position for remeshing.

Before issuing this command, clear the database via the [[clear|/CLEAR]] command.

For more information, see [Rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html) Distributed-Memory Parallel (DMP) Restriction This command is not supported in a DMP solution.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_REZONE.html
