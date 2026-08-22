---
apdl: "CLRMSHLN"
method: clrmshln
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.clrmshln
generated: 2026-08-22
tags: [mapdl-command]
---

# CLRMSHLN

PyMAPDL: `mapdl.clrmshln(**kwargs)`

Clears meshed entities.

## Notes

When you use the GUI method to set the number of elements on specified lines, and any of those lines is connected to one or more meshed lines, areas, or volumes, the program gives you the option to clear the meshed entities. This occurs only when you perform this operation via the GUI; the program does not provide such an option when you use the command method ( [[lesize|LESIZE]] ).

If you activate the mesh clearing option, the program invokes a Mechanical APDL macro, **CLRMSHLN**, that clears the meshed entities. This macro name will appear in the log file ( `Jobname.LOG` ). This macro is for the Mechanical APDL program's internal use only. This command is not intended to be typed in directly in a Mechanical APDL session, although it can be included in an input file for batch input or for use via [[input|/INPUT]].

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CLRMSHLN.html
