---
apdl: "*EXIT"
method: starexit
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.process_controls.ProcessControls.starexit
generated: 2026-08-22
tags: [mapdl-command]
---

# *EXIT

PyMAPDL: `mapdl.starexit(**kwargs)`

Exits a do-loop.

## Notes

The command following the `*ENDDO` is executed next. The exit option may also be conditional \[Use the `*IF` \]. The **\*EXIT** command must appear on the same file as the `*DO` command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EXIT_st.html
