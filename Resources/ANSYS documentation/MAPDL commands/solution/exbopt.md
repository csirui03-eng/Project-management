---
apdl: "EXBOPT"
method: exbopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.exbopt
generated: 2026-08-22
tags: [mapdl-command]
---

# EXBOPT

PyMAPDL: `mapdl.exbopt(outinv2='', outtcms='', outsub='', outcms='', outcomp='', outrm='', noinv='', outele='', **kwargs)`

Specifies `.EXB` file output options in a CMS generation pass.

**Command default:**

Default settings as described for each argument are used.

## Parameters

**outinv2**

Output control for 2nd order invariant:

- `0` - Do not output (default).
- `1` - Output the second order invariant.

**outtcms**

Output control for `.TCMS` file:

- `0` - Do not output (default).
- `1` - Output the `.TCMS` file.

**outsub**

Output control for `.SUB` file:

- `0` - Do not output (default).
- `1` - Output the `.SUB` file.

**outcms**

Output control for `.CMS` file:

- `0` - Do not output (default).
- `1` - Output the `.CMS` file.

**outcomp**

Output control for node and element component information:

- `0` - Do not output any component information.
- `1` - Output node component information only.
- `2` - Output element component information only.
- `3` - Output both node and element component information (default).

**outrm**

Output control for the recovery matrix:

- `0` - Do not output (default).
- `1` - Output the recovery matrix to `fileEXB`.
- `2` - Output the recovery matrix to a separate file, `file_RECOVEREXB`.

**noinv**

Invariant calculation:

- `0` - Calculate all invariants (default).
- `1` - Suppress calculation of the 1st and 2nd order invariants. NOINV = 1 suppresses OUTINV2 = 1.

**outele**

Output control for the element data:

- `0` - Do not output (default).
- `1` - Output the element data.

## Notes

When the body property file ( `file.EXB` ) is requested in a CMS generation pass ( [[cmsopt|CMSOPT]],,,,,,,EXB command), the `.TCMS`, `.SUB`, and `.CMS` files are not output by default. Use the **EXBOPT** command to request these files, as needed.

**EXBOPT** can also be used to manage some content in the `.EXB` file for improving performance and storage (see the `OUTINV2`, `OUTCOMP`, `OUTRM`, `NOINV`, and `OUTELE` arguments described above).

If both recovery matrix output ( `OUTRM` = 1 or 2) and the `.TCMS` file ( `OUTTCMS` = 1) are requested, the `.TCMS` file writing is turned off due to potentially large in-core memory use.

For more information on how to generate `file.EXB`, see [Ansys Interface to AVL EXCITE](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/substrexbcms.html)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EXBOPT.html
