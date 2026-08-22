---
apdl: "EMODIF"
method: emodif
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.emodif
generated: 2026-08-22
tags: [mapdl-command]
---

# EMODIF

PyMAPDL: `mapdl.emodif(iel='', stloc='', i1='', i2='', i3='', i4='', i5='', i6='', i7='', i8='', **kwargs)`

Modifies a previously defined element.

## Parameters

**iel**

Replace the previous node numbers assigned to this element with these corresponding values. A (blank) retains the previous value (except in the `I1` field, which resets the `STLOC` node number to zero).

For attributes ( `STLOC` = MAT, TYPE, etc.), replace the existing value with the `I1` value (or the default if `I1` is zero or blank).

For attributes MAT and REAL, inputting the label GCN for `I1` replaces the existing attribute value with zero for the specified elements. This is a special case used only for converting contact elements ( `TARGE169` through `CONTA177` ) from a pair-based definition to a [general contact definition](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctec_toolsgencont.html).

**stloc**

Starting location ( `n` ) of first node to be modified or the attribute label.

If `n`, modify element node positions `n`, `n` +1, etc. ( `n` = 1 to 20). For example, if `STLOC` = 1, `I1` refers to the first node, `I2`, the second, etc. If `STLOC` = 9, `I1` refers to the ninth node, `I2`, the tenth, etc. Attributes are also modified to the currently specified values.

Use - `n` to modify only nodes and not attributes.

If zero, modify only the attributes to the currently specified values.

If MAT, TYPE, REAL, ESYS, SECNUM, or EGID, modify only that attribute to the `I1` value.

**i1**, **i2**, **i3**, **i4**, **i5**, **i6**, **i7**, **i8**

Replace the previous node numbers assigned to this element with these corresponding values. A (blank) retains the previous value (except in the `I1` field, which resets the `STLOC` node number to zero).

For attributes ( `STLOC` = MAT, TYPE, etc.), replace the existing value with the `I1` value (or the default if `I1` is zero or blank).

For attributes MAT and REAL, inputting the label GCN for `I1` replaces the existing attribute value with zero for the specified elements. This is a special case used only for converting contact elements ( `TARGE169` through `CONTA177` ) from a pair-based definition to a [general contact definition](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctec_toolsgencont.html).

## Notes

The nodes and/or attributes (MAT, TYPE, REAL, ESYS, SECNUM, or EGID values) of an existing element can be changed with this command.

The EGID attribute is valid only for `MESH200` elements when they are used to generate [reinforcing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_compreinfdirectemb.html) elements (REINF `nnn` ) via the [mesh-independent method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strreinfworkflow.html#) for defining reinforcing.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EMODIF.html
