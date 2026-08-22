---
apdl: "SFLEX"
method: sflex
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.sflex
generated: 2026-08-22
tags: [mapdl-command]
---

# SFLEX

PyMAPDL: `mapdl.sflex(ffax='', ffby='', ffbz='', ffto='', fftsy='', fftsz='', **kwargs)`

Sets flexibility factors for the currently defined pipe element section.

## Parameters

**ffax**: Factor to increase axial flexibility. The default value is 1.0.

**ffby**: Factor to increase bending flexibility about element y axis (bending in the element x-z plane). The default value is 1.0.

**ffbz**: Factor to increase bending flexibility about element z axis (bending in the element x-y plane). The default value is `FFBY`.

**ffto**: Factor to increase torsional flexibility. The default value is 1.0.

**fftsy**: Factor to increase transverse shear flexibility in the element x-z plane. The default value is 1.0.

**fftsz**: Factor to increase transverse shear flexibility in the element x-y plane. The default value is `FFTSY`.

## Notes

The **SFLEX** command sets section-flexibility factors for sections used by pipe elements.

To increase stiffness, use a flexibility factor of less than 1.0.

The `FFBY` and `FFTSY` arguments affect motion in the element x-z plane, and the `FFBZ` and `FFTSZ` arguments affect motion in the element x-y plane. For stout pipe structures with low slenderness ratios, set both FFBY and FFTSY-and/or both FFBZ and FFTSZ (the related bending and transverse shear factors)-to the same value to obtain the expected flexibility effect.

When issued, the **SFLEX** command applies to the pipe section most recently defined via the [[sectype|SECTYPE]] command.

**SFLEX** is valid only for linear material properties and small strain analyses. The command does not support offsets, temperature loading, or initial state loading. While the resulting displacements and reactions are valid, the stresses may not be valid.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFLEX.html
