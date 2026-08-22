---
apdl: "SSPD"
method: sspd
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.sspd
generated: 2026-08-22
tags: [mapdl-command]
---

# SSPD

PyMAPDL: `mapdl.sspd(d11='', d21='', d31='', d22='', d32='', d33='', t='', **kwargs)`

Specifies a preintegrated bending stiffness for shell sections.

## Parameters

**d11**, **d21**, **d31**, **d22**, **d32**, **d33**: Bending stiffness component (symmetric lower part of submatrix \[ **D** \]).

**t**: Temperature.

## Notes

The behavior of shell elements is governed by the generalized-stress/generalized-strain relationship of the [form](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PRESHELL_5.html#strpreshcons) :

(equation not available in the PyMAPDL source, see the Ansys help page)

The **SSPD** command, one of several [preintegrated shell section commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PRESHELL_5.html#membraneoptionnote) , specifies the bending stiffness quantity (submatrix \[ **D** \] data) for a preintegrated shell section. The section data defined is associated with the section most recently defined (via the [[sectype|SECTYPE]] command).

Unspecified commands default to zero.

Related commands are [[sspa|SSPA]], [[sspb|SSPB]], [[sspe|SSPE]], [[ssmt|SSMT]], [[ssbt|SSBT]], and [[sspm|SSPM]].

If you are using the `SHELL181` or `SHELL281` element's Membrane option (KEYOPT(1) = 1), it is not necessary to issue this command.

For complete information, see [Creating a Preintegrated General Shell Section](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PRESHELL_5.html#strpreshcons)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SSPD.html
