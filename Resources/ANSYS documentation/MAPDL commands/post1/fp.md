---
apdl: "FP"
method: fp
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1._fatigue.Fatigue.fp
generated: 2026-08-22
tags: [mapdl-command]
---

# FP

PyMAPDL: `mapdl.fp(stitm='', c1='', c2='', c3='', c4='', c5='', c6='', **kwargs)`

Defines the fatigue S vs. N and Sm vs. T tables.

## Parameters

**stitm**

Starting item number for entering properties (defaults to 1). If 1, data input in field `C1` of this command is entered as the first item in the list; if 7, data input in field `C1` of this command is entered as the seventh item in the list; etc. If the item number is negative, `C1` - `C6` are ignored and the item is deleted. If -ALL, the table is erased. Items are as follows (items 41-62 are required only if simplified elastic-plastic code calculations are to be performed):

- `1,2,...20` - N1, N2,... N20
- `21,22,...40` - S1, S2,... S20
- `41,42,...50` - T1, T2,... T10
- `51,52,...60` - Sm1, Sm2,..., Sm10
- `61` - M (first elastic-plastic material parameter)
- `62,` - N (second elastic-plastic material parameter)

**c1**, **c2**, **c3**, **c4**, **c5**, **c6**: Data inserted into six locations starting with `STITM`. If a value is already in one of these locations, it will be redefined. A blank retains the previous value.

## Notes

Defines the fatigue alternating stress (S) vs. cycles (N) table and the design stress-intensity value (Sm) vs. temperature (T) table. Can also be used to modify any previously stored property tables. Log-log interpolation is used in the S vs. N table and linear interpolation is used in the Sm vs. T table. Cycles and temperatures must be input in ascending order; S and Sm values in descending order. Table values must be supplied in pairs, that is, every N entry must have a corresponding S entry, etc. Not all property pairs per curve need be used. If no S vs. N table is defined, the fatigue evaluation will not produce usage factor results.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FP.html
