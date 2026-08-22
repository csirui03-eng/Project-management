---
apdl: "MDAMP"
method: mdamp
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.mdamp
generated: 2026-08-22
tags: [mapdl-command]
---

# MDAMP

PyMAPDL: `mapdl.mdamp(stloc='', v1='', v2='', v3='', v4='', v5='', v6='', **kwargs)`

Defines the damping ratios as a function of mode.

## Parameters

**stloc**: Starting location in table for entering data. For example, if `STLOC` = 1, data input in the `V1` field applies to the first constant in the table. If `STLOC` = 7, data input in the `V1` field applies to the seventh constant in the table, etc. Defaults to the last location filled + 1.

**v1**, **v2**, **v3**, **v4**, **v5**, **v6**: Data assigned to six locations starting with `STLOC`. If a value is already in this location, it will be redefined. Blank values for `V2` to `V6` leave the corresponding previous value unchanged.

## Notes

Defines the damping ratios as a function of mode. Table position corresponds to mode number. These ratios are added to the [[dmprat|DMPRAT]] value, if defined. Use the [[stat|STAT]] command to list current values. This command applies to mode-superposition harmonic ( [[antype|ANTYPE]],HARMIC), mode- superposition linear transient dynamic ( [[antype|ANTYPE]],TRANS), and spectrum ( [[antype|ANTYPE]],SPECTR) analyses. Repeat the **MDAMP** command for additional constants (10000 maximum).

**MDAMP** can also be defined in a substructure analysis that uses component mode synthesis. The damping ratios are added on the diagonal of the reduced damping matrix, as explained in [Component Mode Synthesis (CMS)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc6.html#eq39b62ffb-3890-471d-a79e-2d6096214d0b)

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MDAMP.html
