---
apdl: "FATIGUE"
method: fatigue
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7._status.Status.fatigue
generated: 2026-08-22
tags: [mapdl-command]
---

# FATIGUE

PyMAPDL: `mapdl.fatigue(**kwargs)`

Specifies "Fatigue data status" as the subsequent status topic.

## Notes

This is a status ( [[stat|STAT]] ) topic command that appears in the log file ( `Jobname.LOG` ) if status is requested for some items. This command is followed immediately by a [[stat|STAT]] command, which reports the status for the specified topic.

If entered directly into the program, the [[stat|STAT]] command should immediately follow this command.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FATIGUE.html
