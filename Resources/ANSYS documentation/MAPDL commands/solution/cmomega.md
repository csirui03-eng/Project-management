---
apdl: "CMOMEGA"
method: cmomega
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.inertia.Inertia.cmomega
generated: 2026-08-22
tags: [mapdl-command]
---

# CMOMEGA

PyMAPDL: `mapdl.cmomega(cm_name='', omegax='', omegay='', omegaz='', x1='', y1='', z1='', x2='', y2='', z2='', **kwargs)`

Specifies the rotational velocity of an element component about a user-defined rotational axis.

## Parameters

**cm_name**: The name of the element component.

**omegax**, **omegay**, **omegaz**

If the `X2`, `Y2`, `Z2` fields are not defined, `OMEGAX`, `OMEGAY`, and `OMEGAZ` specify the components of the rotational velocity vector in the global Cartesian X, Y, Z directions.

If the `X2`, `Y2`, `Z2` fields are defined, only `OMEGAX` is required. `OMEGAX` specifies the scalar rotational velocity about the rotational axis. The rotational direction of `OMEGAX` is designated either positive or negative, and is determined by the "right hand rule."

**x1**, **y1**, **z1**: If the `X2`, `Y2`, `Z2` fields are defined, `X1`, `Y1`, and `Z1` define the coordinates of the beginning point of the rotational axis vector. Otherwise, `X1`, `Y1`, and `Z1` are the coordinates of a point through which the rotational axis passes.

**x2**, **y2**, **z2**: The coordinates of the end point of the rotational axis vector.

## Notes

Specifies the rotational velocity components `OMEGAX`, `OMEGAY`, and `OMEGAZ` of an element component `CM_NAME` about a user-defined rotational axis. The rotational axis can be defined either as a vector passing through a single point or a vector connecting two points.

You can define the rotational velocity and rotational axis for these analysis types:

- Static ( [[antype|ANTYPE]],STATIC)
- Harmonic ( [[antype|ANTYPE]],HARMIC) - full, [VT](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_harmsweep.html#) \[ \], [Krylov](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_Krysweep.html#str_Krylov_macros) \[ \], or mode-superposition
- Transient ( [[antype|ANTYPE]],TRANS) - [full](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR5_4.html#strnote11tlm71999) or mode-superposition
- Substructuring ( [[antype|ANTYPE]],SUBSTR)
- Modal ( [[antype|ANTYPE]],MODAL)

> 

Loads for VT and Krylov methods are supported as long as they are not:

- complex tabulated loads (constant or trapezoidal loads in tabulated form are supported)
- used in conjunction with Rotordynamics ( [[coriolis|CORIOLIS]],on).

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via the [[lvscale|LVSCALE]] command.

Rotational velocities are combined with the element mass matrices to form a body-force load vector term. Units are radians/time. Related commands are [[acel|ACEL]], [[cgloc|CGLOC]], [[cgloc|CGLOC]], [[cgomga|CGOMGA]], [[cmdomega|CMDOMEGA]], [[dcgomg|DCGOMG]], [[domega|DOMEGA]].

See [Analysis Tools](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/str_EnMoinStAn.html)

You can use the **CMOMEGA** command in conjunction with either one of the following two groups of commands, but not with both groups simultaneously:

- GROUP ONE: [[omega|OMEGA]], [[domega|DOMEGA]].
- GROUP TWO: [[cgomga|CGOMGA]], [[dcgomg|DCGOMG]], [[cgloc|CGLOC]].

Components for which you want to specify rotational loading must consist of elements only. The elements you use cannot be part of more than one component, and elements that share nodes cannot exist in different element components. You cannot apply the loading to an assembly of element components.

If you have applied the Coriolis effect ( [[coriolis|CORIOLIS]] ) using a [stationary](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_rot/Hlp_G_ROTGENDYNEQ.html#rotintrogendyneq2) reference frame, the **CMOMEGA** command takes the gyroscopic damping matrix into account for the elements listed under "Stationary Reference Frame" in the notes section of the [[coriolis|CORIOLIS]] command. Mechanical APDL verifies that the rotation vector axis is parallel to the axis of the element; if not, the gyroscopic effect is not applied. If you issue a **CMOMEGA** command when the Coriolis or gyroscopic effect is present, a subsequently issued [[omega|OMEGA]] command has no effect.

The **CMOMEGA** command supports tabular boundary conditions (`TABNAME_X`, `TABNAME_Y`, and `TABNAME_Z`) for `OMEGAX`, `OMEGAY`, and `OMEGAZ` input values ( [[dim|*DIM]] ) for modal, full transient, and full harmonic analyses. In this case, if the end point is specified ( `X2`, `Y2`, `Z2` ), the rotational velocity axis must be along the global X-, Y-, or Z-axis.

The load interpolation setting ( [[kbc|KBC]] ) applies to the rotational velocity, in particular the `OMGSQRDKEY` option for quadratic interpolation.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CMOMEGA.html
