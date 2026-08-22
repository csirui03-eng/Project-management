---
apdl: "BCSOPTION"
method: bcsoption
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.bcsoption
generated: 2026-08-22
tags: [mapdl-command]
---

# BCSOPTION

PyMAPDL: `mapdl.bcsoption(memory_option='', memory_size='', solve_info='', **kwargs)`

Sets memory option for the sparse solver.

**Command default:**

Automatic memory allocation is used.

## Parameters

**memory_option**

Memory allocation option:

- `DEFAULT` - Use the default memory allocation strategy for the sparse solver. The default strategy attempts to run in the INCORE memory mode. If there is not enough available physical memory when the solver starts to run in the INCORE memory mode, the solver will then attempt to run in the OUTOFCORE memory mode.
- `INCORE` - Use a memory allocation strategy in the sparse solver that will attempt to obtain enough memory to run with the entire factorized matrix in memory. This option uses the most amount of memory and should avoid doing any I/O. By avoiding I/O, this option achieves optimal solver performance. However, a significant amount of memory is required to run in this mode, and it is only recommended on machines with a large amount of memory. If the allocation for in-core memory fails, the solver will automatically revert to out-of-core memory mode.
- `OUTOFCORE` - Use a memory allocation strategy in the sparse solver that will attempt to allocate only enough work space to factor each individual frontal matrix in memory, but will store the entire factorized matrix on disk. Typically, this memory mode results in poor performance due to the potential bottleneck caused by the I/O to the various files written by the solver.
- `FORCE` - This option, when used in conjunction with the `Memory_Size` option, allows you to force the sparse solver to run with a specific amount of memory. This option is only recommended for the advanced user who understands sparse solver memory requirements for the problem being solved, understands the physical memory on the system, and wants to control the sparse solver memory usage.

**memory_size**: Initial memory size allocation for the sparse solver in GB. This argument allows you to tune the sparse solver memory and is not generally required. Although there is no upper limit for `Memory_Size`, the `Memory_Size` setting should always be well within the physical memory available, but not so small as to cause the sparse solver to run out of memory. Warnings and/or errors from the sparse solver will appear if this value is set too low. If the FORCE memory option is used, this value is the amount of memory allocated for the entire duration of the sparse solver solution.

**solve_info**

Solver output option:

- `OFF` - Turns off additional output printing from the sparse solver (default).
- `PERFORMANCE` - Turns on additional output printing from the sparse solver, including a performance summary and a summary of file I/O for the sparse solver. Information on memory usage during assembly of the global matrix (that is, creation of the `Jobname.FULL` file) is also printed with this option.

## Notes

This command controls options related to the sparse solver in all analysis types where the sparse solver can be used. It also controls the Block Lanczos eigensolver in a modal or buckling analysis.

The sparse solver runs from one large work space (that is, one large memory allocation). The amount of memory required for the sparse solver is unknown until the matrix structure is preprocessed, including equation reordering. The amount of memory allocated for the sparse solver is then dynamically adjusted to supply the solver what it needs to compute the solution.

If you have a very large memory system, you may want to try selecting the INCORE memory mode for larger jobs to improve performance. When running the sparse solver on a machine with very slow I/O performance (for example, slow hard drive speed), you may want to try using the INCORE memory mode to achieve better performance. However, doing so may require much more memory compared to running in the OUTOFCORE memory mode.

Running with the INCORE memory mode is best for jobs which comfortably fit within the limits of the physical memory on a given system. If the sparse solver work space exceeds physical memory size, the system will be forced to use virtual memory (or the system page/swap file). In this case, it is typically more efficient to run with the OUTOFCORE memory mode. Assuming the job fits comfortably within the limits of the machine, running with the INCORE memory mode is often ideal for jobs where repeated solves are performed for a single matrix factorization. This occurs in a modal or buckling analysis or when doing multiple load steps in a linear, static analysis.

For repeated runs with the sparse solver, you may set the initial sparse solver memory allocation to the amount required for factorization. This strategy reduces the frequency of allocation and reallocation in the run to make the INCORE option fully effective. If you have a very large memory system, you may use the `Memory_Size` argument to increase the maximum size attempted for in-core runs.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BCSOPTION.html
