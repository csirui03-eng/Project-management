---
apdl: "CNCHECK"
method: cncheck
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.database.Database.cncheck
generated: 2026-08-22
tags: [mapdl-command]
---

# CNCHECK

PyMAPDL: `mapdl.cncheck(option='', rid1='', rid2='', rinc='', intertype='', trlevel='', val1='', val2='', val3='', **kwargs)`

Provides and/or adjusts the initial status of contact pairs.

## Parameters

**option**

Option to be performed:

- `DETAIL` - List all contact pair properties (default).
- `SUMMARY` - List only the open/closed status for each contact pair.
- `POST` - Execute a partial solution to write the initial contact configuration to the `jobname.rcn` file.
- `ADJUST` - Physically move contact nodes to the target in order to close a gap or reduce penetration. The initial adjustment is converted to structural displacement values (UX, UY, UZ) and stored in the `jobname.rcn` file.
- `MORPH` - Physically move contact nodes to the target in order to close a gap or reduce penetration, and also morph the underlying solid mesh. The initial adjustment of contact nodes and repositioning of solid element nodes due to mesh morphing are converted to structural displacement values (UX, UY, UZ) and stored in the `jobname.rcn` file.
- `TADJUST` - Physically move target body to the contact surface in order to close a gap or reduce penetration. The initial adjustment is converted to structural displacement values (UX, UY, UZ) and stored in the `jobname.rcn` file.
- `RESET` - Reset target element and contact element key options and real constants to their default values. This option is not valid for general contact.
- `AUTO` - Automatically sets certain real constants and key options to recommended values or settings in order to achieve better convergence based on overall contact pair behaviors. This option is not valid for general contact.
- `TRIM` - Trim contact pair (remove certain contact and target elements).
- `UNSE` - Unselect certain contact and target elements.
- `SPLIT` - Split base (original) contact pairs into smaller sub-pairs at the preprocessing ( [[prep7|/PREP7]] ) level. The main intent of this option is to achieve better scalability in a distributed-memory parallel (DMP) run. The splitting operation may create additional overlapping contact elements at the split boundaries. Contact pairs can only be split once; repeated use of this option results in no further splitting for those contact pairs already split.
- `DMP` - This option is similar to the SPLIT, but it is more automatic and contact pair splitting is done at the solution level ( [[solve|SOLVE]] ) of the first load step, not at the preprocessing level. This option is activated only in a distributed-memory parallel (DMP) run. For this option, `TRlevel` and `InterType` are valid; all other arguments are ignored.
- `MERGE` - Merge all contact sub-pairs that were previously split (by prior `Option` = SPLIT or DMP operations) back to their original pairs. Any contact and target elements deleted due to the trim logic of the splitting operation cannot be recovered by the MERGE operation. All other arguments are ignored.

**rid1**, **rid2**, **rinc**

The meanings of `RID1`, `RID2`, and `RINC` vary depending on the contact type or the `Option` specified, as described below. `RID1` accepts tabular input for some `Option` values. `RID1`, `RID2`, `RINC` are ignored when `Option` = DMP.

Pair-Based Contact For pair-based contact, the range of real constant pair IDs for which `Option` will be performed. If `RID2` is not specified, it defaults to `RID1`. If no value is specified, all contact pairs in the selected set of elements are considered.

General Contact For general contact ( `InterType` = GCN), `RID1` and `RID2` are section IDs associated with general contact surfaces instead of real constant IDs. If `RINC` = 0, the `Option` is performed between the two sections, `RID1` and `RID2`. If `RINC >` 0, the `Option` is performed among all specified sections ( `RID1` to `RID2` with increment of `RINC` ).

Contact Splitting For contact splitting at the preprocessing level ( `Option` = SPLIT only), `RID1`, `RID2`, and `RINC` are used as follows:

- If `RID1`, `RID2`, and `RINC` are non-zero and positive, split the contact pairs from real constant pair ID number `RID1` to `RID2` in increments of `RINC`. In this case, if `TRlevel` is non-zero, it will only be applied to these specified pairs.
- If `RID1` is zero or blank, `TRlevel` will take affect for all contact pairs in the model from largest to smallest.
- If `RID1`, `RID2`, `RINC`, and `TRlevel` are not defined, the program automatically determines the number of sub-pairs for splitting each contact pair.

