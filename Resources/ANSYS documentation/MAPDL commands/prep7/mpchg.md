---
apdl: "MPCHG"
method: mpchg
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.mpchg
generated: 2026-08-22
tags: [mapdl-command]
---

# MPCHG

PyMAPDL: `mapdl.mpchg(mat='', elem='', **kwargs)`

Changes the material number attribute of an element.

## Parameters

**mat**: Assign this material number to the element. Material numbers are defined with the material property commands ( [[mp|MP]] ).

**elem**: Element for material change. If ALL, change materials for all selected elements ( [[esel|ESEL]] ).

## Notes

Changes the material number of the specified element. Between load steps in SOLUTION, material properties cannot be changed from linear to nonlinear, nonlinear to linear, or from one nonlinear option to another.

If you change from one CHABOCHE model to another CHABOCHE model, the different models need to have the same number of data points.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MPCHG.html
