---
apdl: "SPLOT"
method: splot
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.splot
generated: 2026-08-22
tags: [mapdl-command]
---

# SPLOT

PyMAPDL: `mapdl.splot(na1='', na2='', ninc='', mesh='', **kwargs)`

Displays the selected areas and a faceted view of their underlying surfaces

## Parameters

**na1**: Starting area for display of areas and underlying surfaces. If `NA1` = ALL (default), `NA2` and `NINC` are ignored and all selected areas are displayed ( [[asel|ASEL]] command).

**na2**: Last area to be displayed.

**ninc**: Numeric value setting steps between NA1 and NA2 for display. Default value is (1).

**mesh**: Specifies a rectangular mesh density used to display the underlying surface (default 4, i.e. 4 x 4).

## Notes

This command is valid in any processor. The plot output displays the external and internal trim curves and underlying surface. You cannot obtain a faceted view of your surface areas when you are using the [[slashexpand|/EXPAND]] command to create larger graphics displays.

Use [[aplot|APLOT]] for trimmed surface display.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SPLOT.html
