---
apdl: "SF"
method: sf
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_surface_loads.FeSurfaceLoads.sf
generated: 2026-08-22
tags: [mapdl-command]
---

# SF

PyMAPDL: `mapdl.sf(nlist='', lab='', value='', value2='', meshflag='', **kwargs)`

Defines surface loads on nodes.

## Parameters

**nlist**: Nodes defining the surface upon which the load is to be applied. Use the label ALL or P, or a component name. If ALL, all selected nodes ( [[nsel|NSEL]] ) are used (default). If P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**lab**

Valid surface load label. Load labels are listed under **Surface Loads** in the input table for each element type.

(table not available in the PyMAPDL source, see the Ansys help page)

Thermal labels CONV and HFLUX are mutually exclusive.

For an acoustic analysis, apply the fluid-structure interaction flag (Label = FSI) to only the `FLUID29`, `FLUID30`, `FLUID220`, and `FLUID221` elements.

**value**

Surface load value or table name reference for specifying tabular boundary conditions.

If `Lab` = PRES, `VALUE` is the real component of the pressure.

If `Lab` = CONV:

- `VALUE` is typically the film coefficient and `VALUE2` (below) is typically the bulk temperature. If `VALUE` = - `N`, the film coefficient may be a function of temperature and is determined from the HF property table for material `N` ( [[mp|MP]] ). (See the [[scopt|SCOPT]] command for a way to override this option and use - `N` as the film coefficient.) The temperature used to evaluate the film coefficient is usually the average between the bulk and wall temperatures, but may be user-defined for some elements.
- If [[kbc|KBC]],0 has been issued for ramped loads, it affects only `VALUE2` the bulk temperature, and the film coefficient specification is unaffected.
- In a viscous-thermal acoustic analysis, if `Lab` = CONV, `VALUE` is the real part of the heat flux and `VALUE2` is the imaginary part of the heat flux.

If `Lab` = RAD, `VALUE` is surface emissivity.

If `Lab` = PORT, `VALUE` is a port number representing a waveguide exterior port. The port number must be an integer between 1 and 50. For acoustic 2×2 transfer admittance matrix, the port number can be any positive integer. The smaller port number corresponds to the port 1 of the 2×2 transfer admittance matrix and the greater number corresponds to the port 2. If one port of the transfer admittance matrix is connecting to the acoustic-structural interaction interface, the port number corresponds to the port 2 of the transfer admittance matrix. A pair of ports of the 2×2 transfer admittance matrix must be defined in the same element. In an acoustic analysis, the positive port number defines a transparent port, through which the reflected sound pressure wave propagates to the infinity; the negative port number defines a vibro port that is the structural vibration surface.

If `Lab` = SHLD, `VALUE` is the surface normal velocity in a harmonic analysis or in a transient analysis solved with the velocity potential formulation; `VALUE` is the surface normal acceleration in a transient analysis solved with the pressure formulation.

If `Lab` = IMPD, `VALUE` is resistance in (N)(s)/m <sup>3</sup> if `VALUE` \> 0 and is conductance in mho if `VALUE` \< 0 for acoustic or harmonic response analyses. In acoustic transient analyses, `VALUE2` is not used.

If `Lab` = RDSF, `VALUE` is the emissivity value; the following conditions apply: If `VALUE` is between 0 and 1, apply a single value to the surface. If `VALUE` = - `N`, the emissivity may be a function of the temperature, and is determined from the EMISS property table for material `N` ( [[mp|MP]] ). The material `N` does not need to correlate with the underlying solid thermal elements.

If `Lab` = FSIN in a one-way structure-to-acoustic coupling, `VALUE` is the surface interface number.

If `Lab` = FSIN in a unidirectional Mechanical APDL to CFX analysis, `VALUE` is not used.

If `Lab` = ATTN, `VALUE` is the absorption coefficient of the surface.

If `Lab` = VIMP, `VALUE` is resistance of viscous impedance in (N)(s)/m <sup>3</sup>.

If `Lab` = TIMP, `VALUE` is resistance of thermal impedance in (N)(s)/m <sup>3</sup>.

If `Lab` = PERM, `VALUE` is permeability in m <sup>2</sup>.

**value2**

Second surface load value (if any).

If `Lab` = PRES, this value is the imaginary pressure component, used by the following supported elements:

- Surface elements: `SURF153`, `SURF154` and `SURF159`.
- Solid and solid-shell elements: `PLANE182`, `PLANE183`, `SOLID185`, `SOLID186`, `SOLID187`, `SOLSH190`, and `SOLID285`.
- Shell elements: `SHELL181`, `SHELL281`, `SHELL208`, and `SHELL209`.
- Coupled-field elements with structural degrees of freedom: `PLANE222`, `PLANE223`, `SOLID225`, `SOLID226`, and `SOLID227`.

Supported analysis types in this case are:

- Full harmonic ( [[hropt|HROPT]],FULL)
- Mode-superposition harmonic ( [[hropt|HROPT]],MSUP), if the mode-extraction method is Block Lanczos ( [[modopt|MODOPT]] ,LANB), PCG Lanczos ( [[modopt|MODOPT]],LANPCG), Supernode ( [[modopt|MODOPT]],SNODE), Subspace ( [[modopt|MODOPT]],SUBSP), or Unsymmetric ( [[modopt|MODOPT]],UNSYM)

