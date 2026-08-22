---
apdl: "SFA"
method: sfa
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_surface_loads.SolidSurfaceLoads.sfa
generated: 2026-08-22
tags: [mapdl-command]
---

# SFA

PyMAPDL: `mapdl.sfa(area='', lkey='', lab='', value='', value2='', **kwargs)`

Specifies surface loads on the selected areas.

## Parameters

**area**: Area to which surface load applies. If ALL, apply load to all selected areas ( [[asel|ASEL]] ). If `Area` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component may be substituted for `Area`.

**lkey**: Load key associated with surface load (defaults to 1). Load keys (1,2,3, etc.) are listed under "Surface Loads" in the input data table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html). `LKEY` is ignored if the area is the face of a volume region meshed with volume elements.

**lab**

Valid surface load label. Load labels are listed under "Surface Loads" in the input table for each area type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html).

(table not available in the PyMAPDL source, see the Ansys help page)

Thermal labels CONV and HFLUX are mutually exclusive.

For an acoustic analysis, apply the fluid-structure interaction flag (Label = FSI) to only the `FLUID129` or `FLUID130` elements.

**value**

Surface load value or table name reference for specifying tabular boundary conditions.

If `Lab` = CONV:

- `VALUE` is typically the film coefficient and `VALUE2` (below) is typically the bulk temperature. If `Lab` = CONV and `VALUE` = - `N`, the film coefficient may be a function of temperature and is determined from the HF property table for material `N` ( [[mp|MP]] ). (See the [[scopt|SCOPT]] command for a way to override this option and use - `N` as the film coefficient.) The temperature used to evaluate the film coefficient is usually the average between the bulk and wall temperatures, but may be user-defined for some elements.
- If [[kbc|KBC]],0 has been issued for ramped loads, it affects only `VALUE2`, the bulk temperature, and the film coefficient specification is unaffected.
- 

If `Lab` = RAD, `VALUE` is the surface emissivity.

If `Lab` = PORT, `VALUE` is a port number representing a waveguide exterior port. The port number must be an integer between 1 and 50. For acoustic 2×2 transfer admittance matrix, the port number can be any positive integer. The smaller port number corresponds to the port 1 of the 2×2 transfer admittance matrix and the greater port number corresponds to the port 2. If one port of the transfer admittance matrix is connecting to the acoustic-structural interaction interface, the port number corresponds to the port 2 of the transfer admittance matrix. A pair of ports of the 2×2 transfer admittance matrix must be defined in the same element.

If `Lab` = SHLD, `VALUE` is the surface normal velocity in harmonic analysis and the surface normal acceleration in transient analysis for acoustics.

If `Lab` = IMPD, `VALUE` is resistance in (N)(s)/m <sup>3</sup> if `VALUE` \> 0 and is conductance in mho if `VALUE` \< 0 for acoustics. In acoustic transient analyses, `VALUE2` is not used.

If `Lab` = RDSF, `VALUE` is the emissivity value; the following conditions apply: If `VALUE` is between 0 and 1, apply a single value to the surface. If `VALUE` = - `N`, the emissivity may be a function of the temperature, and is determined from the EMISS property table for material `N` ( [[mp|MP]] ). The material `N` does not need to correlate with the underlying solid thermal elements.

If `Lab` = FSIN in a unidirectional Mechanical APDL to CFX analysis, `VALUE` is not used.

If `Lab` = ATTN, `VALUE` is the absorption coefficient of the surface.

**value2**

Second surface load value (if any).

If `Lab` = CONV:

- `VALUE2` is typically the bulk temperature for thermal analyses.
- If [[kbc|KBC]],0 has been issued for ramped loads, the bulk temperature is ramped from the value defined by [[tunif|TUNIF]] to the value specified by `VALUE2` for the first loadstep. If tabular boundary conditions are defined, the [[kbc|KBC]] command is ignored and tabular values are used.
- For acoustic analyses, VALUE2 is not used.

If `Lab` = RAD `VALUE2` is ambient temperature.

If `Lab` = SHLD, `VALUE2` is the phase angle of the normal surface velocity (defaults to zero) for harmonic response analyses while `VALUE2` is not used for transient analyses in acoustics.

If `Lab` = IMPD, `VALUE2` is reactance in (N)(s)/m <sup>3</sup> if `VALUE` \> 0 and is the product of susceptance and angular frequency if `VALUE` \< 0 for acoustics.

If `Lab` = RDSF, `VALUE2` is the enclosure number. Radiation will occur between surfaces flagged with the same enclosure numbers. If the enclosure is open, radiation will also occur to ambient. If `VALUE2` is negative, radiation direction is reversed and will occur inside the element for the flagged radiation surfaces.

If `Lab` = FSIN in a unidirectional Mechanical APDL to CFX analysis, `VALUE2` is the surface interface number (not available from within the GUI).

## Notes

Surface loads may be transferred from areas to elements with the [[sftran|SFTRAN]] or [[sbctran|SBCTRAN]] commands. See the [[sfgrad|SFGRAD]] command for an alternate tapered load capability.

Tabular boundary conditions Tabular boundary conditions ( `VALUE` = `tabname` and/or `VALUE2` = `tabname`) are available for the following surface load labels ( `Lab` ) only: PRES (real and/or imaginary components), CONV (film coefficient and/or bulk temperature) or HFLUX, and RAD (surface emissivity and ambient temperature). Use the [[dim|*DIM]] command to define a table.

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via the [[lvscale|LVSCALE]] command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFA.html
