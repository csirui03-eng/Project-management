---
apdl: "PSDCOM"
method: psdcom
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.psdcom
generated: 2026-08-22
tags: [mapdl-command]
---

# PSDCOM

PyMAPDL: `mapdl.psdcom(signif='', comode='', forcetype='', **kwargs)`

Specifies the power spectral density mode combination method.

## Parameters

**signif**: Combine only those modes whose significance level exceeds the `SIGNIF` threshold. For PSD response ( [[spopt|SPOPT]],PSD), the significance level is defined as the modal covariance matrix term, divided by the maximum modal covariance matrix term. Any term whose significance level is less than `SIGNIF` is considered insignificant and is not contributed to the mode combinations. The higher the `SIGNIF` threshold, the fewer the number of terms used. `SIGNIF` defaults to 0.0001. If `SIGNIF` is specified as 0.0, it is taken as 0.0.

**comode**: First `COMODE` number of modes to be actually combined. `COMODE` must always be less than or equal to `NMODE` (input quantity `NMODE` on the [[spopt|SPOPT]] command). `COMODE` defaults to `NMODE`. `COMODE` performs a second level of control for the first sequential `COMODE` number of modes to be combined. It uses the significance level threshold indicated by `SIGNIF` and operates only on the significant modes.

**forcetype**

Label identifying the forces to be combined:

- `STATIC` - Combine the modal static forces (default).
- `TOTAL` - Combine the modal static plus inertial forces.

## Notes

This command is also valid for PREP7. This command is valid only for [[spopt|SPOPT]],PSD.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSDCOM.html
