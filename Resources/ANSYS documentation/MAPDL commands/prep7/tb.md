---
apdl: "TB"
method: tb
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.data_tables.DataTables.tb
generated: 2026-08-22
tags: [mapdl-command]
---

# TB

PyMAPDL: `mapdl.tb(lab='', matid='', ntemp='', npts='', tbopt='', funcname='', **kwargs)`

Activates a data table for material properties or special element input.

## Parameters

**lab**

Material model data table type:

- `AFDM` - Acoustic frequency-dependent material.

- `AHYPER` - Anisotropic hyperelasticity.

- `ANEL` - Anisotropic elasticity.

- `ANISO` - Generalized Hill anisotropy.

- `AVIS` - Anisotropic viscosity.

- `BB` - Bergstrom-Boyce.

- `BH` - Magnetic field.

- `CAST` - Cast iron.

- `CDM` - Damage.

- `CFOAM` - Crushable foam.

- `CGCR` - [CGCR - Crack-Growth Fracture Criterion](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_TB.html#eq4d382484-99d1-41ac-82dc-5a82d9911274) Crack-growth fracture criterion ( [[cgrow|CGROW]] ).

- `CHABOCHE` - Chaboche nonlinear kinematic hardening using von Mises or Hill plasticity.

- `CONCR` - Concrete element or material data.

- `CREEP` - Creep. Pure creep, creep with isotropic hardening plasticity, or creep with kinematic hardening plasticity using both von Mises or Hill potentials.

- `CRKI` - - Material criterion for adaptive-crack initiation ( [[adpci|ADPCI]] )

- `CTE` - Coefficient of thermal expansion.

- `CZM` - Cohesive zone.

- `DENS` - Mass Density.

- `DLST` - Anisotropic dielectric loss tangent.

- `DMGE` - Damage evolution law.

- `DMGI` - Damage initiation criteria.

- `DPER` - Anisotropic electric permittivity.

- `EDP` - Extended Drucker-Prager (for granular materials such as rock, concrete, soil, ceramics and other pressure-dependent materials).

- `ELASTIC` - Elasticity.

- `ELST` - Anisotropic elastic loss tangent.

- `EXPE` - Experimental data.

- `FCON` - Fluid conductance data.

- `FCLI` - Material strength limits for calculating failure criteria.

- `FLUID` - Fluid.

- `FRIC` - Coefficient of friction based on Coulomb's Law or user-defined friction.

- `GASKET` - Gasket.

- `GURSON` - Gurson pressure-dependent plasticity for porous metals.

- `HFLM` - Film coefficient data.

- `HILL` - Hill anisotropy. When combined with other material options, simulates plasticity, viscoplasticity, and creep - all with the Hill potential.

- `HYPER` - Hyperelasticity material models (Arruda-Boyce, Blatz-Ko, Extended Tube, Gent, Mooney-Rivlin \[default\], Neo-Hookean, Ogden, Ogden Foam, Polynomial Form, Response Function, Yeoh, and user- defined).

- `INTER` - Contact interaction.

- `JOIN` - Joint (linear and nonlinear elastic stiffness, linear and nonlinear damping, and frictional behavior).

- `JROCK` - Jointed rock.

- `MC` - Mohr-Coulomb.

- `MELAS` - Multilinear elasticity.

- `MIGR` - Migration.

- `MPLANE` - Microplane.

- `NLISO` - Voce isotropic hardening law (or power law) for modeling nonlinear isotropic hardening using von Mises or Hill plasticity.

- `PELAS` - Porous elasticity.

- `PERF` - Perforated material for acoustics; equivalent fluid model of perforated media, poroelastic material model, and transfer admittance matrix.

- `PIEZ` - Piezoelectric matrix.

- `PLASTIC` - Nonlinear plasticity.

- `PM` - Porous media. Coupled pore-fluid diffusion and structural model of porous media.

- `PRONY` - Prony series constants for viscoelastic materials.

- `PZRS` - Piezoresistivity.

- `RATE` - Rate-dependent plasticity (viscoplasticity) when combined with the BISO, NLISO or PLASTIC material options, or rate-dependent anisotropic plasticity (anisotropic viscoplasticity) when combined with the HILL and BISO, NLISO or PLASTIC material options.

  The exponential visco-hardening option includes an explicit function for directly defining static yield stresses of materials.

  The Anand unified plasticity option requires no combination with other material models.

- `SDAMP` - Material damping coefficients.

- `SHIFT` - Shift function for viscoelastic materials.

- `SINT` - Sintering. Available with the Additive Suite license.

- `SMA` - Shape memory alloy for simulating [superelasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/smas.html#), [shape memory effect](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/smas.html#), or shape memory effect with [plasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/smas.html#matparmsmaplastic).

- `SOIL` - Soil models.

- `STATE` - User-defined state variables. Valid with **TB**,USER and used with either the [UserMat](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#) or [UserMatTh](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#) subroutine. Also valid with **TB**,CREEP (when `TBOPT` = 100) and used with the UserCreep subroutine.

- `SWELL` - Swelling strain function.

- `TNM` - Three-network model for viscoplastic materials.

- `THERM` - Thermal properties.

- `USER` - User-defined material or thermal material model (general-purpose except for incompressible material models) or thermal material model.

- `WEAR` - Contact surface wear.

- `XTAL` - Crystal plasticity for elasto-viscoplastic crystalline materials.

**matid**: Material reference identification number. Valid value is any number `n`, where 0 \< `n` \< 100,000. Default = 1.

**ntemp**: The number of temperatures for which data will be provided (if applicable). Specify temperatures via the [[tbtemp|TBTEMP]] command.

**npts**: For most labels where `NPTS` is defined, the number of data points to be specified for a given temperature. Define data points via the [[tbdata|TBDATA]] or [[tbpt|TBPT]] commands.

**tbopt**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TB.html) for further information.

**funcname**: The name of the function to be used (entered as `tabname`, where `tabname` is the name of the table created by the Function Tool). Valid only when `Lab` = JOIN (joint element material) and nonlinear stiffness or damping are specified on the `TBOPT` field (see ). The function must be predefined via the Function Tool. To learn more about how to create a function, see [Using the Function Tool](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BASFUNCGRAPH.html)

## Notes

**Data Table Specifications**

Following are input requirements ( `NTEMP`, `NPTS`, and `TBOPT` values) and links to detailed documentation for each data table type ( **TB**, `Lab` value):

- `NTEMP:` - Not used.

- `NPTS :` - Not used.

- `TBOPT:` - Acoustic material options:

  - `MAT` - Material properties
  - `THIN` - Thin layer
  - `RECT` - Rectangular cross-section
  - `CIRC` - Circular cross-section
  - `ROOM` - Diffusion properties for room acoustics

- `References:` - [Defining Acoustic Material Properties](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_acous/acous_mat_room.html)

  See [[tbfield|TBFIELD]] for more information about defining temperature- and/or frequency-dependent properties.

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1. Maximum = 40.

- `NPTS :` - Number of data points to be specified for a given temperature.

- `TBOPT :` - Anisotropic hyperelastic material options.

  - `POLY` - Polynomial strain energy potential.
  - `EXPO` - Exponential strain energy potential.
  - `AVEC` - Define the A vector.
  - `BVEC` - Define the B vector.
  - `PVOL` - Volumetric potential.
  - `USER` - [User-defined](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#) potential invariant set type.
  - `UNUM` - [User-defined](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#) invariant set number.
  - `AU01` - [User-defined](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#) material parameters.
  - `FB01` - [User-defined](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#) fiber directions.

- `References:` - [Anisotropic Hyperelasticity ( TB,AHYPER)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#eq1bb00e38-67c5-4f00-8adb-96bebf98d1f9)

  [Anisotropic Hyperelasticity Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR8_3.html#)

  [Subroutine UserHyperAniso (Writing Your Own Anisotropic Hyperelasticity Laws)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#)

  [Anisotropic Hyperelasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_mat5.html#eqbb7fd6a6-e661-44f4-be06-afb4a29e1bf9)

This material model is not supported for use with the coefficient of thermal expansion ( **TB**,CTE). The maximum number of ANEL tables is 1,000,000.

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 6. Maximum = 6.

- `NPTS :` - Not used.

- `TBOPT :` - Anisotropic elastic matrix options.

  - `0` - Elasticity matrix used as supplied (input in stiffness form).
  - `1` - Elasticity matrix inverted before use (input in flexibility form).

- `References:` - [Anisotropic Elasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/anel.html#eq2863f1de-4565-4ce0-a650-8c6d689c13cc)

- `NTEMP:` - Not used.

- `NPTS :` - Not used.

- `TBOPT:` - Not used.

- `References:` - [Generalized Hill Anisotropy](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#)

- `NTEMP:` - Not used.

- `NPTS :` - Not used.

- `TBOPT:` - Anisotropic viscosity matrix options:

  - `0` - Viscosity matrix (used as specified).
  - `1` - Fluency matrix (converted to viscosity matrix before use).

- `References:` - [Anisotropic Viscosity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_electricmagnet.html#)

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1. The maximum must be a value such that ( `NTEMP` x `NPTS` ) \<= 1000.

- `NPTS :` - Number of material constants.

- `TBOPT :` - Isochoric or volumetric strain-energy function:

  - `ISO` - Define material constants for isochoric strain energy.
  - `PVOL` - Define material constants for volumetric strain energy.

- `References:` - [Bergstrom-Boyce](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_bb.html#eqa1cf87c1-283a-4b62-856b-b656928b3269)

  [Bergstrom-Boyce Material ( TB,BB)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#eq562bbfb4-459d-41bf-89a7-6f815d15f1ca)

  [Bergstrom-Boyce Hyperviscoelasticity Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR8_3.html#)

- `NTEMP :` - Not used.

- `NPTS :` - Number of data points to be specified. Default = 20. Maximum = 500.

- `TBOPT :` - BH curve options.

  - `BH or (blank)` - BH curve data (default).
  - `TCF` - Thermal coefficient data for BH curve modification. This option is valid for the following elements: `PLANE223`, `SOLID226`, `SOLID227`, `PLANE233`, `SOLID236`, and `SOLID237`.

- `References:` -

  [Additional Guidelines for Defining Regional Material Properties and Real Constants](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_lof/Hlp_G_ELE2_3.html#a3nSIn2b4ctg)

- `NTEMP:` - Number of temperatures for which data will be provided. Default = 1. Maximum = 10.

- `NPTS:` - Not used.

- `TBOPT:` - Cast iron options:

  - `ISOTROPIC` - Specifies cast iron plasticity with isotropic hardening.
  - `TENSION` - Defines stress-strain relation in tension.
  - `COMPRESSION` - Defines stress-strain relation in compression.
  - `ROUNDING` - Defines tension yield surface rounding factor.

- `References:` - [Cast Iron](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#)

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1. The maximum must be a value such that ( `NTEMP` x `NPTS` ) \<= 1000.

- `NPTS :` - Number of data points to be specified for a given temperature.

- `TBOPT :` - Damage option:

  - `PSE2` - Mullins effect for hyperelasticity models: Pseudo-elastic model with a modified Ogden- Roxburgh damage function. Requires `NPTS` = 3.
  - `MUSER` - Mullins effect for hyperelasticity models: Pseudo-elastic model with a user-defined damage function.
  - `GDMG` - Generalized damage model parameters.
  - `FIB1` - Damage parameters in fiber direction 1.
  - `FIB2` - Damage parameters in fiber direction 2.
  - `FIB3` - Damage parameters in fiber direction 3.

- `References:` - [Mullins Effect](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_mullinseffect.html#thymullinspseudoelas)

  [Mullins Effect ( TB,CDM)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#eq131b2f6e-5292 - 4143-80f8-e779d52f1a70)

  [Mullins Effect Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR8_3.html#)

  [Regularized Anisotropic Damage](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_damageall.html#)

- `NTEMP :` - Not used.

- `NPTS :` - Not used.

- `TBOPT :` - Crushable foam material option:

  - [YIELD](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#) - Initial yield stress values.
  - [HTYPE](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#) - Hardening evolution type.
  - [MHARD](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#) - Multilinear hardening evolution points.
  - [PPR](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#) - Plastic Poisson's ratio.

- `References:` - [Crushable Foam](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#)

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1.

- `NPTS :` - Number of data points to be specified for a given temperature.

- `TBOPT :` - Fracture-criterion option.

  - [LINEAR](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#) - Linear fracture criterion. Valid when `NPTS` = 3.

  - [BILINEAR](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#) - Bilinear fracture criterion. Valid when `NPTS` = 4.

  - [BK](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#) - B-K fracture criterion. Valid when `NPTS` = 3.

  - [MBK](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#) - Modified B-K (Reeder) fracture criterion. Valid when `NPTS` = 4.

  - [POWERLAW](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#) - Wu's Power Law fracture criterion. Valid when `NPTS` = 6.

  - [USER](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#eq4724c95a-555f-4385-930f-aefcca09897e) - User-defined fracture criterion. Valid when `NPTS` = 20.

  - [PSMAX](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#eq4724c95a-555f-4385-930f-aefcca09897e) - Circumferential stress criterion based on (equation omitted) when sweeping around the crack tip at a given radius. Valid when `NPTS` = 1. Used in an [XFEM](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracfcgxfem.html#fracfcgxfemexample) -based crack-growth analysis only.

  - [STTMAX](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#eq4724c95a-555f-4385-930f-aefcca09897e) - Maximum circumferential stress criterion. Valid when `NPTS` = 1. Used in an [XFEM](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracfcgxfem.html#fracfcgxfemexample) -based crack-growth analysis only.

  - [RLIN](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#fracxfemdecaytab.fn1) - Rigid linear evolution law for the decay of stress. Valid when `NPTS` = 4. Used in an [XFEM](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracfcgxfem.html#fracfcgxfemexample) -based crack-growth analysis only.

  - [PARIS](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#eq4f61610d-5010-4a2d-83de-3c60fba4be9f) - Paris' Law for fatigue crack-growth. Valid when `NPTS` = 2. Used in a [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample)

    \- or [XFEM](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracfcgxfem.html#fracfcgxfemexample) -based fatigue crack-growth analysis only.

  - [WALK](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#eq4ea244c5-0b72-49dc-a7bf-43149889a1cd) - Walker equation for fatigue crack-growth. Valid when `NPTS` = 3. Used in a [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) -based fatigue crack-growth analysis only.

  - [FORM](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#eqd9c4405c-14bc-49a6-9c72-1bbe23d41643) - Forman equation for fatigue crack-growth. Valid when `NPTS` = 3. Used in a [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) -based fatigue crack-growth analysis only.

  - [TFDK](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#eq5a0147ef-6ed3-4a7a-9998 - 213217e78bdf) - Tabular fatigue law for fatigue crack-growth. Used in a [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) -based fatigue crack-growth analysis only.

  - [NG03](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#) - [NASGRO](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#nasgro4) equation v. 3 for fatigue crack-growth. Valid when `NPTS` = 9. Used in a [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) -based fatigue crack-growth analysis only.

  - [NG04](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#) - [NASGRO](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#nasgro4) equation v. 4 for fatigue crack-growth. Valid when `NPTS` = 10. Used in a [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) -based fatigue crack-growth analysis only.

  - KIC - [Critical stress-intensity factor](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#eqa7ac21d8-c5cc-41bd-aced-f664166c2ea0) for static crack-growth. Valid when `NPTS` = 1. Valid in a [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) -based static crack-growth analysis only.

  - JIC - [Critical J-integral](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#eqb5e4514c-a107-4016-847f-af649a691f2f) for static crack-growth. Valid when `NPTS` = 1. Valid in a [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) -based static crack-growth analysis only.

  Fatigue [crack-closure](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#polynomclosure) option. Valid in a [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) -based fatigue crack-growth analysis only, with crack-growth based on Paris[law](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#eq4f61610d-5010-4a2d-83de-3c60fba4be9f) or [tabular fatigue](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#eq5a0147ef-6ed3-4a7a-9998 - 213217e78bdf) law.

  - [ELBER](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#eqe9cf92f4-6e7c-48c1-b951-5ef12345157a)
    - Elber closure function.
  - [SCHIJVE](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#eqe1ec4405-f082-413b-822b-aaedef99bac5)
    - Schijve closure function.
  - [NEWMAN](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#eq3ed68a02-4fc8-46ce-aa3e-7fe3f5923ef5) - Newman closure function.
  - [UPOLY](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/franundcgrowmech.html#eqa6f0d4fd-ce08-4336-b1cf-b632d01a62c1) - Polynomial closure function.

- `References:` - [Fracture Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACBENCH.html)

  [[cgrow|CGROW]] command

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1. The maximum value of `NTEMP` is such that `NTEMP` x (1 + 2 `NPTS` ) = 1000.

- `NPTS :` - Number of kinematic models to be superposed. Default = 1. Maximum = 5.

- `TBOPT :` - \* `(blank)` - Default option for nonlinear kinematic hardening.

  - `TRATE` - Include temperature-rate term in back-stress evolution.
  - `SHDR` - Strain-hardening of dynamic recovery properties. To use this option, `TBOPT` = TRATE is also required.

- `References:` - [Nonlinear Kinematic Hardening](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#)

- `NTEMP :` - Number of temperatures for which data will be provided (used only if `TBOPT` = 0 or 1). Default = 6. Maximum = 6.

- `NPTS :` - Not used.

- `TBOPT :` - Concrete material options.

  - `DP` - [Drucker-Prager](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_geomechanics.html#matgeomechdefDPconcmod) concrete strength parameters.
  - `RCUT` - Rankine tension failure parameter.
  - `DILA` - Drucker-Prager concrete dilatation.
  - `HSD2` - Drucker-Prager concrete [exponential](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_geomechanics.html#eq02d041b8-8522 - 4917-93c4-d757c809944b) [hardening/softening/dilitation (HSD)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_geomechanics.html#matDPconcrlinearsoft) behavior.
  - `HSD4` - Drucker-Prager concrete [steel reinforcement](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_geomechanics.html#eq579f37fd-675c-48f0-941d-890069f7ee1d) HSD behavior.
  - `HSD5` - Drucker-Prager concrete [fracture energy](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_geomechanics.html#eqdae60069 - 4439-4532 - 9997-8223567cabd8) HSD behavior.
  - `HSD6` - Drucker-Prager concrete [linear](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_geomechanics.html#eq1f9198fc-0858-4d52-b551-f12bfd5b2024) HSD behavior.
  - `FPLANE` - Drucker-Prager concrete joint parameters.
  - `FTCUT` - Drucker-Prager concrete joint tension cutoff.
  - `FORIE` - Drucker-Prager concrete joint orientation.
  - `MW` - Menetrey-Willam constitutive model.
  - `MSOL` - [Material solution option](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_geomechanics.html#).

- `References:` - [Drucker-Prager Concrete](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_geomechanics.html#matgeomechdefDPconcmod)

  [Hardening, Softening and Dilatation (HSD) Behavior](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_geomechanics.html#matDPconcrlinearsoft)

  [Menetrey-Willam](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_geomechanics.html#)

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1.

- `NPTS :` - Number of data points to be specified for a given temperature.

- `TBOPT :` - Creep model options.

  - `1 through 13` - Implicit creep option. See for a list of available equations.
  - `100` - USER CREEP option. Define the creep law using the `USERCREEP.F` subroutine. See the [Guide to User-Programmable Features](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/ansysprog_aero_fullycoupled.html)

- `References:` - [Creep](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/rate.html#crei)

  [Creep Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR8_3.html#strimpcrplcd032400)

  See also [Combining Material Models](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/strmamoco050401.html)

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 6. Maximum = 6.

- `NPTS :` - Not used.

- `TBOPT :` - Adaptive crack-initiation options:

  - `PSMAX` - Maximum principal stress (default).

- `References:` - [SMART Method for Crack-Initiation Simulation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fractSMARTinit.html#SMARTcrackinitexamp)

- `NTEMP:` - No limit.

- `NPTS:` - Not used.

\* `TBOPT:` - \* `(blank)` - Enter the secant coefficients of thermal expansion (CTEX,CTEY,CTEZ) (default).

> - `USER` - User-defined thermal strain.
> - `FLUID` - [Fluid thermal-expansion coefficient](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/elemdatatblpor.html#heattranseq) for porous media.
> - `UFSTRAIN` - [User-defined free strain](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/elemdatatblpor.html#eq367d867d-cabc-4697-89e0-446fa8b7527d) in porous media.

- `References:` - [Thermal Expansion](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/ansmattherexp.html#eqd3e72ea4-fb9e-483e-94a3-eaa6081710de)

  [Porous Media Mechanics](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/elemdatatblpor.html#heattranseq)

  [Free-Strain Rate](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/elemdatatblpor.html#eq367d867d-cabc-4697-89e0-446fa8b7527d)

  See also [[tbfield|TBFIELD]] (for defining frequency-dependent, temperature-dependent, and [user-defined field-variable-based](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_fielduserdef.html#) properties).

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1.

- `NPTS :` - Number of data points to be specified for a given temperature.

- `TBOPT :` - Cohesive zone material options.

  - `EXPO` - Exponential material behavior. Valid for interface elements and contact elements.
  - `BILI` - [Bilinear material behavior](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/cozonemats.html#eq882acced-35ea-449a-9f59-1a8f1175f44c). Valid for interface elements, contact elements, and in an [XFEM-based crack-growth](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#fracxfemreferences) analysis when cohesive behavior on the initial crack is desired.
  - `CBDD` - Bilinear material behavior with linear softening characterized by maximum traction and maximum separation. Valid for contact elements only.
  - `CBDE` - Bilinear material behavior with linear softening characterized by maximum traction and critical energy release rate. Valid for contact elements only.
  - `CEXP` - Exponential material behavior for preventing surface penetration on the cohesive interface. Valid for [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) -based crack-growth only.
  - `CLIN` - Linear material behavior with a penalty slope for preventing surface penetration on the cohesive interface. Valid for [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) -based crack-growth only.
  - `VREG` - Viscous regularization. Valid for interface elements and contact elements. Also valid in an XFEM- based crack-growth analysis when cohesive behavior is specified for the initial crack.
  - `USER` - User-defined option. Valid for interface elements only.

- `References:` - [Cohesive Zone Material (CZM) Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_mat11.html#)

  [Cohesive Material Law](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/cozonemats.html#cozonepost)

  [Subroutine userCZM (Creating Your Own Cohesive Zone Material)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#matstatevaruserdefczm)

  [Crack-Initiation and -Growth Simulation, Interface Delamination, and Fatigue Crack-Growth](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracfcgxfem.html)

  [XFEM-Based Crack Analysis and Crack-Growth Simulation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#fracxfemreferences)

  [Enhancing Crack Surfaces with Cohesive Zone Elements](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#eq26e3f167-5353-40f6-b6f1-8c455fe0bc00)

- `NTEMP :` - Not used.

- `NPTS :` - 1

- `TBOPT :` - Not used.

- `References:` - See [[tbfield|TBFIELD]] and [User-Defined Field Variables](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_fielduserdef.html#)

- `NTEMP:` - Not used.

- `NPTS :` - Not used.

- `TBOPT:` - Not used.

- `References:` - [Anisotropic Dielectric Loss Tangent](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_electricmagnet.html#eq2d35a8da-dc5d-4cd9-9141 - 6540016c1258)

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1.

- `NPTS :` - Number of data points to be specified for a given temperature. Default = 4 when `TBOPT` = MPDG

- `TBOPT :` - Damage initiation definition:

  - `1, or MPDG` - Progressive damage evolution based on simple instant material stiffness reduction.
  - `2, or CDM` - Progressive damage evolution based on continuum damage mechanics.

- `Reference:` - [Damage Evolution Law](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_damageall.html#matprogdammodel)

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1.

- `NPTS :` - Number of data points to be specified for a given temperature. Default = 4 when `TBOPT` = FCRT.

- `TBOPT :` - Damage initiation definition:

  - `1 or FCRT` - Define failure criteria as the damage initiation criteria.

- `Reference:` - [Damage Initiation Criteria](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_damageall.html#mat_dmge)

- `NTEMP:` - Not used.

- `NPTS:` - Not used.

\* `TBOPT:` - Permittivity matrix options for `PLANE222`, `PLANE223`, `SOLID225`, `SOLID226`, and `SOLID227` :

> - `0` - Permittivity matrix at constant strain \[ε <sup>S</sup> \] (used as supplied)
> - `1` - Permittivity matrix at constant stress \[ε <sup>T</sup> \] (converted to \[ε <sup>S</sup> \] form before use)

- `References:` - [Anisotropic Electric Permittivity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_electricmagnet.html#eq3ef40343-18c4-490c-b76d-2ba7f66361a2)

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1. Maximum = 40.

- `NPTS :` - Number of data points to be specified for a given temperature.

- `TBOPT :` - EDP material options.

  - `LYFUN` - Linear yield function.
  - `PYFUN` - Power law yield function.
  - `HYFUN` - Hyperbolic yield function.
  - `LFPOT` - Linear flow potential function.
  - `PFPOT` - Power law flow potential function.
  - `HFPOT` - Hyperbolic flow potential function.
  - `CYFUN` - Cap yield function.
  - `CFPOT` - Cap flow potential function.

- `References:` - [Extended Drucker-Prager (EDP)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#)

  [Extended Drucker-Prager Cap](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#)

- `NTEMP:` - Number of temperatures for which data will be provided.

- `NPTS:` - Number of properties to be defined for the material option. This value is set automatically according to the elasticity option ( `TBOPT` ) selected. If `TBOPT` is not specified, default settings become `NPTS` = 2 and `TBOPT` = ISOT.

- `TBOPT:` - Elasticity options:

  - `ISOT` - Isotropic property (EX, NUXY) (default). Setting `NPTS` = 2 also selects this option automatically.
  - `OELN` - Orthotropic option with minor Poisson's ratio (EX, EY, EZ, GXY, GYZ, GXZ, NUXY, NUYZ, NUXZ). `NPTS` = 9. Setting `NPTS` = 9 selects this option automatically. All nine parameters must be set, even for the 2D case.
  - `OELM` - Orthotropic option with major Poisson's ratio (EX, EY, EZ, GXY, GYZ, GXZ, PRXY, PRYZ, PRXZ). `NPTS` = 9. All nine parameters must be set, even for the 2D case.
  - `AELS` - Anisotropic option in stiffness form (D11, D21, D31, D41, D51, D61, D22, D32, D42, D52, D62, D33, D43,..... D66). `NPTS` = 21. Setting `NPTS` = 21 selects this option automatically.
  - `AELF` - Anisotropic option in compliance form (C11, C21, C31, C41, C51, C61, C22, C32, C42, C52, C62, C33, C43,..... C66). `NPTS` = 21.
  - `FIB1` - Fiber parameters in fiber direction 1.
  - `FIB2` - Fiber parameters in fiber direction 2.
  - `FIB3` - Fiber parameters in fiber direction 3.
  - `USER` - User-defined linear elastic properties. For more information on the user_tbelastic subroutine, see the [Guide to User-Programmable Features](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/ansysprog_aero_fullycoupled.html)

- `References:` - See [[tbfield|TBFIELD]] for more information about defining temperature- and/or frequency-dependent properties.

  [Regularized Anisotropic Damage](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_damageall.html#)

  [Full Harmonic Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR4_5.html#sect2_lfd_wk5_2v)

- `NTEMP:` - Not used.

- `NPTS :` - Not used.

- `TBOPT:` - Not used.

- `References:` - [Anisotropic Elastic Loss Tangent](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_electricmagnet.html#eqe22b3cb5-2fc6-4cc3-8cc4-00b26991ab45)

- `NTEMP :` - Number of temperatures for which data will be provided.

- `NPTS :` - Number of data points to be specified for a given temperature.

- `TBOPT :` - Experimental data type:

  - `UNITENSION` - Uniaxial tension experimental data.
  - `UNICOMPRESSION` - Uniaxial compression experimental data.
  - `UNIAXIAL` - Uniaxial experimental data (combined uniaxial tension and compression).
  - `BIAXIAL` - Equibiaxial experimental data.
  - `SHEAR` - Pure shear experimental data (also known as planar tension).
  - `SSHEAR` - Simple shear experimental data.
  - `VOLUME` - Volumetric experimental data.
  - `GMODULUS` - Shear modulus experimental data.
  - `KMODULUS` - Bulk modulus experimental data.
  - `EMODULUS` - Tensile modulus experimental data.
  - `NUXY` - Poisson's ratio experimental data.

- `References:` -

  [Experimental Response Functions](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_mat5.html#thy_unidevfirstinv)

  [Viscoelasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/evis.html#mat_harmvisco)

  See also [[tbfield|TBFIELD]] for information about defining field-dependent experimental data.

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1. Maximum = 20.

- `NPTS :` - Number of data points to be specified for a given temperature. Default = 1. Maximum = 100.

- `TBOPT :` - Not used.

- `References:` - `FLUID116`

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1.

- `NPTS :` - Number of data points to be specified for a given temperature. Default = 20 when `TBOPT` = 1. Default = 9 when `TBOPT` = 2.

- `TBOPT :` - Material strength limit definition:

  - `1` - Define stress-strength limits.
  - `2` - Define strain-strength limits.

- `References:` -

- `NTEMP:` - Number of temperatures for which data will be provided. Default = 1.

- `NPTS:` - Number of data points to be specified for a given temperature.

- `TBOPT:` - Fluid material options:

  - `LIQUID` - Define material constants for a liquid material.
  - `GAS` - Define material constants for a gas material.
  - `PVDATA` - Define pressure-volume data for a fluid material.

- `References:` -

  [Fluid Material Models](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thyfluidmatmod.html#)

\* `NTEMP:` - Number of temperatures for which data will be provided. Default = 1. No maximum limit.

> `NTEMP` is not used for the following situations:
>
> - Isotropic or orthotropic friction defined in terms of field data ( [[tbfield|TBFIELD]] command)
> - User-defined friction ( `TBOPT` = USER)

- `NPTS:` - Number of data points to be specified for user-defined friction ( `TBOPT` = USER). Not used for `TBOPT` = ISO or `TBOPT` = ORTHO.

- `TBOPT:` - Friction options:

  - `ISO` - Isotropic friction (one coefficient of friction, MU) (default). This option is valid for all 2D and 3D contact elements.
  - `ORTHO` - Orthotropic friction (two coefficients of friction, MU1 and MU2). This option is valid for the following 3D contact elements: `CONTA174`, `CONTA175`, and `CONTA177`.
  - `FORTHO` - Orthotropic friction (two coefficients of friction, MU1 and Mu2) with a friction coordinate system fixed in space. This option is valid for the following 3D contact elements: `CONTA174`, `CONTA175`, and `CONTA177`.
  - `EORTHO` - Equivalent orthotropic friction (two coefficients of friction, MU1 and MU2). This option differs from `TBOPT` = ORTHO only in the way the friction coefficients are interpolated when they are dependent upon the following field variables: sliding distance and/or sliding velocity. In this case, the total magnitude of the field variable is used to do the interpolation.
  - `USER` - User defined friction. This option is valid for all 2D and 3D contact elements.

- `References:` - [Contact Friction](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/contfriction.html#userfriction)

  See also [[tbfield|TBFIELD]] for more information about defining a coefficient of friction that is dependent on temperature, time, normal pressure, sliding distance, or sliding relative velocity.

\* `NTEMP :` - Number of temperatures for which data will be provided. Default = 1. The maximum number of temperatures specified is such that `NTEMP` \* `NPTS` \< 2000.

- `NPTS :` - Number of data points to be specified for a given temperature. Default = 5 for `TBOPT` = PARA. Default = 1 for all other values of `TBOPT`.

- `TBOPT :` - Gasket material options.

  - `PARA` - Gasket material general parameters.
  - `COMP` - Gasket material compression data.
  - `LUNL` - Gasket linear unloading data.
  - `NUNL` - Gasket nonlinear unloading data.
  - `TSS` - Transverse shear data.
  - `TSMS` - Transverse shear and membrane stiffness data. (If selected, this option takes precedence over TSS.)

- `References:` - [Gasket](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/gask.html#fnstablestiff)

  [Gasket Joints Simulation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STgaga.html)

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1. Maximum = 40.

- `NPTS :` - Number of data points to be specified for a given temperature.

- `TBOPT :` - GURSON material options.

  - `BASE` - Basic model without nucleation or coalescence (default).
  - `SNNU` - Strain controlled nucleation.
  - `SSNU` - Stress controlled nucleation.
  - `COAL` - Coalescence.

- `References:` - [Gurson](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#matgursondefining)

  [Gurson's Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_mat1.html#gursonchaboche)

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1. Maximum = 20.

- `NPTS :` - Number of data points to be specified for a given temperature. Default = 1. Maximum = 100.

- `TBOPT :` - Not used.

- `References:` - `FLUID116`

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1. Maximum = 40.

- `NPTS :` - Not used.

- `TBOPT:` - Hill plasticity option:

  - `(blank)` - Use one set of Hill parameters (default).
  - `PC` - Enter separate Hill parameters for plasticity and creep. This option is valid for material combinations of creep and Chaboche nonlinear kinematic hardening only.

- `References:` - [Hill Anisotropy](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#)

  [Hill Yield Criterion](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#)

  See also [Combining Material Models](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/strmamoco050401.html)

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1. The maximum value of `NTEMP` is such that `NTEMP` x `NPTS` = 1000.

- `NPTS :` - Number of material parameters to be specified for a given temperature. Exceptions are for `TBOPT` = FOAM, OGDEN, POLY and YEOH, where `NPTS` is the number of terms in the material model's energy function.

- `TBOPT :` - Hyperelastic material options.

  - `BOYCE` - [Arruda-Boyce model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#eqcf34a3a5-b377-4b06-9d92-4a7e8e958452). For `NPTS`, default = 3 and maximum = 3.
  - `BLATZ` - [Blatz-Ko model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#eq1798ab0a-0024-4cef-9876-f55aa5303ff0). For `NPTS`, default = 1 and maximum = 1.
  - `ETUBE` - Extended tube model. Five constants ( `NPTS` = 5) are required.
  - `EXF1` - [Embedded fiber](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#eqeb96a83f-1199-4b6e-9338-edf5bebd5ebd) directions. Three constants ( `NPTS` = 3) define the direction for each fiber. Up to five fibers ( `NPTS` = 15) are allowed.
  - `EX1` - [Embedded fiber](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#eqeb96a83f-1199-4b6e-9338-edf5bebd5ebd) strain energy potential. Two constants ( `NPTS` = 2) are used for each fiber corresponding to the defined fiber directions. Undefined values default to zero.
  - `EXA1` - [Embedded fiber](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#eqeb96a83f-1199-4b6e-9338-edf5bebd5ebd) compression strain energy potential. Two constants ( `NPTS` = 2) are used for each fiber corresponding to the defined fiber directions. If not defined, the values specified via EX1 are used for both tension and compression.
  - `FOAM` - [Hyperfoam (Ogden) model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#eq10fe0596-b96a-403b-93f2-1cd3fd8e5adc). For `NPTS`, default = 1 and maximum is the number of terms in the energy function
  - `GENT` - [Gent model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#eq1300db31-3ece-4812-97ab-279677eddff4). For `NPTS`, default = 3 and maximum = 3.
  - `MOONEY` - [Mooney-Rivlin model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#eqb1e391b8-b91d-4fea-bd00-7efa10f7041e) (default). You can choose a two-parameter Mooney-Rivlin model with `NPTS` = 2 (default), or a three-, five-, or nine-parameter model by setting `NPTS` equal to one of these values.
  - `NEO` - [Neo-Hookean model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#eq9758debe-5160-4a73-82a8-8a94f56d6149). For `NPTS`, default = 2 and maximum = 2.
  - `OGDEN` - [Ogden model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#eqfac052c9-3204 - 4464-961f-51beb045c192). For `NPTS`, default = 1 and maximum is the number of terms in the energy function.
  - `POLY` - [Polynomial form model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#eqeac1ba8c-e46b-4ede-a548-778615d646a5). For `NPTS`, default = 1 and maximum is the number of terms in the energy function.
  - `RESPONSE` - [Experimental response function model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#eqd5e2d942-b39c-4fe3-a1ba-24e8949a80c1). For `NPTS`, default = 0 and maximum is such that `NTEMP` x `NPTS` + 2 = 1000.
  - `YEOH` - [Yeoh model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#eq7eea257d-c84c-4920-ab85-a27129367c87). For `NPTS`, default = 1 and maximum is the number of terms in the energy function.
  - `USER` - User-defined hyperelastic model.

- `References:` - [Hyperelasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#hyperthermdefcon)

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1. No maximum limit. `NTEMP` is used only for user-defined contact interaction ( `TBOPT` = USER).

- `NPTS :` - Number of data points to be specified. `NPTS` is used only for user-defined contact interaction ( `TBOPT` = USER).

- `TBOPT :` - Contact interaction options.

  The following options are valid only for general contact interactions specified via the [[gcdef|GCDEF]]  
  command:

  - `STANDARD` - Standard unilateral contact (default).
  - `ROUGH` - Rough, no sliding.
  - `NOSEPE` - No separation (sliding permitted).
  - `BONDED` - Bonded contact (no separation, no sliding).
  - `ANOSEP` - No separation (always).
  - `ABOND` - Bonded (always).
  - `IBOND` - Bonded (initial contact).

  > The following option is valid for all 2D and 3D contact elements:

  - `USER` - User-defined contact interaction.

- `References:` - [Contact Interaction](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/continteraction.html#continteruser)

  [Defining Your Own Contact Interaction ( USERINTER)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctecuserinterfacial.html#)

- `NTEMP:` - Number of temperatures for which data will be provided. Default = 1.

- `NPTS:` - Number of data points to be specified for a given temperature. `NPTS` is ignored if `TBOPT` = STIF or DAMP.

  If Coulomb friction is specified, `NPTS` is used only for `TBOPT` = MUS1, MUS4, and MUS6.

- `TBOPT:` - Joint element material options.

  > Linear stiffness behavior:

  - `STIF` - Linear stiffness.

  > Nonlinear stiffness behavior:

  - `JNSA` - Nonlinear stiffness behavior in all available components of relative motion for the joint element.
  - `JNS1` - Nonlinear stiffness behavior in local UX direction only.
  - `JNS2` - Nonlinear stiffness behavior in local UY direction only.
  - `JNS3` - Nonlinear stiffness behavior in local UZ direction only.
  - `JNS4` - Nonlinear stiffness behavior in local ROTX direction only.
  - `JNS5` - Nonlinear stiffness behavior in local ROTY direction only.
  - `JNS6` - Nonlinear stiffness behavior in local ROTZ direction only.

  > Linear damping behavior:

  - `DAMP` - Linear damping.

  > Nonlinear damping behavior:

  - `JNDA` - Nonlinear damping behavior in all available components of relative motion for the joint element.
  - `JND1` - Nonlinear damping behavior in local UX direction only.
  - `JND2` - Nonlinear damping behavior in local UY direction only.
  - `JND3` - Nonlinear damping behavior in local UZ direction only.
  - `JND4` - Nonlinear damping behavior in local ROTX direction only.
  - `JND5` - Nonlinear damping behavior in local ROTY direction only.
  - `JND6` - Nonlinear damping behavior in local ROTZ direction only.

  > Friction Behavior:

  - `Coulomb friction coefficient -` - The values can be specified using either [[tbdata|TBDATA]] ( `NPTS` = 0) or [[tbpt|TBPT]] ( `NPTS` is nonzero).

  - `MUS1` - Coulomb friction coefficient (stiction) in local UX direction only.

  - `MUS4` - Coulomb friction coefficient (stiction) in local ROTX direction only.

  - `MUS6` - Coulomb friction coefficient (stiction) in local ROTZ direction only, or

    Coulomb friction coefficient (stiction) for Spherical Joint.

  - `Coulomb friction coefficient - Exponential Law -` - Use [[tbdata|TBDATA]] to specify μ<sub>s</sub>, μ<sub>d</sub>, and c for the exponential law.

  - `EXP1` - Exponential law for friction in local UX direction only.

  - `EXP4` - Exponential law for friction in local ROTX direction only.

  - `EXP6` - Exponential law for friction in local ROTZ direction only.

  > Elastic slip:

  - `SL1` - Elastic slip in local UX direction only.

  - `SL4` - Elastic slip in local ROTX direction only.

  - `SL6` - Elastic slip in local ROTZ direction only, or

    Elastic slip for Spherical Joint.

  - `TMX1` - Critical force in local UX direction only.

  - `TMX4` - Critical moment in local ROTX direction only.

  - `TMX6` - Critical moment in local ROTZ direction only.

  > Stick-stiffness:

  - `SK1` - Stick-stiffness in local UX direction only.

  - `SK4` - Stick-stiffness in local ROTX direction only.

  - `SK6` - Stick-stiffness in local ROTZ direction only, or

    Stick-stiffness for Spherical Joint.

  > Interference fit force/moment:

  - `FI1` - Interference fit force in local UX direction only.
  - `FI4` - Interference fit moment in local ROTX direction only.
  - `FI6` - Interference fit moment in local ROTZ direction only.

- `References:` - [MPC184 Joint](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/jointmat.html#mpcfriction)

- `NTEMP :` - Not used.

- `NPTS :` - Not used.

- `TBOPT :` - \* `BASE` - Base material parameters.

  - `RCUT` - Base material tension cutoff.
  - `RSC` - Residual strength coupling.
  - `FPLANE` - Joint parameters.
  - `FTCUT` - Joint tension cutoff.
  - `FORIE` - Joint orientation.
  - `MSOL` - [Material solution option](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_geomechanics.html#).

- `References:` - [Jointed Rock](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_geomechanics.html#)

- `NTEMP :` - Not used.

- `NPTS :` - Not used.

- `TBOPT :` - \* `BASE` - Mohr-Coulomb material parameters.

  - `RCUT` - Tension cutoff.
  - `RSC` - Residual strength coupling.
  - `POTN` - Plastic potential.
  - `FRICTION` - Friction angle scaling.
  - `COHESION` - Cohesion scaling.
  - `TENSION` - Tension strength scaling.
  - `DILATATION` - Dilatancy angle scaling.
  - `MSOL` - [Material solution option](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_geomechanics.html#).

- `References:` - [Mohr-Coulomb](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_geomechanics.html#)

- `NTEMP :` - Number of temperatures for which data will be provided.

- `NPTS :` - Number of data points to be specified for a given temperature.

- `TBOPT :` - Not used.

- `References:` - [Multilinear Elasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_multilinelas.html#eqb58de8d9-86b1-4b61-ba30-bbf72444234a)

- `NTEMP :` - Not used.

- `NPTS :` - Not used.

- `TBOPT :` - Migration model options.

  - `0` - Atomic (or ion) flux (default).
  - `1` - Vacancy flux.

- `References:` - [Migration Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/migr.html#migr_vacancy)

  [Electric-Diffusion Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cou/coupelecdiff.html#)

  [Thermal-Diffusion Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cou/couthermdiffanal.html#coudirextda)

  [Structural-Diffusion Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cou/coustrdiffana.html#)

  [Electric-Diffusion Coupling](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thry_elec_diff_couple.html#eq4df90de8-0708-4ba0-90a1-b9cb38b44dcf)

  [Thermal-Diffusion Coupling](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thry_therm_diff_couple.html#eqa72b8051-83ce-4640-b97b-e6bae9fed535)

  [Structural-Diffusion Coupling](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thry_str_diff_cou.html#eq00699203-a90a-4e59-a5d5-803bca2f9dad)

- `NTEMP :` - The number of temperatures for which data will be provided. Default = 1. Maximum is such that `NTEMP` x `NPTS` = 1000.

- `NPTS :` - The number of data points to be specified for a given temperature. Default = 6. Maximum is such that `NTEMP` x `NPTS` = 1000.

- `TBOPT :` - Microplane model options:

  - `ORTH` - [Elastic microplane material with damage](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/microplane.html#) model (default).
  - `DPC` - [Coupled damage-plasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/microplane.html#) microplane model.
  - `NLOCAL` - [Nonlocal parameters](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/microplane.html#eq1cc4a2af-945c-470d-a125-21c3c06eccea).

- `References:` - [Microplane](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/microplane.html#matmicroplanereadlist)

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1.

- `NPTS :` - Number of data points to be specified for a given temperature. Default = 4. Maximum = 4.

- `TBOPT :` - Isotropic hardening options.

  - `VOCE` - Voce hardening law (default).
  - `POWER` - Power hardening law.

- `References:` - [Nonlinear Isotropic Hardening](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#matnlisvocelaw)

- `NTEMP:` - Not used.

- `NPTS:` - Not used.

- `TBOPT:` - Equivalent fluid model options:

  - `JCA` - Johnson-Champoux-Allard model
  - `DLB` - Delaney-Bazley model
  - `MIKI` - Miki model
  - `ZPRO` - Complex impedance and propagating constant model
  - `CDV` - Complex density and velocity model

  Poroelastic acoustic material:

  - `PORO` - Poroelastic material model

  Transfer admittance matrix options:

  - `YMAT` - General transfer admittance matrix model
  - `SGYM` - Transfer admittance matrix model of square grid structure
  - `HGYM` - Transfer admittance matrix model of hexagonal grid structure

- `References:` - [Perforated Media](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/acousticmat.html#acous_mat_trans_admit)

  [Equivalent Fluid of Perforated Materials](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thyacous_proprad.html#)

  [Poroelastic Acoustics](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thyacous_poroelastic.html#thyacous_poro_coup)

  [Perforated Material](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_acous/acous_mat_equivperf.html#acous_poromat)

  [Trim Element with Transfer Admittance Matrix](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_acous/acous_excit_loads.html#)

  See [[tbfield|TBFIELD]] for more information about defining temperature and/or frequency-dependent properties.

- `NTEMP :` - Not used.

- `NPTS :` - Not used.

- `TBOPT :` - Piezoelectric matrix options.

  - `0` - Piezoelectric stress matrix \[e\] (used as supplied)
  - `1` - Piezoelectric strain matrix \[d\] (converted to \[e\] form before use)

- `References:` - [Piezoelectricity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_electricmagnet.html#eqa42ac64b-bb76-4eab-ad28-d8fba52e2755)

  [Piezoelectric Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cou/Hlp_G_COU3_piezo.html#)

- `NTEMP:` - Not used.

- `NPTS:` - Not used.

- `TBOPT:` - Plasticity option:

  - `BISO` - [Bilinear isotropic hardening plasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#).

  - `BKIN` - [Bilinear kinematic hardening plasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#).

  - `MISO` - [Multilinear isotropic hardening plasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#).

  - `KINH` - [Multilinear kinematic hardening plasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#).

    The number of points ( [[tbpt|TBPT]] commands issued) is limited to 100 for this option.

  - `KSR2` - [Kinematic static recovery](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#).

  - `ISR` - [Isotropic static recovery](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#).

- `References:` - [Rate-Independent Plasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#sintering)

- `NTEMP :` - Not used.

- `NPTS :` - Not used.

- `TBOPT :` - \* `POISSON` - Porous elasticity model..

- `References:` - [Porous Elasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_porous_elasticity.html#matporelasdefining)

- `NTEMP :` - The number of temperatures. Default = 1. The maximum must be a value such that ( `NTEMP` x `NPTS` ) \<= 1000.

- `NPTS :` - The number of material constants. Default = 4. The maximum must be a value such that ( `NTEMP` x `NPTS` ) \<= 1000.

- `TBOPT :` - Porous media options:

  - `PERM` - Permeability
  - `BIOT` - Biot coefficient
  - `SP` - Solid property
  - `FP` - Fluid property
  - `DSAT` - Degree-of-saturation table
  - `RPER` - Relative-permeability table
  - `GRAV` - Gravity magnitude

- `References:` - [Porous Media Material Properties](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/elemdatatblpor.html#pormedunitsperm)

  [Porous Media Flow](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thypormediaflow.html#eqf368dccd-e6d9-4ee1-af36-04edf2a7e0ed)

  [Structural-Pore-Fluid-Diffusion-Thermal Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cou/Hlp_G_COU_porefluiddiffstruct.html#coupfdsanalysis)

  [Applying Initial Degree of Saturation and Relative Permeability](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/Hlp_G_INSTAPPL.html#)

  See also [VM260](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_vm/Hlp_V_VM260.html#vm260.results1).

- `NTEMP:` - Number of temperatures for which data will be provided. Default = 1.

  Unused for `TBOPT` = EXPERIMENTAL.

- `NPTS:` - Defines the number of Prony series pairs for `TBOPT` = SHEAR or `TBOPT` = BULK. Default = 1.

  Unused for `TBOPT` = INTEGRATION and `TBOPT` = EXPERIMENTAL.

- `TBOPT:` - Defines the behavior for viscoelasticity.

  - `SHEAR` - Shear Prony series.
  - `BULK` - Bulk Prony series.
  - `INTEGRATION` - Stress update algorithm.
  - `EXPERIMENTAL` - Complex modulus from experimental data.

- `References:` - [Viscoelasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/evis.html#mat_harmvisco)

- `NTEMP:` - Not used.

- `NPTS:` - Not used.

- `TBOPT:` - Piezoresistive matrix options

  - `0` - Piezoresistive stress matrix (used as supplied)
  - `1` - Piezoresistive strain matrix (used as supplied)

- `References:` - [Piezoresistivity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_electricmagnet.html#eqe0185ba1-ccf6-46fc-99f8-7b3596865855)

  [Piezoresistive Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cou/Hlp_G_COU3_piezores.html#)

- `NTEMP :` - The number of temperatures for which data will be provided. Default is 1. Maximum is such that `NTEMP` x `NPTS` = 1000.

- `NPTS :` - The number of data points to be specified for a given temperature. Default = 2. Maximum is such that `NTEMP` x `NPTS` = 1000.

- `TBOPT :` - Rate-dependent viscoplasticity options.

  - `PERZYNA` - Perzyna option (default).
  - `PEIRCE` - Peirce option.
  - `EVH` - Exponential visco-hardening option.
  - `ANAND` - Anand option.

- `References:` - [Rate-Dependent Plasticity (Viscoplasticity)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/rate.html#matdpcreep)

  [Viscoplasticity Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR8_3.html#avFlpr2dtlm)

  [Rate-Dependent Plasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_mat2.html#matanandvisco)

  See also [Combining Material Models](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/strmamoco050401.html)

- `NTEMP:` - Number of temperatures for which data will be provided. Default = 1.

- `NPTS:` - Number of properties to be defined for the material option. Default = 1 for each material damping option ( `TBOPT` ) selected.

- `TBOPT:` - Material damping options:

  - `STRU or 1` - Structural damping coefficient (default).
  - `ALPD or 2` - Rayleigh mass proportional material damping.
  - `BETD or 3` - Rayleigh stiffness proportional material damping.

- `References:` - [Material Damping](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_matdamping.html#)

  [Full Harmonic Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR4_5.html#sect2_lfd_wk5_2v)

  [Damping Matrices](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool3.html#)

- `NTEMP:` - Allows one temperature for which data will be provided.

\* `NPTS:` - Number of material constants to be entered as determined by the [shift function](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/evis.html#mat_userdefshift) specified via `TBOPT`. Not used for `TBOPT` = PLIN.

> - `3` - for `TBOPT` = WLF
> - `2` - for `TBOPT` = TN
> - `` n, :sub:`f `` - for TBOPT = FICT, where n :sub:\`f is the number of partial fictive temperatures

- `TBOPT:` - Shift function:

  - `WLF` - [Williams-Landel-Ferry](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/evis.html#eq54042d38-108a-429b-a239-e5796a477097).
  - `TN` - [Tool-Narayanaswamy](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/evis.html#matliquidcoeef).
  - `FICT` - [Tool-Narayanaswamy](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/evis.html#matliquidcoeef) with fictive temperature.
  - `PLIN` - [Piecewise linear](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/evis.html#eqba8af3fc-fa01-4b6b-992c-094ad649ad1f).
  - `USER` - User-defined.

- `References:` - [Viscoelasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/evis.html#mat_harmvisco)

- `NTEMP:` - Not used.

- `NPTS:` - Not used.

- `TBOPT:` - Sintering options:

  - `INIT` - [Initial conditions](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#) : relative density, particle diameter, and grain-size diameter. The initial relative density can alternatively be specified as a location-varying initial state ( [[inistate|INISTATE]] ).
  - `PARAM` - [Sintering activation temperature](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#) and mode specification.
  - `STRESS` - Sintering stress coefficients.
  - `VSCOEF` - [Viscosity coefficients](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#). Mutually exclusive with VSTABLE.
  - `VSTABLE` - Table of viscosity values. Mutually exclusive with VSCOEF.
  - `GROWTH` - [Grain-growth](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#) parameters.
  - `RIEDEL` - Selects the Riedel sintering model (default) and defines the viscous moduli coefficients.
  - `SOVS` - Selects the Skorohold-Olevsky sintering model and defines the viscous moduli coefficients.
  - `ANICONST` - [Orthotropic factors](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#) to be applied to the viscous bulk and shear moduli. The factors remain constant throughout densification.

- `References:` - [Sintering](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#)

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1.

- `NPTS :` - Number of data points to be specified for a given temperature. Default = 7 if `TBOPT` = SUPE or MEFF, 2 if `TBOPT` = METE, 6 if `TBOPT` = METL or METH, and 7 if `TBOPT` = MEPD.

- `TBOPT :` - Shape memory model option:

  SUPE - [Superelasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/smas.html#) option (default).

  MEFF - [Shape memory effect](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/smas.html#) option.

  METE - Shape memory effect with [plasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/smas.html#matparmsmaplastic) option: elastic phase-dependent and thermal expansion.

  METL - Shape memory effect with [plasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/smas.html#matparmsmaplastic) option: limits of transformation in strain-stress-temperature space.

  METH - Shape memory effect with [plasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/smas.html#matparmsmaplastic) option: transformation hardening.

  MEPD - Shape memory effect with [plasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/smas.html#matparmsmaplastic) option: plastic response.

  METC - Shape memory effect with [plasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/smas.html#matparmsmaplastic) option: tension-compression asymmetry response and hysteresis response.

- `Reference:` - [Shape Memory Alloy (SMA)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/smas.html#matsmareadlist)

- `NTEMP :` - Not used.

- `NPTS :` - Not used.

- `TBOPT :` - \* `CAMCLAY` - Modified Cam-clay material model.

  - `MSOL` - [Material solution option](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_geomechanics.html#).

- `References:` - [Cam-clay](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_geomechanics.html#)

When `Lab` = STATE, state variable specifications affect user-defined material models. The subroutine in use depends on the element type used when `Lab` = USER is specified.

- `NTEMP :` - Not used.

- `NPTS :` - Number of state variables.

- `TBOPT :` - Not used.

- `References:` - [Customizing Material Behavior](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/matcustommatmods.html#matsubroutstatevars)

- `NTEMP :` - Number of temperatures for which data will be provided. The maximum value of NTEMP is such that NTEMP x NPTS = 1000

- `NPTS :` - Number of data points to be specified for a given temperature. The maximum value of NPTS is such that NPTS x NTEMP = 1000.

- `TBOPT :` - Swelling model options:

  - `LINEAR` - Linear swelling function.
  - `EXPT` - Exponential swelling function.
  - `USER` - User-defined swelling function. Define the swelling function via subroutine userswstrain (described in the [Programmer\&#39;s Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Hlp_P_UPFTOC.html)). Define temperature-dependent constants via the [[tbtemp|TBTEMP]] and [[tbdata|TBDATA]] commands. For solution-dependent variables, define the number of variables via the **TB**,STATE command.

- `References:` - [Swelling](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/swel.html#eqe6a35e77-4361-4a55-8524-4e97a33209aa)

  [Swelling Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR8_3.html#)

- `NTEMP :` - Not used.

- `NPTS :` - Not used.

- `TBOPT :` - Thermal properties:

  - `COND` - Thermal conductivity.
  - `ENTH` - Enthalpy. Enthalpy must be a function of temperature only (see Considerations for Enthalpy).
  - `SPHT` - Specific heat. For [porous media](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/elemdatatblpor.html#pormedflowdamp), solid-skeleton specific heat.
  - `FLSPHT` - Fluid-specific heat for [porous media](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/elemdatatblpor.html#pormedflowdamp).

- `References:` - [Thermal Properties](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/thermalmat.html#)

  [Porous Media Mechanics](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/elemdatatblpor.html#heattranseq)

- `NTEMP :` - Not used.

- `NPTS :` - Not used.

- `TBOPT :` - Three-network model material options:

  - `NETA` - Network A properties.
  - `NETB` - Network B properties.
  - `NETC` - Network C properties.
  - `FLOW` - Network flow properties.
  - `TDEP` - Temperature-dependence factors.
  - `LOCK` - Chain-locking stretch.
  - `BULK` - Bulk modulus.

- `References:` - [Three-Network Model ( TB,TNM)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#mathypertnmrefs)

When `Lab` = USER, the **TB** command activates either the [UserMat](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#) (user-defined material) or the [UserMatTh](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#) (user-defined thermal material) subroutine automatically. The subroutine activated depends on the element type used.

- `NTEMP :` - Number of temperatures for which data will be provided. Default = 1.
- `NPTS :` - Number of data points to be specified for a given temperature. Default = 48.

\* `TBOPT:` - User-defined material model ( [UserMat](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#) ) or thermal material model ( [UserMatTh](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#) ) options:

> - `NONLINEAR` - Nonlinear iterations are applied (default).
> - `LINEAR` - Nonlinear iterations are not applied. This option is ignored if there is any other nonlinearity involved, such as contact, geometric nonlinearity, etc.
> - `MXUP` - This option indicates a [UserMat material model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#) to be used with [mixed u-P element formulation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_continuumelems.html#EL2omnusjwf091100) for material exhibiting incompressible or nearly incompressible behavior.
> - `THERM` - Thermal material model ( UserMatTh ) for a coupled-field analysis using elements `SOLID225`, `SOLID226` and `SOLID227` with thermal degrees of freedom. Use this option in a coupled structural-thermal analysis to specify a user-defined thermal material model ( [UserMatTh](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#) ) independently of the user-defined structural material model ( [UserMat](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#) ).

- `References:` - [Customizing Material Behavior](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/matcustommatmods.html#matsubroutstatevars)

  [Subroutine UserMat (Creating Your Own Material Model)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#)

  [Subroutine UserMatTh (Creating Your Own Thermal Material Model)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Z7K4r1e5lcd.html#)

- `NTEMP:` - Number of temperatures for which data will be provided.

- `NPTS:` - Number of data points to be specified for the wear option. This value is set automatically based on the selected wear option ( `TBOPT` ). If `TBOPT` is not specified, the default becomes `NPTS` = 5 and `TBOPT` = ARCD.

- `TBOPT:` - Wear model options:

  - `ARCD` - Archard wear model (default).
  - `USER` - User-defined wear model.
  - `AUTS` - Automatic scaling of wear increment. Must be used in conjunction with one of the wear models ( `TBOPT` = ARCD or USER).

- `References:` - [Contact Surface Wear](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/contwearmat.html#)

  [Contact Surface Wear](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctec_includwear.html)

  See also [[tbfield|TBFIELD]] for more information about defining temperature and/or time-dependent properties.

- `NTEMP:` - Unused.

- `NPTS:` - Unused.

- `TBOPT:` - Crystal plasticity material options:

  - `ORIE` - Crystal orientation.
  - `NSLFAM` - Number of slip families.
  - `FORM` - Formulation number.
  - `XPARAM` - Crystal characteristic parameters.
  - `HARD` - Slip system hardness properties.
  - `FLFCC` - Face-centered cubic (FCC) flow parameters.
  - `FLHCP` - Hexagonal closed packed (HCP) flow parameters.
  - `FLBCC` - Body-centered cubic (BCC) flow parameters.

- `Reference:` - [Crystal Plasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/crystalplast.html#cpmrefs)

**TB** activates a data table for use by subsequent [[tbdata|TBDATA]] or [[tbpt|TBPT]] commands. The table space is initialized to zero values. Data from this table are used for most nonlinear material descriptions as well as for special input for some elements.

For a list of elements supporting each material model ( `Lab` value), see [Material Model Element Support](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/Mp8sasdgh.html#fncptnnnedp)

For information about linear material property input, see [[mp|MP]].

This command is also valid in SOLUTION.

### Considerations for Enthalpy ( `TBOPT` = ENTH)

- To ensure correct results, you must define enthalpy over a large enough temperature range to span all computed temperatures during the solution. The **TB** command does not extrapolate enthalpy values beyond the specified temp range like the [[mp|MP]] command does.
- If both the **TB** and [[mp|MP]] commands are used to specify enthalpy values, enthalpy values defined via the **TB** command are used and those defined via the [[mp|MP]] command are ignored.

(table not available in the PyMAPDL source, see the Ansys help page)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TB.html
