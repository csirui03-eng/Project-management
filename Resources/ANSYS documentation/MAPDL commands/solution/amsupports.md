---
apdl: "AMSUPPORTS"
method: amsupports
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.additive_manufacturing.AdditiveManufacturing.amsupports
generated: 2026-08-22
tags: [mapdl-command]
---

# AMSUPPORTS

PyMAPDL: `mapdl.amsupports(nsupports='', compname='', sectarray='', **kwargs)`

Specifies information about the supports in an [additive manufacturing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_cal.html) analysis.

## Parameters

**nsupports**: Number of supports.

**compname**: Root name of the components containing the elements comprising each support. (For example, if `CompName` = "MySupport," MySupport1 represents support 1, MySupport2 represents support 2, etc.)

**sectarray**: Name of the array ( [[dim|*DIM]] ) containing the section-reference ID for each support.

## Notes

The section-reference ID array ( `SectArray` ) is `NSUPPORTS` long, with each array member representing a section-reference ID of a corresponding support.

[[sectype|SECTYPE]] specifies the type of support, and [[secdata|SECDATA]] specifies the geometry of the support.

> **Example: Specifying Support Information in an Additive Manufacturing Analysis**
>
> ``` apdl
> ! specify supports
> *dim,suppsect,,2               ! two supports
> suppsect(1)=101                ! support 1 sectID=101
> suppsect(2)=101                ! support 2 sectID=101
> !
> sectype,101,support,block      ! sectype is a block support
> secdata,.07,1                  ! wall thickness and spacing
> amsupport,2,support,suppsect   ! root name is "support" and suppsect is the
>                                !   array name containing the section IDs
> ```

This command is also valid in PREP7.

For more information, including a list of the elements and commands used in an additive manufacturing analysis, see [AM Process Simulation in Workbench Additive](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_AM_in_WB.html#add_ag_load_addon)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AMSUPPORTS.html
