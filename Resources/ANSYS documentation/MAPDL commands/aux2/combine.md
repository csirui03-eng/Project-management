---
apdl: "COMBINE"
method: combine
group: aux2
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux2.binary_file_manipulation.BinaryFileManipulation.combine
generated: 2026-08-22
tags: [mapdl-command]
---

# COMBINE

PyMAPDL: `mapdl.combine(filetype='', num='', **kwargs)`

Combines distributed memory parallel ( DMP ) files.

## Parameters

**filetype**

Type of solution file to combine. There is no default; if (blank), the command is ignored.

- `RST` - Structural results file ( `.RST` )
- `RTH` - Thermal results file ( `.RTH` )
- `RMG` - Magnetics results file ( `.RMG` )
- `RSTP` - Linear perturbation results file ( `.RSTP` )
- `EMAT` - Element matrix file ( `.EMAT` ).
- `ESAV` - Element saved data file ( `.ESAV` )
- `MODE` - Modal results file ( `.MODE` )
- `MLV` - Modal load vector file ( `.MLV` )
- `IST` - Initial state file ( `.IST` )
- `FULL` - Full matrix file ( `.FULL` )
- `RFRQ` - Reduced complex displacement file ( `.RFRQ` )
- `RDSP` - Reduced displacement file ( `.RDSP` )
- `RNNN` - Multiframe restart files ( `.Rnnn` )

**num**

Number of `.Rnnn` files to combine:

- `ALL` - Combine all `.Rnnn` files (default).
- `N` - Combine only `.RN` files, where N is an integer from 1 to 999.

## Notes

The **COMBINE** command is used within the AUX2 auxiliary processor to combine local solution files from a distributed memory parallel solution into a single, global file. Before using this command, you must enter the AUX2 processor by issuing the [[aux2|/AUX2]] command.

In a distributed-memory parallel ( DMP ) solution, you can use the [[dmpoption|DMPOPTION]] command to bypass the file combination step, causing all individual local files to be kept on the local disks in the current working directory. Later on, you can start a new distributed memory parallel solution and use the **COMBINE** command to combine local files into a global file for a downstream solution or another operation (such as postprocessing with [[post1|/POST1]] ). For example, the command **COMBINE**,RST will combine local results files ( `JobnameN.RST` ) into a global results file ( `Jobname.RST` ).

The **COMBINE** command cannot be used to combine local files generated during a distributed memory parallel solution that used the frequency or cyclic harmonic index domain decomposition method ( [[ddoption|DDOPTION]],FREQ or [[ddoption|DDOPTION]],CYCHI).

If **COMBINE**,RNNN is specified, all of the multiframe restart files named `Jobname.R001` to `Jobname.R999` will automatically be combined. To combine only one set of `.Rnnn` restart files, place only that set of restart files in your current working directory, or use the `NUM` argument to specify which set of `.Rnnn` files to combine.

When the **COMBINE** command is used in a subsequent distributed memory parallel (DMP) session, the number of processors must be the same as in the DMP solution that generated the files.

When running on a cluster, the local solution files must be available in the working directory on each node in the subsequent session. As an example, consider the following command line used to generate local solution files:

``` apdl
ansys232 -dis -machines machine1: 4: machine2: 1: machine3: 2-i input -o output
```

Different machines can be used in the subsequent session to combine these files. However, the total number of cores must remain unchanged (seven in the above case), and the local files must be copied to the working directory (or directories) on each of the machines used in the subsequent session.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_COMBINE.html
