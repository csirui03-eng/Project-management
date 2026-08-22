---
apdl: "*MFOURI"
method: mfouri
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.array_parameters.ArrayParameters.mfouri
generated: 2026-08-22
tags: [mapdl-command]
---

# *MFOURI

PyMAPDL: `mapdl.mfouri(oper='', coeff='', mode='', isym='', theta='', curve='', **kwargs)`

Calculates the coefficients for, or evaluates, a Fourier series.

## Parameters

**oper**

Type of Fourier operation:

- `FIT` - Calculate Fourier coefficients `COEFF` from `MODE`, `ISYM`, `THETA`, and `CURVE`.
- `EVAL` - Evaluate the Fourier curve `CURVE` from `COEFF`, `MODE`, `ISYM` and `THETA`

**coeff**: Name of the array parameter vector containing the Fourier coefficients (calculated if `Oper` = FIT, required as input if `Oper` = EVAL). See [[starset|*SET]] for name restrictions.

**mode**: Name of the array parameter vector containing the mode numbers of the desired Fourier terms.

**isym**

Name of the array parameter vector containing the symmetry key for the corresponding Fourier terms. The vector should contain keys for each term as follows:

- `0 or 1` - Symmetric (cosine) term
- `-1` - Antisymmetric (sine) term.

**theta**, **curve**: Names of the array parameter vectors containing the theta vs. curve description, respectively. Theta values should be input in degrees. If `Oper` = FIT, one curve value should be supplied with each theta value. If `Oper` = EVAL, one curve value will be calculated for each theta value.

## Notes

### Argument descriptions

- `oper : str` - Type of Fourier operation:
  - `FIT` - Calculate Fourier coefficients `COEFF` from `MODE`, `ISYM`, `THETA`, and `CURVE`.
  - `EVAL` - Evaluate the Fourier curve `CURVE` from `COEFF`, `MODE`, `ISYM` and `THETA`
- `coeff : str` - Name of the array parameter vector containing the Fourier coefficients (calculated if `Oper` = FIT, required as input if `Oper` = EVAL). See [[starset|*SET]] for name restrictions.
- `mode : str` - Name of the array parameter vector containing the mode numbers of the desired Fourier terms.

\* `isym : str` - Name of the array parameter vector containing the symmetry key for the corresponding Fourier terms. The vector should contain keys for each term as follows:

> - `0 or 1` - Symmetric (cosine) term
> - `-1` - Antisymmetric (sine) term.

- `theta, curve : str` - Names of the array parameter vectors containing the theta vs. curve description, respectively. Theta values should be input in degrees. If `Oper` = FIT, one curve value should be supplied with each theta value. If `Oper` = EVAL, one curve value will be calculated for each theta value.

Calculates the coefficients of a Fourier series for a given curve, or evaluates the Fourier curve from the given (or previously calculated) coefficients. The lengths of the `COEFF`, `MODE`, and `ISYM` vectors must be the same-typically two times the number of modes desired, since two terms (sine and cosine) are generally required for each mode. The lengths of the `CURVE` and `THETA` vectors should be the same or the smaller of the two will be used. There should be a sufficient number of points to adequately define the curve-at least two times the number of coefficients. A starting array element number (1) must be defined for each array parameter vector. The vector specifications [[vlen|*VLEN]], [[vcol|*VCOL]], [[vabs|*VABS]], [[vfact|*VFACT]], and [[vcum|*VCUM]] do not apply to this command. Array elements should not be skipped with the [[vmask|*VMASK]] and the `NINC` value of the [[vlen|*VLEN]] specifications. The vector being calculated ( `COEFF` if `Oper` is FIT, or `CURVE` if `Oper` is EVAL) must exist as a dimensioned array ( [[dim|*DIM]] ).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MFOURI.html
