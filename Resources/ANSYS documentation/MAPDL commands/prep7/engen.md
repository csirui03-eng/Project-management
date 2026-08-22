---
apdl: "ENGEN"
method: engen
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.engen
generated: 2026-08-22
tags: [mapdl-command]
---

# ENGEN

PyMAPDL: `mapdl.engen(iinc='', itime='', ninc='', iel1='', iel2='', ieinc='', minc='', tinc='', rinc='', cinc='', sinc='', dx='', dy='', dz='', **kwargs)`

Generates elements from an existing pattern.

## Parameters

**iinc**: Increment to be added to element numbers in pattern.

**itime**, **ninc**: Do this generation operation a total of `ITIME` s, incrementing all nodes in the given pattern by `NINC` each time after the first. `ITIME` must be \> 1 if generation is to occur. `NINC` may be positive, zero, or negative.

**iel1**, **iel2**, **ieinc**: Generate elements from the pattern that begins with `IEL1` to `IEL2` (defaults to `IEL1` ) in steps of `IEINC` (defaults to 1). If `IEL1` is negative, `IEL2` and `IEINC` are ignored and use the last \| `IEL1` \| elements (in sequence backward from the maximum element number) as the pattern to be repeated. If `IEL1` = ALL, `IEL2` and `IEINC` are ignored and all selected elements ( [[esel|ESEL]] ) are used as the pattern to be repeated. If `IEL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `IEL1` ( `IEL2` and `IEINC` are ignored).

**minc**: Increment material number of all elements in the given pattern by `MINC` each time after the first.

**tinc**: Increment type number by `TINC`.

**rinc**: Increment real constant table number by `RINC`.

**cinc**: Increment element coordinate system number by `CINC`.

**sinc**: Increment section ID number by `SINC`.

**dx**, **dy**, **dz**: Define nodes that do not already exist but are needed by generated elements ( [[ngen|NGEN]], `ITIME,INC,NODE1,,,DX,DY,DZ` ). Zero is a valid value. If blank, `DX`, `DY`, and `DZ` are ignored.

## Notes

Same as the [[egen|EGEN]] command except it allows element numbers to be explicitly incremented ( `IINC` ) from the generated set. Any existing elements already having these numbers will be redefined.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ENGEN.html
