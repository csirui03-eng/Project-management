---
apdl: "/STATUS"
method: slashstatus
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.run_controls.RunControls.slashstatus
generated: 2026-08-22
tags: [mapdl-command]
---

# /STATUS

PyMAPDL: `mapdl.slashstatus(lab='', **kwargs)`

Lists the status of items for the run.

## Parameters

**lab**

Items to list status for:

- `ALL` - List all below (default).
- `TITLE` - List only titles, `Jobname`, and revision number.
- `UNITS` - List only units.
- `MEM` - List only memory data statistics.
- `DB` - List only database statistics
- `CONFIG` - List only configuration parameters.
- `GLOBAL` - Provides a global status summary.
- `SOLU` - Provides a solution status summary.
- `PROD` - Provides a product summary.

## Notes

Displays various items active for the run (such as the Mechanical APDL revision number, `Jobname`, titles, units, configuration parameters, database statistics, etc.).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_STATUS.html
