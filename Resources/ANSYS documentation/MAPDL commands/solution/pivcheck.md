---
apdl: "PIVCHECK"
method: pivcheck
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.pivcheck
generated: 2026-08-22
tags: [mapdl-command]
---

# PIVCHECK

PyMAPDL: `mapdl.pivcheck(key='', prntcntrl='', **kwargs)`

Controls the behavior of an analysis when a negative or zero equation solver pivot value is encountered.

**Command default:**

The program checks for negative or zero pivot values ( `Key` = AUTO). If any are found, the analysis may stop with an error or may proceed with only a warning, depending on various criteria pertaining to the type of analysis being solved.

## Parameters

**key**

Determines whether to stop or continue an analysis when a negative or zero equation solver pivot value is encountered:

- `AUTO` - Check for negative or zero pivot values for analyses performed with the sparse and PCG solvers. When one is encountered, an error or warning is issued, per various criteria relating to the type of analysis being solved. An error causes the analysis to stop; a warning allows the analysis to continue. A negative pivot value may be valid for some nonlinear and multiphysics analyses (for example, electromagnetic and thermal analyses); this key has no effect in these cases.
- `ERROR` - Check for negative or zero pivot values for analyses performed with the sparse and PCG solvers. When one is encountered, an error is issued, stopping the analysis. A negative pivot value may be valid for some nonlinear and multiphysics analyses (for example, electromagnetic and thermal analyses); this key has no effect in these cases.
- `WARN` - Check for negative or zero pivot values for analyses performed with the sparse and PCG solvers. When one is encountered, a warning is issued and the analysis continues. A negative pivot value may be valid for some nonlinear and multiphysics analyses (for example, electromagnetic and thermal analyses); this key has no effect in these cases.
- `OFF` - Pivot values are not checked. This key causes the analysis to continue in spite of a negative or zero pivot value.

**prntcntrl**

Provides print options. Print output with these options will be sent to the default output file, not to the files created by the nonlinear diagnostic tools ( [[nldiag|NLDIAG]] ).

- `ONCE` - Print only the maximum and minimum pivot information on the first call to the sparse solver (which is the default solver). This is the default behavior.
- `EVERY` - Print the maximum and minimum pivot information at every call to the sparse solver. This option is provided for nonlinear analysis diagnostics.

## Notes

This command is valid for all analyses. In a nonlinear analysis, a negative pivot may be valid. In some cases, rigid body motions in a nonlinear analysis will be trapped by error routines checking infinitely large displacements (DOF limit exceeded) or nonconvergence status. An under-constrained model may avoid the pivot check, but fail with a DOF limit exceeded error.

Machine precision may affect whether a small pivot triggers an error or bypasses this checking logic. You may wish to review the ratio of the maximum to absolute minimum pivot values. For ratios exceeding 12 to 14 orders of magnitude, the accuracy of the computed solution may be degraded by the severe ill-conditioning of the assembled matrix.

Note that negative pivots corresponding to Lagrange multiplier based mixed u-P elements are not checked or reported by this command. Negative pivots arising from the u-P element formulation and related analyses can occur and lead to correct solutions.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PIVCHECK.html
