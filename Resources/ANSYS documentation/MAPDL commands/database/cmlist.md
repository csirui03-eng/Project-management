---
apdl: "CMLIST"
method: cmlist
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.components.Components.cmlist
generated: 2026-08-22
tags: [mapdl-command]
---

# CMLIST

PyMAPDL: `mapdl.cmlist(name='', key='', entity='', **kwargs)`

Lists the contents of a component or assembly.

## Parameters

**name**: Name of the component or assembly to be listed (if blank, list all selected components and assemblies). If `Name` is specified, then `Entity` is ignored.

**key**

Expansion key:

- `0` - Do not list individual entities in the component.
- `1 or EXPA` - List individual entities in the component.

**entity**

If `Name` is blank, then the following entity types can be specified:

- `VOLU` - List the volume components only.
- `AREA` - List the area components only.
- `LINE` - List the line components only.
- `KP` - List the keypoint components only
- `ELEM` - List the element components only.
- `NODE` - List the node components only.

## Notes

This command is valid in any processor. For components, it lists the type of geometric entity. For assemblies, it lists the components and/or assemblies that make up the assembly.

Examples of possible usage:

- **CMLIST** - List all selected components.
- **CMLIST**, EXPA - List all selected components and for each component list the underlying entity ID's.
- **CMLIST**, `Name` - List the specified component.
- **CMLIST**, `Name`,EXPA - List specified component along with all underlying entity ID's.
- **CMLIST**, EXPA, `Entity` - List all selected components of specified entity type. For each component also list the underlying entity ID's.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CMLIST.html
