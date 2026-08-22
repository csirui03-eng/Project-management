---
apdl: "SSPA"
method: sspa
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.sspa
generated: 2026-08-22
tags: [mapdl-command]
---

# SSPA

PyMAPDL: `mapdl.sspa(a11='', a21='', a31='', a22='', a32='', a33='', t='', **kwargs)`

Specifies a preintegrated membrane stiffness for shell sections.

## Parameters

**a11**, **a21**, **a31**, **a22**, **a32**, **a33**: Membrane stiffness component (symmetric lower part of submatrix \[ **A** \]).

**t**: Temperature.

## Notes

The behavior of shell elements is governed by the generalized-stress/generalized-strain relationship of the [form](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PRESHELL_5.html#strpreshcons) :

(equation not available in the PyMAPDL source, see the Ansys help page)

The **SSPA** command, one of several [preintegrated shell section commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PRESHELL_5.html#membraneoptionnote), specifies the membrane stiffness quantity (submatrix \[ **A** \]) for a preintegrated shell section. The section data defined is associated with the section most recently defined (via the [[sectype|SECTYPE]] command).

Unspecified values default to zero.

Related commands are [[sspb|SSPB]], [[sspd|SSPD]], [[sspe|SSPE]], [[ssmt|SSMT]], [[ssbt|SSBT]], and [[sspm|SSPM]].

For complete information, see [Creating a Preintegrated General Shell Section](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PRESHELL_5.html#strpreshcons)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SSPA.html
