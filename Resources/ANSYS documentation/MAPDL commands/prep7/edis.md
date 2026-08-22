---
apdl: "EDIS"
method: edis
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edis
generated: 2026-08-22
tags: [mapdl-command]
---

# EDIS

PyMAPDL: `mapdl.edis(option='', pidn='', pido='', **kwargs)`

Specifies stress initialization in an explicit dynamic full restart

analysis.

## Parameters

**option**

Label identifying the option to be performed.

ADD - Define stress initialization between parts (default).

**pidn**: New part ID or part assembly ID in the full restart analysis (defaults to all parts in the model).

**pido**: Old part ID or part assembly ID in the previous analysis, (default to PIDN).

## Notes

The EDIS command is only valid in an explicit dynamic full restart analysis (EDSTART,3). (EDIS is ignored if it is not preceded by the EDSTART,3 command.) Use EDIS to specify which parts and/or part assemblies should undergo stress initialization in the restart based on the stresses from the previous analysis. You can specify stress initialization for multiple parts (or part assemblies) by issuing EDIS multiple times. If you issue EDIS with no arguments, stress initialization is performed for all parts in the restart analysis that have a corresponding part (having the same part ID) in the previous analysis.

In a full restart analysis, the complete database is written as an LS- DYNA input file, Jobname_nn.K. When the LS-DYNA solution begins, LS- DYNA performs the stress initialization using file Jobname_nn.K and the restart dump file (d3dumpnn specified on the EDSTART command) from the previous analysis. At the end of initialization, all the parts that were specified by the EDIS commands are initialized from the data saved in the restart dump file. In order for the stress initialization to be performed successfully, the new parts in the full restart analysis and the old parts in the previous analysis must have the same number of elements, same element order, and same element topology. (The parts may have different identifying numbers.) If this is not the case, the stresses cannot be initialized. If part assemblies are used, the part assemblies must contain the same number of parts. (See A Full Restart in the ANSYS LS-DYNA User's Guide for more details).

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
