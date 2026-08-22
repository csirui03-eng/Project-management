---
apdl: "CEIMS"
method: ceims
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.constraint_equations.ConstraintEquations.ceims
generated: 2026-08-22
tags: [mapdl-command]
---

# CEIMS

PyMAPDL: `mapdl.ceims(toler='', sname1='', sname2='', kprint='', intf1nod='', intf2nod='', **kwargs)`

Generates constraint equations at the interstage boundary in a [multistage cyclic symmetry analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/ans_mstag_introTheory.html).

## Parameters

**toler**: Tolerance for determining if selected nodes are on the interface. `TOLER` is a fraction of the element dimension (defaults to 0.25 (25%)). Nodes outside the element by more than the tolerance are not accepted as being on the interface.

**sname1**: The name of the first stage or part. For details on required node and element selections, see *Node and Element Selection Requirements*.

**sname2**: The name of the second stage or part. For details on required node and element selections, see *Node and Element Selection Requirements*.

**kprint**

Option to print mapped nodes and elements.

- `0 (, or OFF)` - Do not print mapped nodes and elements (default).
- `1 (, or ON)` - Print mapped nodes and elements.

**intf1nod**: The name of the interstage nodal component of the first stage or sector part to be tied to the second stage or part named `IntF2Nod`. It is optional to specify `IntF1Nod` (see *Node and Element Selection Requirements* ), but if used, `IntF2Nod` must also be specified.

**intf2nod**: The name of the interstage nodal component of the second stage or sector part to be tied to the first stage or part named `IntF1Nod`. It is optional to specify `IntF2Nod` (see *Node and Element Selection Requirements* ), but it used, `IntF1Nod` must also be specified.

## Notes

This command can be used to generate constraint equations to tie the interface nodes of two cyclic sector parts.

Mapping is performed so mesh patterns at the interface of both parts can be different.

This command is supported for the following degrees of freedom (DOFs) at the interstage boundary: UX, UY, UZ, ROTX, ROTY, ROTZ. Since only 3D elements are supported, UX, UY, and UZ are required. Note that if rotational DOFs are included, all three of them must be present.

### Node and Element Selection Requirements

You can specify the interface nodes in one of two ways: If you specify `IntF1Nod` and `IntF2Nod` nodal components, there are no other node or element selection requirements.

Otherwise, prior to issuing CEIMS:

\* the **nodes** at the interface of the first cyclic sector part ( `Sname1`, part having the largest cyclic sector angle) must be selected, and

\* the **elements** at the interface of the second cyclic sector part ( `Sname2`, part having the smallest cyclic sector angle) must be selected.

For cyclic sector parts, select only base sector quantities (not duplicate sector ones). See also the [[nsel|NSEL]] and [[esel|ESEL]] commands for selecting nodes and elements.

The degrees of freedom of the first part interface nodes are interpolated with the corresponding degrees of freedom of the nodes of the second part interface elements using the shape functions of those elements.

Constraint equations are created between interface nodes. Those nodes should not have any other constraints defined, but if so they must be compatible.

**Example Usage** [Example: Static Analysis of a Compressor Model with 4 Axial Stages Without a Duplicate Sector](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/multistage_ex_compressor.html#)

[Example: Linear Perturbation Modal Analysis of a Simplified Model with 2 Axial Stages and a Non- planar Interstage Boundary](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/multistag_ex_linearPert.html#)

[Example: Modal Analysis of Turbomachinery Stage Modeled as 2 Radial Stages with Offset Cyclic Edge Starting Points](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/multistag_ex_modal_turboOffset.html#)

[Example: Mutistage Multiharmonic Modal Analysis of a Hollow Cylinder Modeled Using 2 Stages](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/mstag_hollowCyl2stages.html#)

[Example: Multiharmonic Linear Perturbation Modal Analysis of a Simplified Model with 3 Axial Stages](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/ans_mstagExMultiHarmLP.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CEIMS.html
