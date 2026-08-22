---
apdl: "SSTATE"
method: sstate
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.special_purpose.SpecialPurpose.sstate
generated: 2026-08-22
tags: [mapdl-command]
---

# SSTATE

PyMAPDL: `mapdl.sstate(action='', cm_name='', val1='', val2='', val3='', val4='', val5='', val6='', val7='', val8='', val9='', **kwargs)`

Defines a steady-state rolling analysis.

## Parameters

**action**

Action to perform for defining or manipulating steady-state rolling analysis data:

- `DEFINE` - Define steady-state rolling analysis data
- `LIST` - List current steady-state rolling analysis data
- `DELETE` - Delete steady-state rolling analysis data

**cm_name**: Element component name

**val1**, **val2**, **val3**, **val4**, **val5**, **val6**, **val7**, **val8**, **val9**: Input values (based on the `Action` type)

## Notes

The **SSTATE** command specifies steady-state rolling analysis parameters for the given element component. The program runs the steady-state rolling analysis if the corresponding element key option is enabled for that element component.

The command supports the following elements:

(table not available in the PyMAPDL source, see the Ansys help page)

For information about steady-state rolling for rebar and solid elements, see [Steady-State Rolling](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_geosteadystroll.html#)

The following data types can be defined:

- SPIN - Spinning motion
- TRANSLATE - Rigid body motion (velocity) that the spinning component is undergoing

**Define the steady-state spinning motion:**

**SSTATE**, DEFINE, `CM_Name`, SPIN, `OMEGA`, `Method`, `Val4`, `Val5`, `Val6`, `Val7`, `Val8`, `Val9`

- `OMEGA` - Spin velocity
- `Method` - Method to use for defining the spin axis:
  - `POINTS` - Define the spin axis using two points:

    `Val4`, `Val5`, `Val6` - Coordinates of the first point

    `Val7`, `Val8`, `Val9` - Coordinates of the second point

    This definition method is currently the only option.

    > **Example: Defining Steady-State Spinning Motion**
    >
    > This command defines a steady-state spinning motion of 120 rad/s around the spin axis:
    >
    > ``` apdl
    > SSTATE,DEFINE, CM_Name,SPIN,120,POINTS,0,0,0,0,1,0
    > ```
    >
    > In this case, two points with coordinates (0,0,0) and (0,1,0) define the spin axis in the global Y direction.

**Define the rigid body motion (velocity):**

**SSTATE**, DEFINE, `CM_Name`, TRANSLATE, `Val2`, `Val3`, `Val4`

- `Val2`, `Val3`, `Val4` - Rigid body velocity components

**SSTATE**, LIST, `CM_Name`

Lists all steady-state rolling analysis data defined on the specified element component. All data is listed if no component ( `CM_Name` ) is specified.

**SSTATE**, DELETE, `CM_Name`

Deletes all steady-state rolling analysis data defined on the specified element component. All data is deleted if no component ( `CM_Name` ) is specified.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SSTATE.html
