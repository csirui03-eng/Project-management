---
apdl: "/QUIT"
method: quit
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.processor_entry.ProcessorEntry.quit
generated: 2026-08-22
tags: [mapdl-command]
---

# /QUIT

PyMAPDL: `mapdl.quit(**kwargs)`

Exits a processor.

## Notes

This is an alternative to the [[finish|FINISH]] command. If any cleanup or file writing is normally done by the [[finish|FINISH]] command, it is bypassed if the **/QUIT** command is used instead. A new processor may be entered after this command. See the `/EXIT` command to terminate the run.

This command is valid in any processor. This command is not valid at the Begin level.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_QUIT.html
