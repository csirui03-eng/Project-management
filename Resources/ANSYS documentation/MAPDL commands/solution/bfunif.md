---
apdl: "BFUNIF"
method: bfunif
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_body_loads.FeBodyLoads.bfunif
generated: 2026-08-22
tags: [mapdl-command]
---

# BFUNIF

PyMAPDL: `mapdl.bfunif(lab='', value='', **kwargs)`

Assigns a uniform body-force load to all nodes.

**Command default:**

Set TEMP to the reference temperature ( [[tref|TREF]] but not [[mp|MP]],REFT), and FLUE and HGEN to zero.

## Parameters

**lab**

Valid body load label. If ALL, use all appropriate labels.

(table not available in the PyMAPDL source, see the Ansys help page)

**value**: Uniform value associated with `Lab` item, or table name when specifying tabular boundary conditions. To specify a table, enclose the table name in percent signs (%), for example, **BFUNIF**, `Lab`,`tabname`.

## Notes

In a transient or nonlinear thermal analysis, the uniform temperature is used during the first iteration of a solution as follows: (a) as the starting nodal temperature except where temperatures are explicitly specified ( [[d|D]], [[dk|DK]] ), and (b) to evaluate temperature-dependent material properties. In a structural analysis, the uniform temperature is used as the default temperature for thermal strain calculations and material property evaluation except where body load temperatures are specified ( [[bf|BF]], [[bfe|BFE]], [[bfk|BFK]], [[ldread|LDREAD]] ). In other scalar field analyses, the uniform temperature is used for material property evaluation.

An alternate command, [[tunif|TUNIF]], may be used to set the uniform temperature instead of **BFUNIF**,TEMP. Since [[tunif|TUNIF]] (or **BFUNIF**,TEMP) is step-applied in the first iteration, you should use [[bf|BF]], ALL, TEMP, Value to ramp on a uniform temperature load.

You can specify a table name only when using temperature (TEMP), heat generation rate (HGEN), and diffusing substance generation rate (DGEN) body load labels. When using TEMP, you can define a one- dimensional table that varies with respect to time (TIME) only. When defining this table, enter TIME as the primary variable. No other primary variables are valid.

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via the [[lvscale|LVSCALE]] command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BFUNIF.html
