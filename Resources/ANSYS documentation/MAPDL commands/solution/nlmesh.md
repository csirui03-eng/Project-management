---
apdl: "NLMESH"
method: nlmesh
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.nlmesh
generated: 2026-08-22
tags: [mapdl-command]
---

# NLMESH

PyMAPDL: `mapdl.nlmesh(control='', val1='', val2='', **kwargs)`

Controls remeshing in [nonlinear adaptivity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVREZ.html).

## Parameters

**control**

The mesh-quality control to adjust:

- `NLAY` - The sculpting layer adjustment:

  `VAL1` - The number of sculpting layers, beginning with detected seed elements. Valid for 2D and 3D analysis.

  - Default: `VAL1` = 10 for 2D analysis, `VAL1` = 2 for 3D analysis.
  - For local (partial) remeshing, this option helps the remesher to detect remeshing regions from the whole deformed model.
  - Generally, a larger `VAL1` leads to larger remeshing regions and tends to unite isolated multiple regions. A larger value also tends to result in better remeshing quality (and increases mapping and solution overhead accordingly).
  - Only elements with the same element and material properties as seed elements are included into the remeshing regions.
  - `VAL1` = 0 is not valid, as the remeshing regions would contain only the detected seed elements, resulting in many small cavities within remeshing regions (especially if the specified mesh- quality metric threshold ( [[nladaptive|NLADAPTIVE]] ) is relatively large).

  `VAL2` - Same as `VAL1`, except that `VAL1` controls remeshing to remove distortion and `VAL2` controls element refinement. Default: `VAL2` = 1 for 2D analysis, `VAL2` = 2 for 3D analysis.

  Not used in a [NLAD-ETCHG analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/nladetchgexample.html).

  For more information about this control, see [Sculpting Layers Control](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnanewmesh.html#)

- `BDRA` - The boundary angle threshold in degrees. Use this adjustment to retain geometry features of the original (source) mesh. Valid for both 2D and 3D analysis.

  In a 3D analysis, this value is the dihedral angle (the angle between the normal vectors from two neighboring surface facets). In a 2D analysis, this value is the 2D patch boundary edge normal angle. If the edge angle or dihedral angle is larger than the specified threshold, the node shared by 2D edges or edges shared by 3D facets are retained during remeshing.

  Valid values: 0 \< `VAL1` \< 80.

  Default for 2D analysis: `VAL1` = 10. Default for 3D analysis: `VAL1` = 15.

  Generally, a larger `VAL1` improves the quality of the new mesh (and may even repair local tiny edges or facets of poor quality). Too large a value, however, may also smooth out some geometric features, leading to slightly different results and possibly causing convergence issues in the substeps immediately following remeshing.

  For more information about this control, see [Boundary-Angle and Edge-Angle Control](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnanewmesh.html#)

- `AEDG` - The edge angle threshold in degrees. Valid for 3D analysis only.

  Use this control to split 3D patch segments. The edge angle is the angle between adjacent surface segment edges sharing a node. If the edge angle is larger than the specified threshold (VAL1), the segment splits and the node is automatically treated as a node to be retained.

  Default: `VAL1` = 10.

  Generally, a larger `VAL1` improves the quality of the new mesh, but may result in loss of feature nodes. The effect is similar to that of boundary angles ( `Control` = BDRA).

  For more information about this control, see [Boundary-Angle and Edge-Angle Control](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnanewmesh.html#)

- `SRAT` - The global sizing ratio. Valid for 2D and 3D analysis.

  `VAL1` - The global sizing ratio for remeshing.

  - Default: `VAL1` = 1.0. The default value results in the new mesh having a size similar to that of the original mesh.
  - Generally, set the value ( `VAL1` ) to \>= 0.7. The model can be refined (\< 1.0) or coarsened (\> 1.0) up to 3x depending on the mesh-sizing gradient and number of 3D elements, and approximately 2x for 2D elements.

  `VAL2` - Same as `VAL1`, except that `VAL1` controls remeshing to remove distortion and `VAL2` controls element refinement. Default: `VAL2` = 0.75.

  Not used in a [NLAD-ETCHG analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/nladetchgexample.html).

  For more information about this control, see [Global Sizing Control](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnanewmesh.html#)

- `GRAD` - Adjusts the new mesh-sizing gradient during remeshing. Valid for 2D and 3D analysis.

  Valid values: `VAL1` = 0, 1, 2, or 3. Default: `VAL1` = 2 for 2D analysis, `VAL1` = 3 for 3D analysis.

  - `VAL1` = 0 - The mesh-sizing gradient is not retained. The new mesh is uniform and has an approximate average size on the entire remeshed domain(s), even if the original mesh has sizing gradients.
  - `VAL1` = 1 - The new mesh follows the original mesh-sizing gradient to retain the element averaged-edge length. This value tends to coarsen the mesh in the location of the distorted elements during remeshing.
  - `VAL1` = 2 - The new mesh follows the sizing gradient of the original mesh, with additional sizing compensation based on the element size change due to deformation during solution. This value tends to refine the mesh at the location of the distorted elements, where the distortion may have originated from deformation during solution.
  - `VAL1` = 3 - Similar to `VAL1` = 2, but assumes that perfect mesh quality is not required, thus avoiding over-refinement of minor distorted regions. Valid for 3D analysis only.

  For more information about this control, see.

- `QTOL` - The new mesh-acceptance tolerance ( `PLANE182`, `PLANE222`, `SOLID187`, `SOLID227`, and `SOLID285` ).

  `VAL1` - Controls remeshing to remove distortion. Default: 0.05.

  `VAL2` - Controls element refinement. Default: 0.5.

  For `PLANE182` and `PLANE222`, `VAL2` is the only valid option (for mesh refinement), and the new mesh is accepted when ( MaxCornerAngleNew - MaxCornerAngleOld ) / MaxCornerAngleOld \<= `QTOL`.

  For `SOLID285`, the new mesh is accepted when ( SkewnessNew - SkewnessOld ) / SkewnessOld \<= `QTOL`.

  For `SOLID187` and `SOLID227`, the new mesh is accepted when, in addition to skewness, ( JacobianOld - JacobianNew ) / JacobianOld \<= `QTOL`.

  The program uses both tolerance and mesh-quality parameters to determine whether or not a new mesh is accepted.

  Not used in a [NLAD-ETCHG analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/nladetchgexample.html).

- `REFA` - The refinement algorithm adjustment ( `PLANE182`, `PLANE222`, and `SOLID285` ). Valid for 2D and 3D analysis.

  `VAL1` -

  - SPLIT - Use mesh [splitting](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnanewmesh.html#) instead of general remeshing. This is the only valid value.

  If not specified, mesh refinement occurs via general remeshing (except for `PLANE183` ).

  Not used in a [NLAD-ETCHG analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/nladetchgexample.html).

- `TCOR` - Coordinate truncation adjustments for nodal locations of the meshes during remeshing. Valid for 2D and 3D analysis.

  `VAL1` -

  - ON - Truncates the decimal value after the seventh position. Default behavior for `PLANE182`, `PLANE222`, and `SOLID285` (augmented Lagrange and penalty contact formulations only).
  - OFF - No truncation occurs on the decimal value. Default behavior for `SOLID187` and `SOLID227` (all contact formulations), and `PLANE182` and `PLANE222` (Lagrange multiplier contact formulation only).

- `AGGR` - Aggressive remeshing. Creates meshes with improved shape metrics. May change some global remeshing control parameters applied by other **NLMESH** commands, and may increase remeshing time. Valid for both 2D and 3D nonlinear adaptivity analysis.

  `VAL1` -

  - ON - Enable aggressive remeshing.
  - OFF - Disable aggressive remeshing (default).

- `ELSZ` - Reduces the set of remeshable (seed) elements used for remeshing by filtering out elements based on their size, preventing over- or under-refinement in the remeshing regions. Valid only in [general remeshing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnanewmesh.html#nladsimultaneous) using an energy -, position-, or [contact](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnacriteria.html#advczmcriterion) -based refinement criterion.

  `Val1` is a user-defined lower bound of the element size, and `Val2` is a user-defined upper bound of the element size. If both are specified, seed elements selected via the specified criterion are filtered out if their size is \< `Val1` or \> `Val2`. If `Val1` is unspecified, only the size check with `Val2` occurs. If `Val2` is unspecified, only the size check with `Val1` occurs.

- `NSTR` - Reduces the set of remeshable (seed) elements used for remeshing by filtering out elements based on their (maximum) equivalent stress level, preventing over- or under-refinement in the remeshing regions based on the stress state. Valid only in [general remeshing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnanewmesh.html#nladsimultaneous) using an energy -, position-, or [contact](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnacriteria.html#advczmcriterion) -based refinement criterion.

  `Val1` is a user-defined lower bound of element equivalent stress, and `Val2` is a user-defined upper bound of the element equivalent stress. If both are specified, seed elements selected by the specified criterion are filtered out if their (maximum) equivalent stress is \< `Val1` or \> `Val2`. If `Val1` is unspecified, only the equivalent stress check with `Val2` occurs. If `Val2` is unspecified, only the equivalent stress check with `Val1` occurs.

  **Important:** Before specifying this option, copy the integration-point results to the nodes ( [[eresx|ERESX]],NO).

- `NSTN` - Reduces the set of remeshable (seed) elements used for remeshing by filtering out elements based on their (maximum) equivalent strain level, preventing over- or under-refinement in the remeshing regions based on the strain state. Valid only in [general remeshing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnanewmesh.html#nladsimultaneous) using an energy -, position-, or [contact](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnacriteria.html#advczmcriterion) -based refinement criterion.

  `Val1` is a user-defined lower bound of the element equivalent strain, and `Val2` is a user- defined upper bound of the element equivalent strain. If both are specified, seed elements selected by the specified criterion are filtered out if their (maximum) equivalent strain is \< `Val1` or \> `Val2`. If `Val1` is unspecified, only the equivalent strain check with `Val2` occurs. If `Val2` is unspecified then only the equivalent strain check with `Val1` occurs.

  **Important:** Before specifying this option, copy the integration-point results to the nodes ( [[eresx|ERESX]],NO).

- `LIST` - Lists all mesh-quality control parameters.

  If `VAL1` has been specified for a given mesh control, the most recently specified value is listed. If a value was not explicitly specified, the default value is listed (assuming that the problem has been solved at least once).

**val1**

Numerical input value that varies according to the specified `Control` option.

Valid for all `Control` options. Can be used when controlling remeshing for both distortion removal and for element refinement.

**val2**

Numerical input value that varies according to the specified `Control` option.

Valid only for these `Control` options: NLAY, SRAT, and QTOL. Also used for controlling remeshing for element refinement.

## Notes

**NLMESH** is a global control command enabling mesh-quality adjustments for remeshing in [nonlinear adaptivity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnaexample.html). The command can be used when components are associated with mesh-quality criteria ( [[nladaptive|NLADAPTIVE]] with `Criterion` = MESH, or another criterion with mesh change through general refinement).

Issue the **NLMESH** command only in cases where advanced mesh-quality control is desirable for remeshing in nonlinear adaptivity. The control values specified apply to all components having mesh- quality-based criteria defined, or components having mesh change through general refinement, and can be modified at every load step during the nonlinear adaptive solution or when performing a restart analysis.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NLMESH.html
