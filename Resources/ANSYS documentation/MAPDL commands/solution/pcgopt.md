---
apdl: "PCGOPT"
method: pcgopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.pcgopt
generated: 2026-08-22
tags: [mapdl-command]
---

# PCGOPT

PyMAPDL: `mapdl.pcgopt(lev_diff='', fallback='', reduceio='', strmck='', wrtfull='', lm_key='', **kwargs)`

Controls PCG solver options.

## Parameters

**lev_diff**

Indicates the level of difficulty of the analysis. Valid settings are AUTO or 0 (default), 1, 2, 3, 4, or 5. This option applies to both the PCG solver when used in static and full transient analyses and to the PCG Lanczos method in modal analyses.

- Specify AUTO to allow Mechanical APDL to select the proper level of difficulty for the model.
- Lower values (1 or 2) generally provide the best performance for well-conditioned problems.
- Values of 3 or 4 generally provide the best performance for ill-conditioned problems; however, higher values may increase the solution time for well-conditioned problems. Higher level-of- difficulty values typically require more memory.
- The highest value of 5 essentially performs a factorization of the global matrix (similar to the sparse solver) and may require a very large amount of memory. This level is generally recommended for small- to medium-sized problems when using the PCG Lanczos mode-extraction method.

For example, models containing elongated elements (that is, elements with high aspect ratios) and models containing contact elements can lead to ill-conditioned problems. To determine if your problem is ill-conditioned, view the `Jobname.PCS` file to see the number of PCG iterations needed to reach a converged solution. Generally, static or full transient solutions that require more than 1500 iterations are considered to be ill-conditioned for the PCG solver.

**fallback**

Controls whether Mechanical APDL switches to the sparse direct solver automatically ( [[eqslv|EQSLV]],SPARSE) under certain conditions. (The criteria are listed below.) When Mechanical APDL switched the equation solver, the simulation attempts to continue without interruption.

- `AUTO` - Automatically switch to the sparse solver when one of the following conditions apply (default):
  - The assembled matrix is detected to be indefinite.
  - The PCG solver requires more than 2000 iterations to reach convergence.
  - The PCG solver fails to converge.
- `ON` - More aggressive fallback criteria. Automatically switch to the sparse solver when one of the following conditions apply:
  - The assembled matrix is detected to be indefinite.
  - The PCG solver requires more than 1500 iterations to reach convergence.
  - The PCG solver fails to converge.
- `OFF` - Disables the fallback logic so that there is no automatic switching, and only the PCG solver is used to solve the equations for this simulation.

After switching to the sparse solver, the program reverts back to the PCG solver under certain conditions. See the Notes section for details.

**reduceio**

Controls whether the PCG solver will attempt to reduce I/O performed during equation solution:

- `AUTO` - Automatically chooses whether to reduce I/O or not (default).
- `YES` - Reduces I/O performed during equation solution in order to reduce total solver time.
- `NO` - Does NOT reduce I/O performed during equation solution.

This option applies to both the PCG solver when used in static and full transient analyses and to the PCG Lanczos method in modal analyses.

**strmck**

Controls whether or not a Sturm sequence check is performed:

- `OFF` - Does NOT perform Sturm sequence check (default).
- `ON` - Performs Sturm sequence check

This option applies only when using the PCG Lanczos method in modal analyses. When using this option, a factorization must be performed and will require a very large amount of memory for extra computations. This option is generally recommended for small- to medium-sized problems. If the Sturm sequence check takes a large amount of computing time, use the `Jobname.ABT` file to abort the Sturm check, or press the STOP button if in interactive mode.

**wrtfull**

Controls whether or not the `.FULL` file is written.

- `ON` - Write `.FULL` file (default)
- `OFF` - Do not write `.FULL` file.

This option applies only when using the PCG Lanczos method in modal analyses because the `.FULL` file is never written when using the PCG solver in static or full transient analyses.

If using [[msave|MSAVE]],ON and conditions for the [[msave|MSAVE]] command are met, a complete `.FULL` file is never written regardless of this option.

If constraint equations are present in the model, a `.FULL` file is always written regardless of this option.

