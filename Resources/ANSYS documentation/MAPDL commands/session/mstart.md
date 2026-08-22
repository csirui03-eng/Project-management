---
apdl: "/MSTART"
method: mstart
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.run_controls.RunControls.mstart
generated: 2026-08-22
tags: [mapdl-command]
---

# /MSTART

PyMAPDL: `mapdl.mstart(label='', key='', **kwargs)`

Controls the initial GUI components.

## Parameters

**label**

Label identifying the GUI component:

- `ZOOM` - [Pan, Zoom, Rotate](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_wid/Hlp_UI_PanZoom.html#wpanzoomk) dialog box, off by default.
- `WORK` - [Offset Working Plane](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_wid/Hlp_UI_WP_Offset.html#wwpoffsetdynamic) dialog box, off by default.
- `WPSET` - [Working Plane Settings](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_wid/Hlp_UI_WP_Set.html#wwpsetgrid) dialog box, off by default.
- `ABBR` - [Edit Toolbar/Abbreviations](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_wid/Hlp_UI_Toolbar.html#edittoolbarselect) dialog box, off by default.
- `PARM` - [Scalar Parameters](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_wid/Hlp_UI_Scal_Parm.html#wscalparmselect) dialog box, off by default.
- `SELE` - Select Entities dialog box, off by default.
- `ANNO` - Annotation dialog box, off by default.
- `HARD` - Hard Copy dialog box, off by default.
- `UTIL` - Activates the pre-6.1 (UIDL) GUI (off by default).

**key**

Switch value:

- `OFF or 0` - Component does not appear when GUI is initialized.
- `ON or 1` - Component appears when GUI is initialized.

## Notes

Controls which components appear when the Graphical User Interface (GUI) is initially brought up. This command is valid only before the GUI is brought up ( [[menu|/MENU]],ON) and is intended to be used in the `start.ans` file. It only affects how the GUI is initialized ; you can always bring up or close any component once you are in the GUI.

This command is valid only at the Begin Level.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MSTART.html
