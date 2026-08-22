---
apdl: "SSBT"
method: ssbt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.ssbt
generated: 2026-08-22
tags: [mapdl-command]
---

# SSBT

PyMAPDL: `mapdl.ssbt(bt11='', bt22='', bt12='', t='', **kwargs)`

Specifies preintegrated bending thermal effects for shell sections.

## Parameters

**bt11**, **bt22**, **bt12**: Bending thermal effects component \[ **B** <sup>T</sup> \].

**t**: Temperature.

## Notes

The behavior of shell elements is governed by the generalized-stress/generalized-strain relationship of the [form](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PRESHELL_5.html#strpreshcons) :

(equation not available in the PyMAPDL source, see the Ansys help page)

The **SSBT** command, one of several [preintegrated shell section commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PRESHELL_5.html#membraneoptionnote), specifies the bending thermal effects quantity (submatrix \[ **B** <sup>T</sup> \] data) for a preintegrated shell section. The section data defined is associated with the section most recently defined (via the [[sectype|SECTYPE]] command).

The \[ **B** <sup>T</sup> \] quantity represents bending stress resultants caused by a unit raise in temperature on a fully constrained model. For a layered composite shell, it is usually necessary to specify both the \[ **B** <sup>T</sup> \] and \[ **M** <sup>T</sup> \] quantities (by issuing the **SSBT** and [[ssmt|SSMT]] commands, respectively).

Unspecified values default to zero.

Related commands are [[sspa|SSPA]], [[sspb|SSPB]], [[sspd|SSPD]], [[sspe|SSPE]], [[ssmt|SSMT]], and [[sspm|SSPM]].

If you are using the `SHELL181` or `SHELL281` element's Membrane option (KEYOPT(1) = 1), it is not necessary to issue this command.

For complete information, see [Creating a Preintegrated General Shell Section](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PRESHELL_5.html#strpreshcons)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SSBT.html
