---
apdl: "CYCSPEC"
method: cycspec
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.cycspec
generated: 2026-08-22
tags: [mapdl-command]
---

# CYCSPEC

PyMAPDL: `mapdl.cycspec(label='', node='', item='', comp='', **kwargs)`

Defines the set of result items for a subsequent [[cyccalc|CYCCALC]] command in postprocessing a cyclic harmonic mode-superposition analysis.

**Command default:**

No defaults are available for the **CYCSPEC** command. You must issue this command to define the set of result items for evaluation in a subsequent [[cyccalc|CYCCALC]] command used in computing results of a cyclic harmonic mode-superposition analysis.

## Parameters

**label**

One of the following labels:

- `ADD` - Adds a new specification to the set (default). The maximum number of specifications that can be defined is 50.
- `LIST` - Lists the current set of specifications. `Node`, `Item`, `Comp` are ignored.
- `ERASE` - Erases the current set of specifications. `Node`, `Item`, `Comp` are ignored.
- `DELETE` - Deletes an existing specification. `Item`, `Comp` are ignored.

**node**

The node at which to evaluate the results. If `Node` is a nodal component, then all nodes in the component are included. All sectors containing this node (or set of nodes) are evaluated.

For `LABEL` = DELETE, use `Node` to indicate which specification in the set to delete.

**item**

Specifies the type of values to evaluate:

- `U` - Displacement
- `S` - Stress
- `EPEL` - Elastic strain

**comp**

Specifies the specific component of displacement, stress, or strain to evaluate:

- `X,Y,Z` - Direct components
- `XY,YZ,XZ` - Shear components (stress and strain only)
- `1,2,3` - Principal values (stress and strain only)
- `EQV` - Equivalent value (stress and strain only)
- `SUM` - Vector sum (displacement only)
- `NORM` - L2 norm for the set of nodes (displacement only)

## Notes

Up to 50 specifications can be defined for use in a subsequent [[cyccalc|CYCCALC]] command. If more than 50 specifications are desired, erase the table after the [[cyccalc|CYCCALC]] operation and add new specifications and repeat the [[cyccalc|CYCCALC]] command. All the specified nodes, items, and components are evaluated for all sectors and the maximum amplitude value output. For combined stresses and strains ( `Comp` = 1,2,3 or EQV) or displacement vector sum ( `Comp` = SUM), a 360 degree phase sweep is performed at each location to determine the maximum.

Additional POST1 controls are used to refine the specification. For component values, components are in the [[rsys|RSYS]] direction. For shell elements, the results are at the [[shell|SHELL]] location. For EPEL,EQV, the results are based on the `EFFNU` value on the [[avprin|AVPRIN]] command. The controls active when the [[cyccalc|CYCCALC]] command is issued determine the result values. If results at another [[shell|SHELL]] location are desired, issue the new [[shell|SHELL]] command and then re-issue the [[cyccalc|CYCCALC]] command.

If a single node is input, the `Item` / `Comp` value at that location in each sector is output. If a node component is given, then the maximum `Item` / `Comp` value within the set of nodes of each sector is output, one value for each sector (the node of the maximum may vary from sector to sector). For stress and strain items, only corner nodes are valid.

For the displacement norm option ( `Item` = U, `Comp` = NORM), the L2 norm computed from all the nodes in the component is output, one per sector.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CYCSPEC.html
