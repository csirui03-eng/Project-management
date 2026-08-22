---
apdl: "EGID"
method: egid
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.egid
generated: 2026-08-22
tags: [mapdl-command]
---

# EGID

PyMAPDL: `mapdl.egid(val='', **kwargs)`

Specifies a global identifier for a set of `MESH200` elements.

## Parameters

**val**: An integer for identifying a set of `MESH200` elements used in a [reinforcing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_compreinfdirectemb.html) analysis. Default = 1.

## Notes

`VAL` is a global identifier that you assign to a set of `MESH200` elements in a [reinforcing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_compreinfdirectemb.html) analysis. The command is valid only when using the [mesh-independent method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strreinfworkflow.html#) for defining reinforcing.

The global identifier that you specify is transferred to the reinforcing members (individual reinforcings) when they are generated ( [[ereinf|EREINF]] ).

Issue **EGID** before generating the `MESH200` elements.

If necessary, you can change the global identifier for an existing set of `MESH200` elements ( [[emodif|EMODIF]] ).

For more information about using this command in a mesh-independent reinforcing analysis, see [Selecting and Displaying Groups of Reinforcing Members](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strreinfworkflow.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EGID.html
