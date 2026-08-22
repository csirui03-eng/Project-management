---
apdl: "PERTURB"
method: perturb
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.perturb
generated: 2026-08-22
tags: [mapdl-command]
---

# PERTURB

PyMAPDL: `mapdl.perturb(type_='', matkey='', contkey='', loadcontrol='', **kwargs)`

Sets linear perturbation analysis options.

**Command default:**

Linear perturbation analysis is disabled ( `Type` = OFF) by default. When the linear perturbation analysis is enabled, linear material property behavior is assumed for stress calculations; contact status for all contact pairs from the point of restart is used by default; and all loads and constraints from the restart step are deleted, except for displacement constraints and inertia loads, by default.

## Parameters

**type_**

Type of linear perturbation analysis to be performed:

- `STATIC` - Perform a linear perturbation static analysis.
- `MODAL` - Perform a linear perturbation modal analysis.
- `BUCKLE` - Perform a linear perturbation eigenvalue buckling analysis.
- `HARMONIC` - Perform a linear perturbation full harmonic analysis.
- `SUBSTR` - Perform a linear perturbation substructure generation pass.
- `OFF` - Do not perform a linear perturbation analysis (default).

**matkey**

Key for specifying how the linear perturbation analysis uses material properties, valid for all structural elements except contact elements. For more information, see [Linear Perturbation Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thylinpert.html#anplpdown)

- `AUTO` - The program selects the material properties for the linear perturbation analysis automatically (default). The materials are handled in the following way:

  - For pure linear elastic materials used in the base analysis, the same properties are used in the linear perturbation analysis.
  - For hyperelastic materials used in the base analysis, the material properties are assumed to be linear elastic in the linear perturbation analysis. The material property data (or material Jacobian) is obtained based on the tangent of the hyperelastic material's constitutive law at the point where restart occurs.
  - For hyperviscoelastic materials used in the base analysis, the program uses the harmonic material formulation in perturbed full harmonic solutions.
  - For other nonlinear materials used in the base analysis, the material properties are assumed to be linear elastic in the linear perturbation analysis. The material data is the same as the linear portion of the nonlinear materials (that is, the parts defined via [[mp|MP]] commands).
  - For `COMBIN39`, the stiffness is that of the first segment of the force-deflection curve.

- `TANGENT` - Use the tangent (material Jacobian) on the material constitutive curve as the material property. The material property remains linear in the linear perturbation analysis and is obtained at the point of the base analysis where restart occurs. The materials are handled in the following way:

  - For pure linear elastic materials used in the base analysis, the same properties are used in the linear perturbation analysis. Because the material constitutive curve is linear, the tangent is the same as the base analysis.
  - For hyperelastic materials used in the base analysis, the program uses the same tangent as that used for `MatKey` = AUTO, and the results are therefore identical.
  - For hyperviscoelastic materials used in the base analysis, the program uses the harmonic material formulation in perturbed full harmonic solutions.
  - For other nonlinear materials used in the base analysis, the material properties are assumed to be linear elastic in the linear perturbation analysis. The material data is the same as the linear portion of the nonlinear materials (that is, the parts defined via [[mp|MP]] commands).

  The materials and properties typically differ from `Matkey` = AUTO, but it is possible the results  
  could be identical or very similar if a.) the material is elastoplastic rate-independent and is unloading (or has neutral loading) at the restart point, or b.) the material is rate-dependent, depending on the material properties and loading conditions.

  \* For `COMBIN39`, the stiffness is equal to the tangent of the current segment of the force-  
  deflection curve.

  \* In a modal restart solution that follows a linear perturbation modal analysis, the TANGENT option  
  is overridden by the AUTO option and linear material properties are used for stress calculations in the modal restart. See the discussion in the Notes for more information.

- `SPOFF` - Provide the same values as AUTO, but set the spin softening matrix to zero (ignoring the spin softening effect).

  The spin softening effect is excluded in all the linear perturbation analysis types except for linear perturbation buckling. Note that although the spin softening effect is excluded in linear perturbation analysis, it is still included in the base static or full transient analysis if [[nlgeom|NLGEOM]],ON is issued in the base analysis.

**contkey**

