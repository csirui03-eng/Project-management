---
apdl: "CGROW"
method: cgrow
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.data_tables.DataTables.cgrow
generated: 2026-08-22
tags: [mapdl-command]
---

# CGROW

PyMAPDL: `mapdl.cgrow(action='', par1='', par2='', par3='', **kwargs)`

Specifies crack-growth options in a fracture analysis.

## Parameters

**action**

Specifies the action for defining or manipulating crack-growth data:

- [Command Specification for Action= NEW](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CGROW.html#) NEW - Initiate a new set of crack-growth simulation data (default).
- [Command Specification for Action= CID](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CGROW.html#) CID - Specify the crack-calculation ( [[cint|CINT]] ) ID for energy-release rates to be used in the fracture criterion calculation.
- [Command Specification for Action= FCOPTION](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CGROW.html#) FCOPTION - Specify the fracture criterion for crack-growth/delamination.
- [Command Specification for Action= CSFL](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CGROW.html#) CSFL - Specify a crack-surface load for crack-growth.
- [Command Specification for Action= CPATH](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CGROW.html#) CPATH - Specify the element component for crack-growth.
- [Command Specification for Action= DTIME](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CGROW.html#) DTIME - Specify the initial time step for crack-growth.
- [Command Specification for Action= DTMIN](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CGROW.html#) DTMIN - Specify the minimum time step for crack-growth.
- [Command Specification for Action= DTMAX](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CGROW.html#) DTMAX - Specify the maximum time step for crack-growth.
- [Command Specification for Action= FCRAT](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CGROW.html#) FCRAT - Fracture criterion ratio ( [fc](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#vcctuserdeffractcrit) c ).
- [Command Specification for Action= STOP](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CGROW.html#) STOP - Stops the analysis when the specified criterion ( `Par1` ) is reached.
- [Command Specification for Action= METHOD](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CGROW.html#) METHOD - Define the method of crack propagation.
- [Command Specification for Action= FCG](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CGROW.html#) FCG - Specifies [fatigue crack-growth](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracfcgxfem.html#fracfcgxfemexample).
- [Command Specification for Action= SOPT](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CGROW.html#) SOPT - Specifies the crack-growth solution option in a multicrack analysis.
- [Command Specification for Action= RMCONT](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CGROW.html#) RMCONT - Specifies remeshing control options for mesh coarsening.
- [Command Specification for Action= NPLOAD](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CGROW.html#) NPLOAD - Specifies [nonproportional loading](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#) control options for fatigue crack-growth.

**par1**, **par2**, **par3**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CGROW.html) for further information.

## Notes

When `Action` = NEW, the **CGROW** command initializes a crack-growth simulation set. Subsequent **CGROW** commands define the parameters necessary for the simulation.

For multiple cracks, issue multiple **CGROW**,NEW commands (and any subsequent **CGROW** commands necessary to define the parameters) for each crack.

If the analysis is restarted ( [[antype|ANTYPE]],,RESTART), the **CGROW** command must be re-issued.

If the [[save|SAVE]] command is issued after any **CGROW** commands are issued, the **CGROW** commands are not saved to the database. Reissue the **CGROW** command(s) when the database is resumed.

**For** [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) -based crack-growth:

- `Action` = CPATH has no effect.
- `Action` = STOP affects both SMART-based [static](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#frackbasedsifs) and [fatigue](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#fracfcgreferences) crack-growth analyses.
- When `Action` = CSFL with `Option` = CZM, the remeshing for cracks associated with this option is enforced at the end of the first load step and the first substep whether or not the crack grows at this moment. On original crack surfaces (defined via [[cint|CINT]],SURF), `INTER204` elements are initialized fully damaged, as they are used for crack-closure only and do not contribute bonding tractions on crack surfaces. The cohesive tractions on the new open crack surface are defined via the cohesive zone material model type ( [[tb|TB]],CZM) and **CGROW**,CSFL,CZM. This option can be combined with [[adpci|ADPCI]] to initialize a crack with cohesive effect.

**For** [VCCT](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#vcctsimassum) -based crack-growth:

- Crack-growth element components must use the crack tip nodes as the starting nodes of the crack path.
- Fracture criteria ( `Action` = FCOPTION) use energy-release rates calculated via VCCT technology ( [[cint|CINT]],TYPE,VCCT). For information about the fracture criteria available, see [Fracture Criteria](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#vcctuserdeffractcrit) [[tb|TB]], [CGCR - Crack-Growth Fracture Criterion](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_TB.html#eq4d382484-99d1-41ac-82dc-5a82d9911274) CGCR.

**For** [XFEM](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#fracxfemreferences) -based crack-growth:

- The crack specification originates via the [[xfenrich|XFENRICH]], [[xfdata|XFDATA]], or [[xfcrkmesh|XFCRKMESH]] command.
- `Action` = CPATH, DTMIN, or DTMAX has no effect.
- `Action` = STOP affects [fatigue](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracfcgxfem.html#fracfcgxfemexample) crack-growth analysis only.

### Command Specifications

**Command Specification for Action= NEW**

- `Par1` - Crack-growth data set ID (integer value).

**Command Specification for Action= CID**

- `Par1` - Contour-integral calculation ( [[cint|CINT]] ) ID for energy-release rates to be used in fracture criterion calculation.

**Command Specification for Action= FCOPTION**

\* `Par1` - **MTAB** - Crack-growth fracture criterion used with the material data table ( [[tb|TB]], [CGCR - Crack-Growth Fracture Criterion](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_TB.html#eq4d382484-99d1-41ac-82dc-5a82d9911274) CGCR).

> **GTC** - Defines the critical energy-release rate, a simple fracture criterion used for the [VCCT](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#vcctsimassum) method.
>
> **KIC** - Defines the [critical stress-intensity factor](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#eqa7ac21d8-c5cc-41bd-aced-f664166c2ea0). Valid for the [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) method only.
>
> **JIC** - Defines the [critical J-integral](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#eqb5e4514c-a107-4016-847f-af649a691f2f). Valid for the [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) method only.

- `Par2` - For `Par1` = MTAB: Material ID for the material data table.

  For I `Par1` = GTC: Critical energy-release rate value.

  For `Par1` = KIC: Critical stress-intensity factor value.

  For `Par1` = JIC: Critical J-integral value.

- `Par3` - For `Par1` = MTAB, KIC, or JIC: Specifies the fracture-parameter contour to use for [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) crack-growth evaluation. Default = 2.

**Command Specification for Action= CSFL**

- `Par1` - Crack-surface load options:

  - PRES - New crack-surface pressure load.
  - CZM - Entire crack-surface enhanced by `INTER204` 3D 16-node cohesive elements (generated automatically during the first remeshing around the associated crack). See [[cgrow#Notes|CGROW]].

- `Par2` - When `Par1` = PRES: (blank)

  When `Par1` = CZM: A valid material ID (defined via [[tb|TB]],CZM,,,,BILI, [[tb|TB]],CZM,,,,CEXP, or [[tb|TB]],CZM,,,,CLIN \[default\]). If zero or an invalid value is specified, the program uses [[tb|TB]],CZM,,,,CLIN as the default cohesive model type and sets reasonable CZM parameters based on the solid elements around the crack fronts/surfaces. For more information, see [Enhancing Crack Surfaces with Cohesive Zone Elements](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#eq26e3f167-5353-40f6-b6f1-8c455fe0bc00)

- `Par3` - New crack-surface load value, or the name of a table for specifying tabular load values for crack- growth.

  The new crack-surface load is always assumed to be constant. If `Par1` = PRES, `Par3` specifies a constant pressure load.

  To specify a table ( [[dim|*DIM]] ), enclose the table name within "%" characters (

  ``` apdl
  % tablename% ). Only one table can be specified for a crack-growth set, and time is the only
  ```

  primary variable supported.

  ``` apdl
  % tablename% ). Only one table can be specified for a crack-growth set, and time is the only
  ```

  primary variable supported.

**Command Specification for Action= CPATH**

- `Par1` - Interface element component for crack path ( [VCCT](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#vcctsimassum) method only). (Component name must be 32 characters or less.)

**Command Specification for Action= DTIME**

- `Par1` - Initial time step when crack-growth is detected.

**Command Specification for Action= DTMIN**

- `Par1` - Minimum time step allowed when crack-growth is detected.

**Command Specification for Action= DTMAX**

- `Par1` - Maximum time step allowed when crack-growth is detected.

**Command Specification for Action= FCRAT**

- `Par1` - [Fracture criterion ratio](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#vcctuserdeffractcrit) (f<sub>c</sub>, where f<sub>c</sub> is generally around 1). The recommended ratio is 0.95 to 1.05. The default is 1.00.

**Command Specification for Action= STOP**

\* `Par1` - **CEMX** - Stops the analysis when the crack extension for any crack-front node reaches the maximum value (specified via `Par2` ).

> **FBOU** - Stops the analysis when the crack extension reaches the free boundary. Valid only for [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) crack-growth analysis.
>
> **KMAX** - Stops the analysis when the maximum equivalent stress-intensity factor exceeds the specified limit ( `Par2` ). Valid only for SMART crack-growth analysis.

- `Par2` - When `Par1` = CEMX, the value of maximum crack extension allowed.

  When `Par1` = KMAX, the value of the maximum equivalent stress-intensity factor allowed.

**Command Specification for Action= METHOD**

\* `Par1, Par2` - **VCCT** - Use [VCCT](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#vcctsimassum) to grow the crack (default).

> **XFEM** - Use [XFEM](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#fracxfemreferences) to grow the crack.
>
> **SMART** - Use [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) to grow the crack.

- `Par2` - REME - Remeshing-based [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) crack-growth method (the default and only option). Valid only when `Par1` = SMART.

**Command Specification for Action= FCG**

- `Par1` - **METH** - Fatigue crack-growth method.

  **DAMX** - Maximum crack-growth increment.

  **DAMN** - Minimum crack-growth increment.

  **SRAT** - [Stress ratio](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#eq4f61610d-5010-4a2d-83de-3c60fba4be9f).

  **DKTH** - Threshold value of equivalent stress-intensity-factor range (SIFS).

  **DN** - Incremental number of cycles.

- `Par2` - `Method` - [LC or CBC method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#eq0a4098c5-8c81-4f2f-b279-a2fb84dff9ad) CBCmethod. Valid only when `Par1` = METH.

  `VALUE` - Value for the specified `Par1`. Valid only when `Par1` = DAMX, DAMN, SRAT, DKTH, or DN.

  - For `Par1` = SRAT or DKTH, `Par2` can be a constant or table. To specify a table ( [[dim|*DIM]] ), enclose the table name within "%" characters (`tablename`). Only one table can be specified for a crack-growth set, and time is the only primary variable supported.

- `Par3` - Valid only for [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) crack-growth analysis when `Par1` = DKTH.

  MIN or MAX or AVER or blank (default) - The minimum, maximum, or average stress-intensity-factor range (ΔK), respectively. The program calculates the range over the entire crack front, then uses the result to evaluate the threshold criterion. The entire crack is arrested if the specified minimum, maximum, or average ΔK is below the threshold ( `Par2` ). Partial crack-growth does not occur.

  If `Par3` is unspecified (default), the program evaluates threshold criterion at each crack-front node individually and ensures that the crack is arrested locally at any node where ΔK is below the threshold ( `Par2` ). If some nodes have ΔK less than the threshold and others have ΔK greater than the threshold, partial crack-growth occurs at the crack front.

  > \*\*Example: Using
  >
  > ``` apdl
  > CGROW,FCG,DKTH, Par2, Par3
  > ```
  >
  > \*\*
  >
  > If `Par3` = MIN, the program selects the minimum ΔK from the ΔK values calculated at all crack- front nodes for the corresponding crack ID. If the minimum ΔK does not exceed the threshold ( `Par2` ), there is no crack extension at the entire crack front.

**Command Specification for Action= SOPT**

- `Par1` - SCN - Use a single number of cycles for all cracks in a multicrack analysis (even if each crack has separate loading) (default).

  MCN - Allow a separate cycle count for each crack in a multicrack analysis (available only if each crack has separate loading).

**Command Specification for Action= RMCONT**

Valid in a [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) crack-growth analysis only.

- `Par1` - COARSE - Controls [mesh-coarsening](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#).

  ESIZE - Controls element sizing and crack-increment size.

  CMULT - Controls the crack-growth increment multiplier.

- `Par2` - For `Par1` = COARSE:

  - CONS - Remeshing occurs with conservative mesh-coarsening (default).
  - MODE - Remeshing occurs with moderate mesh-coarsening.
  - AGGR - Remeshing occurs with aggressive mesh-coarsening.

  For `Par1` = ESIZE:

  - Crack-front reference element-size value, or the table name for specifying tabular element size values as a function of solution time.

  For `Par1` = CMULT:

  - Crack-front [element-size multiplier function](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#eq7e7daaf3-47a8-4bfe-8dd8-5cc5e3628ff0) :
  - TIME - Controls the crack-growth increment multiplier via the beginning and end of the solution time.
  - CEMX - Controls the crack-growth increment multiplier via the beginning and end of the accumulated maximum crack extension.
  - RMNU - Controls the crack-growth increment multiplier via the beginning and end of the number of remeshing steps.
  - TABLE - The name of the table for controlling the crack-growth increment multiplier.

\* `Par3 - Par5` - For `Par1` = ESIZE and `Par2` = `VALUE` or `tablename` and `Par3` = COMP:

> - `Par4` = Name of the node or element component (≤ 32 characters).
>
> For `Par1` = ESIZE and `Par2` = `VALUE` or `tablename` and `Par3` = NODE:
>
> - `Par4` = Node ID.
>
> For `Par1` = ESIZE and `Par2` = `VALUE` or `tablename` and `Par3` = ELEM:
>
> - `Par4` = Element ID.
>
> For `Par1` = CMULT and `Par2` = TIME:
>
> - `Par3` = `VALUE` - Maximum value of the crack-growth multiplier value.
> - `Par4` = `VALUE` - Time at the beginning of the crack-increment control function.
> - `Par5` = `VALUE` - Time at the end of the crack-increment control function.
>
> For `Par1` = CMULT and `Par2` = CEMX:
>
> - `Par3` = `VALUE` - Maximum value of the crack-growth multiplier value.
> - `Par4` = `VALUE` - Accumulated maximum crack extension at the beginning of the crack-increment control function.
> - `Par5` = `VALUE` - Accumulated maximum crack extension at the end of the crack-increment control function.
>
> For `Par1` = CMULT and `Par2` = RMNU:
>
> - `Par3` = `VALUE` - Maximum value of the crack-growth multiplier value.
> - `Par4` = `VALUE` - Remeshing number at the beginning of the crack-increment control function.
> - `Par5` = `VALUE` - Remeshing number at the end of the crack-increment control function.
>
> For `Par1` = CMULT and `Par2` = TABLE:
>
> - `Par3` = `tablename` - Controls the crack-growth increment multiplier via the tabular data in the specified table.
> - To specify a table ( [[dim|*DIM]] ), enclose the table name `tablename` within % characters. You can specify one table per crack-growth set, and time is the only valid variable.

**Command Specification for Action= NPLOAD**

Valid in a [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) fatigue crack-growth analysis using [nonproportional loading](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#).

- `Par1` - METHOD - Specifies the nonproportional [solution method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#notenostressratio).

  DIRECTION - Specifies the nonproportional [crack-growth-direction method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#eq16b7dac1-430d-4d50-9eaa-763f6660ab4e).

- `Par2` - For `Par1` = METHOD:

  - DKEF - Specifies the effective stress-intensity-factor range method.
  - DKMO - Specifies the stress-intensity-factor range method based on mode separation.
  - TKEF - Specifies the total effective stress-intensity-factor method.
  - TKMO - Specifies the total stress-intensity-factor method based on mode separation.

  For `Par1` = DIRECTION:

  - KMAX - Specifies the maximum-load method for the crack-growth direction.
  - KMIN - Specifies the minimum-load method for the crack-growth direction.
  - KLOC - Specifies the local kink-tip stress-intensity-factor method.

- `Par3` - For `Par2` = KLOC:

  - `w` - Parameter-fitting value between 0 and 1. Default = 0.5.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CGROW.html
