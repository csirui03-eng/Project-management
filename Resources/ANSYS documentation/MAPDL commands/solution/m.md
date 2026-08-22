---
apdl: "M"
method: m
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.master_dof.MasterDof.m
generated: 2026-08-22
tags: [mapdl-command]
---

# M

PyMAPDL: `mapdl.m(node='', lab1='', nend='', ninc='', lab2='', lab3='', lab4='', lab5='', lab6='', support='', **kwargs)`

Defines master degrees of freedom (MDOFs) for superelement generation analyses.

## Parameters

**node**: Node number at which an MDOF is defined. If ALL, define MDOFs at all selected nodes ( [[nsel|NSEL]] ). If `NODE` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE`.

**lab1**: Additional MDOF labels. The nodes defined are associated with each label specified.

**nend**, **ninc**: Define all nodes from `NODE` to `NEND` (defaults to `NODE` ) in steps of `NINC` (defaults to 1) as MDOFs in the specified direction.

**lab2**, **lab3**, **lab4**, **lab5**, **lab6**: Additional MDOF labels. The nodes defined are associated with each label specified.

**support**

Pseudo-constraints key for the free-interface ( [[cmsopt|CMSOPT]],FREE) and residual-flexible free- interface ( [[cmsopt|CMSOPT]], RFFB) CMS method analyses:

OFF - Defined MDOFs remain free during the mode-extraction analysis (default).

ON - Defined MDOFs are constrained during the mode-extraction analysis.

## Notes

Defines master degrees of freedom (MDOFs) for superelement generation. If defined for other analyses, MDOFs are ignored. If used in the SOLUTION processor, this command is valid only within the first load step.

Reissue **M** for additional MDOFs. The number of master nodes allowed is limited only by the maximum system memory available.

The substructure ( [[antype|ANTYPE]],SUBSTR) analysis uses the matrix condensation technique to reduce the structure matrices to those characterized by a set of MDOFs.

MDOFs are identified by a list of nodes and their nodal directions. The actual degree-of-freedom directions available for a given node depends upon the degrees of freedom associated with element types ( [[et|ET]] ) at that node.

There must be some mass (or stress stiffening in the case of a buckling analysis) associated with each MDOF (except for the VOLT label). The mass may be due either to the distributed mass of the element or due to discrete lumped masses at the node.

If an MDOF is specified at a constrained point, it is ignored.

If an MDOF is specified at a coupled node, it should be specified at the prime node of the coupled set.

For cyclic symmetry superelements, if MDOFs are defined at both low- and high-edge nodes, the cyclic constraint equations between those nodes are ignored.

Substructure analysis connection points must be defined as MDOFs.

The `SUPPORT` argument is ignored for the fixed-interface CMS method analysis ( [[cmsopt|CMSOPT]],FIX).

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_M.html
