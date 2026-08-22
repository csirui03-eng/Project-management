---
apdl: "AMRESULT"
method: amresult
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.additive_manufacturing.AdditiveManufacturing.amresult
generated: 2026-08-22
tags: [mapdl-command]
---

# AMRESULT

PyMAPDL: `mapdl.amresult(item='', key='', **kwargs)`

Specifies [additive manufacturing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_cal.html) result data written to a `.txt` None file.

## Parameters

**item**

Result item to output to a tab-delimited `.txt` file:

- `RINT` - Recoater interference. Available in a structural additive manufacturing analysis only.
- `DTEMP` - Layer end temperature. Available in a thermal additive manufacturing analysis only.
- `HSTN` - High Strain. Available in a structural additive manufacturing analysis only.

**key**

Write-control key:

- `OFF` - Does not write the specified result item (default).
- `ON` - Writes the specified result item.

## Notes

This command controls [additive manufacturing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_cal.html) result data written to a `.txt` file. Specifically, `AMResults.txt` is written for recoater interference and layer end temperature, and `AMHighStrain.txt` is written for high strains. The specified results are not written to the database results ( `.RST` ) file.

Result items written to the `.txt` file also include node numbers and x, y, z locations.

RINT gives the z-deformation of a layer just before a new layer is applied. This result value can help to determine whether an issue may occur when spreading a new layer.

DTEMP gives the temperature of a layer just before a new layer is applied. This result value can help to identify regions where the build may be overheating that may result in problematic thermal conditions.

HSTN gives the maximum equivalent strain experienced during the build process. This result value can help to identify regions at risk of cracking.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AMRESULT.html
