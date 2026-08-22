---
apdl: "BSS2"
method: bss2
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.bss2
generated: 2026-08-22
tags: [mapdl-command]
---

# BSS2

PyMAPDL: `mapdl.bss2(val1='', val2='', t='', **kwargs)`

Specifies the transverse shear strain and force relationship in plane XY for beam sections.

## Parameters

**val1**: Transverse shear strain component ( (equation omitted) ).

**val2**: Transverse shear force component ( (equation omitted) ).

**t**: Temperature.

## Notes

The behavior of beam elements is governed by the generalized-stress/generalized-strain relationship of the [form](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRNGBS.html#strngbscons) :

(equation not available in the PyMAPDL source, see the Ansys help page)

The [[bss1|BSS1]] command, one of several [nonlinear general beam section commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRNGBS.html#strngbsstrain), specifies the transverse shear strain and transverse shear force relationship for plane XY of a beam section. The section data defined is associated with the section most recently defined (via the [[sectype|SECTYPE]] command).

Unspecified values default to zero.

Related commands are [[bsax|BSAX]], [[bsm1|BSM1]], [[bsm2|BSM2]], [[bstq|BSTQ]], [[bss1|BSS1]], [[bsmd|BSMD]], and [[bste|BSTE]].

For complete information, see [Using Nonlinear General Beam Sections](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRNGBS.html#strngbscons) .

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BSS2.html
