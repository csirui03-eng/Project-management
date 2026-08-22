---
apdl: "ETABLE"
method: etable
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.element_table.ElementTable.etable
generated: 2026-08-22
tags: [mapdl-command]
---

# ETABLE

PyMAPDL: `mapdl.etable(lab='', item='', comp='', option='', **kwargs)`

Fills a table of element values for further processing.

## Parameters

**lab**

Any unique user-defined label for use in subsequent commands and output headings. A valid label has a maximum of eight characters and is not a general predefined `Item` label. Default: An eight- character label formed by concatenating the first four characters of the `Item` and `Comp` labels.

If the same as a previous user label, the result item is included under the same label. Up to 200 different labels can be defined.

The following predefined labels are reserved:

- `REFL` - Refills all tables previously defined with the **ETABLE** commands (not the [[calc|CALC]] module commands) according to the latest **ETABLE** specifications. It is convenient for refilling tables after the load step ( [[set|SET]] ) has changed. Remaining fields are ignored.
- `STAT` - Displays stored table values.
- `ERAS` - Erases the entire table.

**item**: Label identifying the item. General item labels are shown in the tables below. Some items also require a component label. Character parameters are valid. `Item` = ERAS erases a `Lab` column.

**comp**: Component of the item (if required). General component labels are shown in the tables below. Character parameters can be used.

**option**

Option for storing element table data:

- `MIN` - Store minimum element nodal value of the specified item component.
- `MAX` - Store maximum element nodal value of the specified item component.
- `AVG` - Store averaged element centroid value of the specified item component (default).

## Notes

**ETABLE** defines a table of values per element (the element table) for use in further processing. The element table is organized similar to a spreadsheet, with rows representing all selected elements and columns consisting of result items which have been moved into the table ( `Item`, `Comp` ) via **ETABLE**. Each column of data is identified by a user-defined label ( `Lab` ) for listings and displays.

After entering the data into the element table, you are not limited to listing or displaying your data ( [[plesol|PLESOL]], [[presol|PRESOL]], etc.). You can also perform many types of operations on your data, such as adding or multiplying columns ( [[sadd|SADD]], [[smult|SMULT]] ), defining allowable stresses for safety calculations ( [[sallow|SALLOW]] ), or multiplying one column by another ( [[smult|SMULT]] ). For more information, see [Getting Started](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/afbRsqe0ldm.html)

For [reinforcing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_compreinfdirectemb.html) elements, this command displays the results of reinforcing member (individual reinforcing) selected via the [[layer|LAYER]], `N` command (where `N` is a given reinforcing member). [[layer|LAYER]],0 (default) or [[layer|LAYER]],1 selects the first reinforcing member.

Various results data can be stored in the element table. For example, many items for an element are inherently single-valued (one value per element). The single-valued items include: SERR, SDSG, TERR, TDSG, SENE, TENE, KENE, ASENE, PSENE, AKENE, PKENE, DENE, WEXT, AENE, JHEAT, JS, VOLU, and CENT. All other items are multivalued (varying over the element, such that there is a different value at each node). Because only one value is stored in the element table per element, an average value (based on the number of contributing nodes) is calculated for multivalued items. Exceptions to this averaging procedure are FMAG and all element force items, which represent the sum only of the contributing nodal values.

Two methods of data access can be used with the **ETABLE** command. The method you select depends upon the type of data that you want to store. Some results can be accessed via a generic label (Component Name method), while others require a label and number (Sequence Number method).

The component name method is used to access the general element data (that is, element data which is generally available to most element types or groups of element types). All of the single-valued items and some of the more general multivalued items are accessible with the Component Name method. Various element results depend on the calculation method and the selected results location ( [[avprin|AVPRIN]], [[rsys|RSYS]], [[layer|LAYER]], [[shell|SHELL]], and [[esel|ESEL]] ).

