---
apdl: "PRESOL"
method: presol
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.presol
generated: 2026-08-22
tags: [mapdl-command]
---

# PRESOL

PyMAPDL: `mapdl.presol(item='', comp='', **kwargs)`

Prints the solution results for elements.

## Parameters

**item**: Label identifying the item. Valid item labels are shown in the table below. Some items also require a component label.

**comp**: Component of the item (if required). Valid component labels are shown in the table below.

## Notes

**PRESOL** prints the solution results for the selected elements in the sorted sequence.

For example, **PRESOL**,S prints the stress items SX, SY, SZ, SXY, SYZ, and SXZ for the node locations of the element. Various element results depend on the calculation method ( [[avprin|AVPRIN]] ).

Component results are in the global Cartesian coordinate directions unless transformed ( [[rsys|RSYS]] ).

Shell elements print values at the top, then bottom of the element (or layer). If KEYOPT(8) = 2 (for `SHELL181`, `SHELL208`, `SHELL209`, `SHELL281`, or `ELBOW290` ), the results are printed in the order TOP, BOT and then MID of each element, (or layer). The MID value is the actual value to the results file.

Items are listed as columns of a table versus element number. An exception occurs for item ELEM, which uses an element format (where all applicable line element results are listed per element) instead of a tabular format.

You can issue [[force|FORCE]] to define which component of the nodal load is to be used (static, damping, inertia, or total).

To print items not available via **PRESOL** (such as line element results), see [[etable|ETABLE]] and [[pretab|PRETAB]].

For PowerGraphics ( [[graphics|/GRAPHICS]],POWER), results are listed only for the element surface. Items not supported by PowerGraphics are noted in *PRESOL - General Result Item and Component Labels*.

The results printed by **PRESOL** are unaffected by any requested nodal-averaged results ( [[outres|OUTRES]],NAR). For more information, see [Nodal-Averaged Results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost)

For `Item` = SRES, selected result components ( [[osresult|OSRESULT]] ) are output. See *PRESOL - Selected Result Component Labels*.

### PRESOL - General Result Item and Component Labels

General Item and Component Labels **PRESOL**, `Item, Comp`

