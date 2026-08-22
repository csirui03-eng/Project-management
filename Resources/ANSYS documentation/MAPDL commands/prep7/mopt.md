---
apdl: "MOPT"
method: mopt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.mopt
generated: 2026-08-22
tags: [mapdl-command]
---

# MOPT

PyMAPDL: `mapdl.mopt(lab='', value='', **kwargs)`

Specifies meshing options.

## Parameters

**lab**

Meshing option to be specified (determines the meaning of `Value` ):

- `AORDER` - Mesh by ascending area size order. Set `Value` to ON to mesh smaller areas first. Using this results in finer meshes in critical areas for volume meshes; this can be used for cases where [[smrtsize|SMRTSIZE]] does not mesh as needed. Default is OFF.

- `EXPND` - Area mesh expansion (or contraction) option. (This option is the same as [[smrtsize|SMRTSIZE]],,,EXPND.) This option is used to size internal elements in an area based on the size of the elements on the area's boundaries.

  `Value` is the expansion (or contraction) factor. For example, issuing **MOPT**,EXPND,2 before meshing an area will allow a mesh with elements that are approximately twice as large in the interior of an area as they are on the boundary. If `Value` is less than 1, a mesh with smaller elements on the interior of the area will be allowed. `Value` for this option should be greater than 0.5 but less than 4.

  `Value` defaults to 1, which does not allow expansion or contraction of internal element sizes (except when using [[aesize|AESIZE]] sizing). If `Value` = 0, the default value of 1 will be used. The actual size of the internal elements will also depend on the TRANS option (or upon [[aesize|AESIZE]] or [[esize|ESIZE]] sizing, if used).

- `TETEXPND` - Tet-mesh expansion (or contraction) option. This option is used to size internal elements in a volume based on the size of the elements on the volume's boundaries.

  `Value` is the expansion (or contraction) factor. For example, issuing **MOPT**,TETEXPND,2 before meshing a volume will allow a mesh with elements that are approximately twice as large in the interior of the volume as they are on the boundary. If `Value` is less than 1, a mesh with smaller elements on the interior of the volume will be allowed. `Value` for this option should be greater than 0.1 but less than 3.

  `Value` defaults to 1, which does not allow expansion or contraction of internal element sizes. If `Value` = 0, the default value of 1 will be used. If `Value` is greater than 2, mesher robustness may be affected.

  The TETEXPND option is supported for both the [[vmesh|VMESH]] and [[fvmesh|FVMESH]] commands. Tet-mesh expansion is the only mesh control supported by [[fvmesh|FVMESH]].

- `TRANS` - Mesh-transition option. Controls how rapidly elements are permitted to change in size from the boundary to the interior of an area. (This option performs the same operation as [[smrtsize|SMRTSIZE]],,,,TRANS.)

  `Value` is the transitioning factor. `Value` defaults to 2.0, which permits elements to approximately double in size as they approach the interior of the area. (If `Value` = 0, the default value of 2 will be used.) `Value` must be greater than 1 and, for best results, should be less than 4. The actual size of the internal elements will also depend on the EXPND option (or upon [[aesize|AESIZE]] or [[esize|ESIZE]] sizing, if used).

  For a quad mesh with any element size, this option has no effect, as the program strictly respects any face size to ensure the most uniform quad mesh possible. To obtain a graded mesh using this option, apply [[lesize|LESIZE]] to the lines of the desired face.

- `AMESH` - Triangle surface-meshing option. Valid inputs for `Value` are:

  - `DEFAULT` - Allows the program to choose which triangle mesher to use. In most cases, the program chooses the main triangle mesher, which is the Riemann space mesher. If the chosen mesher fails for any reason, the program invokes the alternate mesher and retries the meshing operation.
  - `MAIN` - The program uses the main triangle mesher (Riemann space mesher), and it does not invoke an alternate mesher if the main mesher fails. The Riemann space mesher is well suited for most surfaces.
  - `ALTERNATE` - The program uses the first alternate triangle mesher (3D tri-mesher), and it does not invoke another mesher if this mesher fails. This option is not recommended due to speed considerations. However, for surfaces with degeneracies in parametric space, this mesher often provides the best results.
  - `ALT2` - The program uses the second alternate triangle mesher (2D parametric space mesher), and it does not invoke another mesher if this mesher fails. This option is not recommended for use on surfaces with degeneracies (spheres, cones, etc.) or poorly parameterized surfaces because poor meshes may result.

