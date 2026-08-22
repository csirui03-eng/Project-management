---
apdl: "EALIVE"
method: ealive
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.birth_and_death.BirthAndDeath.ealive
generated: 2026-08-22
tags: [mapdl-command]
---

# EALIVE

PyMAPDL: `mapdl.ealive(elem='', **kwargs)`

Reactivates an element (for the birth and death capability).

## Parameters

**elem**: Element to be reactivated. If ALL, reactivate all selected elements ( [[esel|ESEL]] ). If `ELEM` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `ELEM`. To specify a table, enclose the table name in percent signs (%), e.g. **EALIVE**,`tabname`.

## Notes

Reactivates the specified element when the birth and death capability is being used. An element can be reactivated only after it has been deactivated ( [[ekill|EKILL]] ).

Reactivated elements have a zero strain (or thermal heat storage, etc.) state.

The usage of tabular input is described in in the [Advanced Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advoceanloading.html).

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EALIVE.html
