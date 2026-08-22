---
apdl: "MODSELOPTION"
method: modseloption
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.modseloption
generated: 2026-08-22
tags: [mapdl-command]
---

# MODSELOPTION

PyMAPDL: `mapdl.modseloption(dir1='', dir2='', dir3='', dir4='', dir5='', dir6='', **kwargs)`

Specifies the criteria for selecting the modes to be expanded.

## Parameters

**dir1**, **dir2**, **dir3**, **dir4**, **dir5**, **dir6**

Selection of the direction to be expanded.

For `ModeSelMethod` = EFFM on the [[mxpand|MXPAND]] command, the directions correspond to the global Cartesian directions, i.e. 1=X, 2=Y, 3=Z, 4=ROTX, 5=ROTY, and 6=ROTZ. If `dir1` = YES, then any mode in this direction is expanded if its modal effective mass divided by the total mass (modal effective mass ratio) is greater than `SIGNIF` on the [[mxpand|MXPAND]] command. If `dir1` =NO, then the specified direction is not considered as a criterion for expansion. If `dir1` is given a numerical decimal value, modes in that direction are selected (starting from the ones with the largest modal effective mass ratios to the smallest) until the sum of their modal effective mass ratio equals this requested threshold.

For `ModeSelMethod` = MODC on the [[mxpand|MXPAND]] command, `dir1` corresponds to the first input spectrum, `dir2` to the second, etc. (i.e. for multiple spectrum inputs; the actual directions correspond to their respective SED directions). If `dir1` =YES, then any mode in this spectrum is expanded if its mode coefficient divided by the largest mode coefficient is greater than SIGNIF on the [[mxpand|MXPAND]] command. If `dir1` =NO, then the specified direction is not considered as a criterion for expansion.

## Notes

This command is only applicable when a mode selection method is defined ( `ModeSelMethod` on the [[mxpand|MXPAND]] command). See [Using Mode Selection](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR_SMSUP.html#strModSelBasDD)

If a numerical value is specified for a direction, the significance threshold (SIGNIF on the [[mxpand|MXPAND]] command) is ignored for the selection of the modes in this direction.

If a mode is determined to be expanded in **any** of the 6 directions, it will be expanded in the `.MODE` file. Otherwise, the mode will not be expanded.

The default behavior is to consider all directions for expansion.

For `ModeSelMethod` = EFFM on the [[mxpand|MXPAND]] command, `dir4`, `dir5`, and `dir6` are not considered if mass related information have been calculated using the lumped approximation instead of the precise calculation (See [Mass Related Information](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/ans_thry_MRI.html#bob121)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MODSELOPTION.html
