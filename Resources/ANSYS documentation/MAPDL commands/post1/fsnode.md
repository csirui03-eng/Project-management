---
apdl: "FSNODE"
method: fsnode
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1._fatigue.Fatigue.fsnode
generated: 2026-08-22
tags: [mapdl-command]
---

# FSNODE

PyMAPDL: `mapdl.fsnode(node='', nev='', nlod='', **kwargs)`

Calculates and stores the stress components at a node for fatigue.

## Parameters

**node**: Node number for which stress components are stored.

**nev**: Event number to be associated with these stresses (defaults to 1).

**nlod**: Loading number to be associated with these stresses (defaults to 1).

## Notes

Calculates and stores the total stress components at a specified node for fatigue. Stresses are stored according to the event number and loading number specified. The location is associated with that previously defined for this node (FL) or else it is automatically defined. Stresses are stored as six total components (SX through SYZ). Temperature and current time are also stored along with the total stress components. Calculations are made from the stresses currently in the database (last [[set|SET]] or [[lcase|LCASE]] command). Stresses stored are in global Cartesian coordinates, regardless of the active results coordinate system ( [[rsys|RSYS]] ).

You can issue the FSLIST command to list stresses, and the FS command to modify stored stresses.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FSNODE.html
