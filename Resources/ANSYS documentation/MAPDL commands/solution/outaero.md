---
apdl: "OUTAERO"
method: outaero
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.outaero
generated: 2026-08-22
tags: [mapdl-command]
---

# OUTAERO

PyMAPDL: `mapdl.outaero(sename='', timeb='', dtime='', **kwargs)`

Outputs the superelement matrices and load vectors to formatted files for aeroelastic analysis.

## Parameters

**sename**: Name of the superelement that models the wind turbine supporting structure. Defaults to the current Jobname.

**timeb**: First time at which the load vector is formed (defaults to be read from `SENAME.sub` ).

**dtime**: Time step size of the load vectors (defaults to be read from `SENAME.sub` ).

## Notes

Both TIMEB and DTIME must be blank if the time data is to be read from the `SENAME.sub` file.

The matrix file ( `SENAME.SUB` ) must be available from the substructure generation run before issuing this command. This superelement that models the wind turbine supporting structure must contain only one master node with six freedoms per node: UX, UY, UZ, ROTX, ROTY, ROTZ. The master node represents the connection point between the turbine and the supporting structure.

This command will generate four files that are exported to the aeroelastic code for integrated wind turbine analysis. The four files are `Jobname.GNK` for the generalized stiffness matrix, `Jobname.GNC` for the generalized damping matrix, `Jobname.GNM` for the generalized mass matrix and `Jobname.GNF` for the generalized load vectors.

For detailed information on how to perform a wind coupling analysis, see [Coupling to External Aeroelastic Analysis of Wind Turbines](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advaerosequential.html)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/None
