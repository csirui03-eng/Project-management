---
apdl: "KSUM"
method: ksum
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.keypoints.Keypoints.ksum
generated: 2026-08-22
tags: [mapdl-command]
---

# KSUM

PyMAPDL: `mapdl.ksum(**kwargs)`

Calculates and prints geometry statistics of the selected keypoints.

## Notes

Calculates and prints geometry statistics (centroid location, moments of inertia, etc.) associated with the selected keypoints. Geometry items are reported in the global Cartesian coordinate system. A unit density is assumed, irrespective of any material associations ( [[katt|KATT]], [[mat|MAT]] ). Items calculated by **KSUM** and later retrieved by a [[get|*GET]] or [[starvget|*VGET]] command are valid only if the model is not modified after the **KSUM** command is issued.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KSUM.html
