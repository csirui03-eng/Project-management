---
apdl: "VSUM"
method: vsum
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.volumes.Volumes.vsum
generated: 2026-08-22
tags: [mapdl-command]
---

# VSUM

PyMAPDL: `mapdl.vsum(lab='', **kwargs)`

Calculates and prints geometry statistics of the selected volumes.

## Parameters

**lab**: Controls the degree of tessellation used in the calculation of area properties. If `LAB` = DEFAULT, area calculations will use the degree of tessellation set through the [[facet|/FACET]] command. If `LAB` = FINE, area calculations are based on a finer tessellation.

## Notes

Calculates and prints geometry statistics (volume, centroid location, moments of inertia, etc.) associated with the selected volumes. Geometry items are reported in the global Cartesian coordinate system. A unit density is assumed unless the volumes have a material association via the [[vatt|VATT]] command. Items calculated by **VSUM** and later retrieved by a [[get|*GET]] or [[starvget|*VGET]] command are valid only if the model is not modified after the **VSUM** command is issued.

Setting a finer degree of tessellation will provide area calculations with greater accuracy, especially for thin, hollow models. However, using a finer degree of tessellation requires longer processing.

For very thin volumes, such that the ratio of the minimum to the maximum dimension is less than 0.01, the **VSUM** command can provide erroneous volume information. To ensure that such calculations are accurate, make certain that you subdivide such volumes so that the ratio of the minimum to the maximum is at least 0.05.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VSUM.html
