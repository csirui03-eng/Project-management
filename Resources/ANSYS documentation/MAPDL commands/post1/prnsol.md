---
apdl: "PRNSOL"
method: prnsol
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.prnsol
generated: 2026-08-22
tags: [mapdl-command]
---

# PRNSOL

PyMAPDL: `mapdl.prnsol(item='', comp='', avg='', datakey='', **kwargs)`

Prints nodal solution results.

## Parameters

**item**: Label identifying the item. Valid item labels are shown in the table below. Some items also require a component label.

**comp**: Component of the item (if required). Valid component labels are shown in the table below. Default = COMP.

**avg**

Specifies whether random acoustic results are averaged. Valid only for `Item` = U and PRES.

- `(blank)` - No averaging (default).
- `AVG` - Print averaged results for random acoustics.

**datakey**

Key to specify which data is printed:

- `AUTO` - [Nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) are used if available; otherwise, the element-based data is used, if available. (Default.)
- `ESOL` - Only element-based results are used. If they are not available, the command is ignored.
- `NAR` - Only nodal-averaged results are used. If they are not available, the command is ignored.

## Notes

Prints the nodal solution results for the selected nodes in the sorted sequence. For [reinforcing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_compreinfdirectemb.html) elements (REINF `nnn` ), results are printed at intersection points of reinforcing elements and base elements.

For example, **PRNSOL**,U,X prints the X component of displacement vector U (that is, the UX degree of freedom).

Component results are in the global Cartesian coordinate directions unless transformed ( [[rsys|RSYS]] ).

Various element results also depend upon the recalculation method and the selected results location ( [[avprin|AVPRIN]], [[rsys|RSYS]], [[layer|LAYER]], [[shell|SHELL]], and [[nsel|NSEL]] ).

If [[layer|LAYER]] is issued, the resulting output is listed in full graphics mode ( [[graphics|/GRAPHICS]],FULL).

You can define which component of the nodal load (static, damping, inertia, or total) should be used ( [[force|FORCE]] ).

PowerGraphics can affect your nodal solution listings. For PowerGraphics ( [[graphics|/GRAPHICS]],POWER), results are listed for the model exterior surfaces only.

When shell element types are present, results are output on a surface-by-surface basis. For shell elements (such as `SHELL181` or `SHELL281` ), and for `ELBOW290`, printed output is for both the top and bottom surfaces. For solid elements such as `SOLID185`, the output is averaged for each surface and printed as follows:

- **Node at a vertex:** Three lines are output (one printed line for each surface).
- **Node on an edge:** Two lines are output (one printed line for each surface).
- **Nodes on a face:** One value is output.
- **Nodes interior to the volume:** No printed values are output.

If a node is common to more than one element, or if a geometric discontinuity exists, several conflicting listings may result. For example, a corner node incorporating results from solid elements and shell elements could yield as many as nine different results; the printed output would be averages at the top and bottom for the three shell surfaces plus averages at the three surfaces for the solid, for a total of nine lines of output. The program does not average result listings across geometric discontinuities when shell element types are present. It is important to analyze the listings at discontinuities to ascertain the significance of each set of data.

When only [reinforcing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_compreinfdirectemb.html) elements (REINF `nnn` ) are selected, results are listed for intersection points of reinforcing elements and base elements. Prints include coordinates of intersection points in global Cartesian coordinate system and results. Results are interpolated from the results of base elements. If a point is common to more than one reinforcing element, or reinforcing member within one reinforcing element, averaged results are printed. Prints also include minimum and maximum values.

The printed output for full graphics ( [[graphics|/GRAPHICS]],FULL) averages results at the node. For shell elements, the default for display is TOP so that the results for the top of the shell are averaged with the other elements attached to that node.

If [[nsort|NSORT]], [[esort|ESORT]] or [[eshape|/ESHAPE]] is issued with PowerGraphics enabled ( [[graphics|/GRAPHICS]],POWER), **PRNSOL** behaves as though full graphics mode is enabled ( [[graphics|/GRAPHICS]],FULL).

Items not supported by PowerGraphics are noted in *PRNSOL - General Result Item and Component Labels*.

