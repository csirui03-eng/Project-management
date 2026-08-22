---
apdl: "BSTQ"
method: bstq
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.bstq
generated: 2026-08-22
tags: [mapdl-command]
---

# BSTQ

PyMAPDL: `mapdl.bstq(val1='', val2='', t='', **kwargs)`

Specifies the cross section twist and torque relationship for beam sections.

## Parameters

**val1**: Twist component ( (equation omitted) ).

**val2**: Torque component ( (equation omitted) ).

**t**: Temperature.

## Notes

The behavior of beam elements is governed by the generalized-stress/generalized-strain relationship of the [form](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRNGBS.html#strngbscons) :

(equation not available in the PyMAPDL source, see the Ansys help page)

The **BSTQ** command, one of several [nonlinear general beam section commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRNGBS.html#strngbsstrain), specifies the cross section twist and torque relationship for a beam section. The section data defined is associated with the section most recently defined (via the [[sectype|SECTYPE]] command).

Unspecified values default to zero.

Related commands are [[bsax|BSAX]], [[bsm1|BSM1]], [[bsm2|BSM2]], [[bss1|BSS1]], [[bss2|BSS2]], [[bsmd|BSMD]], and [[bste|BSTE]].

For complete information, see [Using Nonlinear General Beam Sections](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRNGBS.html#strngbscons) .

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BSTQ.html
