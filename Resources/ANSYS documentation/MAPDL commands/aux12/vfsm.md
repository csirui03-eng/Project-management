---
apdl: "VFSM"
method: vfsm
group: aux12
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux12.radiosity_solver.RadiositySolver.vfsm
generated: 2026-08-22
tags: [mapdl-command]
---

# VFSM

PyMAPDL: `mapdl.vfsm(action='', encl='', opt='', maxiter='', conv='', **kwargs)`

Adjusts view factor matrix to satisfy reciprocity and/or row sum properties.

## Parameters

**action**

Action to be performed:

- `DEFINE` - Define a view factor summation (default)
- `CLEAR` - Resets the scaling method to 0 for all enclosures. All subsequent arguments are ignored.
- `STATUS` - Outputs the `OPT` value for each enclosure in the model.

**encl**: Previously defined enclosure number for the view factor adjustment.

**opt**

Option key:

- `0` - The view factor matrix values are not adjusted (default).
- `1` - The view factor matrix values are adjusted so that the row sum equals 1.0.
- `2` - The view factor matrix values are adjusted so that the row sum equals 1.0 and the reciprocity relationship is satisfied.
- `3` - The view factor matrix values are adjusted so that the reciprocity relationship is satisfied.
- `4` - The view factor matrix values are adjusted so that the original row sum is maintained and the reciprocity relationship is satisfied.

**maxiter**: Maximum number of iterations to achieve convergence. Valid only when `OPT` = 2 or 4. Default is 100.

**conv**: Convergence value for row sum. Iterations will continue (up to `MAXITER` ) until the maximum residual over all the rows is less than this value. Valid only when `OPT` = 2 or 4. Default is 1E-3.

## Notes

To have a good energy balance, it is important to satisfy both the row sum and reciprocity relationships. For more information, see [View Factors](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_heat1.html#eq28e43bc0-b07b-459a-87bc-d8cf1cf99906) in the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html).

`OPT` = 1 and 2 are suitable for perfect enclosures. `OPT` = 1 is less expensive than `OPT` = 2 because no iterations are involved. However, with `OPT` = 1, the reciprocity relationship is not satisfied.

`OPT` = 3 and 4 are suitable for leaky enclosures. `OPT` = 3 is less expensive than `OPT` = 4 because no iterations are involved. However, with `OPT` = 3, the original row sum is not maintained.

The **VFSM** command must be used before [[vfopt|VFOPT]] is issued, or Solve is initiated.

While the primary purpose of the **VFSM** command is to adjust the viewfactor matrix to satisfy reciprocity and rowsum properties, a side effect of this command is that the model could flip from being an imperfect to a perfect enclosure and the space node ignored if the rowsum becomes 1.0. The program's check for an imperfect enclosure is not based geometry, but rather on the value of the rowsum of all rows of the enclosure view factor matrix. A rowsum close to 1.0 is deemed a perfect enclosure; otherwise, it is an imperfect enclosure, which requires you to define a spacenode. It is important to be aware that the **VFSM** command can affect the [view factor](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_heat1.html#eq28e43bc0-b07b-459a-87bc-d8cf1cf99906) rowsum and potentially also whether the enclosure is treated as an imperfect or perfect enclosure.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VFSM.html