For `Item` = SRES, selected result component ( [[osresult|OSRESULT]] ) values are output. See *PRNSOL - Selected Result Component Labels*.

To print midside nodes, first issue [[efacet|/EFACET]],2.

To learn more about the specific behaviors of **PRNSOL** in a cyclic symmetry analysis and printing results for nodes at cyclic edges, see [Using the /CYCEXPAND Command](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycpost.html#)

If [nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) ( [[outres|OUTRES]],NAR or another nodal-averaged label) are in the database, then **PRNSOL** uses the nodal-averaged data for the applicable items (S, EPEL, EPPL, EPCR, EPTH, EPSW) by default. You can change this behavior via the `DataKey` argument. Keep these points in mind when using nodal- averaged results:

- The [[layer|LAYER]] and [[rsys|RSYS]],SOLU commands are not valid with nodal-averaged results. If these commands are used, the element solution is printed instead if applicable.
- Issuing [[esel|ESEL]] before printing nodal-averaged results has no effect on the output.
- PowerGraphics is supported. The output is equivalent to the full model graphics output, but only the appropriate surface nodes are printed. See [Postprocessing Nodal-Averaged Results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#)

### PRNSOL - General Result Item and Component Labels

General Item and Component Labels **PRNSOL**, `Item,Comp`

| Item | Comp | Description |
|----|----|----|
| **Valid item and component labels for nodal degree of freedom results are:** |  |  |
| U | X, Y, Z | X, Y, or Z structural displacement. |
|  | COMP | X, Y, and Z structural displacements and vector sum. |
| ROT | X, Y, Z | X, Y, or Z structural rotation. |
|  | COMP | X, Y, and Z structural rotations and vector sum. |
| TEMP For `SHELL131` and `SHELL132` elements with KEYOPT(3) = 0 or 1, use the labels TBOT, TE2, TE3, ..., TTOP instead of TEMP. |  | Temperature. |
| PRES |  | Pressure. |
| VOLT |  | Electric potential. |
| GFV1, GFV2, GFV3 |  | Nonlocal field values 1, 2, and 3. |
| MAG |  | Magnetic scalar potential. |
| CONC |  | Concentration. Not supported by PowerGraphics. |
| V | X, Y, Z | X, Y, or Z fluid velocity in a fluid analysis. |
|  | COMP | X, Y, and Z fluid velocity and vector sum in a fluid analysis. |
| A | X, Y, Z | X, Y, or Z magnetic vector potential in an electromagnetic analysis. |
|  | COMP | X, Y, and Z magnetic vector potential and vector sum in an electromagnetic analysis. |
| VEL | X, Y, Z | X, Y, or Z velocity in a structural transient dynamic analysis ( [[antype\|ANTYPE]],TRANS). |
|  | COMP | X, Y, and Z velocity and vector sum in a structural transient dynamic analysis ( [[antype\|ANTYPE]],TRANS). |
| ACC | X, Y, Z | X, Y, or Z acceleration in a structural transient dynamic analysis ( [[antype\|ANTYPE]],TRANS). |
|  | COMP | X, Y, and Z acceleration and vector sum in a structural transient dynamic analysis ( [[antype\|ANTYPE]],TRANS). |
| OMG | X, Y, Z | X, Y, or Z rotational velocity in a structural transient dynamic analysis ( [[antype\|ANTYPE]],TRANS). |
|  | COMP | X, Y, and Z rotational velocity and vector sum in a structural transient dynamic analysis ( [[antype\|ANTYPE]],TRANS). |
| DMG | X, Y, Z | X, Y, or Z rotational acceleration in a structural transient dynamic analysis ( [[antype\|ANTYPE]],TRANS). |
|  | COMP | X, Y, and Z rotational acceleration and vector sum in a structural transient dynamic analysis ( [[antype\|ANTYPE]],TRANS). |
| CURR |  | Current. |
| EMF |  | Electromotive force drop. |
| DOF |  | All available degree of freedom labels (10 maximum). |
| FICT | TEMP | Fictive temperature. |
| SPL |  | Sound pressure level. |
| SPLA |  | A-weighted sound pressure level (dBA). |
| VNS |  | Normal velocity on the structural surface. Valid only for `SHELL181`, `SOLID185`, `SOLID186`, `SOLID187`, `SOLSH190`, and `SHELL281`. |
| ENKE |  | Acoustic diffusion energy density |
| **Valid item and component labels for element results are:** |  |  |
| S | COMP | X, Y, Z, XY, YZ, and XZ component stresses. This item outputs [nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) if they are available on the results file. |
|  | PRIN | S1, S2, S3 principal stresses, SINT stress intensity, and SEQV equivalent stress. |
| EPEL | COMP | Component elastic strains. |
|  | PRIN | Principal elastic strains, strain intensity, and equivalent strain. |
|  | FAIL | Maximum Strain Failure Criteria. Works only if failure criteria are provided ( [[fc\|FC]] and [[tb\|TB]] ). |
| EPTH | COMP | Component thermal strains. |
|  | PRIN | Principal thermal strains, strain intensity, and equivalent strain. |
| EPDI | COMP | Component diffusion strains. |
|  | PRIN | Principal diffusion strains, strain intensity, and equivalent strain. |
| EPPL | COMP | Component plastic strains. |
|  | PRIN | Principal plastic strains, strain intensity, and equivalent strain. |
| EPCR | COMP | Component creep strains. |
|  | PRIN | Principal creep strains, strain intensity, and equivalent strain. |
| EPSW |  | Swelling strain. |
| EPTO | COMP | Component total mechanical strains (EPEL + EPPL + EPCR). |
|  | PRIN | Principal total mechanical strains, strain intensity, and equivalent strain. |
| EPTT | COMP | Component total mechanical, thermal, diffusion, and swelling strains (EPEL + EPPL + EPCR + EPTH + EPDI + EPSW). |
|  | PRIN | Principal total mechanical, thermal, diffusion, and swelling strains, strain intensity, and equivalent strain. |
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
| FAIL |  | Failure criteria. **Default components:** Maximum of all failure criteria defined at current location (MAX), maximum strain (EMAX), maximum stress (SMAX), Tsai-Wu Strength Index (TWSI), inverse of Tsai-Wu Strength Ratio Index (TWSR). **Other available components:** Other available components: Hashin Fiber Failure (HFIB), Hashin Matrix Failure (HMAT), Puck Fiber Failure (PFIB), Puck Matrix Failure (PMAT), LaRc03 Fiber Failure (L3FB), LaRc03 Matrix Failure (L3MT), LaRc04 Fiber Failure (L4FB), LaRc04 Matrix Failure (L4MT), and any user-defined failure criteria (USR1 through USR9). USR1 through USR9 require a failure-criteria routine. Issue [[fctyp\|FCTYP]] to activate or remove failure criteria. |
| PFC |  | Failure criteria based on the effective stresses in the damaged material. **Components:** Maximum of all failure criteria defined at current location (MAX), fiber tensile failure (FT), fiber compressive failure (FC), matrix tensile failure (MT), and matrix compressive (MC). |
| PDMG |  | Progressive damage parameters. **Components:** Damage status (STAT, 0 = undamaged, 1 = damaged, 2 = complete damage), fiber tensile damage variable (FT), fiber compressive damage variable (FC), matrix tensile damage variable (MT), matrix compressive damage variable (MC), shear damage variable (S), energy dissipated per unit volume (SED), energy per unit volume due to viscous damping (SEDV). |
| SVAR Not supported by PowerGraphics. | 1, 2, 3,... N | State variable. |
| GKS | COMP | X, XY, XZ component gasket stress. |
| GKD | COMP | X, XY, XZ component gasket total closure. |
| GKDI | COMP | X, XY, XZ component gasket total inelastic closure. |
| GKTH | COMP | X, XY, XZ component thermal closure. |
| SS | X, XY, XZ | Interface traction (stress). |
| SD | X, XY, XZ | Interface separation. |
| CONT |  | Contact items (STAT For contact elements `CONTA172`, `CONTA174`, `CONTA175`, and `CONTA177`, the reported data are averaged across the element. To obtain a more meaningful STAT value, use [[presol\|PRESOL]]., PENE, PRES, SFRIC, STOT, SLIDE, GAP, FLUX, CNOS, FPRS). See component descriptions in [[plnsol\|PLNSOL]]. |
| TG | COMP | Component thermal gradients and vector sum. No vector sum is calculated for coupled pore-pressure-thermal (CPT `nnn` ) elements. |
| TF | COMP | Component thermal fluxes and vector sum. |
| PG | COMP | Components and vector sum for velocity or energy density flux (room acoustics). |
| EF | COMP | Component electric fields and vector sum. |
| D | COMP | Component electric flux densities and vector sum. |
| H | COMP | Component magnetic field intensities and vector sum. |
| B | COMP | Component magnetic flux densities and vector sum. |
| CG | COMP | Component concentration gradient or vector sum. |
| DF | COMP | Component diffusion flux density or vector sum. |
| FMAG | COMP | Component electromagnetic forces and vector sum. |
| JC | COMP | Conduction current density for elements that support conduction current calculation. Components (X, Y, Z) and vector sum (SUM). |
| BFE |  | Body temperatures (calculated from applied temperatures) as used in solution (area and volume elements only). |
| CAP |  | Material cap plasticity model only: Cohesion (C0); hydrostatic compaction yielding stress (X0); I1 at the transition point at which the shear and compaction envelopes intersect (K0); ZONE = 0: elastic state, ZONE = 1: compaction zone, ZONE = 2: shear zone, ZONE = 3: expansion zone; effective deviatoric plastic strain (DPLS); volume plastic strain (VPLS). |
| EDPC |  | Material EDP creep model only (not including the cap model): Equivalent creep stress (CSIG); equivalent creep strain (CSTR). |
| ESIG | COMP or blank | Components of Biot's effective stress. |
|  | PRIN | Principal stresses of Biot's effective stress. |
|  | INT | Stress intensity of Biot's effective stress. |
|  | EQV | Equivalent stress of Biot's effective stress. |
| DPAR | TPOR | Total porosity (Gurson material model). |
|  | GPOR | Porosity due to void growth. |
|  | NPOR | Porosity due to void nucleation. |
| FFLX | COMP | Fluid flow flux in poromechanics. |
| FGRA | COMP | Fluid pore pressure gradient components in poromechanics. |
| PMSV | COMP | Void volume ratio, pore pressure, degree of saturation, and relative permeability for coupled pore-pressure CPT elements. |
| NS | COMP | [Nominal strain](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_mat5.html#eq4dc2eb28-41da-4d81-b0d0-8716ce41a6e1) for hyperelastic material, reported in the current configuration (unaffected by [[rsys\|RSYS]] ). |
| MPLA | DMAC, DMAX | Microplane damage, macroscopic and maximum values. |
| MPDP |  | Microplane homogenized total, tension, and compression damages (TOTA, TENS, COMP), and split weight factor (RW). |
| DAMAGE |  | Damage in directions 1, 2, 3 (1, 2, 3) and the maximum damage (MAX). |
| GDMG |  | Damage |
| IDIS |  | Structural-thermal dissipation rate |
| BKS | X, Y, Z, XY, YZ, XZ | Total [nonlinear kinematic backstress](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#) reported in the current configuration (unaffected by [[rsys\|RSYS]] ). Available for 3D, plane strain, and axisymmetric elements. |
| BKS1,...,BKS5 | X, Y, Z, XY, YZ, XZ | Superimposed components of the total [nonlinear kinematic backstress](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#) reported in the current configuration (unaffected by [[rsys\|RSYS]] ). Available for 3D, plane strain, and axisymmetric elements when more than one superimposed back-stress component is defined. |
| EPFR |  | Free strain in porous media |
| SNDI | COMP | Component sound intensity and vector sum. |
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

### PRNSOL - Selected Result Component Labels

Selected Result Component Labels **PRNSOL**,SRES, `Comp`

| Comp       | Description                             |
|------------|-----------------------------------------|
| SVAR `n`   | The `n` th state variable.              |
| FLDUF0 `n` | The `n` th user-defined field variable. |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRNSOL.html
