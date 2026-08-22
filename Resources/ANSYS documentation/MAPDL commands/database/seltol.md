---
apdl: "SELTOL"
method: seltol
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.selecting.Selecting.seltol
generated: 2026-08-22
tags: [mapdl-command]
---

# SELTOL

PyMAPDL: `mapdl.seltol(toler='', **kwargs)`

Sets the tolerance for subsequent select operations.

## Parameters

**toler**: Tolerance value. If blank, restores the default tolerance logic.

## Notes

For selects based on non-integer numbers (e.g. coordinates, results, etc.), items within the range VMIN - `Toler` and VMAX + `Toler` are selected, where VMIN and VMAX are the range values input on the xSEL commands ( [ASEL](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_ASEL.html#ASEL.menupath) [[asel|ASEL]], [ESEL](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_ESEL.html#ESEL.menupath) [[esel|ESEL]], [KSEL](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_KSEL.html#KSEL.menupath) [[ksel|KSEL]], [LSEL](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_LSEL.html#LSEL.menupath) [[lsel|LSEL]], [NSEL](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_NSEL.html#NSEL.menupath) [[nsel|NSEL]], and [VSEL](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_VSEL.html#VSEL.menupath) [[vsel|VSEL]] ).

The default tolerance logic is based on the relative values of VMIN and VMAX as follows:

- If VMIN = VMAX, `Toler` = 0.005 x VMIN.
- If VMIN = VMAX = 0.0, `Toler` = 1.0E-6.
- If VMAX ≠ VMIN, `Toler` = 1.0E-8 x (VMAX-VMIN).

This command is typically used when VMAX-VMIN is very large so that the computed default tolerance is therefore large and the xSEL commands selects more than what is desired.

`Toler` remains active until respecified by a subsequent **SELTOL** command. A **SELTOL** \< blank \> resets back to the default `Toler` logic.

## Examples

Set selection tolarance to 1E-5

``` python
>>> seltol(1E-5)
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SELTOL.html
