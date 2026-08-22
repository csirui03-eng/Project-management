---
apdl: "CM"
method: cm
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.components.Components.cm
generated: 2026-08-22
tags: [mapdl-command]
---

# CM

PyMAPDL: `mapdl.cm(cname='', entity='', kopt='', **kwargs)`

Groups geometry items into a component.

## Parameters

**cname**: An alphanumeric name used to identify this component. `Cname` may be up to 256 characters, beginning with a letter and containing only letters, numbers, dots (.) and underscores (\_). Component names beginning with an underscore (for example, LOOP) are reserved for use by Mechanical APDL and should be avoided. Components named "ALL," "STAT," and "DEFA" are not permitted. Overwrites a previously defined name.

**entity**

Label identifying the type of geometry items to be grouped:

- `VOLU` - Volumes.
- `AREA` - Areas.
- `LINE` - Lines.
- `KP` - Keypoints.
- `ELEM` - Elements.
- `NODE` - Nodes.

**kopt**

Controls how element component contents are updated during [nonlinear mesh adaptivity analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnaexample.html) :

- 0 - Component is not updated during remeshing and therefore contains only initial mesh elements (default).
- 1 - Component is updated during remeshing to contain the updated elements.

This argument is valid only for nonlinear mesh adaptivity analysis with `Entity` = ELEM, and for solid element components only.

## Notes

Components may be further grouped into assemblies ( [[cmgrp|CMGRP]] ). The selected items of the specified entity type will be stored as the component. Use of this component in the select command ( [[cmsel|CMSEL]] ) causes all these items to be selected at once, for convenience.

A component is a grouping of some geometric entity that can then be conveniently selected or unselected. A component may be redefined by reusing a previous component name. The following entity types may belong to a component: nodes, elements, keypoints, lines, areas, and volumes. A component may contain only 1 entity type, but an individual item of any entity may belong to any number of components. Once defined, the items contained in a component may then be easily selected or unselected ( [[cmsel|CMSEL]] ). Components may be listed ( [[cmlist|CMLIST]] ), modified ( [[cmmod|CMMOD]] ) and deleted ( [[cmdele|CMDELE]] ). Components may also be further grouped into assemblies ( [[cmgrp|CMGRP]] ). Other entities associated with the entities in a component (for example, the lines and keypoints associated with areas) may be selected by the [[allsel|ALLSEL]] command.

An item will be deleted from a component if it has been deleted by another operation (see the [[kmodif|KMODIF]] command for an example). Components are automatically updated to reflect deletions of one or more of their items. Components are automatically deleted and a warning message is issued if all their items are deleted. Assemblies are also automatically updated to reflect deletions of one or more of their components or subassemblies, but are not deleted if all their components and subassemblies are deleted.

For [nonlinear mesh adaptivity analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnaexample.html), an extra option is available to update the element component contents automatically during the analysis, applicable in cases where the remeshing region overlaps the defined solid element component region. By enabling the option, the component element boundary is maintained, and the validity of the defined component is guaranteed during the entire analysis run; therefore, the component can be used during both solution and postprocessing.

Components are often used as input to other commands. Some commands restrict the component name to 32 characters. For those commands, this limitation is documented within the command description.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CM.html
