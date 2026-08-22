---
apdl: "WRFULL"
method: wrfull
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_options.LoadStepOptions.wrfull
generated: 2026-08-22
tags: [mapdl-command]
---

# WRFULL

PyMAPDL: `mapdl.wrfull(ldstep='', **kwargs)`

Stops solution after assembling global matrices.

## Parameters

**ldstep**

Specify action to take:

- `OFF or 0` - Turn off feature (default)
- `N` - Turn on feature and set it to stop after assembling the global matrices and writing the `.FULL` file for load step N.

## Notes

This command is used in conjunction with the [[solve|SOLVE]] command to generate the assembled matrix file ( `.FULL` file) only. The element matrices are assembled into the relevant global matrices for the particular analysis being performed and the `.FULL` file is written. Equation solution and the output of data to the results file are skipped. To dump the matrices written on the `.FULL` file into Harwell-Boeing format, use the [[hbmat|HBMAT]] command in /AUX2. To copy the matrices to a postscript format that can be viewed graphically, use the [[psmat|PSMAT]] command.

To use the [[lssolve|LSSOLVE]] macro with this command, you may need to modify the [[lssolve|LSSOLVE]] macro to properly stop at the load step of interest.

This command only valid for linear static, full harmonic, and full transient analyses when the sparse direct solver is selected. This command is also valid for buckling or modal analyses with any mode extraction method. This command is not valid for nonlinear analyses. It is not supported in a linear perturbation analysis.

In general, the assembled matrix file `.FULL` contains stiffness, mass, and damping matrices. However, the availability of the matrices depends on the analysis type chosen when the file is written. Some analyses do not write the matrices individually but instead write combined matrices. For example, a full transient writes a combined stiffness/mass/damping matrix to the full file.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_WRFULL.html