Key that controls contact status for the linear perturbation analysis. This key controls all contact elements ( `TARGE169`, `TARGE170`, `CONTA172`, `CONTA174`, `CONTA175`, `CONTA177`, and `CONTA178` ) globally for all contact pairs. Alternatively, contact status can be controlled locally per contact pair by using the [[cnkmod|CNKMOD]] command. Note that the contact status from the base analysis solution is always adjusted by the local contact controls specified by [[cnkmod|CNKMOD]] first and then modified by the global sticking or bonded control ( `ContKey` = STICKING or BONDED). The tables in the [Notes](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_PERTURB.html#) Notes section show how the contact status is adjusted by [[cnkmod|CNKMOD]] and/or the `ContKey` setting.

- `CURRENT` - Use the current contact status from the restart snapshot (default). If the previous run is nonlinear, then the nonlinear contact status at the point of restart is frozen and used throughout the linear perturbation analysis.
- `STICKING` - For frictional contact pairs (MU \> 0), use sticking contact (for example, MU\*KN for tangential contact stiffness) everywhere the contact state is closed (that is, status is sticking or sliding). This option only applies to contact pairs that are in contact and have a frictional coefficient MU greater than zero. Contact pairs without friction (MU = 0) and in a sliding state remain free to slide in the linear perturbation analysis.
- `BONDED` - Any contact pairs that are in the closed (sticking or sliding) state are moved to bonded (for example, KN for both normal and tangential contact stiffness). Contact pairs that have a status of far-field or near-field remain open.

**loadcontrol**

Key that controls how the load vector of {F<sub>perturbed</sub> } is calculated. This control is provided for convenience of load generation for linear perturbation analysis. In general, a new set of loads is required for a linear perturbation analysis. This key controls all mechanical loads; it does not affect non-mechanical loads. Non-mechanical loads (including thermal loads) are always kept (that is, not deleted).

- `ALLKEEP` - Keep all the boundary conditions (loads and constraints) from the end of the load step of the current restart point. This option is convenient for further load application and is useful for a linear perturbation analysis restarted from a previous linear analysis. For this option, {F<sub>end</sub> } is the total load vector at the end of the load step at the restart point.
- `INERKEEP` - Delete all loads and constraints from the restart step, except for displacement constraints and inertia loads (default). All displacement constraints and inertia loads are kept for convenience when performing the linear perturbation analysis. Note that nonzero and tabular displacement constraints can be considered as external loads; however, they are not deleted when using this option.
- `PARKEEP` - Delete all loads and constraints from the restart step, except for displacement constraints. All displacement constraints are kept for convenience when performing the linear perturbation analysis. Note that nonzero and tabular displacement constraints can be considered as external loads; however, they are not deleted when using this option.
- `DZEROKEEP` - Behaves the same as the PARKEEP option, except that all nonzero displacement constraints are set to zero upon the onset of linear perturbation.
- `NOKEEP` - Delete all the loads and constraints, including all displacement constraints. For this option, {F<sub>end</sub> } is zero unless non-mechanical loads (for example, thermal loads) are present.

## Notes

This command controls options relating to [linear perturbation analyses](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strlinpertother.html). It must be issued in the first phase of a linear perturbation analysis.

This command is also valid in PREP7.

A linear perturbation analysis consists of two phases (two [[solve|SOLVE]] commands). The first phase is a restart from a base analysis. This base analysis must be a linear or nonlinear static analysis or full transient analysis. The first phase starts with the [[antype|ANTYPE]],,RESTART,,,PERTURB command and ends with the [[solve|SOLVE]],ELFORM command. The purpose of the first phase is to re- establish a snapshot of the stiffness matrices at the specified restart point. The second phase, ending with the second [[solve|SOLVE]] command, is for the actual linear perturbation analysis.

The total perturbed loads are calculated as follows:

{F<sub>perturbed</sub> } = {F<sub>end</sub> } + {F<sub>add</sub> }

where:

- {F <sub>end</sub> } = total loads at the end of the load step of the current restart point (load applications are read from the `.LDHI` file). By default, all of the loads in {F <sub>end</sub> } are deleted except for displacement boundary conditions and inertia loads (see the description of `LoadControl` above).
- {F <sub>add</sub> } = Additional (new) loads prescribed by the user in the second phase of the linear perturbation analysis (after the first [[solve|SOLVE]] command is invoked).

In the first phase of a linear perturbation analysis, the [[antype|ANTYPE]],,RESTART command resumes the `Jobname.RDB` database and reads in the `.LDHI` file to establish the {F<sub>end</sub> } load. New load application (adding to {F<sub>add</sub> }) or load removal (changing {F<sub>end</sub> }) can be done only in the second phase of the linear perturbation analysis (after the first [[solve|SOLVE]] command), allowing flexibility in controlling the final {F<sub>perturbed</sub> } to be used.

For `Type` = STATIC, {F<sub>perturbed</sub> } is the actual external load for the static analysis.

For `Type` = MODAL, {F<sub>perturbed</sub> } is calculated and stored in the `.FULL` and `.MODE` files for a subsequent mode-superposition, PSD, or other type of modal-based linear dynamic analysis. Linear dynamic options such as multiple load generations ( [[modcont|MODCONT]],ON), enforced motion ( [[modcont|MODCONT]],,ON), and residual vector methods ( [[resvec|RESVEC]],ON) can be used in a linear perturbation analysis. For these methods, the [[modcont|MODCONT]] or [[resvec|RESVEC]] command must be invoked in the second phase (after the first [[solve|SOLVE]] ) of the linear perturbation procedure. For the enforced motion method, the base identification number should be specified ( [[d|D]] command) in the second phase of the linear perturbation analysis. This base identification number is used later in the downstream mode-superposition or other mode-superposition based analysis.

For `Type` = BUCKLE, {F<sub>perturbed</sub> } is the actual linear buckling load which is used to generate the linear stress stiffening matrix for the buckling analysis.

For `Type` = HARMONIC, {F<sub>perturbed</sub> } is the actual external load for the full harmonic analysis. In this case, {F<sub>perturbed</sub> } can be frequency dependent and can use complex input.

For `Type` = SUBSTR, {F<sub>perturbed</sub> } is used to generate the first reduced external load vector of the substructure.

In most cases involving linear perturbation analysis, `Matkey` = AUTO is the best option for controlling material behavior. `Matkey` = TANGENT is often the better option, however, in special cases such as the following:

- A linear perturbation buckling analysis, to introduce preferred buckling modes into a subsequent post-buckling nonlinear analysis.
- A linear perturbation modal analysis, to introduce preferred modes into a subsequent bifurcation analysis.

If the TANGENT option is used in conjunction with a modal restart solution that follows a linear perturbation modal analysis, then the AUTO option is assumed and linear material properties are used for stress calculations in the modal restart solution. This occurs because the TANGENT material properties are not available during the modal restart phase due to a data architecture limitation. Furthermore, linear material properties are used for the stress calculation in any downstream analysis that uses the modal restart solution.

For more information about the automatic and tangent options, see in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html).

