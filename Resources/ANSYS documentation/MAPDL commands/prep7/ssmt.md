---
apdl: "SSMT"
method: ssmt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.ssmt
generated: 2026-08-22
tags: [mapdl-command]
---

# SSMT

PyMAPDL: `mapdl.ssmt(mt11='', mt22='', mt12='', t='', **kwargs)`

Specifies preintegrated membrane thermal effects for shell sections.

## Parameters

**mt11**, **mt22**, **mt12**: Membrane thermal effects component \[ **M** <sup>T</sup> \].

**t**: Temperature.

## Notes

The behavior of shell elements is governed by the generalized-stress/generalized-strain relationship of the [form](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PRESHELL_5.html#strpreshcons) :

(equation not available in the PyMAPDL source, see the Ansys help page)

The **SSMT** command, one of several [preintegrated shell section commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PRESHELL_5.html#membraneoptionnote), specifies the membrane thermal effects quantity (submatrix \[ **M** <sup>T</sup> \] data) for a preintegrated shell section. The section data defined is associated with the section most recently defined (via the [[sectype|SECTYPE]] command).

The \[ **M** <sup>T</sup> \] quantity represents membrane stress resultants caused by a unit raise in temperature on a fully constrained model. For a layered composite shell, it is usually necessary to specify both the \[ **M** <sup>T</sup> \] and \[ **B** <sup>T</sup> \] quantities (by issuing the **SSMT** and [[ssbt|SSBT]] commands, respectively).

Unspecified values default to zero.

Related commands are [[sspa|SSPA]], [[sspb|SSPB]], [[sspd|SSPD]], [[sspe|SSPE]], [[ssbt|SSBT]], and [[sspm|SSPM]].

For complete information, see [Creating a Preintegrated General Shell Section](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PRESHELL_5.html#strpreshcons)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SSMT.html
