---
apdl: "R"
method: r
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.real_constants.RealConstants.r
generated: 2026-08-22
tags: [mapdl-command]
---

# R

PyMAPDL: `mapdl.r(nset='', r1='', r2='', r3='', r4='', r5='', r6='', **kwargs)`

Defines the element real constants.

## Parameters

**nset**: Real constant set identification number (arbitrary). If same as a previous set number, set is redefined. Set number relates to that defined with the element ( [[real|REAL]] ). Note that the GUI automatically assigns this value.

**r1**, **r2**, **r3**, **r4**, **r5**, **r6**: Real constant values (interpreted as area, moment of inertia, thickness, etc., as required for the particular element type using this set), or table names for tabular input of boundary conditions. Use [[rmore|RMORE]] command if more than six real constants per set are to be input.

## Notes

Defines the element real constants. The real constants required for an element are shown in the Input Summary of each element description in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html). Constants must be input in the same order as shown in that table. If more than the required number of element real constants are specified in a set, only those required are used. If fewer than the required number are specified, zero values are assumed for the unspecified constants.

If using table inputs ( `COMBIN14`, `FLUID116`, `SURF151`, `SURF152`, `CONTA172`, `CONTA174`, `CONTA175`, `CONTA177`, and `COMBI214` only), enclose the table name in % signs (for example, `%tabname%` ).

When copying real constants to new sets, Ansys, Inc. recommends that you use the command input. If you do use the GUI, restrict the real constant copy to only the first six real constants (real constants seven and greater will be incorrect for both the master and copy set).

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_R.html
