---
apdl: "ESOL"
method: esol
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.set_up.SetUp.esol
generated: 2026-08-22
tags: [mapdl-command]
---

# ESOL

PyMAPDL: `mapdl.esol(nvar='', elem='', node='', item='', comp='', name='', **kwargs)`

Specifies element data to be stored from the results file.

## Parameters

**nvar**: Arbitrary reference number assigned to this variable (2 to `NV` ( [[numvar|NUMVAR]] )). Overwrites any existing results for this variable.

**elem**: Element for which data are to be stored. If `ELEM` = P, graphical picking is enabled (valid only in the GUI).

**node**: Node number on this element for which data are to be stored. If blank, store the average element value (except for `FMAG` values, which are summed instead of averaged). If `NODE` = P, graphical picking is enabled (valid only in the GUI).

**item**: Label identifying the item. General item labels are shown in *ESOL - General Result Item and Component Labels*. Some items also require a component label.

**comp**: Component of the item (if required). General component labels are shown in *ESOL - General Result Item and Component Labels* below. If `Comp` is a sequence number ( `n` ), the `NODE` field is ignored.

**name**: 32-character name for identifying the item on the printout and displays. Defaults to a label formed by concatenating the first four characters of the `Item` and `Comp` labels.

## Notes

See *ESOL - General Result Item and Component Labels* for a list of item and component labels for element (excluding line element) results. See *ESOL - Selected Result Component Labels* for a list of valid selected result ( `Item` = SRES) components.

**ESOL** defines element results data to be stored from a results file ( [[file|FILE]] ). Not all items are valid for all elements. To see the available items for a given element, refer to the input and output summary tables in the documentation for that element.

Two methods of data access are available via the **ESOL** command. You can access some data by using a generic label ( component name method ), while others require a label and number ( sequence number method ).

Use the component name method to access general element data (that is, element data generally available to most element types or groups of element types). Element results are in the element coordinate system, except for layered elements where results are in the layer coordinate system. Element forces and moments are in the nodal coordinate system. Results are obtainable for an element at a specified node. Further location specifications can be made for some elements via [[shell|SHELL]], [[layerp26|LAYERP26]], and [[force|FORCE]].

The sequence number method is required for data that is not averaged (such as pressures at nodes and temperatures at integration points), or data that is not easily described generically (such as all derived data for structural line elements and contact elements, all derived data for thermal line elements, and layer data for layered elements).

In a [2D to 3D analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/Hlp_G_ADV2DTO3DREST.html), this command not supported in the POST26 postprocessor and is ignored.

### ESOL - General Result Item and Component Labels

Component Name Method

