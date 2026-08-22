---
apdl: "NLADAPTIVE"
method: nladaptive
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.nladaptive
generated: 2026-08-22
tags: [mapdl-command]
---

# NLADAPTIVE

PyMAPDL: `mapdl.nladaptive(component='', action='', criterion='', option='', val1='', val2='', val3='', val4='', **kwargs)`

Defines the criteria under which the mesh is refined or modified during a nonlinear solution.

## Parameters

**component**

Specifies the element component upon which this command should act:

- `ALL` - All selected components, or all selected elements if no component is selected (default).
- `Name` - Component name.

**action**

Action to perform on the selected component(s):

- `ADD` - Add a criterion to the database.

- `LIST` - List the criteria defined for the specified component(s).

- `OCTREE` - Enable adaptive mesh coarsening for additive manufacturing process simulation using the AM octree method.

- `DELETE` - Delete the criteria defined for the specified component(s).

- `ON` - Enable the defined criteria for the specified component(s) and specify how frequently and when to check them (via ON, `VAL1`, `VAL2`, `VAL3` ):

  `VAL1` - Checking frequency. If \> 0, check criteria at every `VAL1` substeps. If \< 0, check criteria at each of the `VAL1` points (approximately equally spaced) between `VAL2` and `VAL3`. (Default = -1.)

  `VAL2` - Checking start time, where `VAL2` \< `VAL3`. (Default = Start time of load step.)

  `VAL3` - Checking end time, where `VAL3` \> `VAL2`. (Default = End time of load step.)

  `VAL4` - `SOLID187` element type ID (defined prior to issuing this command). Valid only for `SOLID185` or `SOLID186` components in a [NLAD-ETCHG analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/nladetchgexample.html).

- `OFF` - Disable the defined criteria for the specified component(s).

**criterion**

Type of criterion to apply to the selected component(s):

- `CONTACT` - Contact-based. Valid only for `Action` = ADD, `Action` = LIST, or `Action` = DELETE.
- `ENERGY` - Energy-based. Valid only for `Action` = ADD, `Action` = LIST, or `Action` = DELETE.
- `BOX` - A position-based criterion, defined by a box. Valid only for `Action` = ADD, `Action` = LIST, or `Action` = DELETE.
- `MESH` - A mesh-quality-based criterion. Valid only for `Action` = ADD, `Action` = LIST, or `Action` = DELETE.
- `ALL` - All criteria and options. Valid only for `Action` = LIST or `Action` = DELETE. `Option` and all subsequent arguments are ignored.

**option**

Criterion option to apply to the selected component(s):

- `NUMELEM` - For target elements only, defines the minimum number of contact elements to contact with each target element. If this criterion is not satisfied, the program refines the contact elements and the associated solid elements. For this option, `VAL1` must be a positive integer.

  Valid only for `Criterion` = CONTACT and `Action` = ADD, LIST, or DELETE.

- `MEAN` - Checks the strain energy of any element that is part of the defined component for the condition E<sub>e</sub> ≥ c<sub>1</sub> \* E<sub>total</sub> / `NUME` (where c<sub>1</sub> = `VAL1`, E<sub>total</sub> is the total strain energy of the component, and `NUME` is the number of elements of the component). If this criterion is satisfied at an element, the program refines the element. `VAL1` must be non-negative. Default = 1.

  Valid only for `Criterion` = ENERGY and `Action` = ADD, LIST, or DELETE.

- `XYZRANGE` - Defines the location box in which all elements within are to be split or refined. Up to six values following the `Option` argument (representing the x1, x2, y1, y2, z1, and z2 coordinates) are allowed. An unspecified coordinate is not checked.

  Valid only for `Criterion` = BOX and `Action` = ADD, LIST, or DELETE.

- `LAYER` - Sets layer options for AM octree adaptive meshing for additive simulations.

  - `VAL1` - Number of layers to keep at fine mesh resolution between the current, top layer and the layers to be remeshed. Default = 2.
  - `VAL2` - Number of buffer elements to keep at fine mesh resolution between the part edges and the remeshed elements. Default = 2.

  Valid only for `Action` = OCTREE.

- `SKEWNESS` - Mesh-quality-control threshold for elements `SOLID187`, `SOLID285`, and `SOLID227` :

  - `VAL1` - Defines skewness. Valid values: 0.0 through 1.0. Default = 0.9.
  - `VAL2` - Maximum Jacobian ratio at element integration points ( `SOLID187` and `SOLID227` only). Valid values: 0.0 to 1.0. Default = 0.1.

  Valid only for `Criterion` = MESH and `Action` = ADD, LIST, or DELETE.

- `SHAPE` - Mesh-quality control threshold for elements `PLANE182` and `PLANE222`. Also applies to `SOLID185` and `SOLID186` in a [NLAD-ETCHG analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/nladetchgexample.html).

  `VAL1` - Maximum corner angle of an element in degrees. Valid values are 0 through 180. Default = 160 (2D analysis) or 155 (3D analysis). An element is remeshed when any of its corner angles reach the specified value.

  Valid only for `Criterion` = MESH and `Action` = ADD, LIST, or DELETE.

