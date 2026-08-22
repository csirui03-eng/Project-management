---
apdl: "PRCINT"
method: prcint
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.prcint
generated: 2026-08-22
tags: [mapdl-command]
---

# PRCINT

PyMAPDL: `mapdl.prcint(id_='', node='', dtype='', **kwargs)`

Lists fracture parameter ( [[cint|CINT]] ) results data.

## Parameters

**id_**: Crack ID number.

**node**: Crack tip node number. Default = ALL. Valid only for 3D analysis.

**dtype**

Data type to output:

- `JINT` - J-integral

- `IIN1` - Interaction integral 1

- `IIN2` - Interaction integral 2

- `IIN3` - Interaction integral 3

- `K1` - Mode 1 stress-intensity factor

- `K2` - Mode 2 stress-intensity factor

- `K3` - Mode 3 stress-intensity factor

- `G1` - Mode 1 energy release rate

- `G2` - Mode 2 energy release rate

- `G3` - Mode 3 energy release rate

- `GT` - Total energy release rate

- `MFTX` - Total material force X

- `MFTY` - Total material force Y

- `MFTZ` - Total material force Z

- `TSTRESS` - T-stress

- `CEXT` - Crack extension

- `CSTAR` - C2-integral

- `STTMAX` - Maximum circumferential stress

- `PSMAX` - Maximum circumferential stress when (equation omitted)

- `DLTA` - Incremental crack extension in a [fatigue crack-growth analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracfcgxfem.html#fracfcgxfemexample)

- `DLTN` - Number of incremental cycles in a fatigue crack-growth analysis

- `DLTK` - Equivalent stress intensity factors in a fatigue crack-growth analysis

- `R` - Stress (load) ratio in a fatigue crack-growth analysis

- `UFAC` - U-factor (crack closure) in a fatigue crack-growth analysis

- `CRDX` - X coordinate of the crack tip

- `CRDY` - Y coordinate of the crack tip

- `CRDZ` - Z coordinate of the crack tip

- `APOS` - Position attribute of the crack-tip node:

  - `Positive integer` - The subcrack Subcracks typically appear in [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) crack-growth analyses and are uncommon in other types of fracture analyses.

    > ID number to which this tip belongs. For a crack with only a single subcrack, this value is 1.

  - `Negative integer` - The absolute value of the negative integer is the subcrack ID number to which this tip belongs.

    The negative sign indicates that this crack tip is the end of this subcrack, and that this subcrack is a closed polygon. It must be connected to the first tip of this subcrack when the crack front is plotted.

  For more information, see .

## Notes

**Examples: APOS Usage**

The following examples show how APOS values Issuing [[get|*GET]] is an effective way to obtain APOS values.

> are applied in several cases for fracture analysis.

The most common situation is that an open crack exists in `N` crack tips, and all tips are connected into a single subcrack. The APOS values for each tip are:

(table not available in the PyMAPDL source, see the Ansys help page)

For a closed crack without extra subcracks, the APOS values are:

(table not available in the PyMAPDL source, see the Ansys help page)

The following crack has two subcracks, the first open and the second closed. Assuming `M` tips on the first subcrack and `N` tips on the second, the APOS values are:

(table not available in the PyMAPDL source, see the Ansys help page)

When a crack tip node is defined, the values associated with the specified node are listed.

`Dtype` = STTMAX or PSMAX are valid for [phantom-node-based](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#fracxfemfig2) XFEM analyses only.

`Dtype` = CRDX, CRDY, CRDZ, and APOS are valid only in a fatigue/static crack-growth analysis using [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) or [singularity-based](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#fracxfemfig1) XFEM.

`Dtype` = DLTA, DLTN, DLTK, R are valid only in a [fatigue crack-growth analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#) using [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample) or [singularity-based](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#fracxfemfig1) XFEM.

`Dtype` = UFAC is valid only in a fatigue crack-growth analysis using [SMART](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/fracSMART.html#fracsmartexample).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRCINT.html
