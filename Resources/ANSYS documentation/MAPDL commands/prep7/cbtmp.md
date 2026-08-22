---
apdl: "CBTMP"
method: cbtmp
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.data_tables.DataTables.cbtmp
generated: 2026-08-22
tags: [mapdl-command]
---

# CBTMP

PyMAPDL: `mapdl.cbtmp(temp='', **kwargs)`

Specifies a temperature for composite-beam input.

## Parameters

**temp**: Temperature value.

## Notes

The **CBTMP** command, one of several [composite beam-section commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PREBEAMSECT_5.html#), specifies a temperature to be associated with the data input via subsequent [[cbmx|CBMX]] (preintegrated cross-section stiffness), [[cbmd|CBMD]] (preintegrated section mass), or [[cbte|CBTE]] (thermal-expansion) commands.

The specified temperature remains active unt il the next **CBTMP** command is issued.

An unspecified temperature value defaults to zero.

For complete information, see [Using Preintegrated Composite Beam Sections](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PREBEAMSECT_5.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CBTMP.html