- `QMESH` - Quadrilateral surface meshing option. (Quadrilateral surface meshes will differ based on which triangle surface mesher is selected. This is true because all free quadrilateral meshing algorithms use a triangle mesh as a starting point.) Valid inputs for `Value` are:

  - `DEFAULT` - Let the program choose which quadrilateral mesher to use. In most cases, the program will choose the main quadrilateral mesher, which is the Q-Morph (quad-morphing) mesher. For very coarse meshes, the program may choose the alternate quadrilateral mesher instead. In most cases, the Q-Morph mesher results in higher quality elements. If either mesher fails for any reason, the program invokes the other mesher and retries the meshing operation. (Default.)
  - `MAIN` - The program uses the main quadrilateral mesher (Q-Morph mesher), and it does not invoke the alternate mesher if the main mesher fails.
  - `ALTERNATE` - The program uses the alternate quadrilateral mesher, and it does not invoke the Q-Morph mesher if the alternate mesher fails. To use the alternate quadrilateral mesher, you must also select **MOPT**,AMESH,ALTERNATE or **MOPT**,AMESH,ALT2.

- `VMESH` - Tetrahedral element meshing option. Valid inputs for `Value` are:

  - `DEFAULT` - Let the program choose which tetrahedra mesher to use.
  - `MAIN` - Use the main tetrahedra mesher (Delaunay technique mesher). (GHS3D meshing technology by P. L. George, INRIA, France.) For most models, this mesher is significantly faster than the alternate mesher.
  - `ALTERNATE` - Use the alternate tetrahedra mesher (advancing front mesher). This mesher does not support the generation of a tetrahedral volume mesh from facets ( [[fvmesh|FVMESH]] ). If this mesher is selected and you issue the [[fvmesh|FVMESH]] command, the program uses the main tetrahedra mesher to create the mesh from facets and issues a warning message to notify you.

- `SPLIT` - Quad splitting option for non-mapped meshing. If `Value` = 1, ON, or ERR, quadrilateral elements in violation of shape error limits are split into triangles (default). If `Value` = 2 or WARN, quadrilateral elements in violation of either shape error or warning limits are split into triangles. If `Value` = OFF, splitting does not occur, regardless of element quality.

- `LSMO` - Line smoothing option. `Value` can be ON or OFF. If `Value` = ON, smoothing of nodes on area boundaries is performed during smoothing step of meshing. During smoothing, node locations are adjusted to achieve a better mesh. If `Value` = OFF (default), no smoothing takes place at area boundaries.

- `CLEAR` - This option affects the element and node numbering after clearing a mesh. If `Value` = ON (default), the starting node and element numbers will be the lowest available number after the nodes and elements are cleared. If `Value` = OFF, the starting node and element numbers are not reset after the clear operation.

- `PYRA` - Transitional pyramid elements option. `Value` can be ON or OFF. If `Value` = ON (default), the program automatically creates transitional pyramid elements, when possible. Pyramids may be created at the interface of tetrahedral and hexahedral elements, or directly from quadrilateral elements. For pyramids to be created, you must also issue the command [[mshape|MSHAPE]],1,3D (degenerate 3D elements). If `Value` = OFF, the program does not create transitional pyramid elements.

- `TIMP` - Identifies the level of tetrahedra improvement to be performed when the next free volume meshing operation is initiated ( [[vmesh|VMESH]], [[fvmesh|FVMESH]] ). (For levels 2-5, improvement occurs primarily through the use of face swapping and node smoothing techniques.) Valid inputs for `Value` are:

  - `0` - Turn off tetrahedra improvement. Although this value can lead to faster tetrahedral mesh creation, it is not recommended because it often leads to poorly shaped elements and mesh failures.
  - `1` - Do the minimal amount of tetrahedra improvement. (Default.) This option is supported by the main tetrahedra mesher only ( **MOPT**,VMESH,MAIN). If the alternate tetrahedra mesher ( **MOPT**,VMESH,ALTERNATE) is invoked with this setting, the program automatically performs tetrahedra improvement at level 3 instead ( **MOPT**,TIMP,3).
  - `2` - Perform the least amount of swapping/smoothing. No improvement occurs if all tetrahedral elements are within acceptable limits.
  - `3` - Perform an intermediate amount of swapping/smoothing. Some improvement is always done.
  - `4` - Perform the greatest amount of swapping/smoothing. Meshing takes longer with this level of improvement, but usually results in a better mesh.
  - `5` - Perform the greatest amount of swapping/smoothing, plus additional improvement techniques. This level of improvement usually produces results that are similar to those at level 4, except for very poor meshes.
  - `6` - For linear tetrahedral meshes, this value provides the same level of improvement as **MOPT**,TIMP,5. For quadratic tetrahedral meshes, this value provides an additional pass of cleanup. This value is supported for both the main ( **MOPT**,VMESH,MAIN) and alternate ( **MOPT**,VMESH,ALTERNATE) tetrahedra meshers.

- `STAT` - Display status of **MOPT** settings. `Value` is ignored.

- `DEFA` - Set all **MOPT** options to default values. `Value` is ignored.

**value**: Value, as described for each different `Lab` above.

## Notes

See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for more information on the **MOPT** command and its options.

This command is also valid for [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MOPT.html
