---
apdl: "*VPLOT"
method: starvplot
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.array_parameters.ArrayParameters.starvplot
generated: 2026-08-22
tags: [mapdl-command]
---

# *VPLOT

PyMAPDL: `mapdl.starvplot(parx='', pary='', y2='', y3='', y4='', y5='', y6='', y7='', y8='', **kwargs)`

Graphs columns (vectors) of array parameters.

## Parameters

**parx**: Name of the array parameter whose column vector values will be the abscissa of the graph. If blank, row subscript numbers are used instead. `ParX` is not sorted by the program.

**pary**, **y2**, **y3**, **y4**, **y5**, **y6**, **y7**, **y8**: Additional column subscript of the `ParY` array parameter whose values are to be graphed against the `ParX` values.

## Notes

The column to be graphed and the starting row for each array parameter must be specified as subscripts. Additional columns of the `ParY` array parameter may be graphed by specifying column numbers for `Y2`, `Y3`,..., `Y8`. For example, **\*VPLOT**,TIME (4,6), DISP (8,1),2,3 specifies that the 1st, 2nd, and 3rd columns of array parameter DISP (all starting at row 8) are to be graphed against the 6th column of array parameter TIME (starting at row 4). The columns are graphed from the starting row to their maximum extent. See the [[vlen|*VLEN]] and [[vmask|*VMASK]] commands to limit or skip data to be graphed. The array parameters specified on the **\*VPLOT** command must be of the same type (type ARRAY or TABLE; ( [[dim|*DIM]] ). Arrays of type TABLE are graphed as continuous curves. Arrays of type ARRAY is displayed in bar chart fashion.

The normal curve labeling scheme for **\*VPLOT** is to label curve 1 "COL 1", curve 2 "COL 2" and so on. You can use the [[gcolumn|/GCOLUMN]] command to apply user-specified labels (8 characters maximum) to your curves. See [Modifying Curve Labels](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_apdl/Hlp_P_APDL3_11.html#apdlch3figt14lm) in the [Ansys Parametric Design Language Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_apdl/apdlxpl.html) for more information on using [[gcolumn|/GCOLUMN]].

When a graph plot reaches minimum or maximum y-axis limits, the program indicates the condition by clipping the graph. The clip appears as a horizontal magenta line. Mechanical APDL calculates y-axis limits automatically; however, you can modify the (YMIN and YMAX) limits via the [[yrange|/YRANGE]] command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VPLOT_st.html
