---
apdl: "PLNSOL"
method: plnsol
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.plnsol
generated: 2026-08-22
tags: [mapdl-command]
---

# PLNSOL

PyMAPDL: `mapdl.plnsol(item='', comp='', kund='', fact='', fileid='', avg='', datakey='', **kwargs)`

Displays solution results as continuous element contours.

## Parameters

**item**: Label identifying the item. Valid item labels are shown in the table below. Some items also require a component label.

**comp**: Component of the item (if required). Valid component labels are shown in the table below.

**kund**

Undisplaced shape key:

- `0` - Do not overlay undeformed structure display.
- `1` - Overlay displaced contour plot with undeformed display (appearance is system-dependent).
- `2` - Overlay displaced contour plot with undeformed edge display (appearance is system- dependent).

**fact**: Scale factor for 2D display for contact items. Default value is 1. A negative scaling factor inverts the display.

**fileid**: The file index number (obtained via [[nldiag|NLDIAG]],NRRE,ON). Valid only for `Item` = NRRE.

**avg**

Specifies whether random acoustic results are averaged. Valid only for `Item` = U and PRES.

- `(blank)` - No averaging (default).
- `AVG` - Display averaged results for random acoustics.

**datakey**

Key to specify which data is plotted:

- `AUTO` - [Nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) are used, if available; otherwise, the element-based data is used, if available. (Default.)
- `ESOL` - Only element-based results are used. If they are not available, the command is ignored.
- `NAR` - Only nodal-averaged results are used. If they are not available, the command is ignored.

## Notes

**PLNSOL** displays the solution results as continuous contours across element boundaries for the selected nodes and elements.

For example, **PLNSOL**,S,X displays the X component of stress S (that is, the SX stress component). Various element results depend upon the recalculation method and the selected results location ( [[avprin|AVPRIN]], [[rsys|RSYS]], [[layer|LAYER]], [[shell|SHELL]], and [[nsel|NSEL]] ).

Contours are determined by linear interpolation within each element from the nodal values, averaged at a node whenever two or more elements connect to the same node. (The exception is FMAG, which is summed at the node.)

For [reinforcing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_compreinfdirectemb.html) elements (REINF `nnn` ), contours are determined by interpolation within each reinforcing member of reinforcing elements from the results of the base elements. Element results of members within the same reinforcing element are smoothed based on the order of its base element. **PLNSOL** displays constant results for a reinforcing element if the base elements are low-order, and linear results when the base elements are high-order.

For PowerGraphics displays ( [[graphics|/GRAPHICS]],POWER), results are plotted for the model exterior surface only. Items not supported by PowerGraphics are noted in *PLNSOL - Valid Item and Component Labels*.

To plot midside nodes, first issue [[efacet|/EFACET]],2.

If [nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) ( [[outres|OUTRES]],NAR or another nodal-averaged label) are in the database, then **PLNSOL** uses the nodal-averaged data for the applicable items (S, EPEL, EPPL, EPCR, EPTH, EPSW) by default. You can change this behavior via the `DataKey` argument. Keep these points in mind when using nodal- averaged results:

