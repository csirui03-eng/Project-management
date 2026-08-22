---
apdl: "FINISH"
method: finish
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.processor_entry.ProcessorEntry.finish
generated: 2026-08-22
tags: [mapdl-command]
---

# FINISH

PyMAPDL: `mapdl.finish(**kwargs)`

Exits normally from a processor.

## Notes

This command exits any of the Mechanical APDL processors.

When exiting the Mechanical APDL processors, data remains intact in the database, but the database is not automatically written to a file. (Issue [[save|SAVE]] to write the database to a file.)

If exiting POST1 or POST26:

- POST1: Data in the database remains intact (including the POST1 element table data, the path table data, the fatigue table data, and the load case pointers).
- POST26: Data in the database remains intact, except that POST26 variables are erased and specification commands (such as [[file|FILE]], [[prtime|PRTIME]], and [[nprint|NPRINT]] ) are reset. Issue [[quit|/QUIT]] to exit the processor and bypass these exceptions.

See [[quit|/QUIT]] for an alternate processor exit command.

This command is valid in any processor. This command is not valid at the Begin level.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FINISH.html