This option is useful in a distributed-memory parallel processing analysis because assembling the global stiffness and mass matrices on the head compute node before writing the `.FULL` file can take a considerable amount of memory. By setting `Wrtfull` = OFF, this assembly process is skipped on the head compute node, decreasing the amount of memory required to compute the modes and mode shapes. `Wrtfull` = OFF does not affect the results for the modes and mode shapes. However, without a `.FULL` file, the participation factor table computations do not occur.

To generate the `.FULL` file, such as for a harmonic, transient mode-superposition, or spectrum analysis, rerun the modal analysis with `Wrtfull` = ON, or use the [[wrfull|WRFULL]] command.

**lm_key**

Controls use of the PCG solver for `MPC184` elements that involve the Lagrange multiplier method. This option applies only to the PCG solver when used in static analyses, full transient analyses, and modal analyses that use the PCG Lanczos mode-extraction method ( [[modopt|MODOPT]],LANPCG).

- `ON` - Allow use of the PCG solver with certain `MPC184` element types that use the Lagrange multiplier method. (default)
- `OFF` - Do not use the PCG solver with any `MPC184` element types that use the Lagrange multiplier method.

The Lagrange multiplier method used by `MPC184` elements transfers the Lagrange multipliers into multiple point constraints and, hence, can be solved by the PCG solver. The current `MPC184` element types supported are: [rigid beam](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_MPC184link.html#mpc184linkprores), [rigid link](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_MPC184link.html#mpc184linkprores), [slider](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_MPC184slid.html#mpc184slidprores), [revolute joint](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_MPC184revo.html#mpc184revoprores), [universal joint](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_MPC184univ.html#mpc184univprores), [translational joint](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_MPC184tran.html#mpc184transprores), [cylindrical joint](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_MPC184cyl.html#mpc184cylinprores), [weld joint](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_MPC184weld.html#mpc184weldprores), [spherical joint](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_MPC184sphe.html#mpc184spherprores), and [general joint](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_MPC184gen.html#mpc184generprores) . For all other `MPC184` element types, the PCG solver cannot be used, and the equation solver automatically switches to the sparse solver regardless of the `LM_Key` setting on **PCGOPT**. The [[msave|MSAVE]] command does not support the `LM_Key` = ON option.

## Notes

`ReduceIO` works independently of the [[msave|MSAVE]] command in the PCG solver. Setting `ReduceIO` to YES can significantly increase the memory usage in the PCG solver.

To minimize the memory used by the PCG solver with respect to the `Lev_Diff` option only, set `Lev_Diff` = 1 if you do not have sufficient memory to run the PCG solver with `Lev_Diff` = AUTO.

The [[msave|MSAVE]],ON command is not valid in these circumstances:

- when `Lev_Diff` = 5; in this case, the `Lev_Diff` value will automatically be reset to 2.
- with the `StrmCk` option; in this case, `StrmCk` will be set to OFF.
- when the `Fallback` option is enabled (set to AUTO or ON); in this case, `Fallback` will automatically be reset to OFF.

For Lagrange-formulation contact methods and mixed u-P formulations, the PCG solver cannot be used, and the sparse solver is required.

`Fallback` logic is automatically disabled ( `Fallback` = OFF) in these circumstances:

- for analyses that include `MPC184` elements using the Lagrange multiplier method to impose kinematic constraints
- for thermal analyses that use the quasi-static ( [[thopt|THOPT]],QUASI) option.

**Reverting to the PCG Solver After an Automatic Switch to the Sparse Solver**

**Linear Analysis:** When fallback logic is enabled ( `Fallback` = AUTO or ON) and the program switches to the sparse direct solver during a linear analysis, the sparse solver is used for the remainder of the simulation unless the solver choice is changed by issuing the [[eqslv|EQSLV]] command between load steps.

**Nonlinear Analysis:** If the program switches to the sparse direct solver during a nonlinear analysis, the sparse solver is used for the remaining equilibrium iterations of the current substep. The program reverts back to the PCG solver at the end of the current substep unless one of the following conditions apply:

- The previous call to the sparse solver involved an indefinite or near-singular matrix.
- The last equilibrium iteration of the current substep using the sparse solver was faster than the last successful equilibrium iteration using the PCG solver.
- Three consecutive fallback switches between the sparse and the PCG solvers have occurred.

For both linear and nonlinear analyses, the solver choice can be changed using the [[eqslv|EQSLV]] command between any subsequent load steps.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PCGOPT.html
