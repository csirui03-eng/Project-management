---
apdl: "CINT"
method: cint
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.special_purpose.SpecialPurpose.cint
generated: 2026-08-22
tags: [mapdl-command]
---

# CINT

PyMAPDL: `mapdl.cint(action='', par1='', par2='', par3='', par4='', par5='', par6='', par7='', **kwargs)`

Defines parameters associated with fracture-parameter calculations.

## Parameters

**action**

Specifies action for defining or manipulating initial crack data:

- `NEW` - [Command Specification for Action= NEW](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#) Initiate a new calculation and assign an ID.
- `CTNC` - [Command Specifications for Action= CTNC](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#) Define the crack-tip node component.
- `SURF` - [Command Specifications for Action= SURF](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#) Define the crack-surface node components.
- `CENC` - [Command Specifications for Action= CENC](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#) Define the crack-extension node component, the crack-tip node, and the crack-extension direction.
- `TYPE` - [Command Specifications for Action= TYPE](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#) Define the type of calculation to perform.
- `DELE` - [Command Specifications for Action= DELE](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#) Delete the **CINT** object associated with the specified ID.
- `NCON` - [Command Specifications for Action= NCON](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#) Specify the number of contours to calculate in the contour-integral calculation.
- `SYMM` - [Command Specifications for Action= SYMM](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#) Indicate whether the crack is on a symmetrical line or plane.
- `NORM` - [Command Specifications for Action= NORM](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#) Define the crack-plane normal.
- `UMM` - [Command Specifications for Action= UMM](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#) Enable or disable the unstructured-mesh method (UMM).
- `EDIR` - [Command Specifications for Action= EDIR](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#) Crack-assist extension direction.
- `PLOT` - [Command Specifications for Action= PLOT](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#) Plots the crack- front and crack-tip coordinate system.
- `LIST` - [Command Specifications for Action= LIST](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#) List the **CINT** commands issued, or the elements used, in fracture-parameter calculations.
- `CXFE` - [Command Specifications for Action= CXFE](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#) Define the crack-tip element or crack-front element set. Valid for [XFEM-based crack-growth](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#fracxfemreferences) analysis only.
- `RADIUS` - [Command Specifications for Action= RADIUS](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#) Define the radius at which the given value is to be evaluated. Valid for XFEM-based crack-growth analysis only.
- `RSWEEP` - [Command Specifications for Action= RSWEEP](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#) Define the minimum and maximum sweep angle from existing crack direction. Valid for XFEM-based crack-growth analysis only.
- `INIT` - [Command Specifications for Action= INIT](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#) SMART crack- initiation ID.
- `CSFL` - [Command Specifications for Action= CSFL](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#) Convert initial- stress data to crack-surface traction loading.

**par1**, **par2**, **par3**, **par4**, **par5**, **par6**, **par7**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CINT.html) for further information.

## Notes

Initiate a new calculation via the `Action` = NEW parameter. Subsequent **CINT** commands (with parameters other than NEW) define the input required for the fracture-parameter calculations.

The simplest method is to define crack information via `Action` = CTNC; however, this method limits you to only one node for a given location along the crack front. Use the CTNC option only when all nodes that define the crack front lie in a single plane.

For `Action` = SURF, `Par1` and `Par2` can be the top or bottom crack-face node component. No order is required, provided that if one value the top crach-face node component, the other must be the bottom, and vice-versa. This option is valid only with [[cgrow|CGROW]] for crack-growth simulation.

To define crack information at multiple locations along the crack front, use `Action` = CENC. You can issue **CINT**,CENC, `Par1`, etc. multiple times to define the crack-extension node component, the crack tip, and the crack-extension directions at multiple locations along the crack front.

Although you can vary the sequence of your definitions, all specified crack-tip nodes must be at the crack front, and no crack-tip node can be omitted.

You can define the crack-extension direction directly by specifying either `Action` = CENC or `Action` = NORM.

The crack-assist extension direction ( `Action` = EDIR) provides a generic extension direction when `Action` = CTNC. It helps to define crack-extension directions based on the connectivity of the crack-front elements. For a 2D case when the crack tangent cannot be calculated, the program uses the provided crack-assist extension direction directly.

For an [XFEM-based crack-growth](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#fracxfemreferences) analysis:

- `Action` = CTNC, CENC, NCON, SYMM, UMM, or EDIR have no effect.
- `Action` = CXFE, RADIUS, or RSWEEP are XFEM-specific and invalid for any other type of crack- growth analysis.
- For **CINT**,TYPE, only `Par1` = PSMAX or STTMAX are valid. Other `Par1` values have no effect.

The stress-intensity factors calculation ( **CINT**,TYPE,SIFS) applies only to isotropic linear elasticity. Use only one material type for the crack-tip elements that are used for the calculations.

When calculating energy release rates ( **CINT**,TYPE,VCCT), do not restrict the results from being written to the database ( [[config|/CONFIG]],NOELDB,1) after solution processing; otherwise, incorrect and potentially random results are possible.

Fracture-parameter calculations based on domain integrations such as stress-intensity factors, J-integral, or material force are not supported when contact elements exist inside the domain. The calculations may become path-dependent unless the contact pressure is negligible.

For `Action` = UMM, the default value can be OFF or ON [depending on the element type](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracumm.html#cintondefaulttab). The **CINT** command overrides the default setting for the given element.

The **CINT** command supports only strain data for initial state ( [[inistate|INISTATE]],SET,DTYP,EPEL). Other initial-state capabilities are not supported.

For more information about using the **CINT** command, including supported element types and material behavior, see [Calculating Fracture Parameters](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracumm.html)

### Command Specifications

**Command Specification for Action= NEW**

- `Par1` - **CINT** ID number.

**Command Specifications for Action= CTNC**

- `Par1` - Crack-tip node component name (must be 32 characters or less).
- `Par2` - Crack-extension direction calculation-assist node. Any node on the open side of the crack.
- `Par3` - Crack front's end-node crack-extension direction override flag:
  - `0` - Align the extension direction with the edges attached at the two end nodes of the crack front (default).
  - `1` - Align the extension direction to be perpendicular to the crack front.

**Command Specifications for Action= SURF**

- `Par1` - Crack-surface node component 1 (top or bottom crack face). (Component name must be 32 characters or less.)
- `Par2` - Crack-surface node component 2 (top or bottom crack face, but the opposite of `Par1` ). (Component name must be 32 characters or less.)

**Command Specifications for Action= CENC**

- `Par1` - Crack-extension node component name ( [[cm|CM]] ). (Must be 32 characters or less.)
- `Par2` - Crack-tip node. The crack-tip node defaults to the first node of the crack-extension node component.
- `Par3, Par4` - Coordinate system number ( `Par3` ) and the number of the axis that is coincident with the crack direction ( `Par4` ). When these parameters are defined, `Par5`, `Par6` and `Par7` are ignored.
- `Par5, Par6, Par7` - Global x, y, and z components of the crack-extension direction vector. ( `Par3` and `Par4` must be blank.)

**Command Specifications for Action= TYPE**

- `Par1` - Type of calculation to perform:
  - `JINT` - Calculate [J-integral](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/frac_parmcalctypes.html#strjintcalcmethod) (default).
  - `SIFS` - Calculate [stress-intensity factors](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/frac_parmcalctypes.html#strcalcSIFs).
  - `TSTRESS` - Calculate [T-stress](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/frac_parmcalctypes.html#strtstrcalculating).
  - `MFOR` - Calculate [material forces](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/frac_parmcalctypes.html#strcalcmatforce).
  - `CSTAR` - Calculate [C2-integral](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/frac_parmcalctypes.html#).
  - `VCCT` - Calculate [energy-release rate](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/frac_parmcalctypes.html#strcalcERRproc) using the VCCT method.
  - `PSMAX` - Calculate circumferential stress at the location where (equation omitted) when sweeping around the crack tip at the given radius. Valid in an [XFEM- based crack-growth](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#fracxfemreferences) analysis only.
  - `STTMAX` - Calculate maximum circumferential stress when sweeping around the crack tip at the given radius. Valid in an XFEM-based crack-growth analysis only.

\* `Par2` - Auxiliary stress fields and strategy for **3D** [stress-intensity factors](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/frac_parmcalctypes.html#strcalcSIFs) ( `Par1` = SIFS) calculations:

> - `0` - The plane-strain auxiliary fields are used at the interior nodes along the crack front. The stress- intensity factors at the end nodes of the crack front are set to copy the stress- intensity factors at the adjacent nodes. (Default.)
> - `1` - The plane-stress auxiliary fields are used over the entire crack front.
> - `2` - The plane-strain auxiliary fields are used over the entire crack front.

**Command Specifications for Action= DELE**

- `Par1` - **CINT** ID (default = ALL).

**Command Specifications for Action= NCON**

- `Par1` - Number of contours to be calculated.

**Command Specifications for Action= SYMM**

- `Par1` - \* `OFF, 0, or NO` - No symmetry (default).
  - `ON, 1, or YES` - Symmetric about the crack line/plane.

**Command Specifications for Action= UMM**

- `Par1` - \* `OFF, 0, or NO` - Disable the [unstructured-mesh method (UMM)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracumm.html#fracummassump)  
  (default).

  - `ON, 1, or YES` - Enable the UMM.

**Command Specifications for Action= NORM**

- `Par1` - Coordinate system number (default = 0, global Cartesian).
- `Par2` - Axis of coordinate system (default = 2, global Cartesian Y-axis).

**Command Specifications for Action= EDIR**

- `ITYPE` - Input type for the crack-assist extension direction. Valid values are CS (coordinate system number) or COMP (component x or y extension direction).

- `Par2` - If `ITYPE` = CS, the coordinate system number.

  If `ITYPE` = COMP, the x component of the crack-assist extension direction.

- `Par3` - If `ITYPE` is CS, the axis representing the crack-assist extension direction.

  If `ITYPE` = COMP, the y component of the crack-assist extension direction.

- `Par4` - For `ITYPE` = CS, this value is not specified.

  For `ITYPE` = COMP, the z component of the crack-assist extension direction.

- `Par5` - A reference node on the crack front attached to the crack-assist extension direction. To accurately calculate and flip the crack-extension directions, the crack-assist extension direction defined at this node is rotated as the tangent along the crack front rotates. This capability is useful when the crack-extension directions vary by more than 180 degrees along the crack front.

**Command Specifications for Action= PLOT**

- `Par1` - Crack ID.

- `Par2` - 0 - Disable plotting of crack-tip coordinate system.

  1 - Enable plotting of crack-tip coordinate system (default).

  Color codes are white for the crack-extension direction, green for the crack normal, and red for the direction tangential to the crack front. To clear or delete the plots, issue [[annot|/ANNOT]].

**Command Specifications for Action= LIST**

- `CrackID` - Crack ID. Default = ALL.

- `Par2` - No value - Lists the **CINT** commands issued for the crack. `Par3` and `Par4` are ignored.

  ELEM - Lists the elements used in the fracture-parameter calculation.

- `Par3` - Node number on the crack front/tip. Default = ALL. Valid only when `Par2` =ELEM.

- `Par4` - Contour number around the crack front/tip. Default = ALL. Valid only when `Par2` =ELEM.

**Command Specifications for Action= CXFE**

- `Par1` - Crack-tip element number or crack-front component name. (Component name must be 32 characters or less.)

**Command Specifications for Action= RADIUS**

- `Par1` - Radius at which a value is evaluated (used with **CINT**,TYPE,PSMAX or **CINT**,TYPE,STTMAX only).

**Command Specifications for Action= RSWEEP**

- `Par1` - Number of intervals for the sweep.
- `Par2` - Minimum angle of the sweep.
- `Par3` - Maximum angle of the sweep

**Command Specifications for Action= INIT**

- `Par1` - [[adpci|ADPCI]] ID number. The data associated with the [[adpci|ADPCI]] ID is connected to the **CINT** data set to define [crack-initiation analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fractSMARTinit.html#SMARTcrackinitexamp) details (such as crack location and shape, initiation criteria, etc.).

**Command Specifications for Action= CSFL**

[Initial-stress](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/Hlp_G_INSTWRITVAL.html) data ( mesh-independent ) are converted to a traction load acting on the crack-surfaces (specified via **CINT**,SURF). The traction is applied as a step load for all substeps.

The initial-stress data points are specified at various spatial locations in the global Cartesian coordinate system ( [[csys|CSYS]] ). The data is required in the vicinity of the crack surfaces only. The program interpolates the initial stress at the centroid of each element face of the crack surfaces, then determines the equivalent traction at the element face based on its orientation.

For more information, see and

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CINT.html
