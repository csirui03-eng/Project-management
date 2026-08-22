---
apdl: "AMENV"
method: amenv
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.additive_manufacturing.AdditiveManufacturing.amenv
generated: 2026-08-22
tags: [mapdl-command]
---

# AMENV

PyMAPDL: `mapdl.amenv(tgas='', hgas='', **kwargs)`

Specifies the build-environment thermal boundary conditions in an [additive manufacturing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_cal.html) analysis.

## Parameters

**tgas**: Temperature of the gas in the build enclosure.

**hgas**: Convection coefficient from the part to the enclosure gas.

## Notes

If using the power-bed fusion process ( [[amtype|AMTYPE]],PBF), the convection is applied only to the top of a newly laid layer.

If using the directed-energy deposition process ( [[amtype|AMTYPE]],DED), the convection is applied to the top of a newly laid layer and to the sides of the part already built.

No convection boundary conditions are applied to the plate, although you can define them manually ( [[sf|SF]] and related commands).

This command is also valid in PREP7.

For more information, including a list of the elements and commands used in an additive manufacturing analysis, see [AM Process Simulation in Workbench Additive](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_AM_in_WB.html#add_ag_load_addon)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AMENV.html
