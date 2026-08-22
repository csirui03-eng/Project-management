---
apdl: "/CLEAR"
method: clear
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.set_up.SetUp.clear
generated: 2026-08-22
tags: [mapdl-command]
---

# /CLEAR

PyMAPDL: `mapdl.clear(read='', **kwargs)`

Clears the database.

## Parameters

**read**

File read option:

- `START` - Reread `start.ans` file (default).
- `NOSTART` - Do not reread `start.ans` file.

## Notes

The **/CLEAR** command resets the database to the conditions present at the beginning of the problem.

The command is typically used between multiple analyses in the same run, or between passes of a multipass analysis (such as between substructure generation, use, and expansion passes).

The command sets the import and Boolean options back to the default, deletes all items from the database, and sets memory values to zero for items derived from database information. (All files remain intact.) The command also resets the jobname to match the currently open session `.LOG` and `.ERR` files, returning the jobname to its original value or to the most recent value specified via [[filname|/FILNAME]] with `KEY` = 1.

After the database is cleared, the `start.ans` file is reread (by default) unless `Read` = NOSTART.

Additional commands cannot be stacked (via the \$ separator) on the same line as the **/CLEAR** command.

Use caution when placing the **/CLEAR** command within branching constructs (for example, those using `*DO` or `*IF` commands), as the command deletes all parameters including the looping parameter for do-loops. (To preserve your iteration parameter, issue a [[parsav|PARSAV]] command prior to **/CLEAR**, then follow **/CLEAR** with a [[parres|PARRES]] command.)

This command is valid in any processor. Issuing this command at any point clears the database.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CLEAR.html
