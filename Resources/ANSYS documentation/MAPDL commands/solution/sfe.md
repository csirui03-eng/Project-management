---
apdl: "SFE"
method: sfe
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_surface_loads.FeSurfaceLoads.sfe
generated: 2026-08-22
tags: [mapdl-command]
---

# SFE

PyMAPDL: `mapdl.sfe(elem='', lkey='', lab='', kval='', value1='', value2='', value3='', value4='', meshflag='', **kwargs)`

Defines surface loads on elements.

## Parameters

**elem**: Element to which surface load applies. If ALL, apply load to all selected elements ( [[esel|ESEL]] ). If `Elem` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may be substituted for `Elem`.

**lkey**

Load key or face number associated with surface load (defaults to 1). Load keys (1,2,3, etc.) are listed under "Surface Loads" in the input data table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html).

If you issue [[sfcontrol|SFCONTROL]] before **SFE**, `LKEY` is the face number for [supported structural solid and shell elements](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_SFCONTROL.html#).

**lab**

Valid surface load label. Load labels are listed under "Surface Loads" in the input table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html).

(table not available in the PyMAPDL source, see the Ansys help page)

Thermal labels CONV and HFLUX are mutually exclusive.

For an acoustic analysis, apply the fluid-structure interaction flag (Label = FSI) to only the `FLUID29`, `FLUID30`, `FLUID220`, and `FLUID221` elements.

When a load vector exists for a thermal superelement, it must be applied and have a scale factor of 1 ( **SFE**,,,SELV,,1).

**kval**

Value key. If `Lab` = PRES:

- `0 or 1` - `VALUE1` through `VALUE4` are used as real components of pressures.
- `2` - `VALUE1` through `VALUE4` are used as imaginary components of pressures.

Value key. If `Lab` = CONV:

- `0 or 1` - For thermal analyses, `VALUE1` through `VALUE4` are used as the film coefficients.
- `2` - For thermal analyses, `VALUE1` through `VALUE4` are the bulk temperatures.
- `3` - `VALUE1` through `VALUE4` are used as film effectiveness.
- `4` - `VALUE1` through `VALUE4` are used as free stream temperature.

Value key. If `Lab` = RAD:

- `0 or 1` - `VALUE1` through `VALUE4` are used as the emissivities.
- `2` - `VALUE1` through `VALUE4` are ambient temperatures.

Value key. If `Lab` = RDSF:

- `0 or 1` - `VALUE1` is the emissivity value between 0 and 1.
- `2` - `VALUE1` is the enclosure number.

Value key. If `Lab` = IMPD:

- `0 or 1` - For acoustic harmonic analyses, VALUE1 through VALUE4 are used as the real part of the impedance.
- `2` - For acoustic harmonic analyses, VALUE1 through VALUE4 are used as the imaginary part of the impedance.

Value key. If `Lab` = SHLD:

- `0 or 1` - For acoustic analyses, `VALUE1` through `VALUE4` are used as the normal velocity (harmonic) or normal acceleration (transient).
- `2` - For acoustic analyses, `VALUE1` through `VALUE4` are used as the phase angle for harmonic response analyses.

Value key. If `Lab` = ATTN:

- `0 or 1` - For acoustic analyses, `VALUE1` through `VALUE4` are used as the absorption coefficient of the surface.
- `2` - For acoustic analyses, `VALUE1` through `VALUE4` are used as the transmission loss (dB) of the coupled wall in an energy diffusion solution for room acoustics.

Value key. If `Lab` = SELV:

- `0 or 1` - `VALUE1` is the multiplier on real load vector `LKEY`.
- `2` - `VALUE1` is the multiplier on imaginary load vector `LKEY`.

If only one set of data is supplied, the other set of data defaults to previously specified values (or zero if not previously specified) in the all of the following cases:

