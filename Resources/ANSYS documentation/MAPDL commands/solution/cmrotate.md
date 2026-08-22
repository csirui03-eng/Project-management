---
apdl: "CMROTATE"
method: cmrotate
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.inertia.Inertia.cmrotate
generated: 2026-08-22
tags: [mapdl-command]
---

# CMROTATE

PyMAPDL: `mapdl.cmrotate(cm_name='', rotatx='', rotaty='', rotatz='', x1='', y1='', z1='', x2='', y2='', z2='', **kwargs)`

Specifies the rotational velocity of an element component in a brake-squeal analysis.

## Parameters

**cm_name**: The name of the element component.

**rotatx**, **rotaty**, **rotatz**

If the `X2`, `Y2`, `Z2` fields are not defined, `ROTATX`, `ROTATY`, and `ROTATZ` specify the components of the rotational angle vector in the global Cartesian X, Y, Z directions.

If the `X2`, `Y2`, `Z2` fields are defined, only `ROTATX` is required. `ROTATX` specifies the scalar rotational velocity about the rotational axis. The rotational direction of `ROTATX` is designated either positive or negative, and is determined by the "right hand rule."

**x1**, **y1**, **z1**: If the `X2`, `Y2`, `Z2` fields are defined, `X1`, `Y1`, and `Z1` define the coordinates of the beginning point of the rotational axis vector. Otherwise, `X1`, `Y1`, and `Z1` are the coordinates of a point through which the rotational axis passes.

**x2**, **y2**, **z2**: The coordinates of the end point of the rotational axis vector.

## Notes

The **CMROTATE** command specifies the rotational motion velocity components `ROTATX`, `ROTATY`, and `ROTATZ` of an element component `CM_Name` about a user-defined rotational axis. The rotational axis can be defined either as a vector passing through a single point or a vector connecting two points. **CMROTATE** can be used in static analyses ( [[antype|ANTYPE]],STATIC) and modal analyses ( [[antype|ANTYPE]],MODAL).

This command sets the constant rotational velocity on the nodes of the specified element component, despite any deformation at the nodes. This feature is primarily used for generating sliding contact at frictional contact interfaces in a [brake-squeal analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRmodanexamp.html#strlinearnonpresmodan). This type of analysis typically involves surface-to-surface contact between the brake pad and the rotating disk. The applicable contact elements, therefore, are `CONTA174` and `CONTA175`.

A [brake-squeal analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRmodanexamp.html#strlinearnonpresmodan) generally involves a linear perturbation modal analysis subsequent to a large-deformation static analysis with the Newton-Raphson option set as [[nropt|NROPT]],UNSYM. Therefore, **CMROTATE** is not applicable for multiple load step solves using the [[lssolve|LSSOLVE]] command.

The load interpolation setting ( [[kbc|KBC]] ) applies to the rotational velocity, in particular the `OMGSQRDKEY` option for quadratic interpolation.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CMROTATE.html
