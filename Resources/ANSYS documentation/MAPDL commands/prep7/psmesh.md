---
apdl: "PSMESH"
method: psmesh
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.psmesh
generated: 2026-08-22
tags: [mapdl-command]
---

# PSMESH

PyMAPDL: `mapdl.psmesh(secid='', name='', p0='', egroup='', num='', kcn='', kdir='', value='', ndplane='', pstol='', pstype='', ecomp='', ncomp='', **kwargs)`

Creates and meshes a pretension section ( `PRETS179` ) or a preload section ( `MPC184` ).

## Parameters

**secid**: Unique section number. This number must not already be assigned to a section.

**name**: Unique eight character descriptive name, if desired.

**p0**

Pretension node number (for a pretension section using `PRETS179` ) or joint element number (for a preload section using `MPC184` ).

For a pretension element, the node is defined if it doesn't exist, and the number defaults to the highest node number plus one.

For a joint element, a unique element number is assigned by default.

**egroup**, **num**

Element group on which **PSMESH** will operate. If `Egroup` = P, graphical picking is enabled and `NUM` is ignored (valid only in the GUI).

- `L (or LINE)` - **PSMESH** operates on all elements in the line specified by `NUM`. New pretension nodes are associated with `NUM` or entities below it. Any subsequent [[lclear|LCLEAR]] operation of `NUM` deletes the pretension elements and nodes created by **PSMESH**. ( `MPC184` joint elements and associated contact pairs of a preload section are not deleted by [[lclear|LCLEAR]].)
- `A (or AREA)` - **PSMESH** operates on all elements in the area specified by `NUM`. New pretension nodes are associated with `NUM` or entities below it. Any subsequent [[aclear|ACLEAR]] of `NUM` deletes the pretension elements and nodes created by **PSMESH**. ( `MPC184` joint elements and associated contact pairs of a preload section are not deleted by [[aclear|ACLEAR]].)
- `V (or VOLU)` - **PSMESH** operates on all elements in the volume specified by `NUM`. New pretension nodes are associated with `NUM` or entities below it. Any subsequent [[vclear|VCLEAR]] of `NUM` deletes the pretension elements and nodes created by **PSMESH**. ( `MPC184` joint elements and associated contact pairs of a preload section are not deleted by [[vclear|VCLEAR]].)
- `P` - **PSMESH** operates on elements selected through the subsequent picking operations, and `NUM` is ignored
- `ALL` - The command operates on all selected elements, and `NUM` is ignored.

**kcn**: Coordinate system number for the separation surface and normal direction.

**kdir**

Direction (x, y, or z) normal to separation surface in the `KCN` coordinate system.

If `KCN` is Cartesian, the pretension section normal will be parallel to the `KDIR` axis regardless of the position of the pretension node.

If `KCN` is non-Cartesian, the pretension section normal will be aligned with the `KDIR` direction of system `KCN` at the position of the pretension node.

For an `MPC184` joint element defined as part of a preload section, `KDIR` is used to define the normal of the separation surface and does not affect the axis direction of the joint element.

**value**: Point along the `KDIR` axis at which to locate the separation surface. Ignored if `NDPLANE` is supplied.

**ndplane**: Existing node that **PSMESH** will use to locate the separation surface. If `NDPLANE` is supplied, the location of the separation surface is defined by the `KDIR` coordinate of `NDPLANE`.

**pstol**

Optional tolerance below `VALUE`. Allows nodes occurring precisely at or slightly below the separation to be identified properly as above the plane. Has the effect of shifting the plane down by `PSTOL`. The following expression represents the default value:

(equation not available in the PyMAPDL source, see the Ansys help page)

(that is, ΔX = X `max` - X `min` ).

**pstype**

Type of pretension or preload section to be generated.

If a positive value is specified (or if this argument is left blank), a pretension section that includes `PRETS179` elements is generated. The value entered is the element type number for `PRETS179`. If no number is specified, the program defines the element type number.

