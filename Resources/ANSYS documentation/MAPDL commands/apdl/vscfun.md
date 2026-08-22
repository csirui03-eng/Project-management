---
apdl: "*VSCFUN"
method: vscfun
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.array_parameters.ArrayParameters.vscfun
generated: 2026-08-22
tags: [mapdl-command]
---

# *VSCFUN

PyMAPDL: `mapdl.vscfun(parr='', func='', par1='', **kwargs)`

Determines properties of an array parameter.

## Parameters

**parr**: The name of the resulting scalar parameter. See [[starset|*SET]] for name restrictions.

**func**

Functions:

- `MAX` - Maximum: the maximum `Par1` array element value.
- `MIN` - Minimum: the minimum `Par1` array element value.
- `LMAX` - Index location of the maximum `Par1` array element value. Array `Par1` is searched starting from its specified index.
- `LMIN` - Index location of the minimum `Par1` array element value. Array `Par1` is searched starting from its specified index.
- `FIRST` - Index location of the first nonzero value in array `Par1`. Array `Par1` is searched starting from its specified index.
- `LAST` - Index location of the last nonzero value in array `Par1`. Array `Par1` is searched starting from its specified index.
- `SUM` - Sum: `Par1` (the summation of the `Par1` array element values).
- `MEDI` - Median: value of `Par1` at which there are an equal number of values above and below.
- `MEAN` - Mean: (σ Par1)/NUM, where NUM is the number of summed values.
- `VARI` - Variance: (σ (( `Par1` -MEAN)\*\*2))/NUM.
- `STDV` - Standard deviation: square root of VARI.
- `RMS` - Root-mean-square: square root of (σ ( `Par1` \*\*2))/NUM.
- `NUM` - Number: the number of summed values (masked values are not counted).

**par1**: Array parameter vector in the operation.

## Notes

Operates on one input array parameter vector and produces one output scalar parameter according to: `ParR` = f( `Par1` )

where the functions (f) are described below. The starting array element number must be defined for the array parameter vector. For example, **\*VSCFUN**,MU,MEAN,A(1) finds the mean of the A vector values, starting from the first value and stores the result as parameter MU. Operations use successive array elements ( [[vlen|*VLEN]], [[vmask|*VMASK]] ) with the default being all successive array elements. Absolute values and scale factors may be applied to all parameters ( [[vabs|*VABS]], [[vfact|*VFACT]] ). Results may be cumulative ( [[vcum|*VCUM]] ). See the [[voper|*VOPER]] command for details.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VSCFUN.html
