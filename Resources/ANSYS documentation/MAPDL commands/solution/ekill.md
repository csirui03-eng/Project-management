---
apdl: "EKILL"
method: ekill
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.birth_and_death.BirthAndDeath.ekill
generated: 2026-08-22
tags: [mapdl-command]
---

# EKILL

PyMAPDL: `mapdl.ekill(elem='', **kwargs)`

Deactivates an element (for the birth and death capability).

## Parameters

**elem**: Element to be deactivated. If ALL, deactivate all selected elements ( [[esel|ESEL]] ). If `ELEM` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `ELEM`. To specify a table, enclose the table name in percent signs (%), e.g. **EKILL**,`tabname`.

## Notes

Deactivates the specified element when the birth and death capability is being used. A deactivated element remains in the model but contributes a near-zero stiffness (or conductivity, etc.) value ( [[estif|ESTIF]] ) to the overall matrix. Any solution-dependent state variables (such as stress, plastic strain, creep strain, etc.) are set to zero. Deactivated elements contribute nothing to the overall mass (or capacitance, etc.) matrix, and do not generate a load vector (pressures, convections, gravity, etc.).

The usage of tabular input is described in in the [Advanced Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advoceanloading.html).

The element can be reactivated with the [[ealive|EALIVE]] command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EKILL.html
