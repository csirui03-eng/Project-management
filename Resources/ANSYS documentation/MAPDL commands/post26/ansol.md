---
apdl: "ANSOL"
method: ansol
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.set_up.SetUp.ansol
generated: 2026-08-22
tags: [mapdl-command]
---

# ANSOL

PyMAPDL: `mapdl.ansol(nvar='', node='', item='', comp='', name='', mat='', real='', ename='', datakey='', **kwargs)`

Specifies averaged element nodal data to be stored from the results file.

## Parameters

**nvar**: Arbitrary reference number assigned to this variable (2 to `NV` ( [[numvar|NUMVAR]] )). Overwrites any existing results for this variable.

**node**: Node number for which data are to be stored.

**item**: Label identifying the item. General item labels are shown in *ANSOL - General Result Item and Component Labels* below. Some items also require a component label.

**comp**: Component of the item (if required). General component labels are shown in *ANSOL - General Result Item and Component Labels*. Selected result components ( `Item` = SRES) are shown in *ANSOL - Selected Result Component Labels*.

**name**: 32-character name to identify the item on the printout and displays. Default: An eight-character label formed by concatenating the first four characters of the `Item` and `Comp` labels.

**mat**: Material number. Average is calculated based on the subset of elements with the specified material number. Default: Use all elements in the active set unless `Real` and/or `Ename` is specified.

**real**: Real number. Average is calculated based on the subset of elements with the specified real number. Default: Use all elements in the active set unless `Mat` and/or `Ename` is specified.

**ename**: Element type name. Average is calculated based on the subset of elements with the specified element type name. Default: Use all elements in the active set unless `Mat` and/or `Real` is specified.

**datakey**

Key to specify which data is stored:

- `AUTO` - [Nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) are used if they are available for the first applicable time step; otherwise, the element-based data is used, if available. (Default.)
- `ESOL` - Only element-based results are used. If they are not available, the command is ignored.
- `NAR` - Only nodal-averaged results are used. If they are not available, the command is ignored.

`Mat`, `Real`, and `Ename` are ignored when nodal-averaged results are used.

## Notes

Valid item and component labels for element nodal results are listed in *ANSOL - General Result Item and Component Labels*.

**ANSOL** defines element nodal results data to be stored from a results file ( [[file|FILE]] ). Not all items are valid for all nodes. See the input and output summary tables of each element attached to the node for the available items.

