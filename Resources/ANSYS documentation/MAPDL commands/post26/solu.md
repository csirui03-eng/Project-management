---
apdl: "SOLU"
method: solu
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.set_up.SetUp.solu
generated: 2026-08-22
tags: [mapdl-command]
---

# SOLU

PyMAPDL: `mapdl.solu(nvar='', item='', comp='', name='', **kwargs)`

Specifies solution summary data per substep to be stored.

## Parameters

**nvar**: Arbitrary reference number assigned to this variable (2 to `NV` ( [[numvar|NUMVAR]] )).

**item**: Label identifying the item. Valid item labels are shown in the table below. Some items may also require a component label.

**comp**: Component of the item (if required). Valid component labels are shown in the table below. None are currently required.

**name**: Thirty-two character name identifying the item on printouts and displays. Defaults to an eight character label formed by concatenating the first four characters of the `Item` and `Comp` labels.

## Notes

See also the [[priter|PRITER]] command of POST1 to display some of these items directly. Valid for a static or full transient analysis. All other analyses have zeros for the data. Valid item and component labels for solution summary values are:

(table not available in the PyMAPDL source, see the Ansys help page)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SOLU.html
