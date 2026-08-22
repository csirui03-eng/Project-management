---
apdl: "ADPCI"
method: adpci
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.special_purpose.SpecialPurpose.adpci
generated: 2026-08-22
tags: [mapdl-command]
---

# ADPCI

PyMAPDL: `mapdl.adpci(action='', par1='', par2='', par3='', par4='', par5='', par6='', par7='', par8='', **kwargs)`

Defines parameters associated with adaptive crack initiation.

## Parameters

**action**

Specifies action for defining or manipulating initial crack data:

- `DEFINE` - [Command Specification for Action= DEFINE](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_ADPCI.html#) Initiate a new adaptive-crack calculation and assign an ID.
- `GEOM` - [Command Specifications for Action= GEOM](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_ADPCI.html#) Define the geometry data for initializing a crack.
- `DELE` - [Command Specifications for Action= DELE](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_ADPCI.html#) Delete the **ADPCI** data set associated with the specified ID.
- `LIST` - [Command Specifications for Action= LIST](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_ADPCI.html#) List the **ADPCI** data set associated with the specified ID.

**par1**, **par2**, **par3**, **par4**, **par5**, **par6**, **par7**, **par8**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ADPCI.html) for further information.

## Notes

For **ADPCI**,GEOM,LCS, the ellipse center locates at the origin of the local coordinate system. The local coordinate system Y axis defines the plane normal of the ellipse, and X and Z axes define two orientations of the ellipse. (The LCS argument is equivalent to combining the CENTER and AXES arguments. Separate **ADPCI**,GEOM commands to specify those arguments are therefore not issued.)

For more information about using **ADPCI** in a crack-initiation analysis, see [SMART Method for Crack-Initiation Simulation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fractSMARTinit.html#SMARTcrackinitexamp)

### Command Specifications

**Command Specification for Action= DEFINE**

- `Par1` - **ADPCI** ID number.
- `Par2` - Surface-node component name for defining the crack-initiation zone (must be 32 characters or less).
- `Par3` - Material ID for defining the crack-initiation criterion.
- `Par4` - Shape of the initialized crack:
  - ELLIPSE - Elliptical crack shape (default, and the only valid value).

**Command Specifications for Action= GEOM**

- `Par1` - **ADPCI** ID number.
- `Par2` - Crack geometry characteristic to define:
  - CENTER - Specify the ellipse center location.
  - AXES - Specify the directions of the two ellipse axes.
  - ALEN - Specify the lengths of two ellipse axes. This value is required when AXES or LCS is specified.
  - LCS - Local coordinate system number for defining the ellipse center location and axes directions. See [[adpci#Notes|ADPCI]] below.
- `Par3` - The first value to assign to the geometry characteristic specified via `Par2` :
  - If `Par2` = CENTER, the X coordinate of the ellipse center.
  - If `Par2` = AXES, the X component of the first ellipse axis direction.
  - If `Par2` = ALEN, the length of the first ellipse axis.
  - If `Par2` = LCS, the local coordinate system number.
- `Par4` - The second value to assign to the geometry characteristic specified via `Par2` :
  - If `Par2` = CENTER, the Y coordinate of the ellipse center.
  - If `Par2` = AXES, the Y component of the first ellipse axis direction.
  - If `Par2` = ALEN, the length of the second ellipse axis.
- `Par5` - The third value to assign to the geometry characteristic specified via `Par2` :
  - If `Par2` = CENTER, the Z coordinate of the ellipse center.
  - If `Par2` = AXES, the Z component of the first ellipse axis direction.
- `Par6` - The fourth value to assign to the geometry characteristic specified via `Par2` :
  - If `Par2` = AXES, the X component of the second ellipse axis direction.
- `Par7` - The fifth value to assign to the geometry characteristic specified via `Par2` :
  - If `Par2` = AXES, the Y component of the second ellipse axis direction.
- `Par8` - The sixth value to assign to the geometry characteristic specified via `Par2` :
  - If `Par2` = AXES, the Z component of the second ellipse axis direction.

**Command Specifications for Action= DELE**

- `Par1` - **ADPCI** ID (default = ALL).

**Command Specifications for Action= LIST**

- `Par1` - **ADPCI** ID number (default = ALL).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ADPCI.html
