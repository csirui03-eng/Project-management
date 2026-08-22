---
apdl: "PAUSE"
method: pause
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.run_controls.RunControls.pause
generated: 2026-08-22
tags: [mapdl-command]
---

# PAUSE

PyMAPDL: `mapdl.pause(**kwargs)`

Temporarily releases the current product license.

## Notes

The **PAUSE** command temporarily releases (or pauses) the current product license so that another application can use it.

This application consumes a license as soon as you launch it, and retains that license until it is finished. If you launch the product interactively, the license is retained until you either close the application or issue a **PAUSE** command via the command line.

No other operation (other than [[save|SAVE]] or `/EXIT` ) is possible in the current application while use of the product license is paused.

When the second application has finished and releases the license, issue an [[unpause|UNPAUSE]] command via the command line to restore use of the license to the current application.

For more information, see the [Ansys Licensing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/licensing/Hlp_IN_TBSHOOT.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PAUSE.html
