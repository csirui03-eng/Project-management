---
apdl: "PLESOL"
method: plesol
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.plesol
generated: 2026-08-22
tags: [mapdl-command]
---

# PLESOL

PyMAPDL: `mapdl.plesol(item='', comp='', kund='', fact='', avg='', **kwargs)`

Displays solution results as discontinuous element contours.

## Parameters

**item**: Label identifying the item. Valid item labels are shown in the table below. Some items also require a component label.

**comp**: Component of the item (if required). Valid component labels are shown in the table below.

**kund**

Undisplaced shape key:

- `0` - Do not overlay undeformed structure display.
- `1` - Overlay displaced contour plot with undeformed display (appearance is system-dependent).
- `2` - Overlay displaced contour plot with undeformed edge display (appearance is system- dependent).

**fact**: Scale factor for 2D display of contact items. Default = 1. To invert the display, specify a negative scaling factor.

**avg**

Specifies whether results of reinforcing members within the same reinforcing element are smoothed:

- `0` - Disable smoothing.
- `1` - Enable smoothing (default), displaying constant results of reinforcing members if the base elements are low-order, and linear results when the base elements are high-order.

## Notes

**PLESOL** displays the solution results as element contours discontinuous across element boundaries for the selected elements.

For example, **PLESOL**,S,X displays the X component of stress S (that is, the SX stress component). Various element results depend on the calculation method and the selected results location ( [[avprin|AVPRIN]], [[rsys|RSYS]], and [[esel|ESEL]] ).

Contours are determined by linear interpolation within each element, unaffected by the surrounding elements; that is, no nodal averaging occurs. The discontinuity between contours of adjacent elements is an indication of the gradient across elements. Component results are displayed in the active results coordinate system ( [[rsys|RSYS]] \[default is global Cartesian\]).

To display items not available via **PLESOL** (such as line element results), see [[etable|ETABLE]] and [[pletab|PLETAB]].

For PowerGraphics displays ( [[graphics|/GRAPHICS]],POWER), results are plotted only for the model exterior surface. Items not supported by PowerGraphics are noted in *PLESOL - General Result Item and Component Labels*.

The results displayed by **PLESOL** are unaffected by any requested nodal-averaged results ( [[outres|OUTRES]],NAR). For more information, see [Nodal-Averaged Results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost)

For `Item` = SRES, selected result ( [[osresult|OSRESULT]] ) values are output. See *PLESOL - Selected Result Component Labels*.

### PLESOL - General Result Item and Component Labels

