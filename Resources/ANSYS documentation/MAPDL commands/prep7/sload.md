---
apdl: "SLOAD"
method: sload
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.sload
generated: 2026-08-22
tags: [mapdl-command]
---

# SLOAD

PyMAPDL: `mapdl.sload(secid='', plnlab='', kinit='', kfd='', fdvalue='', lsload='', lslock='', **kwargs)`

Loads a pretension section.

**Command default:**

The default pretension load value `FDVALUE` is zero (no load). A positive value puts the pretension elements in tension.

No default exists for the `LSLOAD` applied load step value. You must specify the load step in which to apply the `FDVALUE`.

No default exists for the `LSLOCK` locked load step value. You must specify the load step in which to lock the `FDVALUE`.

## Parameters

**secid**: Unique section number. The number must already be assigned to a pretension section.

**plnlab**

Label representing the pretension load sequence number in the format "PL `nn` " where `nn` is an integer from 1 through 99 (for example, PL01 through PL99).

Specify a value of DELETE to delete all loads on the specified pretension section ( `SECID` ). In this case, the command ignores any other argument values.

**kinit**

Initial action key for pretension load PL01. (This field is omitted for PL02 and up.) Three scenarios are possible:

- `LOCK` - Constrains (connects) the cutting plane on the pretension section. This value is the default.
- `SLID` - Unconstrains (disconnects) the cutting plane on the pretension section.
- `TINY` - Applies a very small pretension load (0.1% of `FDVALUE` ) before the desired load is established. The small load prevents convergence problems which can occur when the desired load is not established in the first load step. This value is valid only if `KFD` = FORC.

**kfd**

Force/Displacement key. Specifies whether `FDVALUE` is a force or a displacement:

- `FORC` - Apply a force on the specified pretension section. This value is the default.
- `DISP` - Apply a displacement (adjustment) on the specified pretension section.

**fdvalue**: Pretension load value. If `KFD` = FORC, this value is a pretension force. If `KFD` = DISP, this value is a pretension displacement (adjustment).

**lsload**: Load step in which to apply the `FDVALUE`.

**lslock**: The load step in which the displacement value resulting from the pretension force is locked. This value is valid only if `KFD` = FORC.

## Notes

The **SLOAD** command applies pretension loads to specified pretension sections ( `PRETS179` -based) created via the [[psmesh|PSMESH]] command. A pretension load is ramp-applied ( [[kbc|KBC]] = 0) if it is a force ( `KFD` = FORC), and step-applied ( [[kbc|KBC]] = 1) if it is a displacement ( `KFD` = DISP).

You can lock the load value at a specified load step. When locked, the load changes from a force to a displacement, and the program applies the load as a constant displacement in all future load steps. Locking is useful when applying additional loadings. The additional loadings alter the effect of the initial load value, but because locking transforms the load into a displacement, it preserves the initial load's effect.

In modal and harmonic analyses, any pretension load (force, displacement, or locked) is ignored and no load is produced.

The **SLOAD** command is not valid for `MPC184` -based preload sections created with [[psmesh|PSMESH]].

> **Example: Applying a Load**
>
> The following command shows how to establish loads on a pretension section:
>
> ``` apdl
> SLOAD,1,PL01,TINY,FORC,5000,2,3
> ```
>
> In this example, the load is applied to pretension section
>
> ``` apdl
> 1
> ```
>
> , and the sequence begins with the initial action key, `KINIT`, set to `TINY`. A small stabilization load (5 = 0.10% of 5000) is applied in the first load step, as the actual pretension force is not applied until the second load step. The next four fields set the actual load: the `KFD` value `FORC` specifies the type of load, `FDVALUE` defines the pretension load value ( `5000` ), `LSLOAD` specifies the load step in which the force is applied ( `2` ), and the `LSLOCK` field specifies the load step in which the force is locked ( `3` ). Additional sets of four fields can be used to define additional loads.
>
> **Example: Editing an Existing Load**
>
> You can use the **SLOAD** command to edit (overwrite) existing loads on a pretension section. This example changes the load on pretension section 1 (set above) to 6000:
>
> ``` apdl
> SLOAD,1,PL01,,,6000,2,3
> ```
>
> Unspecified values (blank fields), as shown in this example, remain unchanged from prior settings. If no prior specifications exist, then default values ( `KINIT` = LOCK and `KFD` = FORC) apply.
>
> **Example: Deleting All Loads**
>
> The command can also delete all loads on a specified pretension section, as shown here:
>
> ``` apdl
> SLOAD,1,DELETE
> ```
>
> **Example: Locking a Pretension Element**
>
> For a prestressed modal analysis, this command locks the pretension element:
>
> ``` apdl
> SLOAD,1,PL01,LOCK,DISP,0,1,2
> ```

**Multiple Loadings** The **SLOAD** command allows you to apply multiple loadings. You can add up to 15 loadings (PL01 through PL15), or delete loadings, for any given pretension section(s).

> **Example: Applying Multiple Loadings**
>
> The following **SLOAD** commands, issued in the order shown, establish a pretension load sequence in pretension section 2 with a force of 25 in load step (LS) 2, locked in LS 3-6, a force of 50 in LS 7, locked in LS 8-11, a force of 75 in LS 12, locked in LS 13 and beyond:
>
> ``` apdl
> SLOAD,2,PL01,LOCK,FORC,25,2,3
> ```
>
> ``` apdl
> SLOAD,2,PL02,,FORC,50,7,8
> ```
>
> ``` apdl
> SLOAD,2,PL03,,FORC,75,12,13
> ```
>
> At the same time, you can issue SLOAD commands to apply loads on other pretension sections. For example, in addition to the commands listed above, you could issue the following command to apply a load on pretension section 3:
>
> ``` apdl
> SLOAD,3,PL01,LOCK,FORC,25,3,4
> ```

Any addition or deletion of a loading applies to the selected sections only. Mechanical APDL does not apply or delete a load until you click the Apply or OK button.

After you have successfully solved for a specified `LSLOAD` (GUI field Apply at LS ) and eventually `LSLOCK` (GUI field Lock at LS ) value, you cannot modify that loading's settings during subsequent steps of the analysis. Similarly, you cannot delete loadings that you have already partially or completely solved.

You can select more than one pretension section at a time in order to specify identical loadings on them. Before you completely solve a given loading, any combination of pretension sections is valid. The following limitations apply:

\* After you have completely solved one or more loadings, Mechanical APDL allows multiple selection of only those pretension sections having

- \- the same number of defined loadings, and \* - the identical loading number from the most recent

  completely solved loading.

- A multiple selection meeting the necessary criteria retains the settings that are identical for all selected pretension sections and leaves all other fields blank.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SLOAD.html
