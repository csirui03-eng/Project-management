---
apdl: "AMTYPE"
method: amtype
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.additive_manufacturing.AdditiveManufacturing.amtype
generated: 2026-08-22
tags: [mapdl-command]
---

# AMTYPE

PyMAPDL: `mapdl.amtype(process='', **kwargs)`

Specifies the printing process in an [additive manufacturing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_cal.html) analysis.

## Parameters

**process**

Process option:

- `PBF` - Powder-bed fusion process.
- `DED` - Directed-energy deposition process.

## Notes

The powder-bed fusion (PBF) process uses thermal energy from a laser or electron beam to selectively fuse powder in a powder bed.

The directed-energy deposition (DED) process uses thermal energy, typically from a laser, to fuse materials by melting them as they are deposited.

This command is also valid in PREP7.

For more information, including a list of the elements and commands used in an additive manufacturing analysis, see [AM Process Simulation in Workbench Additive](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_AM_in_WB.html#add_ag_load_addon)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AMTYPE.html
