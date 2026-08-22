---
apdl: "ALLSEL"
method: allsel
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.selecting.Selecting.allsel
generated: 2026-08-22
tags: [mapdl-command]
---

# ALLSEL

PyMAPDL: `mapdl.allsel(labt='', entity='', **kwargs)`

Selects all entities with a single command.

## Parameters

**labt**

Type of selection to be made:

- `ALL` - Selects all items of the specified entity type and all items of lower entity types (default).
- `BELOW` - Selects all items directly associated with and below the selected items of the specified entity type.

**entity**

Entity type on which selection is based:

- `ALL` - All entity types (default).
- `VOLU` - Volumes.
- `AREA` - Areas.
- `LINE` - Lines.
- `KP` - Keypoints.
- `ELEM` - Elements.
- `NODE` - Nodes.

## Notes

**ALLSEL** is a convenience command that allows the user to select all items of a specified entity type or to select items associated with the selected items of a higher entity.

An entity hierarchy is used to decide what entities will be available in the selection process. This hierarchy from top to bottom is as follows: volumes, areas, lines, keypoints, elements, and nodes. The hierarchy may also be divided into two branches: the solid model and the finite element model. The label ALL selects items based on one branch only, while BELOW uses the entire entity hierarchy. For example, **ALLSEL**,ALL,VOLU selects all volumes, areas, lines, and keypoints in the data base. **ALLSEL**,BELOW,AREA selects all lines belonging to the selected areas; all keypoints belonging to those lines; all elements belonging to those areas, lines, and keypoints; and all nodes belonging to those elements.

The \$ character should not be used after the **ALLSEL** command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ALLSEL.html
