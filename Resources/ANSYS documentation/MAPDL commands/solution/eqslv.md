---
apdl: "EQSLV"
method: eqslv
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.eqslv
generated: 2026-08-22
tags: [mapdl-command]
---

# EQSLV

PyMAPDL: `mapdl.eqslv(lab='', toler='', mult='', keepfile='', **kwargs)`

Specifies the type of equation solver.

**Command default:**

The sparse direct solver is the default solver for all analyses, with the exception of modal/buckling analyses.

For modal/buckling analyses, there is no default solver. You must specify a solver with the [[modopt|MODOPT]] or [[bucopt|BUCOPT]] command. The specified solver automatically chooses the required internal equation solver (for example, [[modopt|MODOPT]] ,LANPCG automatically uses **EQSLV**,PCG internally, and [[bucopt|BUCOPT]],LANB automatically uses **EQSLV**,SPARSE internally).

## Parameters

**lab**

Equation solver type:

- `SPARSE` - Sparse direct equation solver. Applicable to real-value or complex-value symmetric and unsymmetric matrices. Available only for STATIC, HARMIC (full method only), TRANS (full method only), SUBSTR, and PSD spectrum analysis types ( [[antype|ANTYPE]] ). Can be used for nonlinear and linear analyses, especially nonlinear analysis where indefinite matrices are frequently encountered. Well suited for contact analysis where contact status alters the mesh topology. Other typical well- suited applications are: (a) models consisting of shell/beam or shell/beam and solid elements (b) models with a multi-branch structure, such as an automobile exhaust or a turbine fan. This is an alternative to iterative solvers since it combines both speed and robustness. Generally, it requires considerably more memory (~10x) than the PCG solver to obtain optimal performance (running totally in-core). When memory is limited, the solver works partly in-core and out-of-core, which can noticeably slow down the performance of the solver. See the [[bcsoption|BCSOPTION]] command for more details on the various modes of operation for this solver.

  This solver can be run using shared-memory parallel (SMP), distributed-memory parallel (DMP), or hybrid parallel processing. For DMP, this solver preserves all of the merits of the classic or shared memory sparse solver. The total sum of memory (summed for all processes) is usually higher than the shared memory sparse solver. System configuration also affects the performance of the distributed memory parallel solver. If enough physical memory is available, running this solver in the in-core memory mode achieves optimal performance. The ideal configuration when using the out-of- core memory mode is to use one processor per machine on multiple machines (a cluster), spreading the I/O across the hard drives of each machine, assuming that you are using a high-speed network such as Infiniband to efficiently support all communication across the multiple machines.

  This solver supports use of the [GPU accelerator capability](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_dan/gputrouble.html).

- `JCG` - Jacobi Conjugate Gradient iterative equation solver. Available only for STATIC, HARMIC (full method only), and TRANS (full method only) analysis types ( [[antype|ANTYPE]] ). Can be used for structural, thermal, and multiphysics applications. Applicable for symmetric, unsymmetric, complex, definite, and indefinite matrices. Recommended for 3D harmonic analyses in structural and multiphysics applications. Efficient for heat transfer, electromagnetics, piezoelectrics, and acoustic field problems.

  This solver can be run using shared-memory parallel (SMP), distributed-memory parallel (DMP), or hybrid parallel processing. For DMP, in addition to the limitations listed above, this solver only runs in a distributed parallel fashion for STATIC and TRANS (full method) analyses in which the stiffness is symmetric and only when not using the fast thermal option ( [[thopt|THOPT]] ). Otherwise, this solver disables distributed-memory parallelism at the onset of the solution, and shared-memory parallelism is used instead.

  This solver supports use of the [GPU accelerator capability](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_dan/gputrouble.html). When using the GPU accelerator capability, in addition to the limitations listed above, this solver is available only for STATIC and TRANS (full method) analyses where the stiffness is symmetric and does not support the fast thermal option ( [[thopt|THOPT]] ).

- `ICCG` - Incomplete Cholesky Conjugate Gradient iterative equation solver. Available for STATIC, HARMIC (full method only), and TRANS (full method only) analysis types ( [[antype|ANTYPE]] ). Can be used for structural, thermal, and multiphysics applications, and for symmetric, unsymmetric, complex, definite, and indefinite matrices. The ICCG solver requires more memory than the JCG solver, but is more robust than the JCG solver for ill-conditioned matrices.

  This solver can only be run in shared-memory parallel mode. If it is run in DMP mode, this solver disables distributed-memory parallelism at the onset of the solution, and shared-memory parallelism is used instead

  This solver does not support use of the [GPU accelerator capability](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_dan/gputrouble.html).

- `QMR` - Quasi-Minimal Residual iterative equation solver. Available for the HARMIC (full method only) analysis type ( [[antype|ANTYPE]] ). Can be used for symmetric, complex, definite, and indefinite matrices. The QMR solver is more stable than the ICCG solver.

  This solver can only be run in shared memory parallel mode and only supports 1 core. If it is run in DMP mode, this solver disables distributed-memory parallelism at the onset of the solution, and shared-memory parallelism is used instead

  This solver does not support use of the [GPU accelerator capability](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_dan/gputrouble.html).

