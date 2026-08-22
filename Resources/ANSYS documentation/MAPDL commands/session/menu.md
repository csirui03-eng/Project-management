---
apdl: "/MENU"
method: menu
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.run_controls.RunControls.menu
generated: 2026-08-22
tags: [mapdl-command]
---

# /MENU

PyMAPDL: `mapdl.menu(key='', **kwargs)`

Activates the Graphical User Interface (GUI).

## Parameters

**key**

Activation key:

- `ON` - Activates the menu system (device dependent).

## Notes

Activates the Graphical User Interface (GUI).

> [!WARNING]
> if you include the **/MENU**,ON command in your `start.ans`, it should be the last command in the file. Any commands after **/MENU**,ON may be ignored. (It is not necessary to include the [[show|/SHOW]] and **/MENU**,ON commands in `start.ans` if you will be using the launcher to enter the Mechanical APDL program.)

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MENU.html
