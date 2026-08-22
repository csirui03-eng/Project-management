---
apdl: "RESET"
method: reset
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.set_up.SetUp.reset
generated: 2026-08-22
tags: [mapdl-command]
---

# RESET

PyMAPDL: `mapdl.reset(**kwargs)`

Resets all POST1 or POST26 specifications to initial defaults.

## Notes

Has the same effect as entering the processor the first time within the run. In POST1, resets all specifications to initial defaults, erases all element table items, path table data, and load case pointers. In POST26, resets all specifications to initial defaults, erases all variables defined, and zeroes the data storage space.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RESET.html