- `PCG` - Preconditioned Conjugate Gradient iterative equation solver (licensed from Computational Applications and Systems Integration, Inc.). Requires less disk file space than SPARSE and is faster for large models. Useful for plates, shells, 3D models, large 2D models, and other problems having symmetric, sparse matrices. Such matrices are typically positive definite, but could be indefinite for some nonlinear analyses. The PCG solver can also be used for single-field thermal analyses involving unsymmetric matrices. Requires twice as much memory as JCG. Available only for analysis types ( [[antype|ANTYPE]] ) STATIC, TRANS (full method only), or MODAL (with PCG Lanczos option only). Also available for the use pass of substructure analyses ( `MATRIX50` ). The PCG solver can robustly handle models that involve the use of constraint and/or coupling equations ( [[ce|CE]], [[ceintf|CEINTF]], [[cp|CP]], [[cpintf|CPINTF]], and [[cerig|CERIG]] ). With this solver, you can use the [[msave|MSAVE]] command to obtain a considerable memory savings.

  The PCG solver can handle ill-conditioned problems by using a higher level of difficulty (see [[pcgopt|PCGOPT]] ). Ill-conditioning arises from elements with high aspect ratios, contact, and plasticity.

  This solver can be run in shared-memory parallel or distributed-memory parallel mode. In DMP mode, this solver preserves all of the merits of the classic or shared-memory PCG solver. The total sum of memory (summed for all processes) is about 30% more than the shared-memory PCG solver.

  This solver supports use of the [GPU accelerator capability](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_dan/gputrouble.html).

**toler**

Iterative solver tolerance value. Used only with the Jacobi Conjugate Gradient, Incomplete Cholesky Conjugate Gradient, Pre-conditioned Conjugate Gradient, and Quasi-Minimal Residual equation solvers. For the PCG solver, the default is 1.0E-8. When using the PCG Lanczos mode extraction method, the default solver tolerance value is 1.0E-4. For the JCG and ICCG solvers with symmetric matrices, the default is 1.0E-8. For the JCG and ICCG solvers with unsymmetric matrices, and for the QMR solver, the default is 1.0E-6. Iterations continue until the SRSS norm of the residual is less than `TOLER` times the norm of the applied load vector. For the PCG solver in the linear static analysis case, 3 error norms are used. If one of the error norms is smaller than `TOLER`, and the SRSS norm of the residual is smaller than 1.0E-2, convergence is assumed to have been reached. See [Iterative Solver](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool8.html#eq464eb6bb-fd2e-4e26-bc92-38d0e6628891)

When used with the Pre-conditioned Conjugate Gradient equation solver, `TOLER` can be modified between load steps (this is typically useful for nonlinear analysis).

If a `Lev_Diff` value of 5 is specified on the [[pcgopt|PCGOPT]] command (either program- or user- specified), `TOLER` has no effect on the accuracy of the obtained solution from the PCG solver; a direct solver is used when `Lev_Diff` = 5.

**mult**: Multiplier (defaults to 2.5 for nonlinear analyses; 1.0 for linear analyses) used to control the maximum number of iterations performed during convergence calculations. Used only with the Pre- conditioned Conjugate Gradient equation solver (PCG). The maximum number of iterations is equal to the multiplier ( `MULT` ) times the number of degrees of freedom (DOF). If `MULT` is input as a negative value, then the maximum number of iterations is equal to abs( `MULT` ). Iterations continue until either the maximum number of iterations or solution convergence has been reached. In general, the default value for `MULT` is adequate for reaching convergence. However, for ill- conditioned matrices (that is, models containing elements with high aspect ratios or material type discontinuities) the multiplier may be used to increase the maximum number of iterations used to achieve convergence. The recommended range for the multiplier is 1.0 (equation omitted) `MULT` (equation omitted) 3.0. Normally, a value greater than 3.0adds no further benefit toward convergence, and merely increases timerequirements. If the solution does not converge with 1.0 (equation omitted) `MULT` (equation omitted) 3.0, or in less than 10,000 iterations,then convergence is highly unlikely and further examination of themodel is recommended. Rather than increasing the default value of `MULT`, consider increasing the level of difficulty ( `Lev_Diff` ) on the [[pcgopt|PCGOPT]] command.

**keepfile**

Determines whether files from a SPARSE solver run should be deleted or retained. Applies only to `Lab` = SPARSE for static and full transient analyses.

- `DELE` - Deletes all files from the SPARSE solver run, including the factorized file, `.DSPsymb`, upon [[finish|FINISH]] or `/EXIT` (default).
- `KEEP` - Retains all necessary files from the SPARSE solver run, including the `.DSPsymb` file, in the working directory.

## Notes

The selection of a solver can affect the speed and accuracy of a solution. For a more detailed discussion of the merits of each solver, see [Solution](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS3_stopsolmatrix.html) in the [Basic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/afbRsqe0ldm.html).

This command is also valid in PREP7.

Distributed-Memory Parallel (DMP) Restriction All equation solvers are supported in a DMP analysis. However, the SPARSE and PCG solvers are the only distributed solvers that always run a fully distributed solution. The JCG solver runs in a fully distributed mode in some cases; in other cases, it does not. The ICCG and QMR solvers are not distributed solvers; therefore, you will not see the full performance improvements with these solvers that you would with a fully distributed solution.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EQSLV.html