Tabular Input for `RID1` `RID1` accepts tabular input in the form of a 2D array when `Option` = ADJUST, MORPH or TADJUST. In this case, `RID2`, `RINC`, `Val1`, `Val2`, and `Val3` are ignored. For more information, see [Physically Moving Contact Nodes Toward the Target Surface](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/Hlp_ctec_realkey.html#ctec_adjlrggap)

**intertype**

The type of contact interface ( [pair-based versus general contact](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctec_comppairgen.html#gcfeatnotsup) ) to be considered; or the type of contact pair to be trimmed/unselected/auto-set.

The following labels specify the type of contact interface:

- `(blank)` - Include all contact definitions (pair-based and general contact).
- `GCN` - Include general contact definitions only (not valid when `Option` = RESET or AUTO).

The following labels specify the type of contact pairs to be trimmed/unselected/auto-set (used only when `Option` = TRIM, UNSE, or AUTO, and only for pair-based contact definitions):

- `ANY` - All types (default).
- `MPC` - MPC-based contact pairs (KEYOPT(2) = 2).
- `BOND` - Bonded contact pairs (KEYOPT(12) = 3, 5, 6).
- `NOSP` - No separation contact pairs (KEYOPT(12) = 2, 4).
- `SMAL` - Small sliding contact pairs (KEYOPT(18) = 1).
- `SELF` - Self contact pairs (target surface completely overlaps contact surface).
- `INAC` - Inactive contact pairs (symmetric contact pairs for MPC contact or KEYOPT(8) = 2).

The following labels specify the type of contact pairs to be trimmed only when `Option` = SPLIT or DMP, and only for pair-based contact definitions:

- `(blank)` - The program automatically deletes inactive contact pairs defined by auto-asymmetric selection (KEYOPT(8) = 2). If `Option` = DMP, the program also trims split contact pairs that are associated with bonded contact (KEYOPT(12) = 5 or 6) or small sliding contact (KEYOPT(18) = 1).
- `TRIM` - The program automatically deletes inactive contact pairs defined by auto-asymmetric selection (KEYOPT(8) = 2), and also trims all split contact pairs.

**trlevel**

This argument is either the trimming level for trimming contact pairs or the number of sub-pairs for contact splitting.

Trimming level (used only when `Option` = TRIM, UNSE, or MORPH):

- `(blank)` - Normal trimming (default): remove/unselect contact and target elements which are in far-field.
- `AGGRE` - Aggressive trimming: remove/unselect contact and target elements which are in far- field, and certain elements in near-field.

Number of sub-pairs used for contact splitting (used only when `Option` = SPLIT or DMP):

- `(blank)` - The program automatically chooses the number of sub-pairs for splitting in order to achieve better scalability in a DMP run.
- `N` - Input a non-zero positive number to indicate the maximum number of sub-pairs for splitting the largest contact pair in the model. All other smaller contact pairs will be split following this number proportionally. The number you input may not always be honored; splitting may results in a fewer number of sub-pairs basing on many factors

**val1**, **val2**, **val3**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CNCHECK.html) for further information.

## Notes

The **CNCHECK** command provides information for surface-to-surface, node-to-surface, and line- to-line contact pairs (element types `TARGE169`, `TARGE170`, `CONTA172`, `CONTA174`, `CONTA175`, `CONTA177` ). All contact and target elements of interest, along with the solid elements and nodes attached to them, must be selected for the command to function properly. For performance reasons, the program uses a subset of nodes and elements based on the specified contact regions ( `RID1`, `RID2`, `RINC` ) when executing the **CNCHECK** command.

**CNCHECK** is available in both the PREP7 and SOLUTION processors, but only before the first solve operation (that is, only before the first load step or the first substep).

If the contact and target elements were generated through mesh commands ( [[amesh|AMESH]], [[lmesh|LMESH]], etc.) instead of the [[esurf|ESURF]] command, you must issue [[modmsh|MODMSH]],DETACH before **CNCHECK**. Otherwise, **CNCHECK** will not work correctly.

The following additional notes are available:

The command **CNCHECK**,POST solves the initial contact configuration in one substep. After issuing this command, you can postprocess the contact result items as you would for any other converged load step; however, only the contact status, contact penetration or gap, and contact pressure will have meaningful values. Other contact quantities (friction stress, sliding distance, chattering) will be available but are not useful.

In order to report the real geometric penetration and gap, the program internally sets KEYOPT(9) = 0 during the execution of **CNCHECK**,POST.

Because `Option` = POST forces a solve operation, the PrepPost (PP) license does not work with **CNCHECK**,POST.

If **CNCHECK**,POST is issued within the solution processor, the [[solve|SOLVE]] command that solves the first load step of your analysis should appear in a different step, as shown in the following example:

``` apdl
/SOLU
CNCHECK,POST
FINISH
...

/SOLU
SOLVE
FINISH
...
```

**CNCHECK**,POST writes initial contact results to a file named `jobname.rcn`. When postprocessing the initial contact state, you need to explicitly read results from this file using the [[file|FILE]] and [[set|SET]],FIRST commands in POST1 to properly read the corresponding contact data. Otherwise, the results may be read improperly. The following example shows a valid command sequence for plotting the initial contact gap:

``` apdl
/SOLU
CNCHECK,POST
FINISH
/POST1
FILE,Jobname,RCN
SET,FIRST
PLNSOL,CONT,GAP,0,1
FINISH
...
```

You can issue **CNCHECK**,ADJUST to physically move contact nodes to the target surface. Alternatively, you can issue **CNCHECK**,MORPH to physically move contact nodes to the target surface and then morph the underlying mesh to improve the mesh quality. See [Physically Moving Contact Nodes Toward the Target Surface](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/Hlp_ctec_realkey.html#ctec_adjlrggap) **CNCHECK**,ADJUST or **CNCHECK**,MORPH is issued within the solution processor, the [[solve|SOLVE]] command that solves the first load step of your analysis should appear in a different step:

``` apdl
/SOLU
CNCHECK,ADJUST
FINISH
...

/SOLU
SOLVE
FINISH
...
```

After issuing the **CNCHECK**,ADJUST command, the initial adjustment is converted to structural displacement values (UX, UY, UZ) and stored in a file named `jobname.rcn`. Similarly, the **CNCHECK**,MORPH command converts the initial adjustment of contact nodes as well as the morphing adjustment of solid element nodes to structural displacement values (UX, UY, UZ) and stores them in the `jobname.rcn` file. You can use this file to plot or list nodal adjustment vectors or create a contour plot of the adjustment magnitudes via the displacements. When postprocessing the nodal adjustment values, you need to explicitly read results from this file using the [[file|FILE]] and [[set|SET]],FIRST commands in POST1 to properly read the corresponding contact data. Otherwise, the results may be read improperly.

The `jobname.rcn` file contains information generated from the **CNCHECK**,POST, **CNCHECK**,ADJUST, **CNCHECK**,MORPH, or **CNCHECK**, TADJUST command. If multiple commands are issued in the same analysis, the file is overwritten by the last **CNCHECK** command.

You can issue **CNCHECK**,TADJUST to physically move the target body to the contact surface. This command tries to establish initial contact with penetration in a range specified by `PMAX` and `PMIN`. Similar to the ADJUST and MORPH options, the initial adjustment is converted to structural displacement values (UX, UY, UZ) and stored in the `jobname.rcn` file. This option accepts tabular input in the `RID1` field.

You can specify either a positive or negative value for `PMIN` and `PMAX`. The program interprets a positive value as a scaling factor and interprets a negative value as the absolute value.

For more information, see [Physically Moving the Target Body Toward the Contact Surface](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/Hlp_ctec_realkey.html#)

The command **CNCHECK**,RESET allows you to reset all but a few key options and real constants associated with the specified contact pairs ( `RID1`, `RID2`, `RINC` ) to their default values. This option is only valid for pair-based contact definitions.

The following key options and real constants remain unchanged when this command is issued:

(table not available in the PyMAPDL source, see the Ansys help page)

The command **CNCHECK**,AUTO automatically changes certain default or undefined key options and real constants to optimized settings or values. The changes are based on overall contact pair behaviors. In general, this command improves convergence for nonlinear contact analysis. This option is only valid for pair-based contact definitions.

The tables below list typical KEYOPT and real constant settings implemented by **CNCHECK**,AUTO. The actual settings implemented for your specific model may vary from what is described here. You should always verify the modified settings by issuing **CNCHECK**,DETAIL to list current contact pair properties.

(table not available in the PyMAPDL source, see the Ansys help page)

Set to 0 if KEYOPT(2) \> 1 for debonding.

Set to 1 if underlying elements are superelements, or if KEYOPT(9) = 2 was previously specified.

(table not available in the PyMAPDL source, see the Ansys help page)

PINB default depends on contact behavior (rigid vs. flexible target), [[nlgeom|NLGEOM]],ON or OFF, KEYOPT(9) setting, KEYOPT(12) setting, and the value of real constant CNOF (see ).

**CNCHECK**,AUTO also sets [[pred|PRED]],OFF for the case of a [force-distributed constraint](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/Hlp_ctec_surfcon.html#strbeamso1703) defined via [MPC contact](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/Hlp_ctec_restmpc.html).

You can issue **CNCHECK**,TRIM or **CNCHECK**,UNSEL to remove or unselect contact and target elements which are in far-field (that is, open and not near contact), or even in near-field if aggressive trimming logic is used ( `TRlevel` = AGGRE).

The SPLIT, DMP, and MERGE options are intended for use in a distributed-memory parallel (DMP) run. Use the command **CNCHECK**,SPLIT or **CNCHECK**,DMP to split large contact pairs into smaller sub-pairs so that the smaller contact pairs can be distributed into different cores, thereby improving performance. This functionality is not the same as manually splitting contact pairs during the modeling process. The program splitting logic performs the necessary exchange of data on the boundaries between the split contact pairs to ensure that the results with and without splitting are essentially identical.

The command **CNCHECK**,MERGE can be used to merge the sub-pairs together again, which is useful for postprocessing the contact results based on the original contact pair geometry. However, caution must be taken when a downstream analysis is performed since the MERGE operation may alter the database.

For more information, see [Solving Large Contact Models in a Distributed-Memory Parallel Environment](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctecsplitting.html#ctecsplitlimit)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CNCHECK.html
