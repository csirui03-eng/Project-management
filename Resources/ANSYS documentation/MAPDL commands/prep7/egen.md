---
apdl: "EGEN"
method: egen
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.egen
generated: 2026-08-22
tags: [mapdl-command]
---

# EGEN

PyMAPDL: `mapdl.egen(itime='', ninc='', iel1='', iel2='', ieinc='', minc='', tinc='', rinc='', cinc='', sinc='', dx='', dy='', dz='', **kwargs)`

Generates elements from an existing pattern.

## Parameters

**itime**, **ninc**: Do this generation operation a total of `ITIME` s, incrementing all nodes in the given pattern by `NINC` each time after the first. `ITIME` must be \>1 if generation is to occur. `NINC` may be positive, zero, or negative. If `DX`, `DY`, and/or `DZ` is specified, `NINC` should be set so any existing nodes (as on [[ngen|NGEN]] ) are not overwritten.

**iel1**, **iel2**, **ieinc**: Generate elements from selected pattern beginning with `IEL1` to `IEL2` (defaults to `IEL1` ) in steps of `IEINC` (defaults to 1). If `IEL1` is negative, `IEL2` and `IEINC` are ignored and the last \| `IEL1` \| elements (in sequence backward from the maximum element number) are used as the pattern to be repeated. If `IEL1` = ALL, `IEL2` and `IEINC` are ignored and use all selected elements ( [[esel|ESEL]] ) as pattern to be repeated. If `P1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `IEL1` ( `IEL2` and `INC` are ignored).

**minc**: Increment material number of all elements in the given pattern by `MINC` each time after the first.

**tinc**: Increment element type number by `TINC`. The element types with incremented numbers must be defined before issuing the **EGEN** command.

**rinc**: Increment real constant table number by `RINC`.

**cinc**: Increment element coordinate system number by `CINC`.

**sinc**: Increment section ID number by `SINC`.

**dx**, **dy**, **dz**: Define nodes that do not already exist but are needed by generated elements (as though the [[ngen|NGEN]], `ITIME,INC,NODE1,,,DX,DY,DZ` were issued before **EGEN** ). Zero is a valid value. If blank, `DX`, `DY`, and `DZ` are ignored.

## Notes

A pattern may consist of any number of previously defined elements. The MAT, TYPE, REAL, ESYS, and SECNUM numbers of the new elements are based upon the elements in the pattern and not upon the current specification settings.

You can use the **EGEN** command to generate interface elements ( `INTER192`, `INTER193`, `INTER194`, and `INTER195` ) directly. However, because interface elements require that the element connectivity be started from the bottom surface, you must make sure that you use the correct element node connectivity. See the element descriptions for `INTER192`, `INTER193`, `INTER194`, and `INTER195` for the correct element node definition.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EGEN.html
