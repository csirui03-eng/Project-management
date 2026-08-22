---
apdl: "CMSEL"
method: cmsel
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.components.Components.cmsel
generated: 2026-08-22
tags: [mapdl-command]
---

# CMSEL

PyMAPDL: `mapdl.cmsel(type_='', name='', entity='', **kwargs)`

Selects a subset of components and assemblies.

## Parameters

**type_**

Label identifying the type of select:

- `S` - Select a new set (default).
- `R` - Reselect a set from the current set.
- `A` - Additionally select a set and extend the current set.
- `U` - Unselect a set from the current set.
- `ALL` - Also select all components.
- `NONE` - Unselect all components.

**name**

Name of component or assembly whose items are to be selected (valid only if `Type` = S, R, A, or U).

Graphical picking is enabled if `Type` is blank and `Name` = PICK (or simply "P").

**entity**

If `Name` is blank, then the following entity types can be specified:

- `VOLU` - Select the volume components only.
- `AREA` - Select the area components only.
- `LINE` - Select the line components only.
- `KP` - Select the keypoint components only.
- `ELEM` - Select the element components only.
- `NODE` - Select the node components only.

## Notes

Selecting by component is a convenient adjunct to individual item selection (for example, [[vsel|VSEL]], [[esel|ESEL]], etc.). **CMSEL**, ALL allows you to select components **in addition** to other items you have already selected.

If `Type` = R for an assembly selection ( **CMSEL**,R,\< assembly-name \>), the reselect operation is performed on each component in the assembly in the order in which the components make up the assembly. Thus, if one reselect operation results in an empty set, subsequent operations will also result in empty sets. For example, if the first reselect operation tries to reselect node 1 from the selected set of nodes 3, 4, and 5, the operation results in an empty set (that is, no nodes are selected). Since the current set is now an empty set, if the second reselect operation tries to reselect any nodes, the second operation also results in an empty set, and so on. This is equivalent to repeating the command **CMSEL**,R,\< component-name \> once for each component making up the assembly.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CMSEL.html
