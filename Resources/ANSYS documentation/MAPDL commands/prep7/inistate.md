---
apdl: "INISTATE"
method: inistate
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.data_tables.DataTables.inistate
generated: 2026-08-22
tags: [mapdl-command]
---

# INISTATE

PyMAPDL: `mapdl.inistate(action='', val1='', val2='', val3='', val4='', val5='', val6='', val7='', val8='', val9='', **kwargs)`

Defines initial-state data and parameters.

## Parameters

**action**

Specifies action for defining or manipulating [initial-state](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/Hlp_G_INSTWRITVAL.html) data:

- `SET` - Use `Action` = SET to designate initial-state coordinate system, data type, and material type parameters. See [Command Specification for Action= SET](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_INISTATE.html#).

- `DEFINE` - Use `Action` = DEFINE to specify the actual state values, and the corresponding element, integration point, or layer information. See [Command Specifications for Action= DEFINE](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_INISTATE.html#).

  Use `Action` = DEFINE for [function-based](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/Hlp_G_INSTAPPL.html#) initial state. See [Command Specifications for Action= DEFINE (Function-Based Option)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_INISTATE.html#).

- `WRITE` - Use `Action` = WRITE to write the initial-state values to a file when the [[solve|SOLVE]] command is issued. See [Command Specifications for Action= WRITE](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_INISTATE.html#).

- `READ` - Use `Action` = READ to read the initial-state values from a file. See [Command Specifications for Action= READ](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_INISTATE.html#).

- `LIST` - Use `Action` = LIST to read out the initial-state data. See [Command Specifications for Action= LIST](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_INISTATE.html#).

- `DELETE` - Use `Action` = DELE to delete initial-state data from a selected set of elements. See [Command Specifications for Action= DELETE](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_INISTATE.html#)

**val1**, **val2**, **val3**, **val4**, **val5**, **val6**, **val7**, **val8**, **val9**: Input values based on the `Action` type.

## Notes

**INISTATE** is available for [current-technology elements](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/EL2oldnewtable.html#EL2curtechelembenefits).

The command can also be used with `MESH200` (via the [mesh-independent method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strreinfworkflow.html#strinistmesh200) for defining [reinforcing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_compreinfdirectemb.html) ) to apply an initial state to all generated reinforcing elements automatically. For more information, see [Applying an Initial State to Reinforcing Elements](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strreinfworkflow.html#strinistmesh200)

Initial-state support for a given element is indicated in the documentation for the element under **Special Features**.

Initial-strain input ( **INISTATE**,SET,DTYPE,EPEL) enables the nonlinear solver option automatically even if no nonlinear materials are involved.

The command does not support kinematic hardening material properties (such as [[tb|TB]] ,PLAS,,,,BKIN) or the shape memory alloy material model ( [[tb|TB]],SMA).

**INISTATE** with elastic strain alone is not supported for gasket materials ( [[tb|TB]],GASK) and hyperelastic materials ( [[tb|TB]] ,HYPER, [[tb|TB]] ,BB, [[tb|TB]],AHYPER, [[tb|TB]],CDM, [[tb|TB]],EXPE).

**INISTATE** with initial stress alone is not supported for gasket materials ( [[tb|TB]],GASK).

**INISTATE** with plastic strain (which must include initial strain or stress, plastic strain, and accumulated plastic strain) does not support gasket materials ( [[tb|TB]],GASK), rate-dependent plasticity ( [[tb|TB]],RATE), and viscoelasticity ( [[tb|TB]],PRONY, [[tb|TB]],SHIFT).

For more information about using the initial-state capability, see [Initial State](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/Hlp_G_INSTWRITVAL.html)

### Command Specifications

**Command Specification for Action= SET**

(table not available in the PyMAPDL source, see the Ansys help page)

`Action` = SET specifies and modifies the environment into which you will define the initial-state data (via a subsequent **INISTATE**,DEFINE command). Otherwise, subsequent **INISTATE**,DEFINE data is input as initial stress data in the global Cartesian coordinate system.

**Command Specifications for Action= DEFINE**

- `ELID` - Element ID number when using element-based initial state. Defaults to current element selection.

  Node number when using node-based initial state. Defaults to current node selection.

- `EINT` - Gauss integration point. Default = ALL or -1.

  For node-based initial state ( `Val2` = NODE), element ID number (if specified). The **INISTATE** command is applied only to the specified element (unlike the default behavior, where the command is applied to all selected elements containing the specified node).

  Not valid for material-based initial-state data ( `Val1` = MAT) or node-based initial state ( `Val2` = NODE).

- `KLAYER` - Layer number (for layered solid/shell elements) or cell number for beam/pipe elements. Blank for other supported element types and material-based initial-state data. Default = ALL or -1.

- `ParmInt` - Section integration point within a layer, or cell-integration point for beams (typically four integration points). Default = ALL or -1. Not valid for material-based initial-state data ( `Val1` = MAT) or node-based initial state ( `Val2` = NODE).

  Not valid for material-based initial-state data ( `Val1` = MAT).

  Not used for node-based initial state with elements that do not have a beam/pipe/shell section defined.

  For node-based initial state with beams/pipes, values 1 through 4 can be used to specify the values at corner nodes within a cell.

  For node-based initial state with layered sections, values can be specified at TOP, BOT, and MID, or left blank (ALL or -1).

- `Cxx, Cyy, Czz, Cxy, Cyz, Cxz` - Stress (S), strain (EPEL), or plastic strain (EPPL) values.

You can issue the **INISTATE** command repeatedly to define multiple sets of initial-state values. initial-state data can be specified according to elements, layers or integration points.

When the initial-state parameters are being defined based on the material, ( **INISTATE**,SET,MAT, `MATID` ), `ELID` designates the element ID number and all subsequent values are ignored.

For coupled-field elements, the stresses to input must be Biot's effective stresses.

**Command Specifications for Action= DEFINE (Function-Based Option)**

- `ELID` - Element ID number when using element-based initial state. Defaults to current element selection.

  Node number when using node-based initial state. Defaults to current node selection.

- `EINT` - Gauss integration point (defaults to ALL). Not valid for material-based initial-state data ( `Val1` = MAT) or node-based initial state ( `Val2` = NODE).

- `(Blank)` - Reserved for future use.

- `(Blank)` - Reserved for future use.

- `FuncName` - LINX \| LINY \| LINZ. Apply initial-state data as a linear function of location based on the X axis (LINX), Y axis (LINY), or Z axis (LINZ) in the coordinate system specified via the **INISTATE**,SET,CSYS command. Default coordinate system: CSYS,0 (global Cartesian).

- `C1, C2,..., C12` - For `FuncName` with tensors, each component uses two values. SXX = `C1`

\+ X\* `C2`, SYY = `C3` + X\* `C4`, and so on. Specify 12 values (for the six tensor components).

> For `FuncName` with scalars, only two values `C1` and `C2` ( `VALUE` = `C1` + X\* `C2` ) are necessary to apply the initial state.

You can issue **INISTATE** repeatedly with the function-based option to define multiple sets of initial-state values. Initial-state data can be specified according to elements or integration points.

For coupled-field elements, the stresses to input must be Biot's effective stresses.

**Command Specifications for Action= WRITE**

- `FLAG` - Set this value to 1 to generate the initial-state file, or 0 to disable initial-state file generation.
- `CSID` - Determines the [coordinate system](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/Hlp_G_INSTCSYS.html#eq4c704b69-e237-458d-8c30-b7c4107fed8c) for the initial state:
  - `0 (default)` - Write in global Cartesian coordinate system for solid elements.
  - `-1 (or MAT)` - Write in material coordinate system
  - `-2 (or ELEM)` - Write in element coordinate system for link, beam, and layered elements.
  - `Dtype` - Sets the data type to be written in the `.IST` file:
    - `S` - Output stresses.
    - `EPEL` - Output elastic strain.
    - `EPPL` - Output plastic strain.
    - `PLEQ` - Output equivalent plastic strain.
    - `PLWK` - Output plastic strain energy density.
    - `EPCR` - Output creep strain.
    - `PPRE` - Initial pore pressure.
    - `VOID` - Initial void ratio.
    - `SVAR` - State variables.

Default is 0 for solid elements and -2 for link, beam, and shell elements.

State variables are always written to the `.ist` file in the material coordinate system.

Only the three in-plane stresses for the top and bottom surfaces are written.

For coupled-field elements, the stresses written out are Biot's effective stress values.

Initial pore pressure and void ratio are available for the coupled pore-pressure elements (CPT `nnn` ) only: `CPT212`, `CPT213`, `CPT215`, `CPT216`, and `CPT217`.

**Command Specifications for Action= READ**

Reads initial-state data from a standalone [initial-state (.ist) file](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/Hlp_G_INSTFORMAT.html#meshindepIST) of the specified name ( `Fname` ) and filename extension ( `Ext` ), located in the specified path ( `Path` ). The initial-state file must be in a comma-delimited ASCII file format, consisting of individual rows for each stress/strain item, with each row consisting of columns separated by commas.

Use `Action` = READ to apply complex sets of initial-state data to various elements, cells, layers, sections, and integration points. This option is available for element-integration-point- based initial-state data and node-based initial-state data.

Mapping to nodes may offer better performance when many substeps are involved; however, only location support is available. Mapping to element-integration points supports additional field variables TIME, FREQ and TEMP and generally uses less memory.

For other non-user-defined field variables (such as initial stress or strain), initial state is evaluated only at the first substep in the first load step.

- `MeshIndMethod` - Mesh-Independent method `.ist` read options:
  - 0 or DEFA - [Standard](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/Hlp_G_INSTFORMAT.html#sect2_zrk_jlr_dw) (mesh-dependent) initial state `.ist` file (default).
  - MAPN - Map to nodes internally when applying the initial state.
  - MAPI - Map to element-integration points.
  - DOBJ - Do not use `.ist` data in the finite element solution. (Use this option if [converting initial-stress data to a traction load](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CINT.html#).)

**Command Specifications for Action= LIST**

If using the [standard method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/Hlp_G_INSTAPPL.html#initfuncbased) for applying initial-state data,specify `ELID` = element ID number to list initial-state data for elements. If `ELID` is unspecified, all initial-state data for all selected elements are listed.

If using the mesh-independent method, specify `ELID` = MIND to list initial-state data.

**Command Specifications for Action= DELETE**

If using the [standard method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/Hlp_G_INSTAPPL.html#initfuncbased), specify `ELID` = element ID number to delete initial-state data for elements. If `ELID` is unspecified, all initial-state data for all selected elements are deleted.

If using the mesh-independent method, specify `ELID` = MIND to delete initial-state data.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_INISTATE.html