You can control the contact status for the linear perturbation analysis by using the `ContKey` field on this command and/or the [[cnkmod|CNKMOD]] command. The first table shows the effects of using only the `ContKey` setting on the **PERTURB** command. The second table shows the effects of using both the [[cnkmod|CNKMOD]] command and the `ContKey` setting on **PERTURB**.

### Adjusted Contact Status when PERTURB Command Is Issued

|  |  |  |
|----|----|----|
| **Contact Status from the Base Analysis Solution at the Restart Point** | **ContKeySetting on PERTURB Command** |  |
|  | `ContKey` Value | Adjusted Contact Status |
| 0 - far-field | any | 0 - far-field |
| 1 - near-field | any | 1 - near-field |
| 2 - sliding | CURRENT or STICKING (mu=0) | 2 - sliding |
|  | STICKING (mu\>0) or BONDED | 3 - sticking |
| 3 - sticking | any | 3 - sticking |

### Adjusted Contact Status when Both CNKMOD and PERTURB Are Issued

|  |  |  |  |  |
|----|----|----|----|----|
| **Contact Status from the Base Analysis Solution at the Restart Point** | *\*CNKMOD,*\* `ITYPE` ,12, `Value` | **ContKeySetting on PERTURB Command** |  |  |
|  | KEYOPT(12) Value | Adjusted Contact Status | `ContKey` Value | Final Adjusted Contact Status |
| 0 - far-field | any | 0 - far-field | any | 0 - far-field |
| 1 - near-field | 0, 1, 2, 3, 6 | 1 - near-field | any | 1 - near-field |
|  | 4 | 1 - near-field (if outside of the adjusted pinball region) | any | 1 - near-field |
|  |  | 2 - sliding (if inside of the adjusted pinball region) | CURRENT or STICKING (mu=0) | 2 - sliding |
|  |  |  | STICKING (mu\>0) or BONDED | 3 - sticking |
|  | 5 | 1 - near-field (if outside of the adjusted pinball region) | any | 1 - near-field |
|  |  | 3 - sticking (if inside of the adjusted pinball region) | any | 3 - sticking |
| 2 - sliding | 0, 2, 4 | 2 - sliding | CURRENT or STICKING (mu=0) | 2 - sliding |
|  |  |  | STICKING (mu\>0) or BONDED | 3 - sticking |
|  | 1, 3, 5, 6 | 3 - sticking | any | 3 - sticking |
| 3 - sticking | any | 3 - sticking | any | 3 - sticking |

When `ContKey` is set to CURRENT, all contact related parameters (such as normal stiffness and tangential stiffness) will remain unchanged throughout the linear perturbation analysis. However when `ContKey` is set to STICKING or BONDED, the program will re-evaluate the contact normal and tangential stiffness in order to perform the linear perturbation analysis based on the actual sticking behavior regardless of the friction coefficient value.

Note that the [[cnkmod|CNKMOD]] command allows you to take points in the base analysis that are near contact (within the pinball region) and modify them to be treated as "in contact" in the linear perturbation analysis; see the "1 - near-field" row in the above table with KEYOPT(12) values set to 4 or 5. [[cnkmod|CNKMOD]] also allows you to take points that are sliding in the base analysis and treat them as sticking in the linear perturbation analysis, irrespective of the MU value; see the "2 - sliding" row in the above table with KEYOPT(12) values set to 1,5, or 6.

If an open gap exists at the restart point of the base static/transient solution and the contact status is adjusted as sliding or sticking due to a “bonded” or “no separation” contact behavior definition, then the program will treat it as near-field contact when executing the [[cnkmod|CNKMOD]] command in a downstream linear perturbation analysis.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PERTURB.html
