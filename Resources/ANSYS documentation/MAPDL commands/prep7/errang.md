---
apdl: "ERRANG"
method: errang
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.errang
generated: 2026-08-22
tags: [mapdl-command]
---

# ERRANG

PyMAPDL: `mapdl.errang(emin='', emax='', einc='', **kwargs)`

Specifies the element range to be read from a file.

## Parameters

**emin**, **emax**, **einc**: Elements with numbers from `EMIN` (defaults to 1) to `EMAX` (defaults to 999999999) in steps of `EINC` (defaults to 1) will be read.

## Notes

Defines the element number range to be read ( [[eread|EREAD]] ) from the element file. If a range is also implied from the [[nrrang|NRRANG]] command, only those elements satisfying both ranges will be read.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ERRANG.html
