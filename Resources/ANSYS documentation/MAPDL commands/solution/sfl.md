---
apdl: "SFL"
method: sfl
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_surface_loads.SolidSurfaceLoads.sfl
generated: 2026-08-22
tags: [mapdl-command]
---

# SFL

PyMAPDL: `mapdl.sfl(line='', lab='', vali='', valj='', val2i='', val2j='', **kwargs)`

Specifies surface loads on lines of an area.

## Parameters

**line**: Line to which surface load applies. If ALL, apply load to all selected lines ( [[lsel|LSEL]] ). If `Line` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may be substituted for `Line`.

**lab**

Valid surface load label. Load labels are listed under "Surface Loads" in the input table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html). This command contains some tables and extra information which can be inspected in the original documentation pointed above... sfl1:

Thermal labels CONV and HFLUX are mutually exclusive.

For an acoustic analysis, apply the fluid-structure interaction flag (Label = FSI) to only the `FLUID129` or `FLUID130` elements.

**vali**, **valj**

Surface load values at the first keypoint ( `VALI` ) and at the second keypoint ( `VALJ` ) of the line, or table name for specifying tabular boundary conditions. If `VALJ` is blank, it defaults to `VALI`. If `VALJ` is zero, a zero is used.

If `Lab` = CONV:

- `VALI` and `VALJ` are the film coefficients and `VAL2I` and `VAL2J` are the bulk temperatures.
- To specify a table, enclose the table name in percent signs (%), e.g., `tabname`. (Issue [[dim|*DIM]] to define a table.)
- If `Lab` = CONV and `VALI` = - `N`, the film coefficient may be a function of temperature and is determined from the HF property table for material `N` ( [[mp|MP]] ). (See [[scopt|SCOPT]] for a way to override this option and use - `N` as the film coefficient.)
- If [[kbc|KBC]],0 has been issued for ramped loads, it affects only the bulk temperatures, `VAL2I` and `VAL2J`, and the film coefficient specification, `VALI` and `VALJ`, are unaffected.

If `Lab` = RAD, `VALI` and `VALJ` values are surface emissivities and `VAL2I` and `VAL2J` are ambient temperatures. The temperature used to evaluate the film coefficient is usually the average between the bulk and wall temperatures, but may be user-defined for some elements.

If `Lab` = RDSF, `VALI` is the emissivity value. If `VALI` = `-N`, the emissivity may be a function of the temperature and is determined from the EMISS property table for material `N` ( [[mp|MP]] ).

If `Lab` = FSIN in a unidirectional Mechanical APDL-to-CFX analysis, `VALJ` is the surface interface number (not available from within the GUI) and `VALI` is not used.

**val2i**, **val2j**

Second surface load values (if any). If `VAL2J` is blank, it defaults to `VAL2I`. If `VAL2J` is zero, a zero is used. To specify a table ( `Lab` = CONV), enclose the table name in percent signs (%), for example, `tabname`. Use the [[dim|*DIM]] command to define a table.

If `Lab` = CONV:

- `VAL2I` and `VAL2J` are the bulk temperatures.
- If [[kbc|KBC]],0 has been issued for ramped loads, the bulk temperature is ramped from the value defined by [[tunif|TUNIF]] to the value specified by `VALI` and `VALJ` for the first loadstep. If tabular boundary conditions are defined, the [[kbc|KBC]] command is ignored and tabular values are used for the bulk temperatures.

If `Lab` = RAD, `VAL2I` and `VAL2J` are the ambient temperatures.

If `Lab` = RDSF, `VAL2I` is the enclosure number. Radiation will occur between surfaces flagged with the same enclosure numbers. If the enclosure is open, radiation will occur to the ambient.

`VAL2I` and `VAL2J` are not used for other surface load labels.

## Notes

Specifies surface loads on the selected lines of area regions. The lines represent either the edges of area elements or axisymmetric shell elements themselves. Surface loads may be transferred from lines to elements via [[sftran|SFTRAN]] or [[sbctran|SBCTRAN]]. See [[sfe|SFE]] for a description of surface loads. Loads input on this command may be tapered. See [[sfgrad|SFGRAD]] for an alternate tapered load capability.

You can specify a table name only when using structural (PRES) and thermal (CONV \[film coefficient and/or bulk temperature\], HFLUX), and surface emissivity and ambient temperature (RAD) surface load labels. `VALJ` and `VAL2J` are ignored for tabular boundary conditions.

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via [[lvscale|LVSCALE]].

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFL.html
