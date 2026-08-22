---
apdl: "APPEND"
method: append
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.set_up.SetUp.append
generated: 2026-08-22
tags: [mapdl-command]
---

# APPEND

PyMAPDL: `mapdl.append(lstep='', sbstep='', fact='', kimg='', time='', angle='', nset='', **kwargs)`

Reads data from the results file and appends it to the database.

## Parameters

**lstep**: Load step number of the data set to be read. Defaults to 1. If FIRST, ignore `SBSTEP` and `TIME` and read the first data set. If LAST, ignore `SBSTEP` and `TIME` and read the last data set. If NEXT, ignore `SBSTEP` and `TIME` and read the next data set. If already at the last data set, the next set is the first data set. If NEAR, ignore `SBSTEP` and read the data set nearest to `TIME`. If `TIME` is blank, read the first data set. If LIST, scan the results file to produce a summary of each load step ( `FACT`, `KIMG`, `TIME` and `ANGLE` are ignored).

**sbstep**: Substep number (within `LSTEP` ) (defaults to last substep of load step). For the Buckling ( [[antype|ANTYPE]],BUCKLE) or Modal ( [[antype|ANTYPE]],MODAL) analysis, the substep corresponds to the mode number (defaults to first mode). If `LSTEP` = LIST, `SBSTEP` = 0 or 1 will list the basic load step information; `SBSTEP` = 2 will also list the load step title, and label the imaginary data sets if they exist.

**fact**: Scale factor applied to data read from the file. If zero (or blank), a value of 1.0 is used. Harmonic velocities or accelerations may be calculated from the displacement results from a modal or harmonic ( [[antype|ANTYPE]],HARMIC) analyses. If `FACT` = VELO, the harmonic velocities (v) are calculated from the displacements (d) at a particular frequency (f) according to the relationship v = 2 πfd. Similarly, if `FACT` = ACEL, the harmonic accelerations (a) are calculated as a = (2 πf) <sup>2</sup> d.

**kimg**

Used only with results from complex analyses:

- `0` - Store real part of complex solution.
- `1` - Store imaginary part.

**time**: Time-point identifying the data set to be read. For harmonic analyses, time corresponds to the frequency. For the buckling analysis, time corresponds to the load factor. Used only in the following cases: If `LSTEP` is NEAR, read the data set nearest to `TIME`. If both `LSTEP` and `SBSTEP` are zero (or blank), read data set at time = `TIME`. If `TIME` is between two solution time points on the results file, a linear interpolation is done between the two data sets. Solution items not written to the results file ( [[outres|OUTRES]] ) for either data set will result in a null item after data set interpolation. If `TIME` is beyond the last time point on the file, the last time point is used.

**angle**: Circumferential location (0° to 360°). Defines the circumferential location for the harmonic calculations used when reading from the results file. The harmonic factor (based on the circumferential angle) is applied to the harmonic elements ( `PLANE25`, `PLANE75`, `PLANE78`, `PLANE83`, and `SHELL61` ) of the load case. See the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html) for details. Note that factored values of applied constraints and loads will overwrite any values existing in the database.

**nset**: Data set number of the data set to be read. If a positive value for `NSET` is entered, `LSTEP`, `SBSTEP`, `KIMG`, and `TIME` are ignored. Available set numbers can be determined by **APPEND**,LIST. To determine if data sets are real or imaginary, issue **APPEND**,LIST,2 which labels imaginary data sets.

## Notes

Reads a data set from the results file and appends it to the existing data in the database for the selected model only. The existing database is not cleared (or overwritten in total), allowing the requested results data to be merged into the database. Various operations may also be performed during the read operation. The database must have the model geometry available (or used the [[resume|RESUME]] command before the **APPEND** command to restore the geometry from `File.DB` ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_APPEND.html
