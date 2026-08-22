---
apdl: "QRDOPT"
method: qrdopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.qrdopt
generated: 2026-08-22
tags: [mapdl-command]
---

# QRDOPT

PyMAPDL: `mapdl.qrdopt(reusekey='', symmeth='', cmccoutkey='', **kwargs)`

Specifies additional QRDAMP modal analysis options.

## Parameters

**reusekey**

Reuse key for method= `QRDAMP` specified in [[modopt|MODOPT]] command.

- `ON` - Reuse the symmetric eigensolution from the previous load steps or from the previous solution.
- `OFF` - Do not reuse (calculates symmetric eigensolution at current load step). This is the default.

**symmeth**

Mode-extraction method to be used for the symmetric eigenvalue problem.

- `LANB` - Block Lanczos algorithm (default).
- `SUBSP` - Subspace algorithm.
- `SNODE` - Supernode algorithm.

**cmccoutkey**

Complex Modal Contribution Coefficients (CMCC) output key. See [Calculate the Complex Mode Contribution Coefficients (CMCC)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRmodanexamp.html#streq375ccmcc)

- `ON` - Output the CMCC to the text file `JobnameCMCC`.
- `OFF` - Do not output the CMCC. This is the default.

## Notes

If the `filename.modesym` file exists in the working directory and `ReuseKey` = ON, `filename.modesym` will be reused. If `filename.modesym` does not exist in the working directory, the symmetric eigensolution will be calculated.

When `ReuseKey` =ON, both the new modal analysis ( `filename.modesym` usage) and the preceding modal analysis ( `filename.modesym` generation) must be performed using the same product version number.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_QRDOPT.html
