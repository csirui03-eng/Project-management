---
apdl: "LSUM"
method: lsum
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.lsum
generated: 2026-08-22
tags: [mapdl-command]
---

# LSUM

PyMAPDL: `mapdl.lsum(**kwargs)`

Calculates and prints geometry statistics of the selected lines.

## Notes

Calculates and prints geometry statistics (length, centroid, moments of inertia, etc.) associated with the selected lines. Geometry items are reported in the global Cartesian coordinate system. A unit density is assumed, irrespective of any material associations ( [[latt|LATT]], [[mat|MAT]] ). Items calculated by **LSUM** and later retrieved by a [[get|*GET]] or [[starvget|*VGET]] command are valid only if the model is not modified after the **LSUM** command is issued.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSUM.html
