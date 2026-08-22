---
apdl: "ETCHG"
method: etchg
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.element_type.ElementType.etchg
generated: 2026-08-22
tags: [mapdl-command]
---

# ETCHG

PyMAPDL: `mapdl.etchg(cnv='', **kwargs)`

Changes element types to their corresponding types.

## Parameters

**cnv**

Converts the element types to the corresponding type. Valid labels are:

- `TTS` - Thermal to Structural
- `STT` - Structural to Thermal
- `MTT` - Magnetic to Thermal
- `FTS` - Fluid to Structural
- `ETS` - Electrostatic to Structural
- `ETT` - Electrical to Thermal

## Notes

Changes the currently defined element types to their corresponding types. Elements without a companion element (listed above) are not switched and should be switched with the [[et|ET]] command to an appropriate element type or to a null element. The KEYOPT values for the switched element types are reset to zero or to their default values. You must check these values to see if they are still meaningful. Additionally, if `Cnv` = ETI, ITE, or TTE, all real constants are set to zero.

If `Cnv` = ITE, you will need to choose a material model that corresponds to your previously- defined material properties. If working interactively, the application prompts you to do so.

(table not available in the PyMAPDL source, see the Ansys help page)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ETCHG.html
