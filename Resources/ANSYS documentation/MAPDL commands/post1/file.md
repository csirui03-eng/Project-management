---
apdl: "FILE"
method: file
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.set_up.SetUp.file
generated: 2026-08-22
tags: [mapdl-command]
---

# FILE

PyMAPDL: `mapdl.file(fname='', ext='', **kwargs)`

Specifies the data file where results are to be found.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). If `Fname` is blank, the extension defaults to RST (for structural, fluid, or coupled-field analyses), to RTH (for thermal or electrical analyses), or to RMG (for magnetic analyses). For postprocessing contact results corresponding to the initial contact state in POST1, use the RCN extension. For postprocessing modal coordinates results in POST1, use the RDSP or RFRQ extension.

## Notes

Specifies the Mechanical APDL data file where the results are to be found for postprocessing.

Issuing the **FILE** command with `Ext` = RSDP or RFRQ in POST1 specifies the `.rsdp` or `.rfrq` file used by the [[prmc|PRMC]] and [[plmc|PLMC]] commands. (See POST1 example below.)

**Example Usage**

### POST1

``` apdl
/POST1
FILE,,rdsp   !Choose file Jobname.rdsp from a previous MSUP transient solution
PRMC,2,1     !Plot Modal coordinates from rdsp file (loadstep and substep specified as arguments)
FILE,,rst    !Choose file Jobname.rst
SET,1,1      !Load results from chosen.rst file into database
PRNSOL,u,x   !Plot Nodal displacements (loadstep and substep specified using the SET command)
FINISH       !Exit POST1
```

### POST26

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FILE.html
