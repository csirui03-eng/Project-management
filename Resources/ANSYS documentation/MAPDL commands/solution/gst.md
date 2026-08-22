---
apdl: "/GST"
method: gst
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.gst
generated: 2026-08-22
tags: [mapdl-command]
---

# /GST

PyMAPDL: `mapdl.gst(lab='', runtrack='', **kwargs)`

Enables the Graphical Solution Tracking (GST) feature.

## Parameters

**lab**

Enables or disables the GST feature:

- ON - Enable
- OFF - Disable

**runtrack**

Enables or disables `.GST` file viewing in the Results Tracker utility:

- ON - Enable
- OFF - Disable (default)

## Notes

For interactive sessions using the GUI ( [[menu|/MENU]],ON), GST directs solution graphics to the screen.

For interactive sessions not using the GUI ( [[menu|/MENU]],OFF), or for batch sessions, GST saves solution graphics to the `Jobname.GST` file. To create a `Jobname.GST` file that is compatible with the Results Tracker utility (available via the Mechanical APDL Product Launcher ), issue **/GST**,ON,ON.

You can use the GST feature for these nonlinear analysis types: structural, thermal, electric, magnetic, fluid, and diffusion.

For more information about GST and illustrations of the GST graphics for each analysis type, see the analysis guide for the appropriate discipline.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GST.html
