---
apdl: "BFPORT"
method: bfport
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_body_loads.FeBodyLoads.bfport
generated: 2026-08-22
tags: [mapdl-command]
---

# BFPORT

PyMAPDL: `mapdl.bfport(cmname='', **kwargs)`

Transfers a thermal body-force load (HGEN) from selected `MESH200` elements to reinforcing elements.

## Parameters

**cmname**: Component name containing a list of selected `MESH200` elements.

## Notes

This command transfers a thermal body-force load (HGEN) from selected `MESH200` elements to associated reinforcing elements or members (individual reinforcings). The association is established via [[ereinf|EREINF]] using the [mesh-independent method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strreinfworkflow.html#) for defining reinforcing.

Issue this command after issuing [[ereinf|EREINF]].

Select `MESH200` elements by issuing this command and specifying the component, or by issuing [[esel|ESEL]]. (If you specify a component name, [[esel|ESEL]] is ignored.)

This command supports a thermal body-force load (HGEN) only.

To define the thermal body-force load on `MESH200` elements, issue [[bfe|BFE]] or [[bf|BF]].

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BFPORT.html
