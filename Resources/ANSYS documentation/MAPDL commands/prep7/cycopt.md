---
apdl: "CYCOPT"
method: cycopt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.special_purpose.SpecialPurpose.cycopt
generated: 2026-08-22
tags: [mapdl-command]
---

# CYCOPT

PyMAPDL: `mapdl.cycopt(option='', value1='', value2='', value3='', value4='', value5='', value6='', value7='', **kwargs)`

Specifies solution options for a cyclic symmetry analysis.

## Parameters

**option**

Cyclic symmetry analysis option. There is no default. You must choose o ne of the following options:

- `BCMULT` - Controls whether cyclic sector array parameter names are reused or created new for multiple entities.

  - `Value1` - The flag value.
    - `0 (OFF or NO)` - Create new array parameter names (default)
    - `1(ON or YES)` - Reuse array parameter names

- `COMBINE` - For linear [static cyclic symmetry analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycstaticans.html#cycsym_postproc_stat) with [non-cyclically symmetric loading](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycsolarch.html#) only, expands and combines all harmonic index solutions and writes them to the results file during the solution phase of the analysis.

  - `Value1` - The flag value.
    - `0 (OFF or NO)` - Disable combining of harmonic index solutions (default)
    - `1 (ON or YES)` - Enable combining of harmonic index solutions

- `DEFAULT` - Set the default cyclic solution settings.

- `DOF` - The degrees of freedom to couple from the nodes on the low sector boundary to nodes on the high boundary:

  - `Value1` - The component pair ID number.
  - `Value2, Value3, Value4, ..., Value7` - The constraint-equation/-coupling degree of freedom (DOF) for this pair. Repeat the command to add other DOFs. The default is constraint- equation/-coupling all applicable DOFs.

- `FACETOL` - Tolerance for inclusion of surface nodes into your base sector. Autodetect defaults to 15°, accommodating most sections. Specify a new `Value1` only when extreme cut angles or complex model geometry cause surface nodes to be excluded. See Notes (below) for more information.

  Ansys, Inc. recommends that successful auto-detection depends more on the value of ANGTOL than the value of FACETOL. Please refer to [CYCOPTAuto Detection Tolerance Adjustments for Difficult Cases](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycedgecomp.html#gadvcycopttol7) **CYCOPT** command.

  - `Value1` - The face tolerance applies only to auto detection from node/element models (already meshed and no solid model), and it defaults to 15°.

- `HINDEX` - The [harmonic index](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycmodalans.html#harmindex) ranges to be solved. Applies to static and harmonic analyses only if `Value5` = STATIC.

  By default, the [[solve|SOLVE]] command loops through all available harmonic indices. [Static](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycstaticans.html#cycsym_postproc_stat) and [harmonic](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycmodalans.html#harmindex) analyses only solve harmonic indices required for the applied loads. All other analyses solve them all.

  - `EVEN / ODD` - For low-frequency electromagnetic analysis only, EVEN specifies a symmetric solution and ODD specifies an antisymmetric solution.

    The value you specify is based on the [harmonic index](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycmodalans.html#harmindex) : EVEN (default) indicates harmonic index = 0, and ODD indicates harmonic index = `N` / 2 (where `N` is an integer representing the number of sectors in 360°). A value of ODD applies only when `N` is an even number.

    The **CYCOPT** command with this HINDEX option is cumulative. To remove an option (for example, EVEN), issue this command: **CYCOPT**,HINDEX,EVEN,,,-1

  - `ALL` - Solve all applicable harmonic indices. `Value2` must be blank.

  - `Value1, Value2, Value3` - Solve harmonic indices in range `Value1` through `Value2` in steps of `Value3`. Repeat the command to add other ranges. The default solves all applicable harmonic indices.

  - `Value4` - The only valid value is -1. If specified, it removes `Value1` through `Value2` in steps of `Value3` from the set to solve. By default, if `Value4` = -1 then `Value1` = 0, `Value2` = 0, and `Value3` = 1.

  - `Value5` - For [static](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycstaticans.html#cycsym_postproc_stat) and [harmonic](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycmodalans.html#harmindex) analyses, enter either a number or STATIC:

    If `Value5` = \<number\> the number entered sets the tolerance for determining if the Fourier contribution of a load is significant (default = 1.0E-5). In this case, the harmonic index selection is disabled.

    If `Value5` = STATIC the harmonic index selection is enabled, and no verification is done on the significance of unselected harmonic indicies. Improper selection of the harmonic index range may produce incomplete (incorrect) results.

- `LDSECT` - Restricts subsequently defined force loads and surface loads to a specified sector. The restriction remains in effect until you change or reset it. This option is not available for harmonic analyses based on mode-superposition ( **CYCOPT**,MSUP,1)

  - `Value1` - The sector number. A value other than 0 (default) is valid for a cyclic symmetry analysis with [non- cyclically symmetric loading](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycsolarch.html#) only. A value of 0 (or ALL) resets the default behavior for cyclic loading (where the loads are identical on all sectors).

- `MOVE` - Specifies if the program should move high- or low-edge component nodes paired within the specified tolerance (TOLER) to create precisely matching pairs.

  - `Value1` - The flag value.
    - `0` - Do not move edge component nodes (default)
    - `1 or HIGH` - Move the high-edge component nodes to precisely match the low-edge component nodes
    - `-1 or LOW` - Move the low-edge component nodes to precisely match the high-edge component nodes

- `MSUP` - This flag is used to limit the results written to the `Jobname.MODE` and `Jobname.RST` files in a modal cyclic symmetry analysis. In a linear perturbation analysis, the modal analysis and the first load step of the preceding base analysis must be set to the same value.

  - `Value1` - The flag value.
    - `0 (OFF or NO)` - Write results for the base and duplicate sectors to the `Jobname.MODE` and `Jobname.RST` files.
    - `1 (ON or YES)` - Write only the base sector results to the `Jobname.MODE` and `Jobname.RST` files for use in a subsequent mode-superposition-based analysis. Default, except for cyclic unsymmetric modal, LANPCG, and SNODE solutions, which use `Value1` = 0 as the default. This option is not valid for cyclic unsymmetric modal, LANPCG, and SNODE solutions.

- `STATUS` - List the solution option settings active for the cyclic model.

- `TOLER` - The tolerance used to determine whether a node on the low edge is paired with a node on the high edge.

  - `Value1` - The tolerance value.

    - `Greater than 0` - The absolute distance tolerance for automatic sector-boundary detection and low-/high-edge component node pairing
    - `Less than 0` - The relative tolerance for automatic sector-boundary detection and low-/high-edge component node pairing. In this case, the tolerance is `Value1` \* `Length`, where `Length` is the length of the diagonal of an imaginary box enclosing the model
    - `0` - Tolerance is set to -1.0 x 10 <sup>-4</sup> (default)

  - `Value2` - `ANGTOL` = Maximum allowable angle tolerance. (default = 0.01°)

    The valid range for `ANGTOL` is model dependent.

    If you input both the number of sectors and a sector angle, the angle must match 360/(number of sectors) within `ANGTOL`.

    If you input only a sector angle, it must divide evenly into 360° within `ANGTOL`.

    If you input a sector angle, the final cyclic sector must span that angle within `ANGTOL`.

    For auto detected sector angle, the final cyclic sector must span 360/(number of sectors) within `ANGTOL`, everywhere along the LOW/HIGH boundaries.

    If `ANGTOL` is too small, your CAD or FEA model may not be accurate enough to allow auto detection or verification.

    If `ANGTOL` is too large, you may get an unexpected or incorrect boundary definition, or in other cases fail to detect the boundaries.

    For some difficult cases from FEA models (not solid models), you may need to change the value of `FACETOL` to achieve auto detection. Please refer to [CYCOPTAuto Detection Tolerance Adjustments for Difficult Cases](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycedgecomp.html#gadvcycopttol7) **CYCOPT** command.

- `USRROT` - Flag specifying whether the program should override automatic nodal rotations to edge components and allow you to apply nodal rotations manually.

  - `Value1` - The flag value.
    - `0 (OFF or NO)` - Allow automatic node rotation (default)
    - `1 (ON or YES)` - Suppress automatic node rotation. If you select this option, you must apply appropriate nodal rotations to all edge component nodes; otherwise, your analysis will yield incorrect solution results.
    - `LOW` - Suppresses automatic rotation of low-edge component nodes only, allowing you to apply them manually. Automatic rotation of high-edge component nodes occurs to produce the matching edge nodes required for a valid cyclic solution.
    - `HIGH` - Suppresses automatic rotation of high-edge component nodes only, allowing you to apply them manually. Automatic rotation of low-edge component nodes occurs to produce the matching edge nodes required for a valid cyclic solution.

**value1**, **value2**, **value3**, **value4**, **value5**, **value6**, **value7**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CYCOPT.html) for further information.

## Notes

The program solves a cyclically symmetric model (set up via the [[cyclic|CYCLIC]] command during preprocessing) at the harmonic indices specified via the **CYCOPT** command.

The **CYCOPT**,COMBINE option is an alternative to the [[cycexpand|/CYCEXPAND]] command and is especially useful for testing purposes. However, Ansys, Inc. recommends specifying COMBINE only when the number of sectors is relatively small. (The option expands nodes and elements into the full 360° and can slow postprocessing significantly.

If you issue a **CYCOPT**,TOLER command to set a tolerance for [edge-component](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycedgecomp.html#) pairing before issuing the [[cyclic|CYCLIC]] command, the [[cyclic|CYCLIC]] command uses the specified tolerance when performing automatic edge-component detection.

In cases involving [non-cyclically symmetric loading](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycsolarch.html#) (that is, when LDSECT \> 0), the underlying command operations create or modify the required SECTOR tabular boundary condition (BC) data to apply on the appropriate sector. Therefore, it is not necessary to manipulate tables for situations where the applied BC is not a function of other tabular BC variables such as TIME, X, Y, Z, and so on.

To delete a previously applied load on a specified sector, issue an [[fdele|FDELE]] command.

Because edge nodes are rotated into the cyclic coordinate system during solution, any applied displacements or forces on sector edges will be in the cyclic coordinate system.

The **CYCOPT** command is valid in the preprocessing and solution stages of an analysis.

To learn more about analyzing a cyclically symmetric structure, see the [Cyclic Symmetry Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/cycsym_example.html).

Distributed-Memory Parallel (DMP) Restriction The COMBINE option is not supported in a DMP solution.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CYCOPT.html
