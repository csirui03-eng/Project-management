---
apdl: "NLDIAG"
method: nldiag
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.nldiag
generated: 2026-08-22
tags: [mapdl-command]
---

# NLDIAG

PyMAPDL: `mapdl.nldiag(label='', key='', maxfile='', **kwargs)`

Sets nonlinear diagnostics functionality.

## Parameters

**label**

Diagnostic function:

- `NRRE` - Store the Newton-Raphson residuals information.
- `EFLG` - Identify or display elements or nodes that violate the criteria.
- `CONT` - Write contact information to a single `Jobname.cnd` diagnostic text file during solution.

**key**

Diagnostic function characteristics:

- `OFF or 0` - Suppresses writing of diagnostic information (default).
- `ON or 1` - Writes diagnostic information to the `Jobname.ndxxx`, `Jobname.nrxxx`, or `Jobname.cnd` file. (If `Label` = CONT, this option is the same as the SUBS option described below.)
- `ITER` - Writes contact diagnostic information at each iteration. Valid only when `Label` = CONT.
- `SUBS` - Writes contact diagnostic information at each substep. Valid only when `Label` = CONT.
- `LSTP` - Writes contact diagnostic information at each load step. Valid only when `Label` = CONT.
- `STAT` - Lists information about the diagnostic files in the current working directory.
- `DEL` - Deletes all diagnostic files in the current working directory.

**maxfile**

Maximum number of diagnostic files to create. Valid values are 1 through 999. Default = 4. Valid only when `Label` = NRRE or EFLG.

Information is written to `Jobname.ndxxx` or `Jobname.nrxxx`, where `xxx` iterates from 001 through `MAXFILE`. When the specified maximum number of diagnostic files is reached, the counter resets to 001 and earlier files are overwritten. The `MAXFILE` value specified for this `Label` function applies until a new value is specified.

## Notes

The **NLDIAG** command is a nonlinear diagnostics tool valid for nonlinear analyses that include structural degrees of freedom. It is a debugging tool for use when you must restart after an unconverged solution. The command creates `Jobname.ndxxx`, `Jobname.nrxxx`, or `Jobname.cnd` files in the working directory to store the information you specify.

For more information, see.

Issue the **NLDIAG**,NRRE,ON command to create `Jobname.nrxxx` diagnostic files (for each equilibrium iteration after the first) in which to store the relevant Newton-Raphson residual information of FX, FY, FZ (forces), MX, MY, MZ (moments), HEAT (heat flow), AMPS (current flow), CHRG (electric charge), or RATE (diffusion flow rate) for the last `MAXFILE` equilibrium iterations.

Issue a [[nldpost|NLDPOST]],NRRE,STAT command to list the load step, substep, time, and equilibrium iteration corresponding to each of the `Jobname.nrxxx` diagnostic files in the working directory, then issue a [[plnsol|PLNSOL]],NRRES,, `FileID` command to point to the file from which you want to create a contour plot of your Newton-Raphson residuals.

If you restart or issue a new [[solve|SOLVE]] command, any `Jobname.nrxxx` diagnostic files in the current (working) directory are overwritten.

Issue a **NLDIAG**,EFLG,ON command to create `Jobname.ndxxx` diagnostic files which store IDs for elements violating the following criteria:

- Too large a distortion (HDST)
- Elements contain nodes that have near zero pivots (PIVT) for nonlinear analyses
- Too large a plastic/creep (EPPL/EPCR) strain increment ( [[cutcontrol|CUTCONTROL]] )
- Elements for which mixed u-P constraints are not satisfied (mixed U-P option of 18 `x` solid elements only) (MXUP)
- Hyperelastic element (EPHY), cohesive zone material (EPCZ), or damage strain (EPDM) not converged
- Radial displacement (RDSP) not converged
- `MPC184` multipoint constraint elements using KEYOPT(1) = 6 through 16 with the Lagrange multiplier option fail to satisfy constraint conditions (184J)

For **NLDIAG**,EFLG,ON, all `Jobname.ndxxx` diagnostic files (for each equilibrium iteration after the first) in the current (working) directory are deleted when you issue a new [[solve|SOLVE]] command (or restart).

In the solution processor ( [[slashsolu|/SOLU]] ), use the STAT option to list the active status of this command. In the postprocessor ( [[post1|/POST1]] ), issue a [[nldpost|NLDPOST]],EFLG,STAT command to list the load step, substep, time, and equilibrium iteration corresponding to each of the `Jobname.ndxxx` diagnostic files in the working directory, then issue a [[nldpost|NLDPOST]],EFLG,CM, `FileID` command to create element components that violate the criteria.

