---
apdl: "ASIFILE"
method: asifile
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.misc_loads.MiscLoads.asifile
generated: 2026-08-22
tags: [mapdl-command]
---

# ASIFILE

PyMAPDL: `mapdl.asifile(opt='', fname='', ext='', oper='', kdim='', kout='', limit='', resopt='', **kwargs)`

Writes or reads one-way acoustic-structural coupling data.

## Parameters

**opt**

Command behavior option:

- `WRITE` - Write the structural results to the specified file.
- `READ` - Read the structural results from the specified file. This option is invalid during [[post1|/POST1]] postprocessing.

**fname**: File name and directory path of a one-way acoustic-structural coupling data file (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name (defaults to `jobname` ).

**ext**: File name extension of the one-way acoustic-structural coupling data file (defaults to `.asi` ).

**oper**

Command operation:

- `NOMAP` - No mapping occurs between the structural and acoustic models when reading the structural results from the specified file (default).
- `MAP` - Maps the results from the structural to the acoustic model. (See [[asifile#Notes|ASIFILE]].)

**kdim**

Interpolation criteria. Valid only when `Oper` = MAP.

If `kDim` = 2 or 0, two-dimensional interpolation is applied (that is, interpolate occurs on a surface).

**kout**

Outside region results. Valid only when `Oper` = MAP.

If `kOut` = 0, use the value(s) of the nearest region point for points outside of the region.

If `kOut` = 1, set results extrapolated outside of the region to zero.

**limit**

Number of nearby nodes considered for interpolation. Valid only when `Oper` = MAP.

Minimum = 5. Default = 20.

Lower values reduce processing time; however, some distorted or irregular meshes require a higher value to encounter three nodes for triangulation.

**resopt**

Transient results option:

- `ACEL` - Output or input the particle acceleration in a transient analysis (default).
- `VELO` - Output or input the particle velocity in a transient analysis.

## Notes

The **ASIFILE** command writes to, or reads from, a file containing one-way acoustic-structural coupling data.

Results data on the one-way coupling interface (defined by the [[sf|SF]],,FSIN command) in the structural model are written to the one-way coupling result data file during the structural solution.

By default, one-way coupling results data are read into the acoustic model as the velocity (harmonic) or acceleration (transient) excitation during the sequential acoustic solution. If the transient is to be solved with the velocity potential formulation in acoustics, set `ResOpt` = VELO to write/read the results data as velocity excitation.

If `Oper` = NOMAP, both structural and acoustic models must share the same node number on the one- way coupling interface.

If `Oper` = MAP:

- The one-way coupling interface must be defined in the acoustic model ( [[sf|SF]],,FSIN) such that it corresponds to the field-surface interface number (FSIN) in the structural model.
- The output points are correct only if they are within the boundaries set via the specified input points.
- Calculations for out-of-bound points require much more processing time than do points that are within bounds.
- For each point in the acoustic destination mesh, the command searches all possible triangles in the structural source mesh to find the best triangle containing each point, then performs a linear interpolation inside this triangle. For faster and more accurate results, consider your interpolation method and search criteria carefully (see `LIMIT` ).

You can also write an `.asi` file during postprocessing of the structural model. In the POST1 postprocessor ( [[post1|/POST1]] ), issue the command **ASIFILE**,WRITE, `Fname`, `Ext` to output results on selected surface nodes of the structural model. In the subsequent acoustic analysis, apply the [[sf|SF]],,FSIN,1 command on the selected nodes of the acoustic model, and issue the **ASIFILE**,READ, `Fname`, `Ext` command to read the `.asi` file.

One-way coupling excitation can be applied to multiple frequencies or time steps.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ASIFILE.html
