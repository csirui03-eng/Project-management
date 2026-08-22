---
apdl: "EDRUN"
method: edrun
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edrun
generated: 2026-08-22
tags: [mapdl-command]
---

# EDRUN

PyMAPDL: `mapdl.edrun(option='', cons='', ncpu='', **kwargs)`

Specify LS-DYNA serial or parallel processing.

## Parameters

**option**

LS-DYNA processing option

SERIAL - Use serial processing (default)

SMP - Use Shared Memory Parallel processing

**cons**

Consistency setting (only applicable when Option = SMP)

0 - Result consistency is not required (default)

1 - Result consistency is required

**ncpu**: Number of processors to use (applicable only with Option = SMP)

## Notes

The EDRUN command specifies either serial (one CPU) processing or shared (multiple CPU) memory parallel processing (SMP). When using SMP, the calculations may be executed in a different order, depending on CPU availability and the load on each CPU. You may therefore see slight differences in the results when running the same job multiple times, either with the same number or a different number of processors. Comparing nodal accelerations often shows wider discrepancies. To avoid such differences, you can specify that consistency be maintained by setting CONS = 1. Maintaining consistency can result in an increase of up to 15 percent in CPU time.

The parallel processing setting is only effective when you have multiple CPUs and licenses for the appropriate number of ANSYS LS-DYNA SMP tasks. If your site does not meet both requirements, the EDRUN command sets serial processing, regardless of command settings.

For more information on using SMP, see Solution Features in the ANSYS LS-DYNA User's Guide.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
