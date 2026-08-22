---
apdl: "LCOPER"
method: lcoper
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.load_case_calculations.LoadCaseCalculations.lcoper
generated: 2026-08-22
tags: [mapdl-command]
---

# LCOPER

PyMAPDL: `mapdl.lcoper(oper='', lcase1='', oper2='', lcase2='', sweepang='', **kwargs)`

Performs load case operations.

## Parameters

**oper**

Valid operations are:

- `ZERO` - Zero results portion of database ( `LCASE1` ignored).
- `SQUA` - Square database values ( `LCASE1` ignored).
- `SQRT` - Square root of database (absolute) values ( `LCASE1` ignored).
- `LPRIN` - Recalculate line element principal stresses ( `LCASE1` ignored). Stresses are as shown for the NMISC items of the [[etable|ETABLE]] command for the specific line element type.
- `ADD` - Add `LCASE1` to database values.
- `SUB` - Subtract `LCASE1` from database values.
- `SRSS` - Square root of the sum of the squares of database and `LCASE1`.
- `MIN` - Compare and save in database the algebraic minimum of database and `LCASE1`.
- `MAX` - Compare and save in database the algebraic maximum of database and `LCASE1`.
- `ABMN` - Compare and save in database the absolute minimum of database and `LCASE1` (based on magnitudes, then apply the corresponding sign).
- `ABMX` - Compare and save in database the absolute maximum of database and `LCASE1` (based on magnitudes, then apply the corresponding sign).

**lcase1**: First load case in the operation (if any). See `LCNO` of the [[lcdef|LCDEF]] command. If ALL, repeat operations using all selected load cases ( [[lcsel|LCSEL]] ).

**oper2**

Valid operations are:

- `MULT` - Multiplication: `LCASE1` \* `LCASE2`
- `CPXMAX` - This option does a phase angle sweep to calculate the maximum of derived stresses, equivalent strain, and principal strains for a complex solution where `LCASE1` is the real part and `LCASE2` is the imaginary part. The `Oper` field is not applicable with this option. Also, the [[lcabs|LCABS]] and [[sumtype|SUMTYPE]] commands have no effect on this option. The value of S3 will be a minimum. Absolute maximum is obtained for component quantity. This option does not apply to derived displacement amplitude (USUM). Load case writing ( [[lcwrite|LCWRITE]] ) is not supported. See [POST1 and POST26 - Complex Results Postprocessing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_post15.html#thyeq1cdmplxres6a)

**lcase2**: Second load case. Used only with `Oper2` operations.

**sweepang**: Sweep angle increment in degrees for phase sweep. Used only with `Oper2` = CPXMAX. (Default = 1°)

## Notes

**LCOPER** operates on the database and one or two load cases according to:

- Database = Database `Oper` ( `LCASE1` `Oper2` `LCASE2` )

where operations `Oper` and `Oper2` are as described above.

Absolute values and scale factors may be applied to the load cases before the operations ( [[lcabs|LCABS]], [[lcfact|LCFACT]] ). If `LCASE1` is not specified, only operation `Oper` is performed on the current database. If `LCASE2` is specified, operation `Oper2` is performed before operation `Oper`. If `LCASE2` is not specified, operation `Oper2` is ignored.

Solution items not contained ( [[outres|OUTRES]] ) in either the database or the applicable load cases will result in a null item during a load case operation. Harmonic element data read from a result file load case are processed at zero degrees.

Load case combinations must be performed on load cases from the same results file. Combining load cases from different results files is not supported.

Load case combinations of element-based solutions are performed in the solution coordinate system, and the data resulting from load case combinations are stored in the solution coordinate system. The resultant data are then transformed to the active results coordinate system ( [[rsys|RSYS]] ) when listed or displayed. Except in the cases of `Oper` = LPRIN, ADD, or SUB, you must use [[rsys|RSYS]],SOLU to list or display results. In the case of layered elements, the layer ( [[layer|LAYER]] ) must also be specified.

If [nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) are a part of the load case combination, the resulting nodal-averaged result data are in the global Cartesian coordinate system. Furthermore, the resulting numerical values may differ from the same **LCOPER** operation performed on the same data stored as element results. The SQUA, SQRT, LPRIN, and SRSS operations are not valid when applied to nodal averaged results. For more information, see [Nodal-Averaged Results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost)

Use the [[force|FORCE]] command prior to any combination operation to correctly combine the requested force type.

If Oper2=CPXMAX, the derived stresses and strain calculation do not apply to line elements.

For details on using load case combination, see [Creating and Combining Load Cases](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_4.html#bassummtlm51499325)

For cyclic symmetry ( [[cyclic|CYCLIC]] ), **LCOPER** operates on the raw base and duplicate sector values. It cannot be used on the expanded values ( [[cycexpand|/CYCEXPAND]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LCOPER.html
