---
apdl: "*VFILL"
method: vfill
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.parameter_definition.ParameterDefinition.vfill
generated: 2026-08-22
tags: [mapdl-command]
---

# *VFILL

PyMAPDL: `mapdl.vfill(parr='', func='', con1='', con2='', con3='', con4='', con5='', con6='', con7='', con8='', con9='', con10='', **kwargs)`

Fills an array parameter.

## Parameters

**parr**: The name of the resulting numeric array parameter vector. See [[starset|*SET]] for name restrictions.

**func**

Fill function:

- `DATA` - Assign specified values `CON1`, `CON2`, etc. to successive array elements. Up to 10 assignments may be made at a time. Any CON values after a blank CON value are ignored.

- `RAMP` - Assign ramp function values: `CON1` +((n-1)\* `CON2` ), where n is the loop number ( [[vlen|*VLEN]] ). To specify a constant function (no ramp), set `CON2` to zero.

- `RAND` - Assign random number values based on a uniform distribution RAND( `CON1`, `CON2` ), where:

  - `CON1` is the lower bound (defaults to 0.0)
  - `CON2` is the upper bound (defaults to 1.0)

- `GDIS` - Assign random sample of Gaussian distributions GDIS( `CON1`, `CON2` ) where:

  - `CON1` is the mean (defaults to 0.0)
  - `CON2` is the standard deviation (defaults to 1.0)

- `TRIA` - Assigns random number values based on a triangular distribution TRIA( `CON1`, `CON2`, `CON3` ) where:

  - `CON1` is the lower bound (defaults to 0.0)
  - `CON2` is the location of the peak value ( `CON1` ≤ `CON2` ≤ `CON3` ; `CON2` defaults to 0 if `CON1` ≤ 0 ≤ `CON3`, `CON1` if 0 ≤ `CON1`, or `CON3` if `CON3` ≤ 0)
  - `CON3` is the upper bound (defaults to 1.0 + `CON1` if `CON1` ≥ 0 or 0.0 if `CON1` ≤ 0)

- `BETA` - Assigns random number values based on a beta distribution BETA( `CON1`, `CON2`, `CON3`, `CON4` ) where:

  - `CON1` is the lower bound (defaults to 0.0)
  - `CON2` is the upper bound (defaults to 1.0 + `CON1` if `CON1` ≥ 0 or 0.0 if `CON1` ≤ 0)
  - `CON3` and `CON4` are the alpha and beta parameters, respectively, of the beta function. Alpha and beta must both be positive; they default to 1.0.

- `GAMM` - Assigns random number values based on a gamma distribution: GAMM( `CON1`, `CON2`, `CON3` ) where:

  - `CON1` is the lower bound (defaults to 0.0)
  - `CON2` and `CON3` are the alpha and beta parameters, respectively, of the gamma function. Alpha and beta must both be positive; they default to 1.0.

- `RIGID` - Generates the rigid body modes with respect to the reference point coordinates ( `CON1`, `CON2`, `CON3` ). The dimensions of the array parameter `ParR` are (dim<sub>1</sub>,dim<sub>2</sub> ) where dim<sub>1</sub> is the maximum node number (including internal nodes but excluding orientation nodes ) multiplied by the number of degrees of freedom, and dim<sub>2</sub> is the number of rigid body modes (which corresponds to the number of structural degrees of freedom).

- `CLUSTER` - Generates excitation frequencies with clustering option CLUSTER( `CON1`, `CON2`, `CON3`, `CON4`, `%CON5%` ) where:

  - `CON1` is the lower end of the frequency range in Hz (0 \< `CON1` )
  - `CON2` is the upper end of the frequency range in Hz ( `CON1` \< `CON2` )
  - `CON3` is the number of points on each side of the natural frequency (4 ≤ `CON3` ≤ 20, defaults to 4)
  - `CON4` is the constant damping ratio value or an array parameter (size NFR) specifying the damping ratios (if zero or blank, defaults to constant damping ratio of 0.005)

  \* `CON5` is an array parameter (size NFR) specifying the natural frequencies in Hz The dimension of the resulting array parameter ParR is less than 2+NFR2(2\* `CON3` +1) where NFR is the number of natural frequencies defined in `CON5`.

**con1**, **con2**, **con3**, **con4**, **con5**, **con6**, **con7**, **con8**, **con9**, **con10**: Constants used with above functions.

## Notes

Operates on input data and produces one output array parameter vector according to: `ParR` = f( `CON1`, `CON2`,...)

where the functions (f) are described above. Operations use successive array elements ( [[vlen|*VLEN]], [[vmask|*VMASK]] ) with the default being all successive elements. For example, **\*VFILL** ,A,RAMP,1,10 assigns A(1) = 1.0, A(2) = 11.0, A(3) = 21.0, etc. **\*VFILL**,B(5,1),DATA,1.5,3.0 assigns B(5,1) = 1.5 and B(6,1) = 3.0. Absolute values and scale factors may be applied to the result parameter ( [[vabs|*VABS]], [[vfact|*VFACT]] ). Results may be cumulative ( [[vcum|*VCUM]] ). See the [[voper|*VOPER]] command for details.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VFILL.html
