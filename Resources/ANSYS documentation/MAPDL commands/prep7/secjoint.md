---
apdl: "SECJOINT"
method: secjoint
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.secjoint
generated: 2026-08-22
tags: [mapdl-command]
---

# SECJOINT

PyMAPDL: `mapdl.secjoint(kywrd='', val1='', val2='', val3='', val4='', val5='', val6='', **kwargs)`

Defines local coordinate systems at joint element nodes and other data for joint elements.

## Parameters

**kywrd**

Keyword that indicates the type of joint element data being defined.

- `LSYS or blank` - Define local coordinate systems at the nodes that form the `MPC184` joint element.
- `RDOF` - Define the relative degrees of freedom to be fixed for an `MPC184-General` joint element.
- `PITC` - Define the pitch of an `MPC184-Screw` joint element.
- `FRIC` - Define the geometric quantities required for Coulomb frictional behavior in the `MPC184-Revolute`, `MPC184-Slot`, `MPC184-Translational`, or `MPC184-Spherical` joint element.
- `PNLT` - Define the penalty factors for the penalty-based joint element formulation.

**val1**, **val2**, **val3**, **val4**, **val5**, **val6**

The meaning of `Val1` through `Val6` changes, depending on the value of `Kywrd`.

If `Kywrd` = LSYS (or blank), `Val1` and `Val2` are Identifiers of the local coordinate systems at nodes I and J, respectively, of the joint element. `Val3` through `Val6` are not used.

If `Kywrd` = RDOF, `Val1` through `Val6` are the relative degrees of freedom to be fixed for a general joint element. Input 1 for UX, 2 for UY, 3 for UZ, 4 for ROTX, 5 for ROTY, and 6 for ROTZ. You may input the DOFs in any order.

If `Kywrd` = PITC, `Val1` is the pitch of the screw joint element; pitch is defined as the ratio of relative axial displacement (length units) to relative rotation (in radians). `Val2` through `Val6` are not used.

If `Kywrd` = FRIC, `Val1` through `Val3` are defined as follows.

- **For Revolute Joint:**
- `Val1` = outer radius
- `Val2` = inner radius
- `Val3` = effective length
- **For Translational Joint:**
- `Val1` = effective length
- `Val2` = effective radius
- **For Spherical Joint:**
- `Val1` = effective radius

If `Kywrd` = PNLT, `Val1` and `Val2` are defined as follows, and `Val3` through `Val6` are not used.

- `Val1` - Constraint type:
  - DISP - Displacement-based constraint
  - ROT - Rotation-based constraint
- `Val2` - Scaling factor (input a positive number) or penalty factor (input a negative number) used with the penalty-based joint element formulation:
  - Positive number - the number is used as a scaling factor to scale the internally calculated penalty values.
  - Negative number - the absolute value of the number is used as the penalty factor in calculations.

## Notes

Use this command to define additional section data for `MPC184` joint elements. To overwrite the current values, issue another **SECJOINT** command with the same `Kywrd` value. The data input on this command is interpreted based on the most recently issued [[sectype|SECTYPE]] command.

The command **SECJOINT**,PNLT is only applicable to penalty-based joints (KEYOPT(2) = 1 on most joint elements). The default penalty factor (common to all constraints of the joint element) is of the order of 102E<sub>avg</sub>, where E<sub>avg</sub> is the average Young's modulus of the elements attached to the joint element or deduced from the connections to other elements. The default value may be overridden by specifying user-defined penalty factors via **SECJOINT**,PNLT. The choice of penalty factors can affect the constraint satisfaction as well as overall solution convergence.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SECJOINT.html
