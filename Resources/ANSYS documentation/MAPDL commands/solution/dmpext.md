---
apdl: "DMPEXT"
method: dmpext
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.dmpext
generated: 2026-08-22
tags: [mapdl-command]
---

# DMPEXT

PyMAPDL: `mapdl.dmpext(smode='', tmode='', dmpname='', freqb='', freqe='', nsteps='', **kwargs)`

Extracts modal damping coefficients in a specified frequency range.

## Parameters

**smode**: Source mode number. There is no default for this field; you must enter an integer greater than zero.

**tmode**: Target mode. Defaults to `SMODE`.

**dmpname**: Array parameter name containing the damping results. Defaults to `d_damp`.

**freqb**: Beginning frequency range (real number greater than zero) or 'EIG' at eigenfrequency of source mode. 'EIG' is valid only if `SMODE` = `TMODE`. Note that EIG must be enclosed in single quotes when this command is used on the command line or in an input file. There is no default for this field; you must enter a value.

**freqe**: End of frequency range. Must be blank for `Freqb` = EIG. Default is `Freqb`.

**nsteps**: Number of substeps. Defaults to 1.

## Notes

DMPEXT invokes a Mechanical APDL macro that uses modal projection techniques to compute the damping force by the modal velocity of the source mode onto the target mode. From the damping force, damping parameters are extracted. DMPEXT creates an array parameter `Dmpname`, with the following entries in each row:

- response frequency
- modal damping coefficient
- modal squeeze stiffness coefficient
- damping ratio
- squeeze-to-structural stiffness ratio

The macro requires the modal displacements from the file `Jobname.EFL` obtained from the [[rmflvec|RMFLVEC]] command. In addition, a node component FLUN must exist from all `FLUID136` nodes. The computed damping ratio may be used to specify constant or modal damping by means of the [[dmprat|DMPRAT]] or [[mdamp|MDAMP]] commands. For Rayleigh damping, use the [[abextract|ABEXTRACT]] command to compute ALPHAD and BETAD damping parameters. See Thin Film Analysis for more information on thin film analyses.

The macro uses the [[lssolve|LSSOLVE]] command to perform two load steps for each frequency. The first load case contains the solution of the source mode excitation and can be used for further postprocessing. Solid model boundary conditions are deleted from the model. In addition, prescribed nodal boundary conditions are applied to the model. You should carefully check the boundary conditions of your model prior to executing a subsequent analysis.

This command is also valid in PREP7. Distributed-Memory Parallel (DMP) Restriction This command is not supported in a DMP solution.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DMPEXT.html
