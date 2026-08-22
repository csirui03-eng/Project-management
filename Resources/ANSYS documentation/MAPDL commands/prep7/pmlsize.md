---
apdl: "PMLSIZE"
method: pmlsize
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.artificially_matched_layers.ArtificiallyMatchedLayers.pmlsize
generated: 2026-08-22
tags: [mapdl-command]
---

# PMLSIZE

PyMAPDL: `mapdl.pmlsize(freqb='', freqe='', dmin='', dmax='', thick='', angle='', wavespeed='', **kwargs)`

Determines number of PML or IPML layers.

## Parameters

**freqb**: Minimum operating frequency (no default).

**freqe**: Maximum operating frequency (defaults to `FREQB` ).

**dmin**: Minimum distance from the radiation source to the PML or IPML interface (no default).

**dmax**: Maximum distance from the radiation source to the PML or IPML interface (defaults to `DMIN` ).

**thick**: Thickness of the PML or IPML region (defaults to 0).

**angle**: Incident angle of wave to the PML or IPML interface (defaults to 0).

**wavespeed**: Wave speed in PML or IPML medium (defaults to 343.24 m/s).

## Notes

**PMLSIZE** determines the number of PML or IPML layers for acceptable numerical accuracy.

**PMLSIZE** must be issued before any meshing commands. If the thickness of the PML or IPML region is known, it determines an element edge length (h) and issues [[esize|ESIZE]],h. If the thickness of the PML or IPML region is unknown, it determines the number of layers (n) and issues [[esize|ESIZE]],,n.

See [Artificially Matched Layers](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_acous/acous_artificial.html#acous_aml)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PMLSIZE.html
