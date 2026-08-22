---
apdl: "D"
method: d
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_constraints.FeConstraints.d
generated: 2026-08-22
tags: [mapdl-command]
---

# D

PyMAPDL: `mapdl.d(node='', lab='', value='', value2='', nend='', ninc='', lab2='', lab3='', lab4='', lab5='', lab6='', meshflag='', **kwargs)`

Defines degree-of-freedom constraints at nodes.

## Parameters

**node**: Node at which constraint is to be specified. If ALL, `NEND` and `NINC` are ignored and constraints are applied to all selected nodes ( [[nsel|NSEL]] ). If `Node` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `Node`.

**lab**

Valid degree-of-freedom label. If ALL, use all appropriate labels.

- **Structural labels** : UX, UY, or UZ (displacements); ROTX, ROTY, or ROTZ (rotations); WARP (warping).
- **Thermal labels** : TEMP, TBOT, TE2, TE3,..., TTOP (temperature).
- **Electric labels** : VOLT (voltage); EMF (electromotive force).
- **Magnetic labels** : MAG (scalar magnetic potential); AZ (vector magnetic potential).
- **Acoustic labels** : PRES (pressure); UX, UY, or UZ (displacements for FSI coupled elements); ENKE (acoustic energy density).
- **Pore fluid labels** : PRES (pore pressure); UX, UY, or UZ (displacements); TEMP (temperature).
- **Diffusion labels** : CONC (concentration).

For structural static and transient analyses, translational and rotational velocities are also valid loads. Use these labels: VELX, VELY, VELZ (translational velocities); OMGX, OMGY, OMGZ (rotational velocities).

For structural analyses, HDSP (hydrostatic pressure) is also valid. However, HDSP is not included when `Lab` = ALL.

For structural transient analyses, the following acceleration loads are also valid: ACCX, ACCY, ACCZ (translational accelerations); DMGX, DMGY, DMGZ (rotational accelerations). The velocity and acceleration loads are not included when `Lab` = ALL.

If the node is connected to an `ELBOW290` element, the following pipe cross-section degree-of- freedom labels are also valid: SE, SO, SW, SRA, and SRT. (For details, see the `ELBOW290` documentation.) The degrees of freedom are not included when `Lab` = ALL. To constrain all cross- section degrees of freedom, specify `Lab` = SECT.

