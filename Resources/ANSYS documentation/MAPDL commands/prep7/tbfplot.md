---
apdl: "TBFPLOT"
method: tbfplot
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.tbfplot
generated: 2026-08-22
tags: [mapdl-command]
---

# TBFPLOT

PyMAPDL: `mapdl.tbfplot(matid='', curvefitname='', expdatid='', colx='', coly1='', coly2='', **kwargs)`

Plots [material curve-fitting](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/Hlp_AM_GMCF.html) data.

## Parameters

**matid**: Material reference identification number.

**curvefitname**: Material curve-fitting model name (obtainable via [[tbft|TBFT]],LIST). Enclose the name within single quotes.

**expdatid**: Experimental data ID.

**colx**: Experimental data column to use in the X axis.

**coly1**: Experimental data column to use in the Y axis.

**coly2**: Fitted-data column to use in the Y axis.

## Notes

This command plots the fitted data specified via `ColY2` (the number of experimental data columns + 1) and the data specified via `ColY1` as a function of the X-axis data specified via `ColX`.

Issue this command after curve-fitting has been completed ( [[tbft|TBFT]],SOLVE).

Material curve-fitting does not support saving to ( [[save|SAVE]] ) and resuming from ( [[resume|RESUME]] ) the database file. You must therefore rerun the curve-fitting analysis, then issue **TBFPLOT** again to replot.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TBFPLOT.html
