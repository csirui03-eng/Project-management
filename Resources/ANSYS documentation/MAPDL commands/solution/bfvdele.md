---
apdl: "BFVDELE"
method: bfvdele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_body_loads.SolidBodyLoads.bfvdele
generated: 2026-08-22
tags: [mapdl-command]
---

# BFVDELE

PyMAPDL: `mapdl.bfvdele(volu='', lab='', **kwargs)`

Deletes body-force loads on a volume.

## Parameters

**volu**: Volume at which body load is to be deleted. If ALL, delete for all selected volumes ( [[vsel|VSEL]] ). A component name may also be substituted for `VOLU`.

**lab**: Valid body load label. If ALL, use all appropriate labels. Load labels are listed under "Body Loads" in the input table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html). See the [[bfv|BFV]] command for labels.

## Notes

Deletes body-force loads (and all corresponding finite element loads) for a specified volume and label. Body loads may be defined on a volume with the [[bfv|BFV]] command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BFVDELE.html
