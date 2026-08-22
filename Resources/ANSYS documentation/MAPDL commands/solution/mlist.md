---
apdl: "MLIST"
method: mlist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.master_dof.MasterDof.mlist
generated: 2026-08-22
tags: [mapdl-command]
---

# MLIST

PyMAPDL: `mapdl.mlist(node1='', node2='', ninc='', **kwargs)`

Lists the MDOF of freedom.

## Parameters

**node1**, **node2**, **ninc**: List master degrees of freedom from `NODE1` to `NODE2` (defaults to `NODE1` ) in steps of `NINC` (defaults to 1). If `NODE1` = ALL (default), `NODE2` and `NINC` are ignored and masters for all selected nodes ( [[nsel|NSEL]] ) are listed. If `NODE1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE1` ( `NODE2` and `NINC` are ignored).

## Notes

Lists the master degrees of freedom.

For the free-interface CMS method analysis ( [[cmsopt|CMSOPT]],FREE),Â any pseudo-constraints applied on master degrees of freedom with `SUPPORT` = ON in the [[m|M]] command will be listedÂ when **MLIST** is issued after [[cmsopt|CMSOPT]] (see example printout below).

``` apdl
NODE  LABEL     SUPPORT
 8529  UX
 8529  UY
 8529  UZ
 8545  UX         ON
 8545  UY         ON
 8545  UZ         ON
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MLIST.html
