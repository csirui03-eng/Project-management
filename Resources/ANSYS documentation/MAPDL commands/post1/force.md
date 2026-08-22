---
apdl: "FORCE"
method: force
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.controls.Controls.force
generated: 2026-08-22
tags: [mapdl-command]
---

# FORCE

PyMAPDL: `mapdl.force(lab='', **kwargs)`

Selects the element nodal force type for output.

## Parameters

**lab**

Type of force to be associated with the force items:

- `TOTAL` - Total forces (static, damping, and inertia).
- `STATIC` - Static forces.
- `DAMP` - Damping forces.
- `INERT` - Inertia forces.

## Notes

**FORCE** selects the element nodal force type for output with the POST1 [[presol|PRESOL]], [[plesol|PLESOL]], [[prrfor|PRRFOR]], [[nforce|NFORCE]], [[fsum|FSUM]], etc. commands, the POST26 [[esol|ESOL]] command, and reaction force plotting ( [[pbc|/PBC]] ). For example, **FORCE**,STATIC causes item F of the [[presol|PRESOL]] command to be the static forces for the elements processed. Element member forces (such as those available for beams and shells and processed by Item and Sequence number) are not affected by this command. The SMISC records extract the static force.

In a non-spectrum analysis that includes either contact or pretension elements in the model, the [[prrsol|PRRSOL]] command is valid with the **FORCE** command. Otherwise, the [[prrsol|PRRSOL]] command is not valid with **FORCE**. Use the [[prrfor|PRRFOR]] command, which provides the same functionality as [[prrsol|PRRSOL]], instead.

Use the **FORCE** command prior to any load case operations ( [[lcoper|LCOPER]] ) to insure the correct element nodal force combinations.

In POST26, the [[esol|ESOL]] data stored is based on the active **FORCE** specification at the time the data is stored. To store data at various specifications (for example, static and inertia forces), issue a [[store|STORE]] command before each new specification.

The **FORCE** command cannot be used to extract static, damping, and inertial forces for `MPC184` joint elements.

To retrieve the different force types, use the [[get|*GET]] command with `Entity` =ELEM and `Item1` =EFOR.

The **FORCE** command is not supported in a spectrum analysis. You can specify the force type directly on the combination method commands ( `ForceType` on the [[psdcom|PSDCOM]], [[srss|SRSS]], [[cqc|CQC]], etc. commands).

The **FORCE** command is not supported in a modal analysis.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FORCE.html