| Item | Comp | Description |
|----|----|----|
| S | X, Y, Z, XY, YZ, XZ | Component stress. |
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
| EPPL | X, Y, Z, XY, YZ, XZ | Component plastic strain. |
|  | 1, 2, 3 | Principal plastic strain. |
|  | INT | Plastic strain intensity. |
|  | EQV | Plastic equivalent strain. |
| EPCR | X, Y, Z, XY, YZ, XZ | Component creep strain. |
|  | 1,2,3 | Principal creep strain. |
|  | INT | Creep strain intensity. |
|  | EQV | Creep equivalent strain. |
| EPDI | X, Y, Z, XY, YZ, XZ | Component diffusion strain. |
|  | 1, 2, 3 | Principal diffusion strain. |
|  | INT | Diffusion strain intensity. |
|  | EQV | Diffusion equivalent strain. |
| NL | SEPL | Equivalent stress (from stress-strain curve). |
|  | SRAT | Stress state ratio. |
|  | HPRES | Hydrostatic pressure. |
|  | EPEQ | Accumulated equivalent plastic strain. |
|  | CREQ | Accumulated equivalent creep strain. |
|  | PSV | Plastic state variable. |
|  | PLWK | Plastic work/volume. |
| SEND | ELASTIC The results for this postprocessing SEND component are invalid for `ELBOW290` if that element is used with viscoelastic or viscohyperelastic materials. | Elastic strain energy density. (For [viscoelastic](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/evis.html#mat_harmvisco) and [sintering](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#) materials, the [stored energy](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/evis.html#eq92b60ee3-7e22-457b-9543-53f86d16432a).) |
|  | PLASTIC | Plastic strain energy density. |
|  | CREEP | Creep strain energy density. |
|  | DAMAGE | Damage strain energy density. |
|  | VDAM | Viscoelastic dissipation energy density. |
|  | VREG | Visco-regularization strain energy density. |
|  | DISS | Structural-thermal dissipation. |
|  | ENTO | Total strain energy density (sum of ELASTIC, PLASTIC, and CREEP strain energy densities). |
| CDM | DMG | Damage variable. |
|  | LM | Maximum previous strain energy for virgin material. |
| GKS | X | Gasket component stress (also gasket pressure). |
| GKD | X | Gasket component total closure. |
| GKDI | X | Gasket component total inelastic closure. |
| GKTH | X | Gasket component thermal closure. |
| SS | X, XY, XZ | Interface traction (stress). |
| SD | X,XY,XZ | Interface separation. |
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
| TG For `SHELL131` and `SHELL132` elements with KEYOPT(3) = 0 or 1, use the labels HBOT, HE2, HE3, ..., HTOP instead of HEAT. | X, Y, Z, SUM | Component thermal gradient or vector sum. |
| TF | X, Y, Z, SUM | Component thermal flux or vector sum. |
| PG | X, Y, Z, SUM | Component pressure gradient or vector sum. |
| EF | X, Y, Z, SUM | Component electric field or vector sum. |
| D | X, Y, Z, SUM | Component electric flux density or vector sum. |
| H | X, Y, Z, SUM | Component magnetic field intensity or vector sum. |
| B | X, Y, Z, SUM | Component magnetic flux density or vector sum. |
| CG | X, Y, Z, SUM | Component concentration gradient or vector sum. |
| DF | X, Y, Z, SUM | Component diffusion flux density or vector sum. |
| FMAG | X, Y, Z, SUM | Component electromagnetic forces or vector sum. |
| P | X, Y, Z, SUM | Poynting vector components or vector sum |
| F | X, Y, Z | Component structural force. |
| M | X, Y, Z | Component structural moment. |
| HEAT |  | Heat flow. |
| FLOW |  | Fluid flow. |
| AMPS |  | Current flow. |
| FLUX |  | Magnetic flux. |
| CSG | X, Y, Z | Component magnetic current segment. |
| RATE |  | Diffusion flow rate. |
| SENE |  | "Stiffness" energy. |
| STEN |  | Elemental energy dissipation due to [stabilization](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRUNST.html#). |
| KENE |  | Kinetic energy. |
| ASENE |  | Amplitude stiffness energy. |
| PSENE |  | Peak stiffness energy. |
| AKENE |  | Amplitude kinetic energy. |
| PKENE |  | Peak kinetic energy. |
| DENE |  | Damping energy. |
| WEXT WEXT is calculated for element-based loading only (and not for nodal-force loading). WEXT is stored on elements to which loading has been applied; if surface elements are added on top of other elements, for example, and pressure loading is applied to the surface elements, WEXT is available for the surface elements only. |  | Work due to external load. |
| AENE |  | Artificial energy due to hourglass control/drill stiffness or due to contact stabilization. |
| JHEAT |  | Element Joule heat generation. |
| JC | X, Y, Z, SUM | Conduction current density for elements that support conduction current calculation. Components (X, Y, Z) and vector sum (SUM). |
| JS | X, Y, Z | Source current density for low-frequency magnetic analyses. Total current density (sum of conduction and displacement current densities) in low-frequency electric analyses. Components (X, Y, Z). |
| JT | X, Y, Z, SUM | Total measurable current density in low-frequency electromagnetic analyses. (Conduction current density in a low-frequency electric analysis.) Components (X, Y, Z) and vector sum (SUM). |
| MRE |  | Magnetics Reynolds number. |
| VOLU |  | Volume of volume element. |
| BFE | TEMP | Body temperatures (calculated from applied temperatures) as used in solution (area and volume elements only). |
| FICT | TEMP | Fictive temperature. |
| CAP | C0,X0,K0,ZONE, DPLS,VPLS | Material cap plasticity model only: Cohesion; hydrostatic compaction yielding stress; I1 at the transition point at which the shear and compaction envelopes intersect; zone = 0: elastic state, zone = 1: compaction zone, zone = 2: shear zone, zone = 3: expansion zone; effective deviatoric plastic strain; volume plastic strain. |
| EDPC | CSIG,CSTR | Material EDP creep model only (not including the cap model): Equivalent creep stress; equivalent creep strain. |
| FFLX | X, Y, Z | Fluid flux flow in poromechanics. |
| FGRA | X, Y, Z | Fluid pore pressure gradient in poromechanics. |
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
| BKS1,...,BKS5 | X, Y, Z, XY, YZ, XZ | Superimposed components of the total [nonlinear kinematic backstress](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#) reported in the current configuration (unaffected by [[rsys\|RSYS]] ). Available for 3D, plane strain, and axisymmetric elements when more than one superimposed back-stress component is defined. |
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
| **Sequence Number Method** |  |  |
| **Item** | **Comp** | **Description** |
| SMISC | `snum` | Summable items. |
| NMISC | `snum` | Nonsummable items. |
| LS | `snum` | Line element elastic stresses. |
| LEPEL | `snum` | Line element strains. |
| LEPTH | `snum` | Line element thermal strains. |
| LEPPL | `snum` | Line element plastic strains. |
| LEPCR | `snum` | Line element creep strains. |
| LBFE | `snum` | Line element temperatures. |

### ESOL - Selected Result Component Labels

| Comp       | Description                             |
|------------|-----------------------------------------|
| SVAR `n`   | The `n` th state variable.              |
| FLDUF0 `n` | The `n` th user-defined field variable. |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ESOL.html
