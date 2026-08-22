---
apdl: "BF"
method: bf
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_body_loads.FeBodyLoads.bf
generated: 2026-08-22
tags: [mapdl-command]
---

# BF

PyMAPDL: `mapdl.bf(node='', lab='', val1='', val2='', val3='', val4='', val5='', val6='', meshflag='', **kwargs)`

Defines a nodal body-force load.

## Parameters

**node**: Node to which body load applies. If `Node` = ALL, apply to all selected nodes ( [[nsel|NSEL]] ). A component name may also be substituted for `Node`.

**lab**

Valid body load label. Load labels are listed under Body Loads in the input table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html).

(table not available in the PyMAPDL source, see the Ansys help page)

**val1**, **val2**, **val3**, **val4**, **val5**, **val6**

Value associated with the `Lab` item or table name reference for tabular boundary conditions. Use only `VAL1` for TEMP, FLUE, HGEN, DGEN, MVDI, CHRGD, PORT, and SPRE.

Tabular input is supported for certain labels (see [[bf#Notes|Notes for details). To specify a table, enclose the table name in percent signs (%) (e.g.,]] **BF**, `Node`,TEMP,`tabname`). Use the [[dim|*DIM]] command to define a table.

If `Lab` = MASS for acoustics:

- `VAL1` - Mass source with units of kg/(m <sup>3</sup> *s) in a harmonic analysis or in a transient analysis solved with the velocity potential formulation; or mass source rate with units of kg/(m :sup:\`3\`*s <sup>2</sup> ) in a transient analysis solved with the pressure formulation; or power source with units of watts in an energy diffusion solution for room acoustics
- `VAL2` - Phase angle in degrees
- `VAL3` - Not used
- `VAL4` - Not used
- `VAL5` - Not used
- `VAL6` - Not used

If `Lab` = VELO for acoustics (velocity components in a harmonic analysis or in a transient analysis solved with the velocity potential formulation; or acceleration components in a transient analysis solved with the pressure formulation):

- `VAL1` - X component
- `VAL2` - Y component
- `VAL3` - Z component
- `VAL4` - X-component phase angle in degrees
- `VAL5` - Y-component phase angle in degrees
- `VAL6` - Z-component phase angle in degrees

If `Lab` = VELO for electromagnetics (velocity and angular velocity components in the global Cartesian coordinate system):

- `VAL1` - Velocity component in the X direction
- `VAL2` - Velocity component in the Y direction
- `VAL3` - Velocity component in the Z direction
- `VAL4` - Angular velocity about the X axis (rad/sec)
- `VAL5` - Angular velocity about the Y axis (rad/sec)
- `VAL6` - Angular velocity about the Z axis (rad/sec)

If `Lab` = VELO for thermal (velocity components in the global Cartesian coordinate system):

- `VAL1` - Mass transport velocity component in X direction
- `VAL2` - Mass transport velocity component in Y direction
- `VAL3` - Mass transport velocity component in Z direction
- `VAL4` - Not used
- `VAL5` - Not used
- `VAL6` - Not used

If `Lab` = VELO for diffusion (transport velocity):

- `VAL1` - Transport velocity component in X direction
- `VAL2` - Transport velocity component in Y direction
- `VAL3` - Transport velocity component in Z direction
- `VAL4` - Not used
- `VAL5` - Not used
- `VAL6` - Not used

If `Lab` = IMPD:

- `VAL1` - Resistance in N⋅s/m <sup>3</sup>
- `VAL2` - Reactance in N⋅s/m <sup>3</sup>
- `VAL3` - Not used
- `VAL4` - Not used
- `VAL5` - Not used
- `VAL6` - Not used

If `Lab` = FPBC:

- `VAL1` - Phase shift (product of phase constant and period in unit radian); or Floquet boundary flag (set `VAL1` = YES) for a modal analysis that solves the eigenvalues with a specified frequency ( `FREQMOD` on the [[modopt|MODOPT]] command)
- `VAL2` - Attenuation (product of attenuation constant and period); not used if `VAL1` = YES
- `VAL3` - Not used
- `VAL4` - Not used
- `VAL5` - Not used
- `VAL6` - Not used

If `Lab` = VMEN:

- `VAL1` - Mean flow velocity component in the X direction
- `VAL2` - Mean flow velocity component in the Y direction
- `VAL3` - Mean flow velocity component in the Z direction
- `VAL4` - Not used
- `VAL5` - Not used
- `VAL6` - Not used

If `Lab` = UFOR:

- `VAL1` - Real part of complex force potential
- `VAL2` - Imaginary part of complex force potential
- `VAL3` - Not used
- `VAL4` - Not used
- `VAL5` - Not used
- `VAL6` - Not used

If `Lab` = SFOR:

- `VAL1` - X component of shear force for viscous-thermal acoustics or poroelastic acoustics
- `VAL2` - Y component of shear force for viscous-thermal acoustics or poroelastic acoustics
- `VAL3` - Z component of shear force for viscous-thermal acoustics or poroelastic acoustics
- `VAL4` - X-component phase angle in degrees
- `VAL5` - Y-component phase angle in degrees
- `VAL6` - Z-component phase angle in degrees

If `Lab` = HFLW:

- `VAL1` - Real part of volumetric heat source for viscous-thermal acoustics
- `VAL2` - Imaginary part of volumetric heat source for viscous-thermal acoustics
- `VAL3` - Not used
- `VAL4` - Not used
- `VAL5` - Not used
- `VAL6` - Not used

**meshflag**

Specifies how to apply nodal body-force loading on the mesh. Valid in a [nonlinear adaptivity analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVREZ.html) when `Lab` = HGEN or TEMP, and `Node` is not a component name.

- 0 - Nodal body-force loading occurs on the current mesh (default).
- 1 - Nodal body-force loading occurs on the initial mesh for nonlinear adaptivity.

## Notes

Defines a nodal body-force load (such as temperature in a structural analysis, heat generation rate in a thermal analysis, etc.). Nodal body loads default to the [[bfunif|BFUNIF]] values, if they were previously specified.

Table names are valid for `Lab` value ( `VALn` ) inputs in these cases only:

- `VAL1` = `tabname` for:

temperatures (TEMP), diffusing substance generation rates (DGEN), and heat generation rates (HGEN).

- `VAL1` = `tabname1` and `VAL2` = `tabname2` for:

mass source, mass source rate, or power source (MASS); the Floquet periodic boundary condition  
(FPBC); the force potential (UFOR); and the volumetric heat source (HFLW).

- `VAL1` = `tabname1`, `VAL2` = `tabname2`, and `VAL3` = `tabname3` for:

mean flow velocities (VMEN).

- `VAL1` = `tabname1`, `VAL2` = `tabname2`, `VAL3` = `tabname3`, `VAL4` = `tabname4`, `VAL5` = `tabname5`, and `VAL6` = `tabname6` for:

velocities or accelerations (VELO); and shear force (SFOR).

The heat generation rate loads specified with the **BF** command are multiplied by the weighted nodal volume of each element adjacent to that node. This yields the total heat generation at that node.

In a modal analysis, the Floquet periodic boundary condition (FPBC) is only valid for the acoustic elements `FLUID30`, `FLUID220`, and `FLUID221`.

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via the [[lvscale|LVSCALE]] command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BF.html
