---
apdl: "CECYCMS"
method: cecycms
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.constraint_equations.ConstraintEquations.cecycms
generated: 2026-08-22
tags: [mapdl-command]
---

# CECYCMS

PyMAPDL: `mapdl.cecycms(cyclownod='', cychighnod='', kmap='', toler='', kprint='', usrnmap='', **kwargs)`

Generates the constraint equations for a [multistage cyclic symmetry analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/ans_mstag_introTheory.html).

## Parameters

**cyclownod**

The name of a component for the nodes located on the low angle edge of the sector (up to 256 characters enclosed in single quotes).

The sector is that of the current stage ( `Sname` ) specified with [[msopt|MSOPT]],NEW, `Sname` or [[msopt|MSOPT]],MODIFY, `Sname`. If blank and if the array parameter of edge node pairs does not exist (no user-defined or default for `UsrNMap` ), the default component name is ‘ `Sname` CYCLOW_NOD\`\`.

**cychighnod**

The name of a component for the nodes located on the high angle edge of the sector (up to 256 characters enclosed in single quotes).

The sector is that of the current stage ( `Sname` ) specified with [[msopt|MSOPT]],NEW, `Sname` or [[msopt|MSOPT]],MODIFY, `Sname`. If blank and if the array parameter of edge node pairs does not exist (no user-defined or default for `UsrNMap` ), the default component name is ‘ `Sname` CYCHIGH_NOD\`\`.

**kmap**

Option to use mapping when creating cyclic symmetry constraint equations. This option is ignored if you specify `UsrNMap`.

- `ON` - Use mapping to relate low and high sector boundary DOFs when applying cyclic symmetry constraint equations.
- `OFF` - Use matching node pairs from low and high sector boundaries to apply cyclic symmetry constraint equations (default).

**toler**

Tolerance for determining if one node on the low edge boundary matches the corresponding node on the high edge boundary after the nodes are rotated.

- `If positive` - `TOLER` is absolute (length units, defaults to 1e-4 ). If the distance of the nodes is smaller than this absolute tolerance, the nodes are matched.
- `If negative` - `TOLER` is relative. Considering the diagonal of an imaginary box enclosing the model, `TOLER` is a fraction of the length of that diagonal. Nodes within the relative tolerance are matched.

**kprint**

Option to print the table of matched nodes ( `KMAP` = OFF) or mapped nodes and elements ( `KMAP` = ON).

- `0` - Do not print the table (default).
- `1` - Print the table. If edge nodes are mapped ( `KMAP` = ON) and a high edge node is matching a low edge node, the third column labeled MAPPED lists the node number. (See Snippets of Table Printed with `KPRINT` = 1 on **CECYCMS** ).

**usrnmap**

Option for matching node pairs between low and high edges.

Input the name of an existing array parameter or a numerical key:

- `<name>` - Name of a user-defined array parameter that specifies the matching node pairs. The node pairs in the parameter may be input in any order, but the low edge node must be the first entry in each pair. (See Example: **CECYCMS** with a User-defined Array Parameter for `UsrNMap`.)

- `0 ( or blank)` - If the default array parameter named `Sname` CYCNODPAIR already exists, it is used to specify the matching node pairs (default).

  If this array parameter does not exist, nodes are paired automatically, and the array parameter named `Sname` CYCNODPAIR is created.

- `1` - Nodes are paired automatically, and the array parameter named `Sname` CYCNODPAIR is created. If it exists, it is deleted and re-created.

- `-1` - Nodes are paired automatically without creating or using an array parameter.

## Notes

**CECYCMS**, [[ceims|CEIMS]], and [[msopt|MSOPT]] are commands used in a [multistage cyclic symmetry analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/ans_mstag_introTheory.html).

If edge node pairs are matched ( `KMAP` = OFF) and an array parameter is not specified for `UsrNMap`, components are used for the cyclic edge nodes. You must specify those components using the [[cm|CM]] command and ensure that they contain base sector nodes only. See [Building the Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/multistage_building_model.html#) Example Usage for examples demonstrating the use of **CECYCMS** in multistage cyclic symmetry analyses.

(table not available in the PyMAPDL source, see the Ansys help page)

(table not available in the PyMAPDL source, see the Ansys help page)

**Example Usage**

[Example: Static Analysis of a Compressor Model with 4 Axial Stages Without a Duplicate Sector](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/multistage_ex_compressor.html#)

[Example: Linear Perturbation Modal Analysis of a Simplified Model with 2 Axial Stages and a Non- planar Interstage Boundary](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/multistag_ex_linearPert.html#)

[Example: Modal Analysis of Turbomachinery Stage Modeled as 2 Radial Stages with Offset Cyclic Edge Starting Points](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/multistag_ex_modal_turboOffset.html#)

[Example: Mutistage Multiharmonic Modal Analysis of a Hollow Cylinder Modeled Using 2 Stages](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/mstag_hollowCyl2stages.html#)

[Example: Multiharmonic Linear Perturbation Modal Analysis of a Simplified Model with 3 Axial Stages](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/ans_mstagExMultiHarmLP.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CECYCMS.html
