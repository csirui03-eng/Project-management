---
apdl: "ET"
method: et
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.element_type.ElementType.et
generated: 2026-08-22
tags: [mapdl-command]
---

# ET

PyMAPDL: `mapdl.et(itype='', ename='', kop1='', kop2='', kop3='', kop4='', kop5='', kop6='', inopr='', **kwargs)`

Defines a local element type from the element library.

## Parameters

**itype**: An arbitrary local element-type number. Defaults to 1 + current maximum.

**ename**

A full element name (such as

``` apdl
pipe288
```

) or element number only (such as

``` apdl
288
```

), as given in the [element library](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_USER300.html).

**kop1**, **kop2**, **kop3**, **kop4**, **kop5**, **kop6**: KEYOPT values (1 through 6) as desired for the specified element.

**inopr**: Specify 1 to suppress all element-solution printout for this element type.

## Notes

The ET command selects an element type from the element library and establishes it as a local element type for the current model. Information derived from the element type is used for subsequent commands, so the ET command(s) should be issued early. (The Element Reference describes the available elements.)

A special option, `ename=0`, permits the specified element type to be ignored during solution without actually removing the element from the model. Ename may be set to zero only after the element type has been previously defined with a nonzero Ename. The preferred method of ignoring elements is to use the select commands (such as ESEL).

KOPn are element option keys. These keys (referred to as KEYOPT(n)) are used to turn on certain element options for this element. These options are listed under "KEYOPT" in the input table for each element type in the Element Reference. KEYOPT values include stiffness formulation options, printout controls, and various other element options. If KEYOPT(7) or greater is needed, input their values with the KEYOPT command.

The ET command only defines an element type local to your model (from the types in the element library). The TYPE or similar \[KATT, LATT, AATT, or VATT\] command must be used to point to the desired local element type before meshing.

To activate the ANSYS program's LS-DYNA explicit dynamic analysis capability, use the ET command to choose an element that works only with LS-DYNA (such as SHELL163).

## Examples

Define an element type. Allow MAPDL to pick your the element type.

``` python
>>> etype_num = mapdl.et('', 'SURF154')
>>> etype_num
1
```

Define an element type while specifying the element type number.

``` python
>>> etype_num = mapdl.et(2, 'SOLID186')
>>> etype_num
2
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ET.html
