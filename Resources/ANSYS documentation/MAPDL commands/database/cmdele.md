---
apdl: "CMDELE"
method: cmdele
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.components.Components.cmdele
generated: 2026-08-22
tags: [mapdl-command]
---

# CMDELE

PyMAPDL: `mapdl.cmdele(name='', **kwargs)`

Deletes a component or assembly definition.

## Parameters

**name**: Name of the component or assembly whose definition is to be removed.

## Notes

Entities contained in the component, or the components within the assembly, are unaffected. Only the grouping relationships are deleted. Assemblies are automatically updated to reflect deletion of their components or subassemblies, but they are not automatically deleted when all their components or subassemblies are deleted.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CMDELE.html
