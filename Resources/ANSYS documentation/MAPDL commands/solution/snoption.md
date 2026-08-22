---
apdl: "SNOPTION"
method: snoption
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.snoption
generated: 2026-08-22
tags: [mapdl-command]
---

# SNOPTION

PyMAPDL: `mapdl.snoption(rangefact='', blocksize='', robustlev='', compute='', solve_info='', **kwargs)`

Specifies Supernode (SNODE) eigensolver options.

**Command default:**

`RangeFact` = 2.0. `BlockSize` is set to min( `NMODE`,40), where `NMODE` is the number of modes to be computed as set on the [[modopt|MODOPT]] command. `RobustLev` = 0. `Compute` = BOTH. Additional output is not printed ( `Solve_Info` = OFF).

## Parameters

**rangefact**: Factor used to control the range of eigenvalues computed for each supernode. The value of `RangeFact` must be a number between 1.0 and 10.0. By default the `RangeFact` value is set to 2.0, which means that all eigenvalues between 0 and 2\* `FREQE` are computed for each supernode (where `FREQE` is the upper end of the frequency range of interest as specified on the [[modopt|MODOPT]] command). As the `RangeFact` value increases, the eigensolution for the SNODE solver becomes more accurate and the computational time increases.

**blocksize**: `BlockSize` to be used when computing the final eigenvectors. The value of `Blocksize` must be either MAX or a number between 1 and `NMODE`, where `NMODE` is the number of modes to be computed as set on the [[modopt|MODOPT]] command. Input a value of MAX to force the algorithm to allocate enough memory to hold all of the final eigenvectors in memory and, therefore, only read through the file containing the supernode eigenvectors once. Note that this setting is ONLY recommended when there is sufficient physical memory on the machine to safely hold all of the final eigenvectors in memory.

**robustlev**: Parameter used to control the robustness of the SNODE eigensolver. The value of `RobustLev` must be a number between 0 and 10. Lower values of `RobustLev` allow the eigensolver to run in the most efficient manner for optimal performance. Higher values of `RobustLev` often slow down the performance of the eigensolver, but can increase the robustness; this may be desirable if a problem is detected with the eigensolver or its eigensolution.

**compute**

Key to control which computations are performed by the Supernode eigensolver:

- `EVALUE` - The eigensolver computes only the eigenvalues.
- `EVECTOR` - The eigensolver computes only the eigenvectors (must be preceded by a modal analysis where the eigenvalues were computed using the Supernode eigensolver).
- `BOTH` - The eigensolver computes both the eigenvalues and eigenvectors in the same pass (default).

**solve_info**

Solver output option:

- `OFF` - Turns off additional output printing from the Supernode eigensolver (default).
- `PERFORMANCE` - Turns on additional output printing from the Supernode eigensolver, including a performance summary and a summary of file I/O for the Supernode eigensolver. Information on memory usage during assembly of the global matrices (that is, creation of the `Jobname.FULL` file) is also printed with this option.

## Notes

This command specifies options for the Supernode (SNODE) eigensolver.

Setting `RangeFact` to a value between 2.0 and 10.0 will improve the accuracy of the computed eigenvalues and eigenvectors, but will often increase the computing time of the SNODE eigensolver. Conversely, setting `RangeFact` to a value less than 2.0 will deteriorate the accuracy of the computed eigenvalues and eigenvectors, but will often speed up the computing time of the SNODE eigensolver. The default value of 2.0 has been set as a good blend of accuracy and performance. If the model has rigid body modes, setting `RangeFact` higher than 2 is recommended to achieve better solution accuracy for the lower flexible modes.

The SNODE eigensolver reads the eigenvectors and related information for each supernode from a file and uses that information to compute the final eigenvectors. For each eigenvalue/eigenvector requested by the user, the program must do one pass through the entire file that contains the supernode eigenvectors. By choosing a `BlockSize` value greater than 1, the program can compute `BlockSize` number of final eigenvectors for each pass through the file. Therefore, smaller values of `BlockSize` result in more I/O, and larger values of `BlockSize` result in less I/O. Larger values of `BlockSize` also result in significant additional memory usage, as `BlockSize` number of final eigenvectors must be stored in memory. The default `Blocksize` of min( `NMODE`,40) is normally a good choice to balance memory and I/O usage.

The `RobustLev` field should only be used when a problem is detected with the accuracy of the final solution or if the Supernode eigensolver fails while computing the eigenvalues/eigenvectors. Setting `RobustLev` to a value greater than 0 will cause the performance of the eigensolver to deteriorate. If the performance deteriorates too much or if the eigensolver continues to fail when setting the `RobustLev` field to higher values, then switching to another eigensolver such as Block Lanczos or PCG Lanczos is recommended.

Setting `Compute` = EVALUE causes the Supernode eigensolver to compute only the requested eigenvalues. During this process a `Jobname.SNODE` file is written; however, a `Jobname.MODE` file is not written. Thus, errors will likely occur in any downstream computations that require the `Jobname.MODE` file (for example, participation factor computations, mode superpostion transient/harmonic analysis, PSD analysis). Setting `Compute` = EVECTOR causes the Supernode eigensolver to compute only the corresponding eigenvectors. The `Jobname.SNODE` file and the associated `Jobname.FULL` file are required when requesting these eigenvectors. In other words, the eigenvalues must have already been computed for this model before computing the eigenvectors. This field can be useful in order to separate the two steps (computing eigenvalues and computing eigenvectors).

For more information on the eigensolver's accuracy and a discussion of its known limitations, see in the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SNOPTION.html
