---
apdl: "JSOL"
method: jsol
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.set_up.SetUp.jsol
generated: 2026-08-22
tags: [mapdl-command]
---

# JSOL

PyMAPDL: `mapdl.jsol(nvar='', elem='', item='', comp='', name='', **kwargs)`

Specifies result items to be stored for the joint element.

## Parameters

**nvar**: Arbitrary reference number or name assigned to this variable. Variable numbers can be 2 to `NV` ( [[numvar|NUMVAR]] ) while the name can be an eight-byte character string. Overwrites any existing results for this variable.

**elem**: Element number for which to store results.

**item**: Label identifying the item. Valid item labels are shown in *JSOL - Valid Item and Component Labels* below.

**comp**: Component of the `Item` (if required). Valid component labels are shown in *JSOL - Valid Item and Component Labels* below.

**name**: Thirty-two character name identifying the item on printouts and displays. Defaults to a label formed by concatenating the first four characters of the `Item` and `Comp` labels.

## Notes

This command is valid for the `MPC184` joint elements. The values stored are for the free or unconstrained degrees of freedom of a joint element. Relative reaction forces and moments are available only if stiffness, damping, or friction is associated with the joint element.

### JSOL - Valid Item and Component Labels

| Item | Comp    | Description                                                  |
|------|---------|--------------------------------------------------------------|
| U    | X, Y, Z | x, y, or z relative displacement.                            |
| ROT  | X, Y, Z | x, y, or z relative rotation.                                |
| VEL  | X, Y, Z | x, y, or z relative linear velocity.                         |
| OMG  | X, Y, Z | x, y, or z relative angular velocity.                        |
| ACC  | X, Y, Z | x, y, or z relative linear acceleration.                     |
| DMG  | X, Y, Z | x, y, or z relative angular acceleration.                    |
| RF   | X, Y, Z | Relative reaction forces in the local x, y, or z direction.  |
| RM   | X, Y, Z | Relative reaction moments in the local x, y, or z direction. |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_JSOL.html
