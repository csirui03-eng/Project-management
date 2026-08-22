---
apdl: "AMMAT"
method: ammat
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.additive_manufacturing.AdditiveManufacturing.ammat
generated: 2026-08-22
tags: [mapdl-command]
---

# AMMAT

PyMAPDL: `mapdl.ammat(matpart='', tmelt='', trelax='', **kwargs)`

Specifies the melting and relaxation temperatures of the build material in an [additive manufacturing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_cal.html) analysis.

## Parameters

**matpart**: The material ID of the build part. Default = 1.

**tmelt**: Melting temperature of the build part (required).

**trelax**: Relaxation temperature of the build part (optional).

## Notes

This command is required in an additive manufacturing analysis.

If the part consists of multiple material IDs, you can specify any of the material IDs ( `MATPART` ), as all are of the same material.

The melting temperature ( `TMELT` ) is the temperature at which thermal strains begin to accumulate. This value is typically the liquidus-to-solidus temperature, but may be less for some phase-transition material (such as Ti64).

The relaxation temperature ( `TRELAX` ) is the temperature at which the strains are zeroed out (annealed). You can use `TRELAX` during the build process ( [[amstep|AMSTEP]],BUILD) to account for stress relaxation, but it serves primarily as a simplified stress-relaxation method during the heat- treat step ( [[amstep|AMSTEP]],HEATTREAT). (A creep model offers a more stringent stress-relaxation approach if needed.)

This command is also valid in PREP7.

For more information, including a list of the elements and commands used in an additive manufacturing analysis, see [AM Process Simulation in Workbench Additive](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_AM_in_WB.html#add_ag_load_addon)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AMMAT.html
