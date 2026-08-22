---
apdl: "ENSYM"
method: ensym
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.ensym
generated: 2026-08-22
tags: [mapdl-command]
---

# ENSYM

PyMAPDL: `mapdl.ensym(iinc='', ninc='', iel1='', iel2='', ieinc='', **kwargs)`

Generates elements by symmetry reflection.

## Parameters

**iinc**: Increment to be added to element numbers in existing set.

**ninc**: Increment nodes in the given pattern by `NINC`.

**iel1**, **iel2**, **ieinc**: Reflect elements from pattern beginning with `IEL1` to `IEL2` (defaults to `IEL1` ) in steps of `IEINC` (defaults to 1). If `IEL1` = ALL, `IEL2` and `IEINC` are ignored and pattern is all selected elements ( [[esel|ESEL]] ). If `IEL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `IEL1` ( `IEL2` and `IEINC` are ignored).

## Notes

The **ENSYM** command is similar to the [[esym|ESYM]] command except that it enables explicitly assigned element numbers to the generated set (in terms of an increment `IINC` ). Any existing elements already having these numbers are redefined.

The operation generates a new element by incrementing the nodes on the original element, and reversing and shifting the node connectivity pattern. For example, for a 4-node 2D element, the nodes in positions I, J, K and L of the original element are placed in positions J, I, L and K of the reflected element.

Similar permutations occur for all other element types. For line elements, the nodes in positions I and J of the original element are placed in positions J and I of the reflected element.

See the [[esym|ESYM]] command for additional information about symmetry elements.

This command also provides a convenient way to reverse shell element normals. If the `IINC` and `NINC` argument fields are left blank, the effect of the reflection is to reverse the direction of the outward normal of the specified elements. You cannot use this command to change the normal direction of any element that has a body or surface load. It is best to apply all loading only after ensuring that the element normal directions are acceptable.

Real constants (such as nonuniform shell thickness and tapered beam constants) may be invalidated by an element reversal.

For more information about controlling element normals, see [Revising Your Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD8_6.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ENSYM.html
