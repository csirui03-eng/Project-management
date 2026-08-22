---
apdl: "PIPE"
method: pipe
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.status.Status.pipe
generated: 2026-08-22
tags: [mapdl-command]
---

# PIPE

PyMAPDL: `mapdl.pipe(**kwargs)`

Specifies "Pipe modeling" as the subsequent status topic.

## Notes

This is a status topic command. If status is requested for some items, it appears in the log file ( `Jobname.LOG` ). This command should be followed immediately by a [[stat|STAT]] command, which reports the status for the specified topic.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PIPE.html