Issue the **NLDIAG**,CONT,ON command to create a `Jobname.cnd` diagnostic file which stores contact information for all defined contact pairs at all substeps. Alternatively, you may issue one of the following commands to store contact information at a specific frequency:

- **NLDIAG**,CONT,ITER to write at each iteration
- **NLDIAG**,CONT,SUBS to write at each substep (default)
- **NLDIAG**,CONT,LSTP to write at each load step

Contact diagnostic information is available for elements `CONTA172`, `CONTA174`, `CONTA175`, and `CONTA177` ; it is not available for `CONTA178`.

Diagnostic file `Jobname.cnd` is written during solution and lists, on a pair-base, the following contact information:

- Contact pair ID <sup>\[1\]</sup>
- Number of contact elements in contact <sup>\[2\]</sup>
- Number of contact elements in sticking contact status
- Maximum chattering level
- Maximum contact penetration/Minimum gap <sup>\[3\]</sup>
- Maximum geometric gap
- Maximum normal contact stiffness
- Minimum normal contact stiffness
- Maximum resulting pinball
- Maximum elastic slip distance
- Maximum tangential contact stiffness
- Minimum tangential contact stiffness
- Maximum sliding distance (algebraic sum)
- Maximum contact pressure
- Maximum friction stress
- Average contact depth
- Maximum geometric penetration
- Number of contact points having too much penetration
- Contacting area
- Maximum contact damping pressure
- Maximum tangential contact damping stress
- Maximum total sliding distance ( GSLID ), including near-field
- Minimum total sliding distance ( GSLID ), including near-field
- Maximum normal fluid penetration pressure on contact surface
- Maximum normal fluid penetration pressure on target surface
- Total volume lost due to wear for the contact pair
- Total strain energy due to contact constraint <sup>\[6\]</sup>
- Total frictional dissipation energy <sup>\[6\]</sup>
- Total contact stabilization energy <sup>\[6\]</sup>
- Ansys Workbench contact pair ID <sup>\[4\]</sup>
- Total force due to contact pressure - X component
- Total force due to contact pressure - Y component
- Total force due to contact pressure - Z component <sup>\[5\]</sup>
- Total force due to tangential stress - X component
- Total force due to tangential stress - Y component
- Total force due to tangential stress - Z component <sup>\[5\]</sup>
- Number of contact points having too much sliding for small sliding contact
- Pair-based force convergence norm <sup>\[7\]</sup>
- Pair-based force convergence criterion <sup>\[7\]</sup>
- Maximum tangential fluid penetration pressure on contact surface
- Maximum tangential fluid penetration pressure on target surface
- Maximum sliding distance for closed contact in the current substep

Contact pair ID. A positive number refers to a real constant ID for a pair-based contact definition. A negative number refers to a section ID of a surface in a general contact definition. (See [Comparison of Pair-Based Contact and General Contact](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctec_comppairgen.html#gcfeatnotsup)

Number of contact elements in contact. Other values are interpreted as follows:

\* 0 indicates that the contact pair is in near-field contact status. \* -1 indicates that the contact pair is in far-field contact status. \* -2 indicates that the contact pair is inactive ( symmetric to asymmetric contact ).

A positive value indicates penetration and a negative value indicates a gap. If the contact pair has a far-field contact status, penetration and gap are not available and the value stored is the current pinball radius.

Intended primarily for internal use in the contact tracking of Ansys Workbench.

In a 3D model, the reported item is total force along the Z-axis. In a 2D axisymmetric model (with or without ROTY), the reported item is maximum torque that can potentially act on the Y-axis.

The pair-based dissipation energy and stabilization energy do not include contributions from contact elements that are in far-field. The pair-based strain energy does not include the frictional dissipation energy and stabilization energy; it only contains an elastic recovery energy when the contact status changes from closed to open.

The program uses a default tolerance value of 0.1 to calculate the pair-based force convergence norm and pair-based force convergence criterion. This is not a check for local convergence. It is for monitoring purposes only and is useful for nonlinear contact diagnostics.

In the solution processor ( [[slashsolu|/SOLU]] ), use the **NLDIAG**,CONT,STAT command to list the active status of the contact information. If you subsequently issue a new [[solve|SOLVE]] command (or restart), the `Jobname.cnd` diagnostic file in the current (working) directory is not deleted; information is appended to it. Delete the existing diagnostic file ( **NLDIAG**,CONT,DEL command) if you do not want to retain diagnostic information from previous solutions.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NLDIAG.html
