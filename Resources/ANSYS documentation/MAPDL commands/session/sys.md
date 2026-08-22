---
apdl: "/SYS"
method: sys
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.run_controls.RunControls.sys
generated: 2026-08-22
tags: [mapdl-command]
---

# /SYS

PyMAPDL: `mapdl.sys(string='', **kwargs)`

Passes a command string to the operating system.

## Parameters

**string**: Command string, up to 639 characters (including blanks, commas, etc.). The specified string is passed verbatim to the operating system, that is, no parameter substitution is performed.

## Notes

Passes a command string to the operating system for execution (see the [Operations Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ope/Hlp_G_OPE8.html)). Typical strings are system commands such as list, copy, rename, etc. Control returns to Mechanical APDL after the system procedure is completed. Mechanical APDL may not be aware of your specific user environment. For example, on Linux this command may not recognize aliases, depending on the hardware platform and user environment.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SYS.html
