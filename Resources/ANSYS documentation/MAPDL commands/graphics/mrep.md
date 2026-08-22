---
apdl: "/MREP"
method: mrep
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.mrep
generated: 2026-08-22
tags: [mapdl-command]
---

# /MREP

PyMAPDL: `mapdl.mrep(name='', arg1='', arg2='', arg3='', arg4='', arg5='', arg6='', arg7='', arg8='', arg9='', arg10='', arg11='', arg12='', arg13='', arg14='', arg15='', arg16='', arg17='', arg18='', **kwargs)`

Enables you to reissue the graphics command macro "name" during a replot or zoom operation.

## Parameters

**name**: The name identifying the macro file or macro block on a macro library file. The name can contain up to eight characters maximum and must begin with a letter.

**arg1**, **arg2**, **arg3**, **arg4**, **arg5**, **arg6**, **arg7**, **arg8**, **arg9**, **arg10**, **arg11**, **arg12**, **arg13**, **arg14**, **arg15**, **arg16**, **arg17**, **arg18**: Values to be passed into the file or block.

## Notes

This command reissues the graphics command macro "name" during a replot operation ( [[replot|/REPLOT]] ) or a zoom ( [[zoom|/ZOOM]] ) operation. The program passes the command macro arguments to the replot and zoom feature for use by the graphics macro. You should place the `s-MREP` command at the end of the graphics command macro, following the last graphics command within the macro, to enable the replot or zoom feature.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MREP.html
