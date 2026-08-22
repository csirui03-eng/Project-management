---
apdl: "LCABS"
method: lcabs
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.load_case_calculations.LoadCaseCalculations.lcabs
generated: 2026-08-22
tags: [mapdl-command]
---

# LCABS

PyMAPDL: `mapdl.lcabs(lcno='', kabs='', **kwargs)`

Specifies absolute values for load case operations.

## Parameters

**lcno**: Load case pointer number. If ALL, apply to all selected load cases ( [[lcsel|LCSEL]] ).

**kabs**

Absolute value key:

- `0` - Use algebraic values of load case `LCNO` in operations.
- `1` - Use absolute values of load case `LCNO` in operations.

## Notes

Causes absolute values to be used in the load case operations ( [[lcase|LCASE]] or [[lcoper|LCOPER]] ). Absolute values are taken prior to assigning a load case factor ( [[lcfact|LCFACT]] ) and are applied only to defined load cases ( [[lcdef|LCDEF]] ).

When **LCABS** operates on nodal-averaged results, it may yield different numerical values compared to the same data stored as element results. For more information, see [Nodal-Averaged Results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LCABS.html
