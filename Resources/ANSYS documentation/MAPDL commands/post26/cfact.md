---
apdl: "CFACT"
method: cfact
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.controls.Controls.cfact
generated: 2026-08-22
tags: [mapdl-command]
---

# CFACT

PyMAPDL: `mapdl.cfact(rfacta='', ifacta='', rfactb='', ifactb='', rfactc='', ifactc='', **kwargs)`

Defines complex scaling factors to be used with operations.

**Command default:**

Use the real factors as described with the operation command.

## Parameters

**rfacta**: Real portion of the complex scale factor used in place of `FACTA`.

**ifacta**: Imaginary portion of the complex scale factor used in place of `FACTA`.

**rfactb**: Real portion of the complex scale factor used in place of `FACTB`.

**ifactb**: Imaginary portion of the complex scale factor used in place of `FACTB`.

**rfactc**: Real portion of the complex scale factor used in place of `FACTC`.

**ifactc**: Imaginary portion of the complex scale factor used in place of `FACTC`.

## Notes

Defines complex scale factors to be used with the operations ( [[add|ADD]], [[prod|PROD]], etc.). If this command is supplied, these complex factors override any real factors ( `FACTA`, `FACTB`, `FACTC` ) supplied on the operation commands. Factors are typically involved in scaling a specified variable, such as in the term `FACTA` x `IA` of the [[add|ADD]] command to scale variable `IA` before the ADD operation.

When the **CFACT** command is active, defaults are as follows: 1) if the complex factor is not specified, but the variable upon which it acts (such as `IA` ) is specified, the factor defaults to 1.0+ i 0.0; 2) if the variable upon which the factor operates is not specified, but the factor is specified, the variable defaults to 1.0 so that the term in the operation becomes the complex factor itself; 3) if neither the factor nor the variable number is supplied, the term is omitted from the operation. Once the operation (such as the [[add|ADD]] command) has been processed, the **CFACT** command becomes inactive and must be specified again if it is to be used.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CFACT.html
