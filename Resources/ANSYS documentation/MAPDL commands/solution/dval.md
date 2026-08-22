---
apdl: "DVAL"
method: dval
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_constraints.FeConstraints.dval
generated: 2026-08-22
tags: [mapdl-command]
---

# DVAL

PyMAPDL: `mapdl.dval(baseid='', lab='', value='', value2='', keycal='', **kwargs)`

Defines values at enforced motion base.

## Parameters

**baseid**: The identification number of the enforced motion base (defined using the [[d|D]] command in the modal analysis).

**lab**

- `U` - Enforced displacement.
- `ACC` - Enforced acceleration.

**value**: The value or table name reference for tabular boundary conditions. To specify a table, enclose the table name in percent (%) signs ( **DVAL**, `BaseID`,U,`tablename`). Use the [[dim|*DIM]] command to define a table.

**value2**: The value of the second degree of freedom (if present). If the analysis type and the degree of freedom allow a complex input, `VALUE` is the real component and `VALUE2` is the imaginary component.

**keycal**

Displacement result calculation key:

- `ON` - Calculate absolute displacement and acceleration results (default).
- `OFF` - Calculate relative displacement and acceleration results.

## Notes

In a mode-superposition harmonic or transient analysis, you can apply enforced displacement or acceleration loads. If multiple loads are specified for the same base identification number (BaseID), the last load applied overrides the previous ones. For example, the following commands apply displacement to the base with identification number 1:

``` apdl
DVAL,1,U,VALUE
DVAL,1,ACC,VALUE
```

In this case, the acceleration (ACC) applied in the last command will override the displacement (U).

Issue [[lsclear|LSCLEAR]],LSOPT to delete **DVAL** command options from the database.

For more information, see [Enforced Motion Method for Mode-Superposition Transient and Harmonic Analyses](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR_SMSUP.html#) [Enforced Motion Method for Transient and Harmonic Analyses](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/str_EnMoinStAn.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DVAL.html