The PRES degree of freedom is also available for [porous media](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/elemdatatblpor.html#pormedflowdamp) problems.

**value**

Degree-of-freedom value or table name reference for tabular boundary conditions. To specify a table, enclose the table name in percent (%) signs (for example, **D**, `Node`,TEMP,`tabname`). To define a table, issue [[dim|*DIM]].

If `Value` = SUPPORT, you can specify pseudo-constraints when [using residual vectors](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR_SMSUP.html#ans_str_moda_resresp) in a modal analysis ( [[resvec|RESVEC]],ON) or [CMS](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/advcms.html#advcmsunderstand) analysis ( [[cmsopt|CMSOPT]],RFFB).

If the enforced motion is active in the modal analysis ( [[modcont|MODCONT]],,on), `Value` is the base identification number. It should be an integer greater than or equal to 1 and less than 10000.

**value2**: Second degree-of-freedom value (if any). If the analysis type and the degree of freedom allow a complex input, `Value` (above) is the real component and `VALUE2` is the imaginary component.

**nend**, **ninc**: Specifies the same values of constraint at the range of nodes from `Node` to `NEND` (defaults to `Node` ), in steps of `NINC` (defaults to 1).

**lab2**, **lab3**, **lab4**, **lab5**, **lab6**: Additional degree-of-freedom labels. The same values are applied to the nodes for these labels.

**meshflag**

Specifies how to apply constraint on the mesh. Valid in a [nonlinear adaptivity analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVREZ.html) when `Lab` = UX / UY / UZ and `Node` is not a component name.

- 0 - Constraint applied on the current mesh (default).
- 1 - Constraint applied on the initial mesh for nonlinear adaptivity. ( `NEND` and `NINC` are not valid.)

## Notes

The available degrees of freedom per node are listed under **Degrees of Freedom** in the input table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html). Degrees of freedom are defined in the nodal coordinate system. The positive directions of structural translations and rotations are along and about the positive nodal axes directions. Structural rotations should be input in radians. The node and the degree-of-freedom label must be selected ( [[nsel|NSEL]], [[dofsel|DOFSEL]] ).

In a structural analysis, you can apply only one displacement, velocity, or acceleration load at any degree of freedom. If multiple loads are specified, the last applied load overrides the previous ones. For example, the following commands apply loads to node 100:

- D,100,UX, `Value`
- D,100,VELX, `Value`

In this case, the velocity load (VELX) applied in the last command will override the displacement load (UX).

For elements used in static and low frequency electromagnetic analysis ( `SOLID236` and `SOLID237` ), the AZ degree of freedom is not a z-component of a vector potential, but rather the flux contribution on the element edge. To specify a flux-parallel condition, set AZ = 0. For more information, see [3D Magnetostatics and Fundamentals of Edge-based Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_lof/lof3Dmagfunedgeanalxmps.html) in the [Low-Frequency Electromagnetic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_lof/Hlp_G_ELE16.html).

For `ELBOW290` cross-section degrees of freedom ( `Lab` = SE, SO, SW, SRA, SRT, or SECT), the **D** command can only specify fixed constraints. The degree-of-freedom value must be zero; no other values are valid.

For hydrostatic fluid elements ( `HSFLD241` and `HSFLD242` ), the HDSP degree-of-freedom constraint at the pressure node prescribes the pressure value for all the fluid elements sharing the pressure node.

Tabular boundary conditions ( `VALUE` = `tabname`) are available only for the following degree- of-freedom labels: Electric (VOLT), structural (UX, UY, UZ, ROTX, ROTY, ROTZ, and velocity and acceleration loads VELX, VELY, VELZ, OMGX, OMGY, OMGZ, ACCX, ACCY, ACCZ, DMGX, DMGY, DMGZ), acoustic (PRES, UX, UY, UZ, ENKE ), temperature (TEMP, TBOT, TE2, TE3,..., TTOP), diffusion (CONC). All labels are valid only in static ( [[antype|ANTYPE]],STATIC) and full transient ( [[antype|ANTYPE]],TRANS) analyses.

In a mode-superposition harmonic or transient analysis, you must apply the constraints in the modal portion of the analysis for residual vector ( [Using the Residual Vector or the Residual Response Method to Improve Accuracy](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR_SMSUP.html#ans_str_moda_resresp) [Enforced Motion Method for Mode-Superposition Transient and Harmonic Analyses](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR_SMSUP.html#)

%\_FIX% is a Mechanical APDL reserved table name. When `VALUE` is set to %\_FIX%, the program prescribes the degree of freedom to the current relative displacement value. This option is valid for the following labels: UX, UY, UZ, ROTX, ROTY, ROTZ. Alternatively, functions UX(), UY(), etc. can be used. (See [[get|*GET]] for a list of available functions.) In most cases, %\_FIX% usage is efficient and recommended for all structural degrees of freedom.

When `Value` = SUPPORT, specify only the minimum number of displacement constraints necessary to prevent rigid body motion: three constraints (or fewer, depending on the element type) for 2D models and six (or fewer) for 3D models.

If constraints and initial conditions ( [[ic|IC]] ) are applied at the same node, the constraint specification overrides. This combination is useful when a constraint degree-of-freedom value needs to start with a nonzero value at time = 0.0. For example, if the constraint degree-of-freedom value is prescribed to be a cosine function, then specifying an initial condition for the same node and degree of freedom ensures that the initial value for the constraint degree of freedom at time = 0.0 is same as the cosine function evaluated at time = 0.0. If initial conditions are not specified, the constraint degree-of-freedom value ramps from zero in the first substep of the first load step.

If more than one rotational degrees of freedom are constrained with non-zero rotations (ROTX, ROTY, ROTZ), rotational velocities (OMGX, OMGY, OMGZ), or rotational accelerations (DMGX, DMGY, DMGZ), then the rotation of the constrained node from its initial configuration to its final configuration depends on the combination and the sequence in which the constraints are applied. See Rotations in a Large-Deflection Analysis in [Structural Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_enercalc_app.html).

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_D.html
