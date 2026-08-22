---
apdl: "LDREAD"
method: ldread
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_constraints.FeConstraints.ldread
generated: 2026-08-22
tags: [mapdl-command]
---

# LDREAD

PyMAPDL: `mapdl.ldread(lab='', lstep='', sbstep='', time='', kimg='', fname='', ext='', **kwargs)`

Reads results from the results file and applies them as loads.

## Parameters

**lab**

Valid load label:

- `TEMP` - Temperatures from a thermal analysis are applied as body force nodal loads ( [[bf|BF]] ) in a structural analysis or other type of analysis.

  When used in conjunction with `KIMG` = 1 or `KIMG` = 2, temperatures can be applied to a subsequent thermal analysis as nodal loads ( [[d|D]] ) or initial conditions ( [[ic|IC]] ), respectively.

  See the [[ldread#Notes|LDREAD]] section for details on transferring temperatures from layered thermal shell elements ( `SHELL131`, `SHELL132` ) and layered thermal solid elements ( `SOLID278`, `SOLID279` ).

- `FORC` - Forces from an electromagnetic analysis are applied as force loads ( [[f|F]] ) in a structural analysis. **LDREAD**,FORC reads coupling forces. See the discussion on [force computation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_lof/Hlp_G_ELE6_5.html#emagreluctfig) in the [Low-Frequency Electromagnetic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_lof/Hlp_G_ELE16.html).

  For a full harmonic magnetic analysis, FORC represents the time-averaged force (use in conjunction with `KIMG` = 2). Values are in the nodal coordinate system for the force loads ( [[f|F]] ).

- `HGEN` - Heat generations from an electromagnetic analysis are applied as body-force loads ( [[bfe|BFE]] ) in a thermal analysis. For a full harmonic analysis, HGEN represents the time-averaged heat generation load (use in conjunction with `KIMG` = 2).

- `JS` - Source current density from a current-conduction analysis are applied as body-force loads ( [[bfe|BFE]] ). Values are in the global Cartesian coordinate system.

- `EF` - Electric field element centroid values from an electrostatic analysis are applied as body-force loads ( [[bfe|BFE]] ) in a magnetic analysis. Values are in the global Cartesian coordinate system.

- `REAC` - Reaction loads from any analysis are applied as force loads ( [[f|F]] ) in any analysis. Values are in the nodal coordinate system.

- `CONC` - Concentrations from a diffusion analysis are applied to a subsequent diffusion analysis as nodal loads ( [[d|D]] ) or initial conditions ( [[ic|IC]] ) when used in conjunction with `KIMG` =1 or `KIMG` =2, respectively.

- `VMEN` - Mean flow velocities from a static mean flow analysis are applied to a subsequent harmonic or modal solution of the convective wave equation as body-force loads ( [[bf|BF]] ).

- `VOLT` - Voltages from an electric, electrostatic, or electromagnetic analysis are applied to a subsequent electric, electrostatic, or electromagnetic analysis as nodal loads ( [[d|D]] ) when `KIMG` = 1 or as initial conditions ( [[ic|IC]] ) when `KIMG` = 2.

**lstep**: Load step number of the data set to be read. Defaults to 1. If LAST, ignore `SBSTEP` and `TIME` and read the last data set.

**sbstep**: Substep number (within `LSTEP` ). If zero (or blank), `LSTEP` represents the last substep of the load step.

**time**: Time-point identifying the data set to be read. Used only if both `LSTEP` and `SBSTEP` are zero (or blank). If `TIME` is between two solution time points on the results file, a linear interpolation is done between the two data sets. If `TIME` is beyond the last time point on the file, use the last time point.

**kimg**

When used with results from harmonic analyses ( [[antype|ANTYPE]],HARMIC) `KIMG` establishes which set of data to read:

- `0` - Read the real part of the solution. Valid also for `Lab` = EHFLU to read in time-average heat flux.
- `1` - Read the imaginary part of the solution.
- `2` - Calculate and read the time-average part. Meaningful for `Lab` = HGEN or FORC.

When used with the PRES label, `KIMG` represents the shell element face on which to apply the pressure:

- `1` - Apply pressure to face 1
- `2` - Apply pressure to face 2

When used with the TEMP label, `KIMG` indicates how temperatures are to be applied.

- `0` - Apply temperatures as body loads ( [[bf|BF]] )
- `1` - Apply temperatures as nodal loads ( [[d|D]] )
- `2` - Apply temperatures as initial conditions ( [[ic|IC]] )

When used with the CONC label, `KIMG` indicates how concentrations are to be applied.

- `1` - Apply concentrations as nodal loads ( [[d|D]] )
- `2` - Apply concentrations as initial conditions ( [[ic|IC]] )

When used with the VOLT label, `KIMG` indicates how voltages are to be applied.

- `1` - Apply voltages as nodal loads ( [[d|D]] )
- `2` - Apply voltages as initial conditions ( [[ic|IC]] )

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to RST (or RMF for a static mean flow analysis) if `Fname` is blank.

## Notes

The **LDREAD** command reads results data from the results file and applies them as loads.

The command can also apply results from an analysis defined with one physics environment as loads on a second analysis using a different physics environment. Results values are applied as loads for field-coupling effects (for example, output temperatures from a thermal analysis as input to a structural analysis).

The command works based on the assumption that the meshes have not changed.

Nodal loads are applied only to selected nodes. Element loads are applied only to selected elements. Element surface loads are applied only to selected elements where all face nodes for that surface are selected.

To assure proper distribution of the surface loads, select only the nodes on the element face where the surface load is to be applied.

Scaling and accumulation specifications are applied as the loads are read via the following commands:

- [[bfcum|BFCUM]] for body-force loads. (Heat-generation loads are not accumulated.)
- [[sfcum|SFCUM]] for surface loads.
- [[fcum|FCUM]] for force loads.

List the results via the appropriate list command:

- [[bflist|BFLIST]] or [[bfelist|BFELIST]] for body-force loads.
- [[sfelist|SFELIST]] for surface loads.
- [[flist|FLIST]] for force loads.

Values may be redefined after being read by issuing **LDREAD** again with a different load step and substep, or time value.

This command is also valid in PREP7.

**Transferring Temperature Output from SHELL131 and SHELL132**

If a thermal analysis uses `SHELL131` or `SHELL132` thermal shell elements, temperatures can be transferred as body force element loads ( [[bfe|BFE]] ). In most cases, only the top and bottom temperatures from `SHELL131` and `SHELL132` are used by the structural shell elements; any interior temperatures are ignored. However, all temperatures are used by `SHELL181` having section input, and `SHELL281` having section input; for these elements, therefore, the number of temperature points at a node generated in the thermal model must match the number of temperature points at a node needed by the structural model.

When using `SHELL131` or `SHELL132` information for the **LDREAD** operation, all element types should specify the same set of thermal degrees of freedom.

**Transferring Temperature Output from SOLID278 and SOLID279**

If a thermal analysis uses `SOLID278` or `SOLID279` thermal solid elements, the temperatures are available either at the nodes (KEYOPT(3) = 0) or at the nodes and layers (KEYOPT(3) = 1 or 2). Under normal circumstances, only the nodal temperatures are transferred to the structural elements.

However, if the structural elements are layered solids (KEYOPT(3) = 1 for `SOLSH190`, `SOLID185`, `SOLID186` ) and the thermal elements have KEYOPT(3) = 1 or 2 (layered solid) and KEYOPT(8) = 1 (store data for all layers), then the layer temperatures are transferred to the structural elements. If the number of layers do not match, the algorithm reverts back to nodal temperature transfer.

`KIMG` = 0 (body loads) is the only valid mode for layered temperature transfer.

**Examples** Thermal-Stress Example: Load Transfer Coupled-Field Analysis with One-way Coupling

Induction Heating Example: Load Transfer Coupled-Field Analysis with Two-way Coupling

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LDREAD.html
