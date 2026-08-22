---
apdl: "CECYC"
method: cecyc
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.constraint_equations_.ConstraintEquations.cecyc
generated: 2026-08-22
tags: [mapdl-command]
---

# CECYC

PyMAPDL: `mapdl.cecyc(lowname='', highname='', nsector='', hindex='', tolerance='', kmove='', kpairs='', **kwargs)`

Generates the constraint equations for a cyclic symmetry analysis

## Parameters

**lowname**: Name of a component for the nodes on the low angle edge of the sector. Enclosed in single quotes.

**highname**: Name of a component for the nodes on the high angle edge of the sector. Enclosed in single quotes.

**nsector**: Number of sectors in the complete 360 degrees.

**hindex**: Harmonic index to be represented by this set of constraint equations. If `Hindex` is -1, generate constraint equations for static cyclic symmetry. If `HIndex` is -2, generate constraint equations for static cyclic asymmetry.

**tolerance**: A positive tolerance is an absolute tolerance (length units), and a negative tolerance is a tolerance relative to the local element size.

**kmove**

- `0` - Nodes are not moved.
- `1` - HIGHNAME component nodes are moved to match LOWNAME component nodes exactly.

**kpairs**

- `0` - Do not print paired nodes
- `1` - Print table of paired nodes

## Notes

The analysis can be either modal cyclic symmetry or static cyclic symmetry.

The pair of nodes for which constraint equations are written are rotated into [[csys|CSYS]],1.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CECYC.html
