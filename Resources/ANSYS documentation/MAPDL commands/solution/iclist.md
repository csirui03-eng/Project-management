---
apdl: "ICLIST"
method: iclist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.misc_loads.MiscLoads.iclist
generated: 2026-08-22
tags: [mapdl-command]
---

# ICLIST

PyMAPDL: `mapdl.iclist(node1='', node2='', ninc='', lab='', **kwargs)`

Lists the initial conditions.

## Parameters

**node1**, **node2**, **ninc**: List initial conditions for nodes `NODE1` to `NODE2` (defaults to `NODE1` ) in steps of `NINC` (defaults to 1). If `NODE1` = ALL (default), `NODE2` and `NINC` are ignored and initial conditions for all selected nodes ( [[nsel|NSEL]] ) are listed. If `NODE1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may be substituted for `NODE1` ( `NODE2` and `NINC` are ignored).

**lab**

Label identifying the initial condition to list out:

- `DISP` - Displacements, temperature, etc. (default).
- `VELO` - Velocities.
- `ACC` - Accelerations.

## Notes

Lists the initial conditions specified by the [[ic|IC]] or [[icrotate|ICROTATE]] command. Listing applies to all the selected nodes ( [[nsel|NSEL]] ) and DOF labels. **ICLIST** is not the same as the [[dlist|DLIST]] command. All the initial conditions including the default conditions are listed for the selected nodes.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ICLIST.html