If `Lab` = CONV:

- `VALUE2` is the bulk temperature for thermal analyses.
- If [[kbc|KBC]],0 has been issued for ramped loads, the bulk temperature is ramped from the value defined by [[tunif|TUNIF]] to the value specified by `VALUE2` for the first loadstep. If tabular boundary conditions are defined, the [[kbc|KBC]] command is ignored and tabular values are used.
- For viscous-thermal acoustics `VALUE2` is the imaginary part of heat flux.

If `Lab` = RAD, `VALUE2` is the ambient temperature.

If `Lab` = SHLD, `VALUE2` is the phase angle of the normal surface velocity (defaults to zero) for harmonic response analyses while `VALUE2` is not used for transient analyses in acoustics.

If `Lab` = IMPD, `VALUE2` is reactance in (N)(s)/m <sup>3</sup> if `VALUE` \> 0 and is the product of susceptance and angular frequency if `VALUE` \< 0 for acoustics.

If `Lab` = RDSF, `VALUE2` is the enclosure number. Radiation will occur between surfaces flagged with the same enclosure numbers. If the enclosure is open, radiation will also occur to ambient. If `VALUE2` is negative radiation direction is reversed and will occur inside the element for the flagged radiation surfaces.

If `Lab` = FSIN in a unidirectional Mechanical APDL to CFX analysis, `VALUE2` is the surface interface number (not available from within the GUI).

If `Lab` = PORT, `VALUE2` is not used.

If `Lab` = ATTN, `VALUE2` is the transmission loss (dB) of the coupled wall in an energy diffusion solution for room acoustics.

If `Lab` = VIMP, `VALUE2` is reactance of viscous impedance in (N)(s)/m <sup>3</sup>.

If `Lab` = TIMP, `VALUE2` is reactance of thermal impedance in (N)(s)/m <sup>3</sup>.

**meshflag**

Specifies how to apply normal pressure loading on the mesh. Valid in a [nonlinear adaptivity analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVREZ.html) when `Lab` = PRES and `Nlist` is a nodal component defined prior to any remeshing activity.

0 - Pressure loading occurs on the current mesh (default).

1 - Pressure loading occurs on the initial mesh for nonlinear adaptivity.

## Notes

Individual nodes cannot be entered for this command. The node list is to identify a surface and the `Nlist` field must contain a sufficient number of nodes to define an element surface. The loads are internally stored on element faces defined by the specified nodes. All nodes on an element face (including midside nodes, if any) must be specified for the face to be used, and the element must be selected.

If all nodes defining a face are shared by an adjacent face of another selected element, the face is not free and will not have a load applied. If more than one element can share the same nodes (for example, a surface element attached to a solid element), select the desired element type before issuing the **SF** command. The **SF** command applies only to area and volume elements.

For shell elements, if the specified nodes include face one (which is usually the bottom face) along with other faces (such as edges), only face one is used. Where faces cannot be uniquely determined from the nodes, or where the face does not fully describe the load application, issue [[sfe|SFE]] instead of **SF**. A load key of 1 (which is typically the first loading condition on the first face) is used if the face determination is not unique. A uniform load value is applied over the element face.

You can use these related surface-load commands with **SF** :

- [[sfe|SFE]] - Defines surface loads on elements. You can also use it to apply tapered loads on individual element faces.
- [[sfbeam|SFBEAM]] - Applies surface loads to beam elements.
- [[sfcontrol|SFCONTROL]] - Applies general (normal, tangential, and other) surface loads to [supported structural elements](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_SFCONTROL.html#).
- [[sfcum|SFCUM]] - Accumulates (adds) surface loads applied via **SF**.
- [[sfdele|SFDELE]] - Delete loads applied via **SF**.
- [[sffun|SFFUN]] - Applies loads from a node-vs.-value function.
- [[sfgrad|SFGRAD]] - Applies an alternate tapered load.

Tabular boundary conditions Tabular boundary conditions ( `VALUE` = `tabname` and/or `VALUE2` = `tabname`) are available for the following surface load labels ( `Lab` ) only: PRES (real and/or imaginary components), CONV (film coefficient and/or bulk temperature; or heat flux for viscous-thermal acoustics), HFLUX, DFLUX (diffusion flux), RAD (surface emissivity and ambient temperature), IMPD (resistance and reactance), SHLD (normal velocity and phase or acceleration), ATTN ( absorption coefficient or transmission loss ), VIMP (viscous impedance), and TIMP (thermal impedance). Issue [[dim|*DIM]] to define a table.

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via the [[lvscale|LVSCALE]] command.

This command is also valid in the PREP7 and [[slashmap|/MAP]] processors.

Ansys Mechanical Enterprise **SF**,FSI and **SF**,FSIN are available only in the Ansys Mechanical Enterprise family of products (Ansys Mechanical Enterprise, Ansys Mechanical Enterprise PrepPost, and Ansys Mechanical Enterprise Solver).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SF.html
