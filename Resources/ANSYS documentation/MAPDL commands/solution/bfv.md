---
apdl: "BFV"
method: bfv
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_body_loads.SolidBodyLoads.bfv
generated: 2026-08-22
tags: [mapdl-command]
---

# BFV

PyMAPDL: `mapdl.bfv(volu='', lab='', val1='', val2='', val3='', phase='', **kwargs)`

Defines a body-force load on a volume.

## Parameters

**volu**: Volume to which body load applies. If ALL, apply to all selected volumes ( [[vsel|VSEL]] ). A component name may also be substituted for `Volu`.

**lab**

Valid body load label. Load labels are listed under "Body Loads" in the input table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html).

(table not available in the PyMAPDL source, see the Ansys help page)

**val1**, **val2**, **val3**: Value associated with the `Lab` item or a table name for specifying tabular boundary conditions. Use only `VAL1` for TEMP, FLUE, HGEN, and CHRGD. Use `VAL1`, `VAL2`, and `VAL3` for the X, Y, and Z components of JS. For `Lab` = JS in magnetics, use `VAL1`, `VAL2`, and `VAL3` for the X, Y, and Z components. For acoustics, if `Lab` = JS, use `VAL1` for mass source in a harmonic analysis or mass source rate in a transient analysis, and ignore `VAL2` and `VAL3`. When specifying a table name, you must enclose the table name in percent signs (%), e.g., **BFV**, `Volu`, `Lab`,`tabname`. Use the [[dim|*DIM]] command to define a table.

**phase**: Phase angle in degrees associated with the JS label.

## Notes

Defines a body-force load (such as temperature in a structural analysis, heat generation rate in a thermal analysis, etc.) on a volume. Body loads may be transferred from volumes to volume elements (or to nodes if volume elements do not exist) with the [[bftran|BFTRAN]] or [[sbctran|SBCTRAN]] commands. Body loads default to the value specified on the [[bfunif|BFUNIF]] command, if it was previously specified.

You can specify a table name only when using temperature (TEMP) and heat generation rate (HGEN) body load labels.

Body loads specified by the **BFV** command can conflict with other specified body loads. See Resolution of Conflicting Body Load Specifications in the [Basic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS19.html) for details.

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via the [[lvscale|LVSCALE]] command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BFV.html