- Emissivities are supplied and `Lab` = RAD
- Temperatures are supplied and `Lab` = RAD
- Temperatures are supplied and `Lab` = CONV
- Film coefficients are supplied and `Lab` = CONV
- Normal velocity/acceleration for acoustics is supplied and `Lab` = SHLD
- Phase angle for acoustics is supplied and `Lab` = SHLD

**value1**

First surface load value (typically at the first node of the face), or the name of a table for specifying tabular boundary conditions.

Face nodes are listed in the order given for **Surface Loads** in the input data table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html). For example, for `SOLID185`, the item 1-JILK associates `LKEY` = 1 (face 1) with nodes J, I, L, and K. Surface load value `VALUE1` then applies to node J of face 1. To specify a table, enclose the table name in percent signs (%), for example, `tabname`. Use the [[dim|*DIM]] command to define a table. Only one table can be specified, and it must be specified in the `VALUE1` position; tables specified in the `VALUE2`, `VALUE3`, or `VALUE4` positions are ignored. `VALUE2` applies to node I, etc.

If `Lab` = PRES and `KVAL` = 2, this value is the imaginary pressure component, used by the following supported elements:

- Surface elements: `SURF153`, `SURF154` and `SURF159`.
- Solid and solid-shell elements: `PLANE182`, `PLANE183`, `SOLID185`, `SOLID186`, `SOLID187`, `SOLSH190`, and `SOLID285`.
- Shell elements: `SHELL181`, `SHELL281`, `SHELL208`, and `SHELL209`.
- Coupled-field elements with structural degrees of freedom: `PLANE222`, `PLANE223`, `SOLID225`, `SOLID226`, and `SOLID227`.

If `Lab` = CONV, `KVAL` = 0 or 1, and `VALUE1` = - `N`, the film coefficient is assumed to be a function of temperature and is determined from the HF property table for material `N` ( [[mp|MP]] ). (See the [[scopt|SCOPT]] command for a way to override this option and use - `N` as the film coefficient.) The temperature used to evaluate the film coefficient is usually the average between the bulk and wall temperatures, but may be user-defined for some elements.

If `Lab` = CONV, `KVAL` = 2, `VALUE1` specifies the bulk temperature. If [[kbc|KBC]],0 has been issued for ramped loads, the bulk temperature is ramped from the value defined by [[tunif|TUNIF]] to that specified on `VALUE1` (for the first loadstep). If a table name is specified for `VALUE1`, the [[kbc|KBC]] command is ignored and tabular values are used.

If `Lab` = PORT, `VALUE1` is a port number representing a waveguide port. The port number must be an integer between 1 and 50. For an acoustic 2×2 transfer admittance matrix, the port number can be any positive integer. The smaller port number corresponds to port 1 of the 2×2 transfer admittance matrix, and the greater port number corresponds to port 2. If one port of the transfer admittance matrix is connecting to the acoustic-structural interaction interface, the port number corresponds to port 2 of the transfer admittance matrix. A pair of ports of the 2×2 transfer admittance matrix must be defined in the same element.

If `Lab` = RDSF, `KVAL` = 0 or 1, and `VALUE1` = - `N`, the emissivity is assumed to be a function of the temperature, and is determined from the EMISS property table for material `N` ( [[mp|MP]] ). The material `N` does not need to correlate with the underlying solid thermal elements. If `Lab` = RDSF, `KVAL` = 2, and `VALUE1` is negative, radiation direction is reversed and will occur inside the element for the flagged radiation surfaces.

If `Lab` = FSIN in a unidirectional Mechanical APDL-to-CFX analysis, `VALUE1` is not used.

If `Lab` = SELV, `VALUE1` represents the scale factor (default = 0.0).

If `Lab` = ATTN, `VALUE1` is the absorption coefficient.

**value2**, **value3**, **value4**

Surface load values at the second, third, and fourth nodes (if any) of the face.

If all three values are blank, all default to `VALUE1`, giving a constant load. Zero or other blank values are used as zero.

