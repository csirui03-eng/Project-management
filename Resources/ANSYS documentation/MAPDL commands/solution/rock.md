---
apdl: "ROCK"
method: rock
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.rock
generated: 2026-08-22
tags: [mapdl-command]
---

# ROCK

PyMAPDL: `mapdl.rock(cgx='', cgy='', cgz='', omx='', omy='', omz='', **kwargs)`

Specifies a rocking response spectrum.

## Parameters

**cgx**, **cgy**, **cgz**: Global Cartesian X, Y, and Z location of center of rotation about which rocking occurs.

**omx**, **omy**, **omz**: Global Cartesian angular components of the rocking.

## Notes

Specifies a rocking response spectrum effect in the spectrum ( [[antype|ANTYPE]],SPECTR) analysis.

The excitation direction with rocking included is not normalized to one; rather, it scales the spectrum. For example, consider a node at coordinates (1,1,0), subject to an excitation in the X direction ( `SEDX` = 1.0 on [[sed|SED]] ), and a rocking with center `CGX` = 1.0, `CGY` = `CGZ` = 0, and angular component about Z ( `OMZ` = 0.5). The total excitation direction at this node is:

(equation not available in the PyMAPDL source, see the Ansys help page)

So that half the spectrum input is applied at this node.

For more information on the equations, see [Participation Factors and Mode Coefficients](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc7.html#eqe483f2f2-aaa1-4080-a835-10c0e1e18f57)

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ROCK.html
