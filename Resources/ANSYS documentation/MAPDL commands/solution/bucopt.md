---
apdl: "BUCOPT"
method: bucopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.bucopt
generated: 2026-08-22
tags: [mapdl-command]
---

# BUCOPT

PyMAPDL: `mapdl.bucopt(method='', nmode='', shift='', ldmulte='', rangekey='', **kwargs)`

Specifies buckling analysis options.

## Parameters

**method**

Mode extraction method to be used for the buckling analysis:

- `LANB` - Block Lanczos
- `SUBSP` - Subspace iteration

See [Eigenvalue and Eigenvector Extraction](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool13.html#eltcomplexeigens)

**nmode**: Number of buckling modes (that is, eigenvalues or load multipliers) to extract (defaults to 1).

**shift**

By default, this value acts as the initial shift point about which the buckling modes are calculated (defaults to 0.0).

When `RangeKey` = RANGE, this value acts as the lower bound of the load multiplier range of interest ( `LDMULTE` is the upper bound).

**ldmulte**

Boundary for the load multiplier range of interest (defaults to (equation omitted) ).

When `RangeKey` = CENTER, the `LDMULTE` value determines the lower and upper bounds of the load multiplier range of interest (- `LDMULTE`, + `LDMULTE` ).

When `RangeKey` = RANGE, the `LDMULTE` value is the upper bound for the load multiplier range of interest ( `SHIFT` is the lower bound).

**rangekey**

Key used to control the behavior of the eigenvalue extraction method (defaults to CENTER):

- `CENTER` - Use the CENTER option control (default); the program computes `NMODE` buckling modes centered around `SHIFT` in the range of (- `LDMULTE`, + `LDMULTE` ).
- `RANGE` - Use the RANGE option control; the program computes `NMODE` buckling modes in the range of ( `SHIFT`, `LDMULTE` ).

## Notes

Specifies buckling analysis ( [[antype|ANTYPE]],BUCKLE) options. Additional options used only for the Block Lanczos (LANB) eigensolver are specified by the [[lanboption|LANBOPTION]] command. For more difficult buckling problems, you can specify an alternative version of the Block Lanczos eigensolver ( [[lanboption|LANBOPTION]],,,ALT1).

Eigenvalues from a buckling analysis can be negative and/or positive. The program sorts the eigenvalues from the most negative to the most positive values. The minimum buckling load factor may correspond to the smallest eigenvalue in absolute value, or to an eigenvalue within the range, depending on your application (that is, linear perturbation buckling analysis or purely linear buckling analysis).

It is recommended that you request an additional few buckling modes beyond what is needed in order to enhance the accuracy of the final solution. It is also recommended that you input a non zero `SHIFT` value and a reasonable `LDMULTE` value (that is, a smaller `LDMULTE` that is closer to the last buckling mode of interest) when numerical problems are encountered.

When using the RANGE option, defining a range that spans zero is not recommended. If you are seeking both negative and positive eigenvalues, it is recommended that you use the CENTER option.

This command is also valid in PREP7. If used in SOLUTION, this command is valid only within the first load step.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BUCOPT.html