If `VALUE2`, `VALUE3`, or `VALUE4` are magnitudes of the load, they are ignored if `VALUE1` is a table. If `VALUE2`, `VALUE3`, or `VALUE4` are any other values, they are used even if `VALUE1` is a table (for example, the load direction for face 5 of `SURF154` ).

If `Lab` = FSIN in a unidirectional Mechanical APDL-to-CFX analysis, `VALUE2` is the surface interface number (not available in the GUI). `VALUE3` and `VALUE4` are not used.

**meshflag**

Specifies how to apply normal pressure loading on the mesh. Valid in a [nonlinear adaptivity analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVREZ.html) when `Lab` = PRES and `KVAL` = 0 or 1.

0 - Pressure loading occurs on the current mesh (default).

1 - Pressure loading occurs on the initial mesh for nonlinear adaptivity.

## Notes

**SFE** defines surface loads on selected elements.

> [!WARNING]
> You cannot use **SFE** with the `INFIN110` or `INFIN111` elements without prior knowledge of element-face orientation (that is, you must know which face is the exterior in order to flag it). Also, for surface-effect elements `SURF153` and `SURF154`, use `LKEY` to enable tangential and other loads. For [supported structural solid and shell elements](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_SFCONTROL.html#), issue [[sfcontrol|SFCONTROL]] to define tangential and other loads.

**SFE** can apply tapered loads over the faces of most elements.

You can use these related surface-load commands with **SFE** :

- [[sf|SF]] - Defines surface loads on nodes.
- [[sfbeam|SFBEAM]] - For beam elements allowing lateral surface loads that can be offset from the nodes, this command specifies the loads and offsets.
- [[sfcontrol|SFCONTROL]] - Applies general (normal, tangential, and other) surface loads to [supported structural elements](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_SFCONTROL.html#).
- [[sfcum|SFCUM]] - Accumulates (adds) surface loads applied via **SFE**.
- [[sfdele|SFDELE]] - Delete loads applied via **SFE**.
- [[sffun|SFFUN]] - Applies loads from a node-vs.-value function.
- [[sfgrad|SFGRAD]] - Applies an alternate tapered load.

The **SFE** command can also define fluid-pressure-penetration loads ( `Lab` = PRES) at a contact interface. For this type of load, `LKEY` = 1 is used to specify the normal pressure values, `LKEY` = 3 is used to specify the tangential pressure values along the x direction of [[esys|ESYS]], `LKEY` = 4 is used to specify the tangential pressure values along the y direction of [[esys|ESYS]], and `LKEY` = 2 is used to specify starting points and penetrating points. See [Applying Fluid Penetration Pressure](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctecfluidpress.html#fl_press_dir_2D)

Film effectiveness and free-stream temperatures specified via `Lab` = CONV are valid only for `SURF151` and `SURF152`. Film effectiveness must be between 0 and 1 and it defaults to 0. If film effectiveness is applied, bulk temperature is ignored. When film effectiveness and free stream temperatures are specified, the commands to specify a surface-load gradient ( [[sfgrad|SFGRAD]] ) or surface-load accumulation ( [[sfcum|SFCUM]] ) are not valid. For more information about film effectiveness, see [Conduction, Convection, and Mass Transport (Advection)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_heat1.html#thyeq10conductnov1601)

You can specify a table name only when using structural (PRES) and thermal (CONV \[film coefficient, bulk temperature, film effectiveness, and free stream temperature\], HFLUX), diffusion flux (DFLUX), surface emissivity and ambient temperature (RAD), impedance (IMPD), normal velocity or acceleration (SHLD), absorption coefficient (ATTN), and substructure (SELV) surface load labels.

When a tabular function load is applied to an element, the load will not vary according to the positioning of the element in space.

For cases where Lab=FSI, MXWF, FREE, and INF, VALUE is not needed.

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via the [[lvscale|LVSCALE]] command.

This command is also valid in the PREP7 and [[slashmap|/MAP]] processors.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFE.html