| Item | Comp | Description |
|----|----|----|
| S | COMP or blank | Component (X, Y, Z, XY, YZ, XZ) stresses. |
|  | PRIN | Principal stresses (1, 2, 3), stress intensity (INT), and equivalent stress (EQV). |
| EPEL | COMP or blank | Component (X, Y, Z, XY, YZ, XZ) elastic strains. |
|  | PRIN | Principal elastic strains (1, 2, 3), strain intensity (INT), and equivalent strain (EQV). |
| EPTH | COMP or blank | Component (X, Y, Z, XY, YZ, XZ) thermal strains. |
|  | PRIN | Principal thermal strains (1, 2, 3), strain intensity (INT), and equivalent strain (EQV). |
| EPDI | COMP or blank | Component (X, Y, Z, XY, YZ, XZ) diffusion strains. |
|  | PRIN | Principal diffusion strains (1, 2, 3), strain intensity (INT), and equivalent strain (EQV). |
| EPPL | COMP or blank | Component (X, Y, Z, XY, YZ, XZ) plastic strains. |
|  | PRIN | Principal plastic strains (1, 2, 3), strain intensity (INT), and equivalent strain (EQV). |
| EPCR | COMP or blank | Component (X, Y, Z, XY, YZ, XZ) creep strains. |
|  | PRIN | Principal creep strains (1, 2, 3), strain intensity (INT), and equivalent strain (EQV). |
| EPSW |  | Swelling strain. |
| EPTO | COMP or blank | Component (X, Y, Z, XY, YZ, XZ) total mechanical strains (EPEL + EPPL + EPCR). |
|  | PRIN | Principal total mechanical strains (1, 2, 3), strain intensity (INT), and equivalent strain (EQV). |
| EPTT | COMP or blank | Component (X, Y, Z, XY, YZ, XZ) total mechanical, thermal, diffusion, and swelling strains (EPEL + EPPL + EPCR + EPTH + EPDI + EPSW). |
|  | PRIN | Principal total mechanical, diffusion, thermal, and swelling strains (1, 2, 3), strain intensity (INT), and equivalent strain (EQV). |
| NL |  | Nonlinear items (SEPL, SRAT, HPRES, EPEQ, CREQ, PSV, PLWK). |
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
| FAIL |  | Failure criteria for virgin material. Not supported by PowerGraphics. Works only if failure criteria are provided ( [[fc\|FC]] and [[tb\|TB]] ). **Default components:** Maximum of all failure criteria defined at current location (MAX), maximum strain (EMAX), maximum stress (SMAX), Tsai-Wu Strength Index (TWSI), inverse of Tsai-Wu Strength Ratio Index (TWSR). **Other available components:** Hashin Fiber Failure (HFIB), Hashin Matrix Failure (HMAT), Puck Fiber Failure (PFIB), Puck Matrix Failure (PMAT), LaRc03 Fiber Failure (L3FB), LaRc03 Matrix Failure (L3MT), LaRc04 Fiber Failure (L4FB), LaRc04 Matrix Failure (L4MT), and any user-defined failure criteria (USR1 through USR9). USR1 through USR9 require a failure-criteria routine. Issue [[fctyp\|FCTYP]] to activate or remove failure criteria. |
| PFC |  | Failure criteria based on the effective stresses in the damaged material. **Components:** Maximum of all failure criteria defined at current location (MAX), fiber tensile failure (FT), fiber compressive failure (FC), matrix tensile failure (MT), and matrix compressive (MC). |
| PDMG |  | Progressive damage parameters. **Components:** Damage status (STAT, 0 = undamaged, 1 = damaged, 2 = complete damage), fiber tensile damage variable (FT), fiber compressive damage variable (FC), matrix tensile damage variable (MT), matrix compressive damage variable (MC), shear damage variable (S), energy dissipated per unit volume (SED), energy per unit volume due to viscous damping (SEDV). |
| FCMX |  | Maximum failure criterion over the entire element. **Components:** Layer number where the maximum occurs (LAY), name of the maximum failure criterion (FC), and value of the maximum failure criterion (VAL). |
| SVAR | 1,2,3,... N | State variable. |
| GKS |  | Gasket component (X, XY, XZ) stress. |
| GKD |  | Gasket component (X, XY, XZ) total closure. |
| GKDI |  | Gasket component (X, XY, XZ) total inelastic closure. |
| GKTH |  | Gasket component (X, XY, XZ) thermal closure. |
| CONT |  | Contact items (STAT, PENE, PRES, SFRIC, STOT, SLIDE, GAP, FLUX, CNOS, FPRS). See component descriptions in [[plesol\|PLESOL]]. |
| TG |  | Component (X, Y, Z) thermal gradients and vector sum (SUM). No vector sum is calculated for coupled pore-pressure-thermal (CPT `nnn` ) elements. |
| TF |  | Component (X, Y, Z) thermal fluxes and vector sum (SUM). |
| PG |  | Component (X, Y, Z) and vector sum (SUM) for velocity or energy density flux (room acoustics). |
| EF |  | Component (X, Y, Z) electric fields and vector sum (SUM). |
| D |  | Component (X, Y, Z) electric flux densities and vector sum (SUM). |
| H |  | Component (X, Y, Z) magnetic field intensities and vector sum (SUM). |
| B |  | Component (X, Y, Z) magnetic flux densities and vector sum (SUM). |
| CG |  | Component concentration gradient or vector sum. |
| DF |  | Component diffusion flux density or vector sum. |
| FMAG |  | Component (X, Y, Z) electromagnetic forces and vector sum (SUM). |
| P |  | Poynting vector components (X, Y, Z) and sum (SUM). |
| CG |  | Concentration gradient. |
| F |  | Component (X, Y, Z) structural forces. Use [[force\|FORCE]] for type. Do not use **PRESOL** to obtain contact forces for contact elements, as the force values reported may not be accurate for these elements. Use [[etable\|ETABLE]] instead. |
| M |  | Component (X, Y, Z) structural moments. |
| HEAT |  | Heat flow. |
| FLOW |  | Fluid flow. |
| AMPS |  | Current flow. |
| CHRG |  | Charge. |
| FLUX |  | Magnetic flux. |
| CSG |  | Component (X, Y, Z) magnetic current segments. |
| FORC |  | All available force items (F to CSG above). (10 maximum). |
| RATE |  | Diffusion flow rate. |
| BFE | TEMP For reinforcing elements `REINF264` and `REINF265`, issue **PRESOL** ,BFE,TEMP to print the intersection-point temperature of each member. You can also print intersection-point temperature gradients ( **PRESOL**,TG) and intersection-point heat flux ( [[plesol\|PLESOL]],TF). For higher- order reinforcing members (generated when using higher-order base elements), the midpoint values are not available for the reinforcing members. | Body temperatures (calculated from applied temperatures) as used in solution (area and volume elements only). |
| ELEM |  | All applicable element results (available only for `LINK180` and previous-generation structural line elements). |
| SERR Some element- and material-type limitations apply. See [[prerr\|PRERR]]. |  | Structural error energy. |
| SDSG |  | Absolute value of the maximum variation of any nodal stress component. |
| TERR |  | Thermal error energy. |
| TDSG |  | Absolute value of the maximum variation of any nodal thermal gradient component. |
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
| JHEAT |  | Element Joule heat generation (coupled-field calculation). |
| JS |  | Source current density for low-frequency magnetic analyses. Total current density (sum of conduction and displacement current densities) in low frequency electric analyses. Components (X, Y, Z) and vector sum (SUM). |
| JT |  | Total measurable current density in low-frequency electromagnetic analyses. (Conduction current density in a low-frequency electric analysis.) Components (X, Y, Z) and vector sum (SUM). |
| JC |  | Conduction current density for elements that support conduction current calculation. Components (X, Y, Z) and vector sum (SUM). |
| MRE |  | Magnetic Reynolds number. |
| VOLU |  | Volume of volume element. |
| CENT |  | Centroid X, Y, or Z location (based on shape function) in the active coordinate system. |
| LOCI |  | Integration point location. |
| SMISC | `snum` | Element summable miscellaneous data value at sequence number `snum` (shown in the Output Data section of each element description). |
| NMISC | `snum` | Element nonsummable miscellaneous data value at sequence number `snum` (shown in the Output Data section of each element description). |
| CAP |  | Material cap plasticity model only: Cohesion (C0); hydrostatic compaction yielding stress (X0); I1 at the transition point at which the shear and compaction envelopes intersect (K0); ZONE = 0: elastic state, ZONE = 1: compaction zone, ZONE = 2: shear zone, ZONE = 3: expansion zone; effective deviatoric plastic strain (DPLS); volume plastic strain (VPLS). |
| EDPC |  | Material EDP creep model only (not including the cap model): Equivalent creep stress (CSIG); equivalent creep strain (CSTR). |
| FICT | TEMP | Fictive temperature. |
| ESIG | COMP or blank | Components of Biot's effective stress. |
|  | PRIN | Principal stresses of Biot's effective stress. |
|  | INT | Stress intensity of Biot's effective stress. |
|  | EQV | Equivalent stress of Biot's effective stress. |
| DPAR | TPOR | Total porosity (Gurson material model). |
|  | GPOR | Porosity due to void growth. |
|  | NPOR | Porosity due to void nucleation. |
| FFLX | COMP | Fluid flow flux components in poromechanics. |
| FGRA | COMP | Fluid pore-pressure gradient components in poromechanics. |
| MENE |  | Acoustic potential energy. |
| PMSV | COMP | Void volume ratio, pore pressure, degree of saturation, and relative permeability for coupled pore-pressure CPT elements. |
| FPIDX | TF01,SF01, TF02,SF02, TF03,SF03, TF04,SF04 | Failure plane surface activity status for concrete and joint rock material models: 1 = yielded, 0 = not yielded. Tension and shear failure status are available for all four sets of failure planes. |
| YSIDX | TENS,SHEA | Yield surface activity status for Mohr-Coulomb, soil, concrete, and joint rock material models: 1 = yielded, 0 = not yielded. |
| NS | COMP | [Nominal strain](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_mat5.html#eq4dc2eb28-41da-4d81-b0d0-8716ce41a6e1) for hyperelastic material, reported in the current configuration (unaffected by [[rsys\|RSYS]] ). |
| MPLA | DMAC,DMAX | Microplane damage, macroscopic and maximum values. |
| MPDP |  | Microplane homogenized total, tension, and compression damages (TOTA, TENS, COMP), and split weight factor (RW). |
| DAMAGE |  | Damage in directions 1, 2, 3 (1, 2, 3) and the maximum damage (MAX). |
| GDMG |  | Damage |
| IDIS |  | Structural-thermal dissipation rate |
| BKS | X, Y, Z, XY, YZ, XZ | Total [nonlinear kinematic backstress](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#) reported in the current configuration (unaffected by [[rsys\|RSYS]] ). Available for 3D, plane strain, and axisymmetric elements. |
| BKS1,...,BKS5 | X, Y, Z, XY, YZ, XZ | Superimposed components of the total [nonlinear kinematic backstress](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#) reported in the current configuration (unaffected by [[rsys\|RSYS]] ). Available for 3D, plane strain, and axisymmetric elements when more than one superimposed back-stress component is defined. |
| EPFR |  | Free strain in porous media |
| SNDI |  | Component (X, Y, Z) sound intensity and vector sum (SUM). |
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

### PRESOL - Selected Result Component Labels

Selected Result Component Labels **PRESOL**,SRES, `Comp`

| Comp       | Description                             |
|------------|-----------------------------------------|
| SVAR `n`   | The `n` th state variable.              |
| FLDUF0 `n` | The `n` th user-defined field variable. |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRESOL.html