- `WEAR` - For contact elements having surface wear specified ( [[tb|TB]],WEAR) only, defines `VAL1` as a critical ratio of magnitude of wear to the average depth of the solid element underlying the contact element. Once this critical ratio is reached for any element, the program morphs the mesh to improve the quality of the elements. `VAL1` must be a positive integer.

  Valid only for `Criterion` = CONTACT and `Action` = ADD, `Action` = LIST, or `Action` = DELETE. Cannot be combined with any other option during solution.

- `CZM` - For contact elements with [cohesive zone material](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnacriteria.html#nladrefsubstep) ( [[tb|TB]],CZM) only, defines `VAL1` as a critical value of change in released energy due to debonding between reference and current substep, and `VAL2` as the critical value for the change in the damage parameter between neighboring elements. Both values can be applied separately or together.

  When the critical value is reached (for either of the defined options) for one contact element, the solid elements underlying that contact element and the corresponding deformable target element are selected as candidates for remeshing.

  `VAL1` must be \> 0. `VAL2` must be \> 0 and \< 1. No default.

  Valid only for `Criterion` = CONTACT and `Action` = ADD, LIST, or DELETE. Combing the CZM criterion with [mesh-quality-based](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnacriteria.html#advmnlaskewnessopt) criteria may be necessary to improve distorted elements.

- `ALL` - All options. Valid only for `Action` = LIST or `Action` = DELETE. All subsequent arguments are ignored.

**val1**, **val2**, **val3**, **val4**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NLADAPTIVE.html) for further information.

## Notes

If a specified component ( `Component` ) is an assembly, the defined criterion applies to all element components included in the assembly.

All components must be defined and selected before the first solve ( [[solve|SOLVE]] ), although their nonlinear adaptivity criteria can be modified from load step to load step, and upon restart. For nonlinear adaptivity to work properly, ensure that all components are selected before each solve.

After issuing this command to define a new criterion, the new criterion becomes active. The program checks the new criterion once per load step, roughly in mid-loading (unless this behavior is changed via `Action` = ON).

When a criterion is defined, it overwrites a previously defined criterion (if one exists) through the same component, or through the component assembly that includes the specified component.

During solution, the same criteria defined for an element through different components are combined, and the tightest criteria and action control ( `Action`,ON, `VAL1` ) are used. If an ON action is defined by a positive `VAL1` value through one component and a negative `VAL1` value through another, the program uses the positive value.

When the AM octree option is specified ( `Action` = OCTREE), the checking frequency ( Action,ON,, VAL1 ), checking start time ( Action,ON, VAL2 ), and checking end time ( Action,ON, VAL3 ) control the checking layer frequency, start layer, and end layer respectively. If start and end layers are not specified, the start layer will default to the checking frequency, and the end layer will default to the final layer of the AM simulation.

If `VAL1` \< 0, the program checks `VAL1` points between `VAL2` and `VAL3`. The time interval between each check points is determined by ( `VAL3` - `VAL2` ) / ( `VAL1` + 1), with the first check point as close to `VAL2` + ( `VAL3` - `VAL2` ) / ( `VAL1` + 1) as possible. Fewer check points can be used if the number of substeps during solution is insufficient (as the program can only check at the end of a substep).

If `VAL2` (start time) and/or `VAL3` (end time) are unspecified or invalid, the program uses the start and/or end time (respectively) of the load step.

`VAL1` applies to tetrahedral elements `SOLID187`, `SOLID227`, and `SOLID285`. When the skewness of an element is \>= `VAL1`, the element is used as the core (seed) element of the remeshed region(s). The most desirable skewness value is 0, applicable when the element is a standard tetrahedral element; the highest value is 1, applicable when the element becomes flat with zero volume. To bypass skewness checking (not recommended), set `VAL1` = 0.

`VAL2` represents the Jacobian ratio and is required for tetrahedral elements `SOLID187` and `SOLID227`. When the maximum Jacobian ratio of an element is \<= `VAL2`, the element is used as the core (seed) element of the remeshed region(s). The most desirable maximum Jacobian ratio is 1, when the element is a standard tetrahedral element; the lowest reported value is -1, when the element is turned inside out. To bypass maximum Jacobian ratio checking (not recommended), set `VAL2` = 0.

If this criterion is used with any other criteria defined for the same component, and a mesh change is requested at the same substep, all criteria defined are considered together. For more information about this special case, see [Simultaneous Quality- and Refinement-Based Remeshing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnanewmesh.html#)

For more information about skewness, maximum Jacobian ratio, and remeshing, see [Nonlinear Mesh Adaptivity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnaexample.html)

For more granular control of the source mesh geometry, see [[nlmesh|NLMESH]].

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NLADAPTIVE.html
