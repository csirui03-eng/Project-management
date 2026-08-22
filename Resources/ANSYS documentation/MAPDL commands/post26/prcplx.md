---
apdl: "PRCPLX"
method: prcplx
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.listing.Listing.prcplx
generated: 2026-08-22
tags: [mapdl-command]
---

# PRCPLX

PyMAPDL: `mapdl.prcplx(key='', **kwargs)`

Defines the output form for complex variables.

## Parameters

**key**

Output form key:

- `0` - Real and imaginary parts.
- `1` - Amplitude and phase angle. Stored real and imaginary data are converted to amplitude and phase angle upon output. Data remain stored as real and imaginary parts.

## Notes

Defines the output form for complex variables. Used only with harmonic analyses ( [[antype|ANTYPE]],HARMIC).

All results data are stored in the form of real and imaginary components and converted to amplitude and/or phase angle as specified via the **PRCPLX** command. The conversion is not valid for derived results (such as principal stress/strain, equivalent stress/strain and USUM).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRCPLX.html
