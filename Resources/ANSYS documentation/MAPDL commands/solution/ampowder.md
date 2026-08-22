---
apdl: "AMPOWDER"
method: ampowder
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.additive_manufacturing.AdditiveManufacturing.ampowder
generated: 2026-08-22
tags: [mapdl-command]
---

# AMPOWDER

PyMAPDL: `mapdl.ampowder(tpowder='', hpowder='', matfactor='', **kwargs)`

Specifies the thermal conditions of the powder in an [additive manufacturing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_cal.html) analysis.

## Parameters

**tpowder**: Temperature of the newly added powder.

**hpowder**: Effective convection coefficient from the part to the powder bed.

**matfactor**: Knockdown factor applied to the solid material properties (to obtain the powder material properties). Default = 0.01.

## Notes

This command applies only to the powder-bed fusion ( [[amtype|AMTYPE]],PBF) process.

To estimate the convection coefficient ( `HPOWDER` ), divide the conduction property of the powder (its KXX) by a characteristic conduction length into the powder (for example, ¼ of the distance from the part boundary to the build-chamber wall).

The program uses the knockdown factor ( `MATFACTOR` ) to estimate the powder properties. The program applies the factor (typically 0.01) to the solid material properties to estimate the properties of the material in its powder state. The powder-state properties are used during the heating of the new layer (before its subsequent solidification and cooldown) prior to the next layer being applied.

This command is also valid in PREP7.

For more information, including a list of the elements and commands used in an additive manufacturing analysis, see [AM Process Simulation in Workbench Additive](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_AM_in_WB.html#add_ag_load_addon)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AMPOWDER.html
