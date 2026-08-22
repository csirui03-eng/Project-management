---
apdl: "RESCOMBINE"
method: rescombine
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.set_up.SetUp.rescombine
generated: 2026-08-22
tags: [mapdl-command]
---

# RESCOMBINE

PyMAPDL: `mapdl.rescombine(numfiles='', fname='', ext='', lstep='', sbstep='', fact='', kimg='', time='', angle='', nset='', order='', **kwargs)`

Reads results from local results files into the database after a distributed-memory parallel solution.

## Parameters

**numfiles**: Number of local results files that are to be read into the database from the distributed-memory parallel solution. This number should be equal to the number of processes used in the parallel solution.

**fname**: File name (jobname) used during the distributed parallel solution. The file name must be an alphanumeric string (up to 32 characters) enclosed in single quotes.

**ext**: File extension for the results files (for example, RST, RTH, RMG, etc.). The file extension must be an alphanumeric string (up to 8 characters) enclosed in single quotes.

**lstep**

Load step number of the data set to be read (defaults to 1):

- `N` - Read load step `N`.
- `FIRST` - Read the first data set ( `Sbstep` and `TIME` are ignored).
- `LAST` - Read the last data set ( `Sbstep` and `TIME` are ignored).
- `NEXT` - Read the next data set ( `Sbstep` and `TIME` are ignored). If at the last data set, the first data set will be read as the next.
- `PREVIOUS` - Read the previous data set ( `Sbstep` and `TIME` are ignored). If at the first data set, the last data set will be read as the previous.
- `NEAR` - Read the data set nearest to `TIME` ( `Sbstep` is ignored). If `TIME` is blank, read the first data set.
- `LIST` - Scan the results files and list a summary of each load step ( `KIMG`, `TIME`, `ANGLE`, `NSET`, and `ORDER` are ignored.)

**sbstep**

Substep number within `Lstep` (defaults to the last substep of the load step). For a buckling ( [[antype|ANTYPE]],BUCKLE) or modal ( [[antype|ANTYPE]],MODAL) analysis, `Sbstep` corresponds to the mode number (defaults to the first mode). Specify `Sbstep` = LAST to store the last substep for the specified load step.

If `Lstep` = LIST, `Sbstep` = 0 or 1 lists the basic step information; `Sbstep` = 2 also lists the basic step information, but includes the load step title, and labels imaginary data sets if they exist.

**fact**: Scale factor applied to data read from the files. If zero (or blank), a value of 1.0 is used. A nonzero factor excludes non-summable items. Harmonic velocities or accelerations may be calculated from the displacement results from a modal ( [[antype|ANTYPE]],MODAL) or harmonic ( [[antype|ANTYPE]],HARMIC) analysis. If `Fact` = VELO, the harmonic velocities (v) are calculated from the displacements (d) at a particular frequency (f) according to the relationship v = 2πfd. Similarly, if `Fact` = ACEL, the harmonic accelerations (a) are calculated as a = (2πf) <sup>2</sup> d.

**kimg**

Used only with complex results (harmonic and complex modal analyses).

- `0 or REAL` - Store the real part of a complex solution (default).
- `1, 2 or IMAG` - Store the imaginary part of a complex solution.

**time**: Time-point identifying the data set to be read. For a harmonic analysis, time corresponds to the frequency. For a buckling analysis, time corresponds to the load factor. Used only in the following cases: If `Lstep` = NEAR, read the data set nearest to `TIME`. If both `Lstep` and `Sbstep` are zero (or blank), read data set at time = `TIME`. If `TIME` is between two solution time points on the results file, a linear interpolation is done between the two data sets. Solution items not written to the results file ( [[outres|OUTRES]] ) for either data set will result in a null item after data set interpolation. If `TIME` is beyond the last time point on the file, the last time point will be used.

**angle**: Circumferential location (0.0 to 360°). Defines the circumferential location for the harmonic calculations used when reading from the results file. The harmonic factor (based on the circumferential angle) is applied to the harmonic elements ( `PLANE25`, `PLANE75`, `PLANE78`, `PLANE83`, and `SHELL61` ) of the load case. See the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html) for details. Note that factored values of applied constraints and loads will overwrite any values existing in the database.

**nset**: Data set number of the data set to be read. If a positive value for `NSET` is entered, `Lstep`, `Sbstep`, `KIMG`, and `TIME` are ignored. Available set numbers can be determined by **RESCOMBINE**,,,,LIST.

**order**

Key to sort the harmonic index results. This option applies to [cyclic symmetry](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/cycsym_example.html) buckling and modal analyses only, and is valid only when `Lstep` = FIRST, LAST, NEXT, PREVIOUS, NEAR or LIST.

- `ORDER` - Sort the harmonic index results in ascending order of eigenfrequencies or buckling load multipliers.
- `(blank)` - No sorting takes place.

## Notes

**RESCOMBINE** is a Mechanical APDL command macro enabling you to combine results from a distributed- memory parallel ( DMP ) solution. A character string input for any argument must be enclosed in single quotes (for example, 'FIRST' input for `Lstep` ).

In a distributed memory parallel solution, a global results file is saved by default. However, if you issued [[dmpoption|DMPOPTION]],RST,NO in the parallel solution, no global results file is written and all local results files will be kept. In this case, you can use **RESCOMBINE** in the general postprocessor ( [[post1|/POST1]] ) to read results into the database for postprocessing.

**RESCOMBINE** cannot be used to combine results from local files generated during a distributed- memory parallel solution that used the frequency or cyclic harmonic index domain decomposition method ( [[ddoption|DDOPTION]],FREQ or [[ddoption|DDOPTION]],CYCHI).

To use **RESCOMBINE**, all local results files from the distributed-memory parallel solution must be in the current working directory. If running on a single machine, the local results files are saved in the working directory by default. If running on a cluster, the local results files are kept in the working directory on each compute node. For the latter case, copy the local results files to the working directory on the primary compute node.

Similar to [[set|SET]], **RESCOMBINE** defines the data set to be read from the results files into the database. Various operations can also be performed during the read operation. (See [[set|SET]] for more information.) The database must have the model data available (or issue [[resume|RESUME]] before **RESCOMBINE** to restore the geometry from `Jobname.DB` ).

After issuing **RESCOMBINE** to combine a set of data into the database, you can issue [[reswrite|RESWRITE]] to write the data set into a new results file. The new results file will essentially contain the current set of results data for the entire (that is, global) model.

Upon completion of a **RESCOMBINE** operation, the current file for postprocessing ( [[file|FILE]] ) is set to the last local results file specified via **RESCOMBINE**. For example, if reading in four local results files, the results file for POST1 is specified as `Jobname3.RST` when **RESCOMBINE** is complete. Therefore, be aware that some downstream postprocessing actions (such as [[set|SET]] ) may be operating on only this one local results file.

**RESCOMBINE** is intended for use in POST1. If you want to postprocess DMP solution results using the POST26 time-history postprocessor, combine your local results files into one global results file ( [[dmpoption|DMPOPTION]],RST,YES).

The load case commands in the general postprocessor (such as [[lcdef|LCDEF]], [[lcfile|LCFILE]], [[lcoper|LCOPER]], etc.) are not supported when using **RESCOMBINE**. Those commands set up pointers in the results file used for postprocessing; they cannot be used with the local results files used by **RESCOMBINE**.

[[cycexpand|/CYCEXPAND]], which performs a cyclic expansion, cannot be used with **RESCOMBINE**.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RESCOMBINE.html
