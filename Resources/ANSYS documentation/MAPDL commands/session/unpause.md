---
apdl: "UNPAUSE"
method: unpause
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.run_controls.RunControls.unpause
generated: 2026-08-22
tags: [mapdl-command]
---

# UNPAUSE

PyMAPDL: `mapdl.unpause(**kwargs)`

Restores use of a temporarily released product license.

## Notes

The **UNPAUSE** command restores use of a temporarily released (paused) product license. The command is valid only after a previously issued [[pause|PAUSE]] command.

When use of the product license is paused via the [[pause|PAUSE]] command, no other operation (other than [[save|SAVE]] or `/EXIT` ) is possible until you issue the **UNPAUSE** command.

For more information, see the documentation for the [[pause|PAUSE]] command and the [Ansys Licensing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/licensing/Hlp_IN_TBSHOOT.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_UNPAUSE.html