Although nodal data is readily available for listing and display ( [[prnsol|PRNSOL]], [[plnsol|PLNSOL]] ) without using the element table, you can also use the Component Name method to enter these results into the element table for further "worksheet" manipulation. (See [Getting Started](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/afbRsqe0ldm.html) `Item` and `Comp` labels for the component name method is shown in *ETABLE - General Result Item and Component Labels*. See *ETABLE - Selected Result Component Labels* for a list of selected result ( `Item` = SRES) `Comp` labels.

The sequence number method enables you to view results for data that is not averaged (such as pressures at nodes, temperatures at integration points, etc.), or data that is not easily described in a generic fashion (such as all derived data for structural line elements and contact elements, all derived data for thermal line elements, layer data for layered elements, etc.). A table illustrating the `Items` (such as LS, LEPEL, LEPTH, SMISC, NMISC, SURF, etc.) and corresponding sequence numbers for each element is shown in the Output Data section of each element description.

Some element table data are reported in the results coordinate system. These include all component results (for example, UX, UY, etc.; SX, SY, etc.). The solution writes component results in the database and on the results file in the solution coordinate system. When you issue the **ETABLE** command, these results are then transformed into the results coordinate system ( [[rsys|RSYS]] ) before being stored in the element table. The default results coordinate system is global Cartesian ( [[rsys|RSYS]],0). All other data are retrieved from the database and stored in the element table with no coordinate transformation.

To display the stored table values, issue the [[pretab|PRETAB]], [[pletab|PLETAB]], or **ETABLE**,STAT command. To erase the entire table, issue **ETABLE**,ERAS. To erase a `Lab` column, issue **ETABLE**, `Lab`,ERAS.

When the GUI is enabled, if a **Delete** operation in a Define Element Table Data dialog box writes this command to a log file ( `Jobname.LOG` or `Jobname.LGW` ), the program sets `Lab` = blank, `Item` = ERASE, and `Comp` = an integer number. In this case, the program has assigned a value of `Comp` that corresponds to the location of a chosen variable name in the dialog list. It is not intended that you type in such a location value for `Comp` in a session; however, a file that contains a GUI-generated **ETABLE** command of this form can be used for batch input or the [[input|/INPUT]] command.

The MIN and MAX options are not available for thermal elements.

The element table data option ( `Option` ) is not available for all output items. See the table below for supported items.

### ETABLE - General Result Item and Component Labels

General Item and Component Labels **ETABLE**, `Lab, Item, Comp`

| Item | Comp | Description |
|----|----|----|
| Valid Item Labels for Degree of Freedom Results |  |  |
| U | X, Y, Z | X, Y, or Z structural displacement. |
| ROT | X, Y, Z | X, Y, or Z structural rotation. |
| TEMP For `SHELL131` and `SHELL132` elements with KEYOPT(3) = 0 or 1, use labels TBOT, TE2, TE3, ..., TTOP instead of TEMP. |  | Temperature. |
| PRES |  | Pressure. |
| VOLT |  | Electric potential. |
| GFV1, GFV2, GFV3 |  | Nonlocal field values 1, 2, and 3. |
| MAG |  | Magnetic scalar potential. |
| V | X, Y, Z | X, Y, or Z fluid velocity. |
| A | X, Y, Z | X, Y, or Z magnetic vector potential. |
| CONC |  | Concentration. |
| CURR |  | Current. |
| EMF |  | Electromotive force drop. |
| Valid Item and Component Labels for Element Results |  |  |
| S Element table option ( `Option` ) is available for this element output data item. | X, Y, Z, XY, YZ, XZ | Component stress. |
|  | 1, 2, 3 | Principal stress. |
|  | INT | Stress intensity. |
|  | EQV | Equivalent stress. |
| EPEL | X, Y, Z, XY, YZ, XZ | Component elastic strain. |
|  | 1, 2, 3 | Principal elastic strain. |
|  | INT | Elastic strain intensity. |
|  | EQV | Elastic equivalent strain. |
| EPTH | X, Y, Z, XY, YZ, XZ | Component thermal strain. |
|  | 1, 2, 3 | Principal thermal strain. |
|  | INT | Thermal strain intensity. |
|  | EQV | Thermal equivalent strain. |
| EPDI | X, Y, Z, XY, YZ, XZ | Component diffusion strain. |
|  | 1, 2, 3 | Principal diffusion strain. |
|  | EQV | Diffusion equivalent strain. |
|  | INT | Diffusion strain intensity. |
| EPPL | X, Y, Z, XY, YZ, XZ | Component plastic strain. |
|  | 1, 2, 3 | Principal plastic strain. |
|  | INT | Plastic strain intensity. |
|  | EQV | Plastic equivalent strain. |
| EPCR | X, Y, Z, XY, YZ, XZ | Component creep strain. |
|  | 1, 2, 3 | Principal creep strain. |
|  | INT | Creep strain intensity. |
|  | EQV | Creep equivalent strain. |
| EPSW |  | Swelling strain. |
| EPTO | X, Y, Z, XY, YZ, XZ | Component total mechanical strain ( excluding thermal) (EPEL + EPPL + EPCR). |
|  | 1, 2, 3 | Principal total mechanical strain. |
|  | INT | Total mechanical strain intensity. |
|  | EQV | Total equivalent mechanical strain. |
| EPTT | X, Y, Z, XY, YZ, XZ | Component total strain including thermal, diffusion, and swelling (EPEL + EPTH + EPPL + EPDI + EPCR + EPSW). |
|  | 1, 2, 3 | Principal total strain. |
|  | INT | Total strain intensity. |
|  | EQV | Total equivalent strain. |
| NL | SEPL | Equivalent stress (from stress-strain curve). |
|  | SRAT | Stress state ratio. |
|  | HPRES | Hydrostatic pressure. |
|  | EPEQ | Accumulated equivalent plastic strain. |
| SEND | ELASTIC The results for this postprocessing SEND component are invalid for `ELBOW290` when that element is used with viscoelastic or viscohyperelastic materials. | Elastic strain energy density. (For [viscoelastic](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/evis.html#mat_harmvisco) and [sintering](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#) materials, the [stored energy](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/evis.html#eq92b60ee3-7e22-457b-9543-53f86d16432a).) |
|  | PLASTIC | Plastic strain energy density. |
|  | CREEP | Creep strain energy density. |
|  | DAMAGE | Damage strain energy density. |
|  | VDAM | Viscoelastic dissipation energy density. |
|  | VREG | Visco-regularization strain energy density. |
|  | DISS | Structural-thermal dissipation. |
|  | ENTO | Total strain energy density (sum of ELASTIC, PLASTIC, and CREEP strain energy densities). |
| SVAR | 1 to MAX | State variable. |
| CDM | DMG | Damage variable. |
|  | LM | Maximum previous strain energy for virgin material. |
| FAIL | MAX For MPC-based contact definitions, the value of STAT can be negative. This indicates that one or more contact constraints were intentionally removed to prevent overconstraint. STAT = -3 is used for MPC bonded contact; STAT = -2 is used for MPC no-separation contact. | Maximum of all active failure criteria defined at the current location ( [[fctyp\|FCTYP]] ). |
|  | EMAX | Maximum Strain Failure Criterion. |
|  | SMAX | Maximum Stress Failure Criterion. |
|  | TWSI | Tsai-Wu Strength Index Failure Criterion. |
|  | TWSR | Inverse of Tsai-Wu Strength Ratio Index Failure Criterion. |
|  | HFIB Some element- and material-type limitations apply. For more information, see [[prerr\|PRERR]]. | Hashin Fiber Failure Criterion. |
|  | HMAT | Hashin Matrix Failure Criterion. |
|  | PFIB | Puck Fiber Failure Criterion. |
|  | PMAT | Puck Matrix Failure Criterion. |
|  | L3FB | LaRc03 Fiber Failure Criterion. |
|  | L3MT | LaRc03 Matrix Failure Criterion. |
|  | L4FB | LaRc04 Fiber Failure Criterion. |
|  | L4MT | LaRc04 Matrix Failure Criterion. |
|  | USR1, USR2,..., USR9 When using the [[emft\|EMFT]] procedure to calculate electromagnetic force ( `PLANE121`, `SOLID122`, `SOLID123`, `PLANE233`, `SOLID236` or `SOLID237` elements only), the FMAG sum will be zero or near zero. | User-defined failure criteria. |
| PFC | MAX Failure criteria are based on the effective stresses in the damaged material. | Maximum of all failure criteria defined at current location. |
|  | FT | Fiber tensile failure criteria. |
|  | FC | Fiber compressive failure criteria. |
|  | MT | Matrix tensile failure criteria. |
|  | MC | Matrix compressive failure criteria. |
| PDMG | STAT | Damage status (0 = undamaged, 1 = damaged, 2 = completely damaged). |
|  | FT | Fiber tensile damage variable. |
|  | FC | Fiber compressive damage variable. |
|  | MT | Matrix tensile damage variable. |
|  | MC | Matrix compressive damage variable. |
|  | S | Shear damage variable (S). |
|  | SED | Energy dissipated per unit volume. |
|  | SEDV | Energy per unit volume due to viscous damping. |
| FCMX | LAY | Layer number where the maximum of all active failure criteria over the entire element occurs. |
|  | FC | Number of the maximum-failure criterion over the entire element: \* 1 - EMAX \* 2 - SMAX \* 3 - TWSI \* 4 - TWSR \* 5 - PFIB \* 6 - PMAT \* 7 - HFIB \* 8 - HMAT \* 9 - L3FB \* 10 - L3MT \* 11 - L4FB \* 12 - L4MT \* 13~21 - USR1~USR9 |
|  | VAL | Value of the maximum failure criterion over the entire element. |
| TG `Comp` = SUM is not supported for coupled pore-pressure-thermal (CPT `nnn` ) elements. | X, Y, Z, SUM | Component thermal gradient or vector sum. |
| TF | X, Y, Z, SUM | Component thermal flux or vector sum. |
| PG | X, Y, Z, SUM | Component pressure gradient or vector sum. |
| EF | X, Y, Z, SUM | Component electric field or vector sum. |
| D | X, Y, Z, SUM | Component electric flux density or vector sum. |
| H | X, Y, Z, SUM | Component magnetic field intensity or vector sum. |
| B | X, Y, Z, SUM | Component magnetic flux density or vector sum. |
| CG | X, Y, Z, SUM | Component concentration gradient or vector sum. |
| DF | X, Y, Z, SUM | Component diffusion flux density or vector sum. |
| FMAG | X, Y, Z, SUM | Component electromagnetic forces or vector sum. |
| SERR |  | Structural error energy. |
| SDSG |  | Absolute value of maximum variation of any nodal stress component. |
| TERR |  | Thermal error energy. |
| TDSG |  | Absolute value of the maximum variation of any nodal thermal gradient component. |
| F | X, Y, Z | Component structural force. Sum of element nodal values. |
| M | X, Y, Z | Component structural moment. Sum of element nodal values. |
| HEAT |  | Heat flow. Sum of element nodal values. |
| FLOW |  | Fluid flow. Sum of element nodal values. |
| AMPS |  | Current flow. Sum of element nodal values. |
| FLUX |  | Magnetic flux. Sum of element nodal values. |
| CSG | X, Y, Z | Component magnetic current segment. |
| RATE |  | Diffusion flow rate. Sum of element nodal values. |
| SENE |  | "Stiffness" energy or thermal heat dissipation (applies to all elements where meaningful). Same as TENE. |
| AENE |  | Artificial energy of the element. This includes the sum of hourglass control energy and energy generated by in-plane drilling stiffness from shell elements (applies to all elements where meaningful). It also includes artificial energy due to contact stabilization. The energy is used for comparisons to SENE energy to predict the solution error due to artificial stiffness. |
| TENE |  | Thermal heat dissipation or "stiffness" energy (applies to all elements where meaningful). Same as SENE. |
| KENE |  | Kinetic energy (applies to all elements where meaningful). |
| ASENE |  | Amplitude "stiffness" energy. |
| PSENE |  | Peak "stiffness" energy. |
| AKENE |  | Amplitude kinetic energy. |
| PKENE |  | Peak kinetic energy. |
| DENE |  | Damping energy. |
| WEXT WEXT is calculated for element-based loading only (and not for nodal-force loading). WEXT is stored on elements to which loading has been applied; if surface elements are added on top of other elements, for example, and pressure loading is applied to the surface elements, WEXT is available for the surface elements only. |  | Work due to external load. |
| STEN |  | Elemental energy dissipation due to [stabilization](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRUNST.html#). |
| JHEAT |  | Element Joule heat generation. |
| JS | X, Y, Z, SUM | Source current density for low-frequency magnetic analyses. Total current density (sum of conduction and displacement current densities) in low frequency electric analyses. Components (X, Y, Z) and vector sum (SUM). |
| JT | X, Y, Z, SUM | Total measurable current density in low-frequency electromagnetic analyses. (Conduction current density in a low-frequency electric analysis.) Components (X, Y, Z) and vector sum (SUM). |
| JC | X, Y, Z, SUM | Conduction current density for elements that support conduction current calculation. Components (X, Y, Z) and vector sum (SUM). |
| MRE |  | Magnetics Reynolds number. |
| VOLU |  | Element volume. Based on unit thickness for 2D plane elements (unless the thickness option is used) and on the full 360 degrees for 2D axisymmetric elements. |
| CENT | X, Y, Z | Undeformed X, Y, or Z location (based on shape function) of the element centroid in the active coordinate system. |
| BFE | TEMP | Body temperatures (calculated from applied temperatures) as used in solution (area and volume elements only). |
| SMISC | snum | Element summable miscellaneous data value at sequence number snum (shown in the Output Data section of each applicable element description). |
| NMISC | snum | Element non-summable miscellaneous data value at sequence number snum (shown in the Output Data section of each applicable element description). |
| SURF | snum | Element surface data value at sequence number snum. |
| CONT | STAT | Contact status: \* 3 = closed and sticking \* 2 = closed and sliding \* 1 = open but near contact \* 0 = open and not near contact |
|  | PENE | Contact penetration (zero or positive). |
|  | PRES | Contact pressure. |
|  | SFRIC | Contact friction stress. |
|  | STOT | Contact total stress (pressure plus friction). |
|  | SLIDE | Contact sliding distance. |
|  | GAP | Contact gap distance (0 or negative). |
|  | FLUX | Total heat flux at contact surface. |
|  | CNOS | Total number of contact status changes during substep. |
|  | FPRS | Fluid penetration pressure. |
| TOPO |  | Densities used for topological optimization. |
| CAP | C0,X0,K0,ZONE, DPLS,VPLS | Material cap plasticity model only: Cohesion; hydrostatic compaction yielding stress; I1 at the transition point at which the shear and compaction envelopes intersect; zone = 0: elastic state, zone = 1: compaction zone, zone = 2: shear zone, zone = 3: expansion zone; effective deviatoric plastic strain; volume plastic strain. |
| EDPC | CSIG,CSTR | Material EDP creep model only (not including the cap model): Equivalent creep stress; equivalent creep strain. |
| ESIG | X,Y,Z,XY,YZ,ZX | Components of Biot's effective stress. |
|  | 1, 2, 3 | Principal stresses of Biot's effective stress. |
|  | INT | Stress intensity of Biot's effective stress. |
|  | EQV | Equivalent stress of Biot's effective stress. |
| DPAR | TPOR | Total porosity (Gurson material model). |
|  | GPOR | Porosity due to void growth. |
|  | NPOR | Porosity due to void nucleation. |
| FFLX | X,Y,Z | Fluid flow flux in poromechanics. |
| FGRA | X,Y,Z | Fluid pore pressure gradient in poromechanics. |
| FICT | TEMP | Fictive temperature. |
| PMSV | VRAT, PPRE, DSAT, RPER | Void volume ratio, pore pressure, degree of saturation, and relative permeability for coupled pore-pressure-thermal elements. |
| YSIDX | TENS,SHEA | Yield surface activity status for Mohr-Coulomb, soil, concrete, and joint rock material models: 1 = yielded, 0 = not yielded. |
| FPIDX | TF01,SF01, TF02,SF02, TF03,SF03, TF04,SF04 | Failure plane surface activity status for concrete and joint rock material models: 1 = yielded, 0 = not yielded. Tension and shear failure status are available for all four sets of failure planes. |
| NS | X, Y, Z, XY, YZ, XZ | [Nominal strain](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_mat5.html#eq4dc2eb28-41da-4d81-b0d0-8716ce41a6e1) for hyperelastic material, reported in the current configuration (unaffected by [[rsys\|RSYS]] ). |
| MPLA | DMAC, DMAX | Microplane damage, macroscopic and maximum values. |
| MPDP | TOTA, TENS, COMP, RW | Microplane homogenized total, tension, and compression damages (TOTA, TENS, COMP), and split weight factor (RW). |
| DAMAGE | 1,2,3,MAX | Damage in directions 1, 2, 3 (1, 2, 3) and the maximum damage (MAX). |
| GDMG |  | Damage |
| IDIS |  | Structural-thermal dissipation rate |
| BKS | X, Y, Z, XY, YZ, XZ | Total [nonlinear kinematic backstress](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#) reported in the current configuration (unaffected by [[rsys\|RSYS]] ). Available for 3D, plane strain, and axisymmetric elements. |
| BKS1,..., BKS5 | X, Y, Z, XY, YZ, XZ | Superimposed components of the total [nonlinear kinematic backstress](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#) reported in the current configuration (unaffected by [[rsys\|RSYS]] ). Available for 3D, plane strain, and axisymmetric elements when more than one superimposed back-stress component is defined. |
| EPFR |  | Free strain in porous media |
| FC1S | 1,2,3,4,5,6 | First set of six components of FCC crystal slip. Available for 3D elements only. |
| FC2S | 1,2,3,4,5,6 | Second set of six components of FCC crystal slip. Available for 3D elements only. |
| HC1S | 1,2,3,4,5,6 | Six components of HCP crystal slip on basal and prismatic systems. Available for 3D elements only. |
| HC2S | 1,2,3,4,5,6 | Six components of HCP crystal slip on pyramidal system. Available for 3D elements only. |
| HC3S | 1,2,3,4,5,6 | First set of six components of HCP crystal slip on the first-order pyramidal system. Available for 3D elements only. |
| HC4S | 1,2,3,4,5,6 | Second set of six components of HCP crystal slip on the first-order pyramidal system. Available for 3D elements only. |
| HC5S | 1,2,3,4,5,6 | Six components of HCP crystal slip on the second-order pyramidal system. Available for 3D elements only. |
| BC1S | 1,2,3,4,5,6 | First set of six components of BCC slip on 111 plane. Available for 3D elements only. |
| BC2S | 1,2,3,4,5,6 | Second set of six components of BCC slip on 111 plane. Available for 3D elements only. |
| BC3S | 1,2,3,4,5,6 | First set of six components of BCC slip on 112 plane. Available for 3D elements only. |
| BC4S | 1,2,3,4,5,6 | Second set of six components of BCC slip on 112 plane. Available for 3D elements only. |
| BC5S | 1,2,3,4,5,6 | First set of six components of BCC slip on 123 plane. Available for 3D elements only. |
| BC6S | 1,2,3,4,5,6 | Second set of six components of BCC slip on 123 plane. Available for 3D elements only. |
| BC7S | 1,2,3,4,5,6 | Third set of six components of BCC slip on 123 plane. Available for 3D elements only. |
| BC8S | 1,2,3,4,5,6 | Fourth set of six components of BCC slip on 123 plane. Available for 3D elements only. |
| FC1H | 1,2,3,4,5,6 | First set of six components of FCC crystal hardness. Available for 3D elements only. |
| FC2H | 1,2,3,4,5,6 | Second set of six components of FCC crystal hardness. Available for 3D elements only. |
| HC1H | 1,2,3,4,5,6 | Sixcomponents of HCP crystal hardness on basal and prismatic systems. Available for 3D elements. |
| HC2H | 1,2,3,4,5,6 | Six components of HCP crystal hardness on pyramidal system. Available for 3D elements only. |
| HC3H | 1,2,3,4,5,6 | First set of six components of HCP crystal hardness on the first-order pyramidal system. Available for 3D elements only. |
| HC4H | 1,2,3,4,5,6 | Second set of six components of HCP crystal hardness on the first-order pyramidal system. Available for 3D elements only. |
| HC5H | 1,2,3,4,5,6 | Six components of HCP crystal hardness on the second-order pyramidal system. Available for 3D elements only. |
| BC1H | 1,2,3,4,5,6 | First set of six components of BCC hardness on 111 plane. Available for 3D elements only. |
| BC2H | 1,2,3,4,5,6 | Second set of six components of BCC hardness on 111 plane. Available for 3D elements only. |
| BC3H | 1,2,3,4,5,6 | First set of six components of BCC hardness on 112 plane. Available for 3D elements only. |
| BC4H | 1,2,3,4,5,6 | Second set of six components of BCC hardness on 112 plane. Available for 3D elements only. |
| BC5H | 1,2,3,4,5,6 | First set of six components of BCC hardness on 123 plane. Available for 3D elements only. |
| BC6H | 1,2,3,4,5,6 | Second set of six components of BCC hardness on 123 plane. Available for 3D elements only. |
| BC7H | 1,2,3,4,5,6 | Third set of six components of BCC hardness on 123 plane. Available for 3D elements only. |
| BC8H | 1,2,3,4,5,6 | Fourth set of six components of BCC hardness on 123 plane. Available for 3D elements only. |
| XELG | 1,2,3,45,6,EQV | Crystal Lagrangian strain in 11, 22, 33, 12, 23,13 directions and its equivalent. Available for 3D elements only. |
| SINT | RHO, ETA, SSTR, GRAIN | Sintering relative density, viscosity, sintering stress, and average grain size values. |

### ETABLE - Selected Result Component Labels

Selected Result Component Labels **ETABLE**, `Lab`,SRES, `Comp`

|            |                                         |
|------------|-----------------------------------------|
| **Comp**   | **Description**                         |
| SVAR `n`   | The `n` th state variable.              |
| FLDUF0 `n` | The `n` th user-defined field variable. |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ETABLE.html
