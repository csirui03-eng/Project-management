---
apdl: "RPSD"
method: rpsd
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.special_purpose.SpecialPurpose.rpsd
generated: 2026-08-22
tags: [mapdl-command]
---

# RPSD

PyMAPDL: `mapdl.rpsd(ir='', ia='', ib='', itype='', datum='', name='', signif='', **kwargs)`

Calculates response power spectral density (PSD).

## Parameters

**ir**: Arbitrary reference number assigned to the resulting variable (2 to `NV` ( [[numvar|NUMVAR]] )). If this number is the same as for a previous variable, the previous variable will be overwritten with this result.

**ia**, **ib**: Reference numbers of the two variables to be operated on. If only one, leave `IB` blank.

**itype**

Defines the type of response PSD to be calculated:

- `0,1` - Displacement (default).
- `2` - Velocity.
- `3` - Acceleration.

**datum**

Defines the reference with respect to which response PSD is to be calculated:

- `1` - Absolute value.
- `2` - Relative to base (default).

**name**: Thirty-two character name identifying variable on listings and displays. Embedded blanks are compressed for output.

**signif**

Combine only those modes whose significance level exceeds the `SIGNIF` threshold. The significance level is defined as the modal covariance matrix term divided by the maximum of all the modal covariance matrix terms. Any term whose significance level is less than `SIGNIF` is considered insignificant and does not contribute to the response. All modes are taken into account by default ( `SIGNIF` = 0.0).

The significance level definition is identical to the one used for the combination ( `SIGNIF` on the [[psdcom|PSDCOM]] command); however, the default value is different.

The significance does not apply to spatial correlation ( [[psdspl|PSDSPL]] ) and wave propagation ( [[psdwav|PSDWAV]] ) response power spectral density.

## Notes

This command calculates response power spectral density (PSD) for the variables referenced by the reference numbers `IA` and `IB`. The variable referred by `IR` will contain the response PSD. You must issue the [[store|STORE]],PSD command first; `File.PSD` must be available for the calculations to occur.

See [POST26 - Response Power Spectral Density](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_post13.html#eqe670f2a2-bc13-4785-aee1-0d74b8bb8922) in the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html) for more information on these equations.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RPSD.html
