---
apdl: "AMBUILD"
method: ambuild
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.additive_manufacturing.AdditiveManufacturing.ambuild
generated: 2026-08-22
tags: [mapdl-command]
---

# AMBUILD

PyMAPDL: `mapdl.ambuild(option='', val1='', val2='', val3='', val4='', **kwargs)`

Specifies printer parameters for the build and other options in an [additive manufacturing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_cal.html) analysis.

## Parameters

**option**

Option:

- `LAYERT` - `VAL1` - Deposition-layer thickness.

  `VAL2` - Mesh height.

  `VAL3` - Error-checking flag. Set to 0 (default) or 1. Setting to 1 causes the application to omit error checks for consistent element size and elements spanning across layers.

- `SCAN` - `VAL1` - Hatch spacing.

  `VAL2` - Beam-travel speed.

- `TIME` - `VAL1` - Inter-layer dwell time. Default = 0.0.

  `VAL2` - Dwell-time multiplier for multiple parts on the build plate or number of repeated symmetry sectors in simulations with symmetry. Default = 1.0.

  `VAL3` - Unused field.

  `VAL4` - Scan time table.

- `PLATE` - `VAL1` - Z-coordinate of the top of the build plate. Default = 0.0.

- `CHECK` - `VAL1` - If YES, create the build-summary file but do not solve. Default = NO.

- `RTHFILE` - `VAL1` - Name of the thermal-results file (including its path). Default = `file.rth` in the current working directory.

- `SSF` - `VAL1` - Strain Scaling Factor. Default = 1.0.

**val1**, **val2**, **val3**, **val4**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AMBUILD.html) for further information.

## Notes

If using a layered tetrahedral mesh, specify the mesh height (LAYERT, `VAL2` ). For Cartesian meshes, the mesh height is determined automatically.

When setting the error-checking flag (LAYERT,,,1), verify your model and results carefully. Using the flag may lead to improper setup of layers or boundary conditions.

The hatch spacing and beam travel speed are the average values used during the build.

The inter-layer dwell time (TIME, `VAL1` ) is the span of time from the end of the deposition of a layer to the start of the deposition of the next layer. It includes the time required for recoater- blade repositioning and powder-layer spreading.

The dwell-time multiplier (TIME, `VAL2` ) accounts for more than one part being printed on the build plate, or it is used to reconcile build time in simulations using symmetry. For multiple parts on a build plate, if the additional parts are the same part as the one being simulated and are arranged in the same orientation on the build plate, the multiplier is the total number of parts. If different parts exist on the plate, the multiplier is an estimate of the time required to build the other parts relative to the part being simulated. In simulations with symmetry, the dwell-time multiplier is the total number of repeated symmetry sectors: 2 for half symmetry, 4 for ¼ symmetry, and so on.

The scan time (TIME, `VAL4` ) represents the amount of time it takes to scan a real layer. By default, the scan time will be determined from each layer's cross-sectional area and other process parameters. When specified, it must be defined as a table with times specified on the Z primary variable. Times that are averaged or interpolated from the table should not include recoating time and will be adjusted to account for superlayer size compared to the deposition thickness.

When specifying the name of the thermal-results file (RTHFILE, `VAL1` ), omit the `.rth` extension. The program also looks for the `thermal.build` file in the same path.

The strain scaling factor (SSF, `VAL1` ) scales the thermal strains in the structural portion of thermal-structural simulations by the specified value.

This command is also valid in PREP7.

For more information, including a list of the elements and commands used in an additive manufacturing analysis, see [AM Process Simulation in Workbench Additive](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_AM_in_WB.html#add_ag_load_addon)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AMBUILD.html