General Item and Component Labels **PLESOL**, `Item, Comp`

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
| EPDI | X, Y, Z, XY, YZ, XZ | Component diffusion strain. Not supported by PowerGraphics. |
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
| EPTH | X, Y, Z, XY, YZ, XZ | Component thermal strain. |
|  | 1, 2, 3 | Principal thermal strain. |
|  | INT | Thermal strain intensity. |
|  | EQV | Thermal equivalent strain. |
| EPSW |  | Swelling strain. |
| EPTO | X, Y, Z, XY, YZ, XZ | Component total mechanical strain (EPEL + EPPL + EPCR). |
|  | 1, 2, 3 | Principal total mechanical strain. |
|  | INT | Total mechanical strain intensity. |
|  | EQV | Total mechanical equivalent strain. |
| EPTT | X, Y, Z, XY, YZ, XZ | Total mechanical, thermal, diffusion, and swelling strain (EPEL + EPPL + EPCR + EPTH + EPDI + EPSW). |
|  | 1, 2, 3 | Principal total mechanical, thermal, diffusion, and swelling strain. |
|  | INT | Total mechanical, thermal, diffusion, and swelling strain intensity. |
|  | EQV | Total mechanical, thermal, diffusion, and swelling equivalent strain. |
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
| FAIL | MAX | Maximum of all active failure criteria defined at the current location. Works only if failure criteria are provided ( [[fc\|FC]] and [[tb\|TB]] ). |
|  | EMAX | Maximum Strain Failure Criterion. |
|  | SMAX | Maximum Stress Failure Criterion. |
|  | TWSI | Tsai-Wu Strength Index Failure Criterion. |
|  | TWSR | Inverse of Tsai-Wu Strength Ratio Index Failure Criterion |
|  | HFIB | Hashin Fiber Failure Criterion. Must first be added ( [[fctyp\|FCTYP]]. |
|  | HMAT | Hashin Matrix Failure Criterion. |
|  | PFIB | Puck Fiber Failure Criterion. |
|  | PMAT | Puck Matrix Failure Criterion. |
|  | L3FB | LaRc03 Fiber Failure Criterion. |
|  | L3MT | LaRc03 Matrix Failure Criterion. |
|  | L4FB | LaRc04 Fiber Failure Criterion. |
|  | L4MT | LaRc04 Matrix Failure Criterion. |
|  | USR1, USR2,..., USR9 | User-defined failure criteria. USR1 through USR9 require a failure-criteria routine. |
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
|  | FC | Number of the maximum-failure criterion over the entire element: \* 1 = EMAX \* 2 = SMAX \* 3 = TWSI \* 4 = TWSR \* 5 = PFIB \* 6 = PMAT \* 7 = HFIB \* 8 = HMAT \* 9 = L3FB \* 10 = L3MT \* 11 = L4FB \* 12 = L4MT \* 13~21 = USR1~USR9 |
|  | VAL | Value of the maximum failure criterion over the entire element: |
| SVAR | 1, 2, 3,... N | State variable. |
| GKS | X, XY, XZ | Gasket component stress. |
| GKD | X, XY, XZ | Gasket component total closure. |
| GKDI | X, XY, XZ | Gasket component total inelastic closure. |
| GKTH | X, XY, XZ | Gasket component thermal closure. |
| SS | X, XY, XZ | Interface traction (stress). |
| SD | X, XY, XZ | Interface separation. |
| CONT | STAT | Contact status: For MPC-based contact definitions, the value of STAT can be negative, indicating that one or more contact constraints were intentionally removed to prevent overconstraint. STAT = -3 is used for MPC bonded contact; STAT = -2 is used for MPC no-separation contact. \* 3 = closed and sticking \* 2 = closed and sliding \* 1 = open but near contact \* 0 = open and not near contact |
|  | PENE | Contact penetration. |
|  | PRES | Contact pressure. |
|  | SFRIC | Contact friction stress. |
|  | STOT | Contact total stress (pressure plus friction). |
|  | SLIDE | Contact sliding distance. |
|  | GAP | Contact gap distance. |
|  | FLUX | Total heat flux at contact surface. |
|  | CNOS | Total number of contact status changes during substep. |
|  | FPRS | Fluid penetration pressure. |
| TG `Comp` = SUM is not supported for coupled pore-pressure-thermal (CPT `nnn` ) elements. | X, Y, Z, SUM | Component thermal gradient or vector sum. |
| TF | X, Y, Z, SUM | Component thermal flux or vector sum. |
| PG | X, Y, Z, SUM | Component or vector sum of velocity or energy density flux (room acoustics). |
| EF | X, Y, Z, SUM | Component electric field or vector sum. |
| D | X, Y, Z, SUM | Component electric flux density or vector sum. |
| H | X, Y, Z, SUM | Component magnetic field intensity or vector sum. |
| B | X, Y, Z, SUM | Component magnetic flux density or vector sum. |
| CG | X, Y, Z, SUM | Component concentration gradient or vector sum. |
| DF | X, Y, Z, SUM | Component diffusion flux density or vector sum. |
| FMAG | X, Y, Z, SUM | Component electromagnetic force or vector sum. |
| P | X, Y, Z, SUM | Poynting vector component or sum. |
| SERR Some element- and material-type limitations apply. (See [[prerr\|PRERR]].) |  | Structural error energy. |
| SDSG |  | Absolute value of the maximum variation of any nodal stress component. |
| TERR |  | Thermal error energy. |
| TDSG |  | Absolute value of the maximum variation of any nodal thermal gradient component. |
| F | X, Y, Z | X, Y, or Z structural force. Do not use **PLESOL** to obtain contact force values for contact elements. (The force values reported may not be accurate for these elements.) Use [[etable\|ETABLE]] instead. |
| M | X, Y, Z | X, Y, or Z structural moment. |
| HEAT |  | Heat flow. |
| FLOW |  | Fluid flow. |
| AMPS |  | Current flow. Use [[force\|FORCE]] for type. |
| CHRG |  | Charge. Use [[force\|FORCE]] for type. |
| FLUX |  | Magnetic flux. |
| CSG | X, Y, Z | X, Y, or Z magnetic current segment component. |
| RATE |  | Diffusion flow rate. |
| SENE |  | "Stiffness" energy or thermal heat dissipation. Same as TENE. |
| STEN |  | Elemental energy dissipation due to [stabilization](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRUNST.html#). |
| TENE |  | Thermal heat dissipation or "stiffness" energy. Same as SENE. |
| KENE |  | Kinetic energy. |
| ASENE |  | Amplitude "stiffness" energy. |
| PSENE |  | Peak "stiffness" energy. |
| AKENE |  | Amplitude kinetic energy. |
| PKENE |  | Peak kinetic energy. |
| DENE |  | Damping energy. |
| WEXT WEXT is calculated for element-based loading only (and not for nodal-force loading). WEXT is stored on elements to which loading has been applied; if surface elements are added on top of other elements, for example, and pressure loading is applied to the surface elements, WEXT is available for the surface elements only. |  | Work due to external load. |
| AENE |  | Artificial energy due to hourglass control/drill stiffness or due to contact stabilization. |
| JHEAT |  | Element Joule heat generation. |
| JS | X, Y, Z, SUM | Source current density for low-frequency magnetic analyses. Total current density (sum of conduction and displacement current densities) in low frequency electric analyses. Components (X, Y, Z) and vector sum (SUM). |
| JT | X, Y, Z, SUM | Total measurable current density in low-frequency electromagnetic analyses. (Conduction current density in a low-frequency electric analysis.) Components (X, Y, Z) and vector sum (SUM). |
| JC | X, Y, Z, SUM | Conduction current density for elements that support conduction current calculation. Components (X, Y, Z) and vector sum (SUM). |
| MRE |  | Magnetic Reynolds number. |
| VOLU |  | Volume of volume element. |
| CENT | X, Y, Z | Centroid X, Y, or Z location (based on shape function) in the active coordinate system. |
| BFE | TEMP For [reinforcing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_compreinfdirectemb.html) elements `REINF264` and `REINF265`, issue **PLESOL** ,BFE,TEMP to plot the corner-point temperature of each member. You can also plot intersection-point temperature gradients ( **PLESOL**,TG) and intersection-point heat flux ( **PLESOL**,TF). For higher-order reinforcing members (generated when using higher-order base elements), the midpoint values are not available for the reinforcing members. | Body temperatures (calculated from applied temperatures) as used in solution (area and volume elements only). For `SOLID278` and `SOLID279` with KEYOPT(3) = 2, use **PLESOL**,BFE,TEMP to plot the temperature distribution through the thickness of the element. When other thermal elements are included in the model, they should be unselected to avoid plotting undefined information. |
| SMISC | `snum` | Element summable miscellaneous data value at sequence number `snum` (shown in the Output Data section of each element description. |
| NMISC | `snum` | Element non-summable miscellaneous data value at sequence number `snum` (shown in the Output Data section of each element description. |
| CAP | C0,X0,K0,ZONE, DPLS,VPLS | Material cap plasticity model only: Cohesion; hydrostatic compaction yielding stress; I1 at the transition point at which the shear and compaction envelopes intersect; zone = 0: elastic state, zone = 1: compaction zone, zone = 2: shear zone, zone = 3: expansion zone; effective deviatoric plastic strain; volume plastic strain. |
| EDPC | CSIG,CSTR | Material EDP creep model only (not including the cap model): Equivalent creep stress; equivalent creep strain. |
| FICT | TEMP | Fictive temperature. |
| ESIG | X,Y,Z,XY,YZ,ZX | Components of Biot's effective stress. |
|  | 1, 2, 3 | Principal stresses of Biot's effective stress. |
|  | INT | Stress intensity of Biot's effective stress. |
|  | EQV | Equivalent stress of Biot's effective stress. |
| DPAR | TPOR | Total porosity (Gurson material model). |
|  | GPOR | Porosity due to void growth. |
|  | NPOR | Porosity due to void nucleation. |
| FFLX | X,Y,Z | Fluid flow flux in poromechanics. |
| FGRA | X,Y,Z | Fluid pore-pressure gradient in poromechanics. |
| MENE |  | Acoustic potential energy. |
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
| SNDI | X, Y, Z, SUM | Component sound intensity or vector sum. |
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

### PLESOL - Selected Result Component Labels

Selected Result Component Labels **PLESOL**,SRES, `Comp`

| Comp       | Description                             |
|------------|-----------------------------------------|
| SVAR `n`   | The `n` th state variable.              |
| FLDUF0 `n` | The `n` th user-defined field variable. |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLESOL.html