If TORQUE is specified, a preload section that includes a [cylindrical joint element](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_MPC184cyl.html#mpc184cylinprores) ( `MPC184` ) is generated as follows:

- **For a 2D model** : An x-axis cylindrical joint element is generated along with two force- distributed surface-based constraints. A local Cartesian coordinate system is created at the first node of the joint element such that the local x- axis is the axis of that element (KEYOPT(4) = 0 for the `MPC184` element).
- **For a 3D model** : A z-axis cylindrical joint element is generated along with two force- distributed surface-based constraints. A local Cartesian coordinate system is created at the first node of the joint element such that the local z- axis is the axis of that element (KEYOPT(4) = 1 for the `MPC184` element).
- **For a 3D model that contains beam elements** : A z-axis cylindrical joint element is generated between the endpoints of two beam elements. (No force-distributed surface-based constraints are needed.) A local Cartesian coordinate system is created at the first node of the joint element such that the local z- axis is the axis of that element (KEYOPT(4) = 1 for the `MPC184` element).

If a negative value is specified, a preload section that includes a [screw joint element](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_MPC184scr.html#mpc184screwprores) ( `MPC184` ) is created with the absolute value of `PSTYPE` used as the pitch value for the joint. This option is only valid for 3D models. Two force-distributed surface-based constraints are generated at the cutting surfaces, except for the case of a beam model which does not need the force-distributed constraints. A local Cartesian coordinate system is created at the first node of the joint element such that the local z- axis is the axis of that element.

**ecomp**: If specified, the name of a component to be composed of new pretension elements and existing elements modified by the **PSMESH** command. This argument is not used with the `MPC184` joint element.

**ncomp**: Name of a component to be composed of nodes on new pretension elements. This argument is not used with the `MPC184` joint element.

## Notes

**PSMESH** generates a pretension section ( `PRETS179` ) or a preload section ( `MPC184` ) for modeling bolt fastener preloads. The type of section is specified by the `PSTYPE` argument.

The **PSMESH** command is valid for structural analyses only.

### Pretension Section ( `PRETS179` )

When `PSTYPE` is a positive value or blank, the **PSMESH** command creates a pretension section normal to the pretension load direction by cutting the mesh along existing element boundaries at the point defined by `VALUE` or `NDPLANE` and inserting `PRETS179` elements. The **PSMESH** command verifies that `PSTYPE` is a `PRETS179` element type; if it is not, the command finds the lowest available `ITYPE` ( [[et|ET]] ) that is `PRETS179`, or it creates a new one if necessary.

When it is necessary to define the pretension node, the program uses node `NDPLANE`. If the `NDPLANE` value is not specified, the program defines the pretension node at:

- The centroid of geometric entity `NUM`, if `Egroup` = LINE, AREA, or VOLU; or
- The centroid location of all selected elements, if `Egroup` = ALL or if graphical picking is used.

If the elements to which the pretension load is to be applied have already been meshed in two groups, **PSMESH** cannot be used to insert the pretension elements. The [[eintf|EINTF]] command must be used to insert the `PRETS179` elements between the two meshed groups.

The **PSMESH** operation copies any nodal temperatures you have defined on the split surface of the original mesh from the original nodes to the newly created coincident duplicate nodes. However, displacements, forces, and other boundary conditions are not copied.

By mathematical definition, the pretension surface must always be a flat plane. In a non-Cartesian coordinate system, the **PSMESH** command creates that plane at the indicated position, oriented with respect to the specified direction of the active system (in the same manner that the [[nrotat|NROTAT]] command orients a nodal system with respect to a curved system). For example, assuming X = 1 and Y = 45 in a cylindrical coordinate system with Z as the axis of rotation ( `KCN` = 1), a pretension surface normal to X tilts 45 degrees away from the global X axis.

A pretension section can be defined for fastener models made up of any 2D or 3D structural solid, beam, shell, pipe, or link element type. The elements can be low- or high-order.

The pretension section is also supported for general axisymmetric elements ( `SOLID272` and `SOLID273` ). **PSMESH** cuts the model and generates `PRETS179` elements between all Fourier nodes in the circumferential direction.

For more information, see [Defining Pretension in a Joint Fastener](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS2_9.html#)

### Preload Section ( `MPC184` )

When `PSTYPE` is a negative value or set to TORQUE, the **PSMESH** command defines an `MPC184` joint element for applying a preload to a bolt undergoing large rotation or large deformation. **PSMESH** cuts the mesh in two parts along existing element boundaries at the point defined by `VALUE` or `NDPLANE`. It generates [force-distributed surface-based constraints](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/Hlp_ctec_surfcon.html#strbeamso1703) (remote points) on the cutting surfaces, inserts an `MPC184` joint element that connects the two pilot nodes, and creates a local Cartesian coordinate system at the first node of the joint element to define the normal direction. If the joint is between beam elements, no force-distributed constraints are generated. For more information, see [Defining Preload in a Joint Fastener Undergoing Large Rotation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/bas_preload_joint.html#)

The preload section based on `MPC184` is not supported for general axisymmetric elements ( `SOLID272` and `SOLID273` ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSMESH.html
