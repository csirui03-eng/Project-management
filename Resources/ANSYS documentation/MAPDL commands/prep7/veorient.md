---
apdl: "VEORIENT"
method: veorient
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.veorient
generated: 2026-08-22
tags: [mapdl-command]
---

# VEORIENT

PyMAPDL: `mapdl.veorient(vnum='', option='', value1='', value2='', **kwargs)`

Specifies brick element orientation for volume mapped (hexahedron) meshing.

**Command default:** Elements are not oriented in any specific manner.

## Parameters

**vnum**: Number identifying volume for which elements are to be oriented (no default).

**option**

Option for defining element orientation:

- `KP` - Orientation is determined by two keypoints on the volume. Input the keypoint numbers (KZ1 and KZ2) in fields `VALUE1` and `VALUE2`, respectively. The element z-axis points from KZ1 toward KZ2. Element x and y directions point away from KZ1 along edges of the volume to make a right-hand triad. (The element x- and y-axes are uniquely determined by this specification.)
- `LINE` - Orientation is determined by one of the lines defining the volume. Input the line number in field `VALUE1`. The element z direction follows the direction of the line. Input a negative value if the desired z direction is opposite to the direction of the specified line. (The element x- and y-axes are uniquely determined by this specification.) ( `VALUE2` is not used.)
- `AREA` - Orientation is determined by one of the areas defining the volume. The area represents the desired element top surface. Input the area number as `VALUE1`. The shortest line in the volume connected to the area will be used to specify the element z direction. (If more than one shortest line exists, the lowest numbered of those is used.) Element x and y directions are not uniquely specified by this option. ( `VALUE2` is not used.)
- `THIN` - Align the element z normal to the thinnest dimension of the volume. The shortest line in the volume is used to specify the element z direction. (If more than one shortest line exists, the lowest numbered of those is used.) Element x and y directions are not uniquely specified by this option. ( `VALUE1` and `VALUE2` are not used.)
- `DELE` - Delete the previously defined volume orientation for the specified volume ( `VNUM` ). ( `VALUE1` and `VALUE2` are not used.)

**value1**, **value2**: Parameters required for the element z-axis direction specification. The meaning of `VALUE1` and `VALUE2` will depend on the chosen `Option`. See the description of `Option` above for details.

## Notes

Use **VEORIENT** before the [[vmesh|VMESH]] command to specify the desired orientation of brick elements in a mapped mesh. **VEORIENT** has no effect on tetrahedron meshes, extruded meshes ( [[vrotat|VROTAT]], [[vdrag|VDRAG]], [[vext|VEXT]], etc.), or swept meshes ( [[vsweep|VSWEEP]] ).

Proper brick orientation is essential for certain element types such as `SOLID185` Layered Solid, `SOLID186` Layered Solid, and `SOLSH190`. In such cases, use **VEORIENT** or [[eorient|EORIENT]] to achieve the desired orientation. For other brick element types, you may need to specify element orientation to control orthotropic material property directions without concern for the element connectivity. For those cases, the [[esys|ESYS]] command is the preferred method of specifying the material property directions.

For `Option` = LINE, AREA, and THIN, the orientation will be internally converted to an equivalent `Option` = KP specification (KP,KZ1,KZ2). Use the [[vlist|VLIST]] command to view the element orientations (in terms of KZ1 and KZ2) associated with each volume.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VEORIENT.html
