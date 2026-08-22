---
apdl: "EDFPLOT"
method: edfplot
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edfplot
generated: 2026-08-22
tags: [mapdl-command]
---

# EDFPLOT

PyMAPDL: `mapdl.edfplot(key='', **kwargs)`

Allows plotting of explicit dynamics forces and other load symbols.

## Parameters

**key**

Load symbol plotting key.

ON or 1 - Turn display of load symbols on (default).

OFF or 0 - Turn display of load symbols off.

## Notes

You must issue EDFPLOT,ON to display explicit dynamics load symbols. The explicit load symbols are erased automatically upon a subsequent plot command.

An explicit load symbol always indicates a positive load direction (e.g., positive X direction for FX load), even if the load value is negative. The load symbol does not reflect the load magnitude. You can use standard ANSYS symbol controls to control the appearance of the load symbol. No load symbol is displayed for temperature loads.

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