- The [[layer|LAYER]] and [[rsys|RSYS]],SOLU commands are not valid with nodal-averaged results. If these commands are used, the element solution is plotted instead if applicable.
- Issuing [[esel|ESEL]] before plotting nodal-averaged results has no effect on the output.
- PowerGraphics is supported. The output is equivalent to the full model graphics output, but only the appropriate surface nodes are plotted. See [Postprocessing Nodal-Averaged Results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#)

For `Item` = SRES, selected result ( [[osresult|OSRESULT]] ) values are output. See *PLNSOL - Selected Result Component Labels*.

### PLNSOL - Valid Item and Component Labels

General Item and Component Labels **PLNSOL**, `Item, Comp`

| Item | Comp | Description |
|----|----|----|
| **Valid item and component labels for nodal degree of freedom results are:** |  |  |
| U | X, Y, Z, SUM | X, Y, or Z structural displacement or vector sum. |
| ROT | X, Y, Z, SUM | X, Y, or Z structural rotation or vector sum. |
| TEMP For `SHELL131` and `SHELL132` elements with KEYOPT(3) = 0 or 1, use the labels TBOT, TE2, TE3, ..., TTOP instead of TEMP to view the individual temperature degree of freedom. When other thermal elements are included in the model, deselect them to avoid plotting undefined information. To view all temperatures in the same plot, set [[eshape\|/ESHAPE]] ,1 and [[graphics\|/GRAPHICS]],POWER and issue **PLNSOL**,TEMP. |  | Temperature. |
| PRES |  | Pressure. |
| GFV1, GFV2, GFV3 |  | Nonlocal field values 1, 2, and 3. |
| VOLT |  | Electric potential. |
| MAG |  | Magnetic scalar potential. |
| CONC |  | Concentration. Not supported by PowerGraphics. |
| V | X, Y, Z, SUM | X, Y, or Z fluid velocity or vector sum in a fluid analysis. |
| A | X, Y, Z, SUM | X, Y, or Z magnetic vector potential or vector sum in an electromagnetic analysis. |
| VEL | X, Y, Z, SUM | X, Y, or Z velocity or vector sum in a structural transient dynamic analysis ( [[antype\|ANTYPE]],TRANS). |
| ACC | X, Y, Z, SUM | X, Y, or Z acceleration or vector sum in a structural transient dynamic analysis ( [[antype\|ANTYPE]],TRANS). |
| OMG | X, Y, Z, SUM | X, Y, or Z rotational velocity or vector sum in a structural transient dynamic analysis ( [[antype\|ANTYPE]],TRANS). |
| DMG | X, Y, Z, SUM | X, Y, or Z rotational acceleration or vector sum in a structural transient dynamic analysis ( [[antype\|ANTYPE]],TRANS). |
| WARP |  | Warping. |
| NRRE | FX, FY, FZ, FNRM, MX, MY, MZ, MNRM | Plot the Newton-Raphson residuals from the file you obtained via the [[nldiag\|NLDIAG]],NRRE,ON command. The FNRM and MNRM labels are computed as the square root of the sum of the squares of the residual component forces or moments (FX,FY,FZ, MX, MY, MZ). When plotting Newton-Raphson residual items ( `Item` = NRRE) from a file on the deformed geometry, the displacements are based on the current set of results in the database. These displacements may not correspond to the loadstep and substep in the `.nrxxxxx` file. (For more information about `.nrxxxxx` files and nonlinear diagnostics postprocessing, see the description of the [[nldpost\|NLDPOST]] command and.) |
|  | SPL |  |
| SPLA |  | A-weighted sound pressure level (dBA). |
| VNS |  | Normal velocity on the structural surface. Valid only for `SHELL181`, `SOLID185`, `SOLID186`, `SOLID187`, `SOLSH190`, and `SHELL281`. |
| ENKE |  | Acoustic diffusion energy density |
| **Valid item and component labels for element results are:** |  |  |
| S | X, Y, Z, XY, YZ, XZ | Component stress. This item plots the solution using [nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) if they are available on the results file. |
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
|  | INT | Diffusion strain intensity. |
|  | EQV | Diffusion equivalent strain. |
| EPPL | X, Y, Z, XY, YZ, XZ | Component plastic strain. |
|  | 1, 2, 3 | Principal plastic strain. |
|  | INT | Plastic strain intensity. |
|  | EQV | Plastic equivalent strain. |
| EPCR | X, Y, Z, XY, YZ, XZ | Component creep strain. |
|  | 1, 2, 3 | Principal creep strain. |
|  | INT | Creep strain intensity. |
|  | EQV | Creep equivalent strain. |
| EPSW |  | Swelling strain. |
| EPTO | X, Y, Z, XY, YZ, XZ | Component total mechanical strain (EPEL + EPPL + EPCR). |
|  | 1, 2, 3 | Principal total mechanical strain. |
|  | INT | Total mechanical strain intensity. |
|  | EQV | Total mechanical equivalent strain. |
| EPTT | X, Y, Z, XY, YZ, XZ | Component total mechanical, thermal, diffusion, and swelling strain (EPEL + EPPL + EPCR + EPTH + EPDI + EPSW). |
|  | 1, 2, 3 | Principal total, mechanical, thermal, diffusion, and swelling strain. |
|  | INT | Total mechanical, thermal, diffusion, and swelling strain intensity. |
|  | EQV | Total mechanical, thermal, diffusion, and swelling equivalent strain. |
| ESIG | X,Y,Z,XY,YZ,ZX | Components of Biot's effective stress. |
|  | 1, 2, 3 | Principal stresses of Biot's effective stress. |
|  | INT | Stress intensity of Biot's effective stress. |
|  | EQV | Equivalent stress of Biot's effective stress. |
| DPAR | TPOR | Total porosity (Gurson material model). |
|  | GPOR | Porosity due to void growth. |
|  | NPOR | Porosity due to void nucleation. |
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
| FAIL | MAX | Maximum of all active failure criteria defined at the current location. (See [[fctyp\|FCTYP]].) Works only if failure criteria are provided ( [[fc\|FC]] and [[tb\|TB]] ). |
|  | EMAX | Maximum Strain Failure Criterion. |
|  | SMAX | Maximum Stress Failure Criterion. |
|  | TWSI | Tsai-Wu Strength Index Failure Criterion. |
|  | TWSR | Inverse of Tsai-Wu Strength Ratio Index Failure Criterion. |
|  | HFIB | Hashin Fiber Failure Criterion. Must first be added ( [[fctyp\|FCTYP]] ). |
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
| SVAR | 1, 2, 3,... N | State variable. |
| GKS | X, XY, XZ | Gasket component stress. |
| GKD | X, XY, XZ | Gasket component total closure. |
| GKDI | X, XY, XZ | Gasket component total inelastic closure. |
| GKTH | X, XY, XZ | Gasket component thermal closure. |
| SS | X, XY, XZ | Interface traction (stress). |
| SD | X, XY, XZ | Interface separation. |
| FICT | TEMP | Fictive temperature. |
| CONT For contact results, PowerGraphics is supported for 3D models only. For the CONT items for elements `CONTA172`, `CONTA174`, `CONTA175`, and `CONTA177`, the reported data is averaged across the element. To obtain a more meaningful STAT value, use [[plesol\|PLESOL]]. | STAT | Contact status For MPC-based contact definitions, the value of STAT can be negative, indicating that one or more contact constraints were intentionally removed to prevent overconstraint. STAT = -3 is used for MPC bonded contact; STAT = -2 is used for MPC no-separation contact. : \* 3 = closed and sticking \* 2 = closed and sliding \* 1 = open but near contact \* 0 = open and not near contact |
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
| CAP | C0,X0,K0,ZONE, DPLS,VPLS | Material cap plasticity model only: Cohesion; hydrostatic compaction yielding stress; I1 at the transition point at which the shear and compaction envelopes intersect; zone = 0: elastic state, zone = 1: compaction zone, zone = 2: shear zone, zone = 3: expansion zone; effective deviatoric plastic strain; volume plastic strain. |
| EDPC | CSIG,CSTR | Material EDP creep model only (not including the cap model): Equivalent creep stress; equivalent creep strain. |
| FFLX | X,Y,Z | Fluid flow flux in poromechanics. |
| FGRA | X,Y,Z | Fluid pore-pressure gradient in poromechanics. |
| FMAG | X, Y, Z, SUM | Component electromagnetic force or vector sum. |
| JC | X, Y, Z, SUM | Conduction current density for elements that support conduction current calculation. Components (X, Y, Z) and vector sum (SUM). |
| BFE | TEMP | Body temperatures (calculated from applied temperatures) as used in solution (area and volume elements only). |
| PMSV | VRAT, PPRE, DSAT, RPER | Void volume ratio, pore pressure, degree of saturation, and relative permeability for coupled pore-pressure-thermal elements. |
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

### PLNSOL - Selected Result Component Labels

Selected Result Component Labels **PLNSOL**,SRES, `Comp`

| Comp       | Description                             |
|------------|-----------------------------------------|
| SVAR `n`   | The `n` th state variable.              |
| FLDUF0 `n` | The `n` th user-defined field variable. |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLNSOL.html
