---
apdl: "CMGRP"
method: cmgrp
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.components.Components.cmgrp
generated: 2026-08-22
tags: [mapdl-command]
---

# CMGRP

PyMAPDL: `mapdl.cmgrp(aname='', cnam1='', cnam2='', cnam3='', cnam4='', cnam5='', cnam6='', cnam7='', cnam8='', **kwargs)`

Groups components and assemblies into an assembly.

## Parameters

**aname**: An alphanumeric name used to identify this assembly. `Aname` may be up to 256 characters, beginning with a letter and containing only letters, numbers, dots (.), and underscores (\_). Overwrites a previously defined `Aname` (and removes it from higher level assemblies, if any).

**cnam1**, **cnam2**, **cnam3**, **cnam4**, **cnam5**, **cnam6**, **cnam7**, **cnam8**: Names of existing components or other assemblies to be included in this assembly.

## Notes

Groups components and other assemblies into an assembly identified by a name. **CMGRP** is used for the initial definition of an assembly. An assembly is used in the same manner as a component. Up to 5 levels of assemblies within assemblies may be used.

An assembly is a convenient grouping of previously defined components and other assemblies. Assemblies may contain components only, other assemblies, or any combination. A component may belong to any number of assemblies. Up to 5 levels of nested assemblies may be defined. Components and assemblies may be added to or deleted from an existing assembly by the [[cmedit|CMEDIT]] command. Once defined, an assembly may be listed, deleted, selected, or unselected using the same commands as for a component. Assemblies are automatically updated to reflect deletions of one or more of their components or lower-level assemblies. Assemblies are not automatically deleted when all their components or subassemblies are deleted.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CMGRP.html