If [nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) ( [[outres|OUTRES]],NAR or another nodal-averaged label) are available, then **ANSOL** uses the nodal- averaged data for the applicable items (S, EPEL, EPPL, EPCR, EPTH) as dictated by the by `DataKey` argument. By default, ( `DataKey` = AUTO), the availability of nodal-averaged results or element- based data is determined at the first load step that has results for the associated item. For more information, see [Postprocessing Nodal-Averaged Results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#)

**Coordinate systems:** Generally, element nodal quantities stored by **ANSOL** are obtained in the solution coordinate system ( [[rsys|RSYS]], SOLU) and then averaged. There are some exceptions as listed below. **ANSOL** does not transform results from [[rsys|RSYS]],SOLU (or from the coordinate systems described for the exceptions below) to other coordinate systems. Verify that all elements attached to the subject node have the same coordinate system before using **ANSOL**.

- Layered element results are in the layer coordinate system ( [[rsys|RSYS]],LSYS). You can further specify the element nodal results, for some elements, with the [[shell|SHELL]], [[layerp26|LAYERP26]], and [[force|FORCE]] commands.
- When **ANSOL** is used to store nodal-averaged result data (based on the `DataType` setting), the global Cartesian coordinate system ( [[rsys|RSYS]],0) is used.

**Shell elements:** The default shell element coordinate system is based on node ordering. For shell elements the adjacent elements could have a different [[rsys|RSYS]],SOLU, making the resultant averaged data inconsistent. A message to this effect is issued when **ANSOL** is used in models containing shell elements. Ensure that consistent coordinate systems are active for all associated elements used by the **ANSOL** command.

**Derived quantities:** Some of the result items supported by **ANSOL** ( *ANSOL - General Result Item and Component Labels* ) are derived from the component quantities. Issue [[avprin|AVPRIN]] to specify the principal and vector sum quantity averaging methods.

**Default:** If `Mat`, `Real`, and `Ename` are not specified, all elements attached to the node are considered. When a material ID, real constant ID, or element-type discontinuity is detected at a node, a message is issued. For example, in a FSI analysis, a `FLUID30` element at the structure interface would be considered; however, because it contains no SX result, it is not used during [[store|STORE]] operations.

### ANSOL - General Result Item and Component Labels

General Item and Component Labels **ANSOL**, `NVAR,NODE,Item,Comp,Name,Mat,Real,Ename,DataType`

| Item | Comp | Description |
|----|----|----|
| S | X, Y, Z, XY, YZ, XZ | Component stress. This item stores [nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) if they are available on the results file. |
|  | 1, 2, 3 | Principal stress. |
|  | INT | Stress intensity. |
|  | EQV | Equivalent stress. |
| EPEL | X, Y, Z, XY, YZ, XZ | Component elastic strain. |
|  | 1, 2, 3 | Principal elastic strain. |
|  | INT | Elastic strain intensity. |
|  | EQV | Elastic equivalent strain. |
| EPPL | X, Y, Z, XY, YZ, XZ | Component plastic strain. |
|  | 1, 2, 3 | Principal plastic strain. |
|  | INT | Plastic strain intensity. |
|  | EQV | Plastic equivalent strain. |
| EPCR | X, Y, Z, XY, YZ, XZ | Component creep strain. |
|  | 1,2,3 | Principal creep strain. |
|  | INT | Creep strain intensity. |
|  | EQV | Creep equivalent strain. |
| EPTH | X, Y, Z, XY, YZ, XZ | Component thermal strain. |
|  | 1, 2, 3 | Principal thermal strain. |
|  | INT | Thermal strain intensity. |
|  | EQV | Thermal equivalent strain. |
| ESIG | X, Y, Z, XY, YZ, XZ | Components of Biot's effective stress. |
|  | 1, 2, 3 | Principal stresses of Biot's effective stress. |
|  | INT | Stress intensity of Biot's effective stress. |
|  | EQV | Equivalent stress of Biot's effective stress. |
| NL | SEPL | Equivalent stress (from stress-strain curve). |
|  | SRAT | Stress state ratio. |
|  | HPRES | Hydrostatic pressure. |
|  | EPEQ | Accumulated equivalent plastic strain. |
|  | CREQ | Accumulated equivalent creep strain. |
|  | PSV | Plastic state variable. |
|  | PLWK | Plastic work/volume. |
| CONT | STAT For more information about the meaning of contact status and its possible values, see [Reviewing Results in POST1](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/Hlp_ctec_revresu.html#ctecpostslide) | Contact status. |
|  | PENE | Contact penetration. |
|  | PRES | Contact pressure. |
|  | SFRIC | Contact friction stress. |
|  | STOT | Contact total stress (pressure plus friction). |
|  | SLIDE | Contact sliding distance. |
|  | GAP | Contact gap distance. |
|  | FLUX | Total heat flux at contact surface. |
|  | CNOS | Total number of contact status changes during substep. |
|  | FPRS | Fluid penetration pressure. |
| TG | X, Y, Z, SUM `Comp` = SUM is not supported for coupled pore-pressure-thermal (CPT `nnn` ) elements. | Component thermal gradient or vector sum. |
| TF | X, Y, Z, SUM | Component thermal flux or vector sum. |
| PG | X, Y, Z, SUM | Component pressure gradient or vector sum. |
| EF | X, Y, Z, SUM | Component electric field or vector sum. |
| D | X, Y, Z, SUM | Component electric flux density or vector sum. |
| H | X, Y, Z, SUM | Component magnetic field intensity or vector sum. |
| B | X, Y, Z, SUM | Component magnetic flux density or vector sum. |
| CG | X, Y, Z, SUM | Component concentration gradient or vector sum. |
| DF | X, Y, Z, SUM | Component diffusion flux density or vector sum. |
| JC | X, Y, Z, SUM | Conduction current density for elements that support conduction current calculation. Components (X, Y, Z) and vector sum (SUM). |
| FFLX | X, Y, Z | Fluid-flow flux in poromechanics. |
| FGRA | X, Y, Z | Fluid pore-pressure gradient in poromechanics. |
| PMSV | VRAT, PPRE, DSAT, RPER | Void volume ratio, pore pressure, degree of saturation, and relative permeability for coupled pore-pressure-thermal elements. |
| NS | X, Y, Z, XY, YZ, XZ | [Nominal strain](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_mat5.html#eq4dc2eb28-41da-4d81-b0d0-8716ce41a6e1) for hyperelastic material, reported in the current configuration (unaffected by [[rsys\|RSYS]] ). |
| MPLA | DMAC, DMAX | Microplane damage, macroscopic and maximum values. |
| MPDP | TOTA, TENS, COMP, RW | Microplane homogenized total, tension, and compression damages (TOTA, TENS, COMP), and split weight factor (RW). |
| EPFR |  | Free strain in porous media |
| DAMAGE | 1,2,3,MAX | Damage in directions 1, 2, 3 (1, 2, 3) and the maximum damage (MAX). |
| GDMG |  | Damage |
| IDIS |  | Structural-thermal dissipation rate |

### ANSOL - Selected Result Component Labels

Selected Result Component Labels **ANSOL**, `NVAR`, `NODE`,SRES, `Comp`, `Name`, `Mat`, `Real`, `Ename`

| Comp       | Description                             |
|------------|-----------------------------------------|
| SVAR `n`   | The `n` th state variable.              |
| FLDUF0 `n` | The `n` th user-defined field variable. |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANSOL.html
