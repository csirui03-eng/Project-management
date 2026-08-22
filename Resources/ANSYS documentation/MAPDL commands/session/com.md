---
apdl: "/COM"
method: com
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.list_controls.ListControls.com
generated: 2026-08-22
tags: [mapdl-command]
---

# /COM

PyMAPDL: `mapdl.com(comment='', **kwargs)`

Places a comment in the output.

## Parameters

**comment**: Comment string, up to 75 characters.

## Notes

The output from this command consists of the comment string. This command is similar to `C***` except that the comment produced by `C***` is more easily identified in the output. Parameter substitution within the comment occurs for every valid expression delimited by percent (%) signs. Enclosing such an expression in single quotes prevents parameter substitution.

Another way to include a comment is to precede it with a ! character (on the same line). The ! may be placed anywhere on the line, and any input following it is ignored as a comment. No output is produced by such a comment, but the comment line is included on the log file. This is a convenient way to annotate the log file.

This command is valid anywhere.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_COM.html
