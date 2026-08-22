---
apdl: "ASUM"
method: asum
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.asum
generated: 2026-08-22
tags: [mapdl-command]
---

# ASUM

PyMAPDL: `mapdl.asum(lab='', **kwargs)`

Calculates and prints geometry statistics of the selected areas.

## Parameters

**lab**: Controls the degree of tessellation used in the calculation of area properties. If `LAB` = DEFAULT, area calculations will use the degree of tessellation set through the [[facet|/FACET]] command. If `LAB` = FINE, area calculations are based on a finer tessellation.

## Notes

Calculates and prints geometry statistics (area, centroid location, moments of inertia, volume, etc.) associated with the selected areas. **ASUM** should only be used on perfectly flat areas.

Geometry items are reported in the global Cartesian coordinate system. A unit thickness is assumed unless the areas have a non-zero total thickness defined by real constant or section data.

For layered areas, a unit density is always assumed. For single-layer areas, a unit density is assumed unless the areas have a valid material (density).

The thickness and density are associated to the areas via the [[aatt|AATT]] command.

Items calculated via **ASUM** and later retrieved via a [[get|*GET]] or [[starvget|*VGET]] command are valid only if the model is not modified after issuing the **ASUM** command.

Setting a finer degree of tessellation will provide area calculations with greater accuracy, especially for thin, hollow models. However, using a finer degree of tessellation requires longer processing.

For very narrow (sliver) areas, such that the ratio of the minimum to the maximum dimension is less than 0.01, the **ASUM** command can provide erroneous area information. To ensure that the calculations are accurate, subdivide such areas so that the ratio of the minimum to the maximum is at least 0.05.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ASUM.html
