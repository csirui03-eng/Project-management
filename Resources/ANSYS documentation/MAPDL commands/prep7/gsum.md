---
apdl: "GSUM"
method: gsum
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.keypoints.Keypoints.gsum
generated: 2026-08-22
tags: [mapdl-command]
---

# GSUM

PyMAPDL: `mapdl.gsum(**kwargs)`

Calculates and prints geometry items.

## Notes

Calculates and prints geometry items (centroid location, moments of inertia, length, area, volume etc.) associated with the selected keypoints, lines, areas, and volumes. Geometry items are reported in the global Cartesian coordinate system. For volumes, a unit density is assumed unless the volumes have a material association via the [[vatt|VATT]] command. For areas, a unit density (and thickness) is assumed unless the areas have a material (and real constant) association via the [[aatt|AATT]] command. For lines and keypoints, a unit density is assumed, irrespective of any material associations ( [[latt|LATT]], [[katt|KATT]], [[mat|MAT]] ). Items calculated by **GSUM** and later retrieved by a [[get|*GET]] or [[starvget|*VGET]] commands are valid only if the model is not modified after the **GSUM** command is issued. This command combines the functions of the [[ksum|KSUM]], [[lsum|LSUM]], [[asum|ASUM]], and [[vsum|VSUM]] commands.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GSUM.html
