---
apdl: "BFL"
method: bfl
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_body_loads.SolidBodyLoads.bfl
generated: 2026-08-22
tags: [mapdl-command]
---

# BFL

PyMAPDL: `mapdl.bfl(line='', lab='', val1='', val2='', val3='', val4='', **kwargs)`

Defines a body-force load on a line.

## Parameters

**line**: Line to which body load applies. If ALL, apply to all selected lines ( [[lsel|LSEL]] ). A component name may also be substituted for `Line`.

**lab**

Valid body load label. Load labels are listed under "Body loads" in the input table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html).

(table not available in the PyMAPDL source, see the Ansys help page)

**val1**, **val2**, **val3**: Value associated with the `Lab` item or a table name for specifying tabular boundary conditions. Use only `VAL1` for TEMP, FLUE, HGEN, and CHRGD. For acoustics, if `Lab` = JS, use `VAL1` for mass source in a harmonic analysis or mass source rate in a transient analysis, and ignore `VAL2` and `VAL3`. When specifying a table name, you must enclose the table name in percent signs (%), for example, **BFL**, `Line`, `Lab`,`tabname`. Use the [[dim|*DIM]] command to define a table.

**val4**: If `Lab` = JS, `VAL4` is the phase angle in degrees.

## Notes

Defines a body-force load (such as temperature in a structural analysis, heat generation rate in a thermal analysis, etc.) on a line. Body loads may be transferred from lines to line elements (or to nodes if line elements do not exist) with the [[bftran|BFTRAN]] or [[sbctran|SBCTRAN]] commands.

You can specify a table name only when using temperature (TEMP) and heat generation rate (HGEN) body load labels.

Body loads specified by the **BFL** command can conflict with other specified body loads. See Resolution of Conflicting Body Load Specifications in the [Basic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS19.html) for details.

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via the [[lvscale|LVSCALE]] command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BFL.html
