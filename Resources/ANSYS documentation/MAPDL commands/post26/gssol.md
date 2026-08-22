---
apdl: "GSSOL"
method: gssol
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.set_up.SetUp.gssol
generated: 2026-08-22
tags: [mapdl-command]
---

# GSSOL

PyMAPDL: `mapdl.gssol(nvar='', item='', comp='', name='', **kwargs)`

Specifies which results to store from the results file when using generalized plane strain.

## Parameters

**nvar**: Arbitrary reference number or name assigned to this variable. Variable numbers can be 2 to `NV` ( [[numvar|NUMVAR]] ) while the name can be an eight byte character string. Overwrites any existing results for this variable.

**item**

Label identifying item to be stored.

- `LENGTH` - Change of fiber length at the ending point.
- `ROT` - Rotation of the ending plane during deformation.
- `F` - Reaction force at the ending point in the fiber direction.
- `M` - Reaction moment applied on the ending plane.

**comp**

Component of the item, if Item = ROT or M.

- `X` - The rotation angle or reaction moment of the ending plane about X.
- `Y` - The rotation angle or reaction moment of the ending plane about Y.

**name**: Thirty-two character name identifying the item on the printout and display. Defaults to the label formed by concatenating the first four characters of the `Item` and `Comp` labels.

## Notes

This command stores the results (new position of the ending plane after deformation) for generalized plane strain. All outputs are in the global Cartesian coordinate system. For more information about the generalized plane strain feature, see Generalized Plane Strain Option of Current-Technology Solid Elements in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GSSOL.html
