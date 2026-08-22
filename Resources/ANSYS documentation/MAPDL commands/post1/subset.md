---
apdl: "SUBSET"
method: subset
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.set_up.SetUp.subset
generated: 2026-08-22
tags: [mapdl-command]
---

# SUBSET

PyMAPDL: `mapdl.subset(lstep='', sbstep='', fact='', kimg='', time='', angle='', nset='', **kwargs)`

Reads results for the selected portions of the model.

## Parameters

**lstep**

Load step number of the data set to be read (defaults to 1):

- `N` - Read load step `N`.
- `FIRST` - Read the first data set ( `SBSTEP` and `TIME` are ignored).
- `LAST` - Read the last data set ( `SBSTEP` and `TIME` are ignored).
- `NEXT` - Read the next data set ( `SBSTEP` and `TIME` are ignored). If at the last data set, the first data set will be read as the next.
- `NEAR` - Read the data set nearest to `TIME` ( `SBSTEP` is ignored). If `TIME` is blank, read the first data set.
- `LIST` - Scan the results file and list a summary of each load step. ( `FACT`, `KIMG`, `TIME` and `ANGLE` are ignored.)

**sbstep**: Substep number (within `Lstep` ). For the buckling ( [[antype|ANTYPE]],BUCKLE) analysis or the modal ( [[antype|ANTYPE]],MODAL) analysis, the substep corresponds to the mode number. Defaults to last substep of load step (except for [[antype|ANTYPE]],BUCKLE or MODAL). If `Lstep` = LIST, `SBSTEP` = 0 or 1 lists the basic step information, whereas `SBSTEP` = 2 also lists the load step title, and labels imaginary data sets if they exist.

**fact**: Scale factor applied to data read from the file. If zero (or blank), a value of 1.0 is used. Harmonic velocities or accelerations may be calculated from the displacement results from a modal ( [[antype|ANTYPE]],MODAL) or harmonic ( [[antype|ANTYPE]],HARMIC) analyses. If `FACT` = VELO, the harmonic velocities (v) are calculated from the displacements (d) at a particular frequency (f) according to the relationship v = 2 πfd. Similarly, if `FACT` = ACEL, the harmonic accelerations (a) are calculated as a = (2 πf) <sup>2</sup> d.

**kimg**

Used only with results from complex analyses:

- `0` - Store real part of complex solution
- `1` - Store imaginary part.

**time**: Time-point identifying the data set to be read. For harmonic analyses, time corresponds to the frequency. For the buckling analysis, time corresponds to the load factor. Used only in the following cases: If `Lstep` is NEAR, read the data set nearest to `TIME`. If both `Lstep` and `SBSTEP` are zero (or blank), read data set at time = `TIME`. If `TIME` is between two solution time points on the results file, a linear interpolation is done between the two data sets. Solution items not written to the results file ( [[outres|OUTRES]] ) for either data set will result in a null item after data set interpolation. If `TIME` is beyond the last time point on the file, use the last time point.

**angle**: Circumferential location (0.0 to 360°). Defines the circumferential location for the harmonic calculations used when reading from the results file. The harmonic factor (based on the circumferential angle) is applied to the harmonic elements ( `PLANE25`, `PLANE75`, `PLANE78`, `PLANE83`, and `SHELL61` ) of the load case. See the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html) for details. Note that factored values of applied constraints and loads will overwrite any values existing in the database.

**nset**: Data set number of the data set to be read. If a positive value for `NSET` is entered, `Lstep`, `SBSTEP`, `KIMG`, and `TIME` are ignored. Available set numbers can be determined by [[set|SET]],LIST.

## Notes

Reads a data set from the results file into the database for the selected portions of the model only. Data that has not been specified for retrieval from the results file by the [[inres|INRES]] command will be listed as having a zero value. Each time that the **SUBSET** command is issued, the data currently in the database will be overwritten with a new set of data. Various operations may also be performed during the read operation. The database must have the model geometry available (or used the [[resume|RESUME]] command before the **SUBSET** command to restore the geometry from `File.DB` ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SUBSET.html
