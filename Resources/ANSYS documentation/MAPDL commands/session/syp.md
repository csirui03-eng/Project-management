---
apdl: "/SYP"
method: syp
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.run_controls.RunControls.syp
generated: 2026-08-22
tags: [mapdl-command]
---

# /SYP

PyMAPDL: `mapdl.syp(string='', arg1='', arg2='', arg3='', arg4='', arg5='', arg6='', arg7='', arg8='', **kwargs)`

Passes a command string and arguments to the operating system.

## Parameters

**string**: Command string (cannot include commas). See also the [[sys|/SYS]] command.

**arg1**, **arg2**, **arg3**, **arg4**, **arg5**, **arg6**, **arg7**, **arg8**: Arguments to be appended to the command string, separated by blanks, commas, or other delimiter characters (see the [Operations Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ope/Hlp_G_OPE8.html)). The arguments may be numbers, parameters, or parametric expressions.

## Notes

Passes a command string to the operating system for execution, along with arguments to be appended to the command string. See the [Operations Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ope/Hlp_G_OPE8.html) for details. Mechanical APDL may not be aware of your specific user environment. For example, on Linux this command may not recognize aliases, depending on the hardware platform and user environment.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SYP.html
