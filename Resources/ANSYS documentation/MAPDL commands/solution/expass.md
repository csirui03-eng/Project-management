---
apdl: "EXPASS"
method: expass
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.expass
generated: 2026-08-22
tags: [mapdl-command]
---

# EXPASS

PyMAPDL: `mapdl.expass(key='', keystat='', **kwargs)`

Specifies an expansion pass of an analysis.

## Parameters

**key**

Expansion pass key:

- `OFF` - No expansion pass will be performed (default).
- `ON` - An expansion pass will be performed.

**keystat**

Static correction vectors key:

- `ON` - Include static correction vectors in the expanded displacements (default).
- `OFF` - Do not include static correction vectors in the expanded displacements.

## Notes

Specifies that an expansion pass of a modal, substructure, buckling, transient, or harmonic analysis is to be performed.

This separate solution pass requires an explicit [[finish|FINISH]] from the preceding analysis and reentry into SOLUTION.

The `KeyStat` argument is applicable to the expansion pass of a substructure analysis, and to the expansion pass of a component mode synthesis (CMS) analysis when the CMS method is fixed-interface or free-interface. For a substructure analysis, the static correction vectors are the first terms of in the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html). For a CMS analysis, the static correction vectors are the third terms of.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EXPASS.html
