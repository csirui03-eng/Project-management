---
apdl: "CMDOMEGA"
method: cmdomega
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.inertia.Inertia.cmdomega
generated: 2026-08-22
tags: [mapdl-command]
---

# CMDOMEGA

PyMAPDL: `mapdl.cmdomega(cm_name='', domegax='', domegay='', domegaz='', x1='', y1='', z1='', x2='', y2='', z2='', **kwargs)`

Specifies the rotational acceleration of an element component about a user-defined rotational axis.

## Parameters

**cm_name**: The name of the element component.

**domegax**, **domegay**, **domegaz**

If the `X2`, `Y2`, `Z2` fields are not defined, `DOMEGAX`, `DOMEGAY`, and `DOMEGAZ` specify the components of the rotational acceleration vector in the global Cartesian X, Y, Z directions.

If the `X2`, `Y2`, `Z2` fields are defined, only `DOMEGAX` is required. `DOMEGAX` specifies the scalar rotational acceleration about the rotational axis. The rotational direction of `DOMEGAX` is designated either positive or negative, and is determined by the "right hand rule."

**x1**, **y1**, **z1**: If the `X2`, `Y2`, `Z2` fields are defined, `X1`, `Y1`, and `Z1` define the coordinates of the beginning point of the rotational axis vector. Otherwise, `X1`, `Y1`, and `Z1` are the coordinates of a point through which the rotational axis passes.

**x2**, **y2**, **z2**: The coordinates of the end point of the rotational axis vector.

## Notes

Specifies the rotational acceleration components `DOMEGAX`, `DOMEGAY`, and `DOMEGAZ` of an element component `CM_NAME` about a user-defined rotational axis. The rotational axis can be defined either as a vector passing through a single point, or a vector connecting two points.

You can define the rotational acceleration and rotational axis with the **CMDOMEGA** command for these analyses:

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

Rotational velocities are combined with the element mass matrices to form a body force load vector term. Units are radians/time <sup>2</sup>.

The **CMDOMEGA** command supports tabular boundary conditions (`TABNAME_X`, `TABNAME_Y`, and `TABNAME_Z`) for `DOMEGAX`, `DOMEGAY`, and `DOMEGAZ` input values ( [[dim|*DIM]] ) for full transient and harmonic analyses. In this case, if the end point is specified ( `X2`, `Y2`, `Z2` ), the rotational velocity axis must be along the global X-, Y-, or Z-axis.

Related commands are [[acel|ACEL]], [[cgloc|CGLOC]], [[cgloc|CGLOC]], [[omega|OMEGA]], [[cmomega|CMOMEGA]], [[dcgomg|DCGOMG]], [[domega|DOMEGA]].

See [Analysis Tools](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/str_EnMoinStAn.html)

You can use the **CMDOMEGA** command in conjunction with any one of the following two groups of commands, but not with both groups simultaneously:

- GROUP ONE: [[omega|OMEGA]], [[domega|DOMEGA]].
- GROUP TWO: [[cgomga|CGOMGA]], [[dcgomg|DCGOMG]], [[cgloc|CGLOC]].

Components for which you want to specify rotational loading must consist of elements only. The elements you use cannot be part of more than one component, and elements that share nodes cannot exist in different element components. You cannot apply the loading to an assembly of element components.

See [Acceleration Effect](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool1.html#)

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CMDOMEGA.html
