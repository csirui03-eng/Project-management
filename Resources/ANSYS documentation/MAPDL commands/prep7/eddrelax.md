---
apdl: "EDDRELAX"
method: eddrelax
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.eddrelax
generated: 2026-08-22
tags: [mapdl-command]
---

# EDDRELAX

PyMAPDL: `mapdl.eddrelax(option='', nrcyck='', drtol='', dffctr='', drterm='', tssfdr='', irelal='', edttl='', **kwargs)`

Activates initialization to a prescribed geometry or dynamic relaxation

for the explicit analysis.

## Parameters

**option**

Specifies when dynamic relaxation is activated.

ANSYS - Stresses are initialized in ANSYS LS-DYNA to a prescribed geometry for small  
strains, according to the solution of an ANSYS (implicit) run. The explicit solution is based on the implicit X,Y,Z displacements and rotations contained in the drelax file (created with the REXPORT command).

DYNA - Dynamic relaxation is on. When you use this option, you can specify some or all  
of the parameters NRCYCK, DRTOL, DFFCTR, DRTERM, TSSFDR, IRELAL, and EDTTL. Any parameters that you do not specify are set to their default values.

OFF - Turn off initialization to a prescribed geometry (Option = ANSYS) or dynamic  
relaxation (Option = DYNA).

**nrcyck**: Number of iterations between convergence checks for dynamic relaxation option. Default = 250.

**drtol**: Convergence tolerance for dynamic relaxation option. Default = 0.001.

**dffctr**: Dynamic relaxation factor. Default = 0.995.

**drterm**: Optional termination time for dynamic relaxation. Termination occurs at this time, or when convergence is attained, whichever comes first. Default = infinity.

**tssfdr**: Scale factor for computed time step during dynamic relaxation. If zero, the value is set to TSSFAC (defined on the EDCTS command). After converging, the scale factor is reset to TSSFAC.

**irelal**

Automatic control for dynamic relaxation option based on algorithm of Papadrakakis.

0 - Not active (default).

1 - Active.

**edttl**: Convergence tolerance on automatic control of dynamic relaxation (default = 0.04).

## Notes

Use Option = ANSYS when running an implicit-to-explicit sequential solution to initialize the structure to a static solution performed earlier by the ANSYS implicit solver. Use Option = DYNA to perform dynamic relaxation within the LS-DYNA program. Use Option = OFF to turn off previously specified stress initialization or dynamic relaxation. You must specify the Option you want; there is no default.

In LS-DYNA, the dynamic relaxation is performed before the regular transient analysis. The convergence process of the dynamic relaxation is not written to the ANSYS history file. The ANSYS results files only include the converged result of the dynamic relaxation, which is the result at time zero in the Jobname.HIS and Jobname.RST files.

You can restart a dynamic relaxation analysis (EDSTART,2 or EDSTART,3) from a previous transient analysis or a previous dynamic relaxation analysis. In the restart, you can change or set the convergence criteria with the EDDRELAX command. Only the load curves that are flagged for dynamic relaxation (PHASE = 1 or 2 on EDLOAD) are applied after restarting. If you restart the explicit portion of an implicit- to-explicit sequential solution, you do not need to reissue the REXPORT command because displacement information contained in the drelax file is already included in the LS-DYNA restart file. If the dynamic relaxation is activated from a regular transient analysis, LS-DYNA continues the output of data to ANSYS results files. This is unlike the dynamic relaxation phase at the beginning of the calculation for which only the converged solution is written.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
