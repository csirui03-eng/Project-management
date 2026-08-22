---
apdl: "USRDOF"
method: usrdof
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.usrdof
generated: 2026-08-22
tags: [mapdl-command]
---

# USRDOF

PyMAPDL: `mapdl.usrdof(action='', dof1='', dof2='', dof3='', dof4='', dof5='', dof6='', dof7='', dof8='', dof9='', dof10='', **kwargs)`

Specifies the degrees of freedom for the user-defined element `USER300`.

## Parameters

**action**

One of the following command operations:

- `DEFINE` - Specify the degrees of freedom (DOFs). This value is the default.
- `LIST` - List all previously specified DOFs.
- `DELETE` - Delete all previously specified DOFs.

**dof1**, **dof2**, **dof3**, **dof4**, **dof5**, **dof6**, **dof7**, **dof8**, **dof9**, **dof10**: The list of DOFs.

## Notes

The **USRDOF** command specifies the degrees of freedom for the user-defined element `USER300`.

Although you can intersperse other commands as necessary for your analysis, issue the **USRDOF** command as part of the following general sequence of commands:

Issue the [[et|ET]] command for element `USER300`, followed by the related [[type|TYPE]] command.

Issue both the [[usrelem|USRELEM]] and **USRDOF** commands (in either order).

Define your element using `USER300`.

The DOF list ( `DOF1` through `DOF10` ) can consist of up to 10 DOFs. Use any valid and appropriate DOF (such as UX, UY, UZ, ROTX, ROTY, ROTZ, AX, AY, AZ, VX, VY, VZ, PRES, WARP, TEMP, VOLT, MAG, EMF, and CURR).

You can specify a maximum of 10 DOFs per **USRDOF** command. To define additional DOFs, issue the command again.

The maximum number of DOFs for a user-defined element-the number of nodes times the number of DOFs per node-cannot exceed 480.

To learn more about user-defined elements, see [Creating a New Element](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Hlp_P_UPFNEWEL.html#upfcreateelem2)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_USRDOF.html
