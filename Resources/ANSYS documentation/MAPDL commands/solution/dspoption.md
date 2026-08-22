---
apdl: "DSPOPTION"
method: dspoption
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.dspoption
generated: 2026-08-22
tags: [mapdl-command]
---

# DSPOPTION

PyMAPDL: `mapdl.dspoption(reord_option='', memory_option='', memory_size='', solve_info='', **kwargs)`

Sets memory option for the sparse solver.

**Command default:**

Automatic memory allocation is used.

## Parameters

**reord_option**

Reordering option:

- `DEFAULT` - Use the default reordering scheme.
- `SEQORDER` - Use a sequential equation reordering scheme. Relative to PARORDER, this option typically results in longer equation ordering times and therefore longer overall solver times. Occasionally, however, this option will produce better quality orderings which decrease the matrix factorization times and improve overall solver performance.
- `PARORDER` - Use a parallel equation reordering scheme. Relative to SEQORDER, this option typically results in shorter equation ordering times and therefore shorter overall solver times. Occasionally, however, this option will produce lower quality orderings which increase the matrix factorization times and degrade overall solver performance.

**memory_option**

Memory allocation option:

- `DEFAULT` - Use the default memory allocation strategy for the sparse solver. The default strategy attempts to run in the INCORE memory mode. If there is not enough physical memory available when the solver starts to run in the INCORE memory mode, the solver will then attempt to run in the OUTOFCORE memory mode.
- `INCORE` - Use a memory allocation strategy in the sparse solver that will attempt to obtain enough memory to run with the entire factorized matrix in memory. This option uses the most amount of memory and should avoid doing any I/O. By avoiding I/O, this option achieves optimal solver performance. However, a significant amount of memory is required to run in this mode, and it is only recommended on machines with a large amount of memory. If the allocation for in-core memory fails, the solver will automatically revert to out-of-core memory mode.
- `OUTOFCORE` - Use a memory allocation strategy in the sparse solver that will attempt to allocate only enough work space to factor each individual frontal matrix in memory, but will share the entire factorized matrix on disk. Typically, this memory mode results in poor performance due to the potential bottleneck caused by the I/O to the various files written by the solver.
- `FORCE` - This option, when used in conjunction with the `Memory_Size` option, allows you to force the sparse solver to run with a specific amount of memory. This option is only recommended for the advanced user who understands sparse solver memory requirements for the problem being solved, understands the physical memory on the system, and wants to control the sparse solver memory usage.

**memory_size**: Initial memory size allocation for the sparse solver for each process ( `Memory_Size` /process in GB ). The `Memory_Size` setting should always be well within the physical memory available, but not so small as to cause the sparse solver to run out of memory. Warnings and/or errors from the sparse solver will appear if this value is set too low. If the FORCE memory option is used, this value is the amount of memory allocated for the entire duration of the sparse solver solution.

**solve_info**

Solver output option:

- `OFF` - Turns off additional output printing from the sparse solver (default).
- `PERFORMANCE` - Turns on additional output printing from the sparse solver, including a performance summary and a summary of file I/O for the sparse solver. Information on memory usage during assembly of the global matrix (that is, creation of the `Jobname.FULL` file) is also printed with this option.

## Notes

This command controls options related to the sparse solver in all analysis types where this solver can be used.

The amount of memory required for the sparse solver is unknown until the matrix structure is preprocessed, including equation reordering. The amount of memory allocated for the sparse solver is then dynamically adjusted to supply the solver what it needs to compute the solution.

If you have a large memory system, you may want to try selecting the INCORE memory mode for larger jobs to improve performance. Also, when running the sparse solver with many processors on the same machine or on a machine with very slow I/O performance (for example, slow hard drive speed), you may want to try using the INCORE memory mode to achieve better performance. However, doing so may require much more memory compared to running in the OUTOFCORE memory mode.

Running with the INCORE memory mode is best for jobs which comfortably fit within the limits of the physical memory on a given system. If the sparse solver workspace exceeds physical memory size, the system will be forced to use virtual memory (or the system page/swap file). In this case, it is typically more efficient to run with the OUTOFCORE memory mode.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DSPOPTION.html
