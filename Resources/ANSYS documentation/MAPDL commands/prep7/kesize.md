---
apdl: "KESIZE"
method: kesize
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.kesize
generated: 2026-08-22
tags: [mapdl-command]
---

# KESIZE

PyMAPDL: `mapdl.kesize(npt='', size='', fact1='', fact2='', **kwargs)`

Specifies the edge lengths of the elements nearest a keypoint.

## Parameters

**npt**: Number of the keypoint whose lines will be adjusted. If ALL, use all selected keypoints ( [[ksel|KSEL]] ). If `NPT` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**size**: Size of elements along lines nearest keypoint `NPT` (overrides any other specified size). If `SIZE` is zero (or blank), use `FACT1` or `FACT2`.

**fact1**: Scale factor applied to a previously defined `SIZE`. Not used if `SIZE` is input.

**fact2**: Scale factor applied to the minimum element division at keypoint `NPT` for any attached line. This feature is useful with adaptive mesh refinement. Not used if `SIZE` or `FACT1` is input.

## Notes

Affects only the line divisions adjacent to the keypoint on lines not previously assigned divisions by other line commands ( [[lesize|LESIZE]], etc.). The remaining line divisions are determined from the division nearest the keypoint at the other end of the line (specified by another **KESIZE** command or the [[esize|ESIZE]] command). Divisions are transferred to the lines during the mesh operation. If smart element sizing is being used ( [[smrtsize|SMRTSIZE]] ), **KESIZE** specifications may be overridden (that is, a smaller element size may be used) to accommodate curvature and small features.

This command is valid in any processor. The command is also valid for [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KESIZE.html
