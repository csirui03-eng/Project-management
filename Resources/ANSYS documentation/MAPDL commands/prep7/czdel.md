---
apdl: "CZDEL"
method: czdel
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.czdel
generated: 2026-08-22
tags: [mapdl-command]
---

# CZDEL

PyMAPDL: `mapdl.czdel(grp1='', grp2='', grp3='', **kwargs)`

Edits or clears cohesive zone sections.

## Parameters

**grp1**: Initial group of cohesive zone elements to be deleted.

**grp2**: Final group of cohesive zone elements to be deleted.

**grp3**: Increment for selected groups.

## Notes

The **CZDEL** command edits or deletes the interface elements and nodes, along with the associated changes made to the underlying plane or solid elements created during a previous [[czmesh|CZMESH]] operation.

Each [[czmesh|CZMESH]] operation will create groups of elements and nodes with component names in the format CZME_EL01 (elements) and CZME_ND01 (nodes). The final number of this format will be the number used for `grp1` and `grp2`. If `grp1` = ALL, all nodes and elements created by the [[czmesh|CZMESH]] command will be deleted. After using **CZDEL**, all the user-defined components will be unselected.

The **CZDEL** command is valid for structural analyses only.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CZDEL.html
