---
apdl: "KEYOPT"
method: keyopt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.element_type.ElementType.keyopt
generated: 2026-08-22
tags: [mapdl-command]
---

# KEYOPT

PyMAPDL: `mapdl.keyopt(itype='', knum='', value='', **kwargs)`

Sets element key options.

## Parameters

**itype**

Element type number as defined on the [[et|ET]] command.

The following labels are valid input for contact elements:

- `CONT` - Set element key options for all contact element types, `CONTA172`, `CONTA174`, `CONTA175`, and `CONTA177`.
- `TARG` - Set element key options for all target element types, `TARGE169` and `TARGE170`.
- `GCN` - Set element key options for all contact element types used in a [general contact](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctec_toolsgencont.html) definition (that is, all contact elements having a real constant set number = 0).

See [Notes](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_KEYOPT.html#refsect2_ibn_np5_xv) Notes for additional `ITYPE` input specific to general contact.

**knum**: Number of the KEYOPT to be defined (KEYOPT( `KNUM` )).

**value**: Value of this KEYOPT.

## Notes

The **KEYOPT** command is an alternative method for inputting element key option (KEYOPT) values via the [[et|ET]] command. (Issue the [[et|ET]] command first to define `ITYPE` ).

The **KEYOPT** command is required for inputting key options numbered higher than six (that is, \> KEYOPT(6)).

If [[etcontrol|ETCONTROL]],SET is enabled, key options that you specify via the **KEYOPT** command might be overridden for many structural elements. For more information, see [Automatic Selection of Element Technologies and Formulations](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_AutoSelectElems.html#EL2recCriteriaNonLin-3)

Specify `ITYPE` = GCN to set element key options for all contact element types used in a [general contact](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctec_toolsgencont.html) definition. You can selectively set element key options for multiple contact element types in a general contact definition by setting `ITYPE` to a valid label (ALL_EDGE, ALL_FACE, ALL_VERT, ALL_TOP, or ALL_BOT) or by inputting a node component name with or without a component name extension (EDGE, FACE, VERT, TOP, or BOT). For more information, see [Defining Non-Default Contact Settings](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctec_nondefset.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KEYOPT.html
