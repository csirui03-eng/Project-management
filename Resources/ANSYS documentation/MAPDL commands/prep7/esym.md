---
apdl: "ESYM"
method: esym
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.esym
generated: 2026-08-22
tags: [mapdl-command]
---

# ESYM

PyMAPDL: `mapdl.esym(ninc='', iel1='', iel2='', ieinc='', **kwargs)`

Generates elements from a pattern by a symmetry reflection.

## Parameters

**ninc**: Increment nodes in the given pattern by `NINC`.

**iel1**, **iel2**, **ieinc**: Reflect elements from pattern beginning with `IEL1` to `IEL2` (defaults to `IEL1` ) in steps of `IEINC` (defaults to 1). If `IEL1` = ALL, `IEL2` and `IEINC` are ignored and pattern is all selected elements ( [[esel|ESEL]] ). If `IEL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `IEL1` ( `IEL2` and `IEINC` are ignored).

## Notes

Generates additional elements from a given pattern (similar to [[egen|EGEN]] ) except with a symmetry reflection. The operation generates a new element by incrementing the nodes on the original element, and reversing and shifting the node connectivity pattern. For example, for a 4-node 2D element, the nodes in positions I, J, K, and L of the original element are placed in positions J, I, L, and K of the reflected element.

Similar permutations occur for all other element types. For line elements, the nodes in positions I and J of the original element are placed in positions J and I of the reflected element.

It is recommended that symmetry elements be displayed and graphically reviewed.

If the nodes are also reflected (as with the [[nsym|NSYM]] command), this pattern is such that the orientation of the symmetry element remains similar to the original element (that is, clockwise elements are generated from clockwise elements).

For a non-reflected node pattern, the reversed orientation has the effect of reversing the outward normal direction (clockwise elements are generated from counterclockwise elements).

Because nodes may be defined anywhere in the model independently of this command, any orientation of the symmetry elements is possible. See also the [[ensym|ENSYM]] command for modifying existing elements.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ESYM.html
