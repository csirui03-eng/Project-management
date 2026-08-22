---
apdl: "MAPVAR"
method: mapvar
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.rezoning.Rezoning.mapvar
generated: 2026-08-22
tags: [mapdl-command]
---

# MAPVAR

PyMAPDL: `mapdl.mapvar(option='', matid='', istrtstress='', ntenstress='', istrtstrain='', ntenstrain='', istrtvect='', nvect='', **kwargs)`

Defines tensors and vectors in user-defined state variables for rezoning and in 2D to 3D analyses.

## Parameters

**option**

- `DEFINE` - Define variables for the specified `MatId` material ID (default).
- `LIST` - List the defined variables for the specified `MatId` material ID.

**matid**

The material ID for the state variables which you are defining ( `Option` = DEFINE) or listing ( `Option` = LIST).

When `Option` = LIST, the default value for this argument is ALL (which lists all defined variables). When `Option` = DEFINE, you must explicitly specify a material ID.

**istrtstress**: The start position of stress-like tensors in the state variables. This value must be either a positive integer or 0 (meaning no stress-like tensors).

**ntenstress**: The number of stress-like tensors in the state variables. This value must be either a positive integer (or 0), and all stress-like tensors must be contiguous.

**istrtstrain**: The start position of strain-like tensors in the state variables. This value must be either a positive integer or 0 (meaning no strain-like tensors).

**ntenstrain**: The number of strain-like tensors in the state variables. This value must be either a positive integer (or 0), and all strain-like tensors must be contiguous.

**istrtvect**: The start position of vectors in the state variables. This value must be either a positive integer or 0 (meaning no vectors).

**nvect**: The number of vectors in the state variables. This value must be either a positive integer (or 0), and all vectors must be contiguous.

## Notes

The **MAPVAR** command identifies the tensors and vectors in user-defined state variables ( [[tb|TB]],STATE) for user-defined materials ( [[tb|TB]],USER and [UserMat](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#) or [UserMatTh](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#) ) or user- defined creep laws ( [[tb|TB]],CREEP,,,,100 and UserCreep ).

To handle large-rotation effects and to correctly differentiate between tensor- and vector-mapping, specify the start position of specific state variables. For stress-like tensors, the shear components saved as state variables are the tensor component. For strain-like tensors, the shear components saved as state variables are twice the tensor components. Therefore, issue the **MAPVAR** command to define the stress-like and strain-like tensors individually. The command ensures that user-defined state variables are mapped correctly during [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html) and in [2D to 3D analyses](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/Hlp_G_ADV2DTO3DREST.html).

In a rezoning operation, **MAPVAR** must be issued after remeshing ( [[remesh|REMESH]],FINISH) but before mapping ( [[mapsolve|MAPSOLVE]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MAPVAR.html
