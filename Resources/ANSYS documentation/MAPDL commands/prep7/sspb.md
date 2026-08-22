---
apdl: "SSPB"
method: sspb
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.sspb
generated: 2026-08-22
tags: [mapdl-command]
---

# SSPB

PyMAPDL: `mapdl.sspb(b11='', b21='', b31='', b22='', b32='', b33='', t='', b12='', b13='', b23='', **kwargs)`

Specifies a preintegrated coupling stiffness for shell sections.

## Parameters

**b11**, **b21**, **b31**, **b22**, **b32**, **b33**: Coupling stiffness component (symmetric lower part of submatrix \[ **B** \]).

**t**: Temperature.

**b12**, **b13**, **b23**: Upper part of submatrix \[ **B** \]

## Notes

The behavior of shell elements is governed by the generalized-stress/generalized-strain relationship of the [form](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PRESHELL_5.html#strpreshcons) :

(equation not available in the PyMAPDL source, see the Ansys help page)

If the coefficients `B` 12, `B` 13, `B` 23 are undefined, the program uses a symmetric form of submatrix \[ **B** \]. If any one of the coefficients `B` 12, `B` 13, `B` 23 is nonzero, the program considers submatrix \[ **B** \] to be unsymmetric.

The **SSPB** command, one of several [preintegrated shell section commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PRESHELL_5.html#membraneoptionnote), specifies the coupling stiffness quantity (submatrix \[ **B** \] data) for a preintegrated shell section. The section data defined is associated with the section most recently defined (via the [[sectype|SECTYPE]] command).

Unspecified values default to zero.

Related commands are [[sspa|SSPA]], [[sspd|SSPD]], [[sspe|SSPE]], [[ssmt|SSMT]], [[ssbt|SSBT]], and [[sspm|SSPM]].

If you are using the `SHELL181` or `SHELL281` element's Membrane option (KEYOPT(1) = 1), it is not necessary to issue this command.

For complete information, see [Creating a Preintegrated General Shell Section](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PRESHELL_5.html#strpreshcons)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SSPB.html
