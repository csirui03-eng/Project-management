---
apdl: "LCFACT"
method: lcfact
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.load_case_calculations.LoadCaseCalculations.lcfact
generated: 2026-08-22
tags: [mapdl-command]
---

# LCFACT

PyMAPDL: `mapdl.lcfact(lcno='', fact='', **kwargs)`

Defines scale factors for load case operations.

## Parameters

**lcno**: Load case pointer number. If ALL, apply to all selected load cases ( [[lcsel|LCSEL]] ).

**fact**: Scale factor applied to load case `LCNO`. Blank defaults to 1.0.

## Notes

Defines scale factors to be used in the load case operations ( [[lcase|LCASE]] or [[lcoper|LCOPER]] ). Scale factors are applied after an absolute value operation ( [[lcabs|LCABS]] ) and are applied only to defined load cases ( [[lcdef|LCDEF]] ).

For details on using load case combination, see [Creating and Combining Load Cases](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_4.html#bassummtlm51499325)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LCFACT.html
