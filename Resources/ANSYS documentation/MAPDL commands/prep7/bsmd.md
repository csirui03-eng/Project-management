---
apdl: "BSMD"
method: bsmd
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.bsmd
generated: 2026-08-22
tags: [mapdl-command]
---

# BSMD

PyMAPDL: `mapdl.bsmd(dens='', t='', **kwargs)`

Specifies mass per unit length for a nonlinear general beam section.

## Parameters

**dens**: Mass density.

**t**: Temperature.

## Notes

The **BSMD** command, one of several [nonlinear general beam section commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRNGBS.html#strngbsstrain), specifies the mass density (assuming a unit area) for a beam section. The value specified is associated with the section most recently defined (via the [[sectype|SECTYPE]] command).

Related commands are [[bsax|BSAX]], [[bsm1|BSM1]], [[bsm2|BSM2]], [[bstq|BSTQ]], [[bss1|BSS1]], [[bss2|BSS2]], and [[bste|BSTE]].

For complete information, see [Using Nonlinear General Beam Sections](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRNGBS.html#strngbscons)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BSMD.html
