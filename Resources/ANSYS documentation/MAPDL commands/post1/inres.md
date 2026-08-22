---
apdl: "INRES"
method: inres
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.controls.Controls.inres
generated: 2026-08-22
tags: [mapdl-command]
---

# INRES

PyMAPDL: `mapdl.inres(item1='', item2='', item3='', item4='', item5='', item6='', item7='', item8='', **kwargs)`

Identifies the data to be retrieved from the results file.

## Parameters

**item1**, **item2**, **item3**, **item4**, **item5**, **item6**, **item7**, **item8**

Data to be read into the database from the results file. May consist of any of the following labels:

- `ALL` - All solution items (default).
- `BASIC` - NSOL, RSOL, NLOAD, STRS, FGRAD, and FFLUX items.
- `NSOL` - Nodal DOF solution.
- `RSOL` - Nodal reaction loads.
- `ESOL` - Element solution items (includes all of the following):
  - `NLOAD` - Element nodal loads.
  - `STRS` - Element nodal stresses.
  - `EPEL` - Element elastic strains.
  - `EPTH` - Element thermal, initial, and swelling strains.
  - `EPPL` - Element plastic strains.
  - `EPCR` - Element creep strains.
  - `FGRAD` - Element nodal gradients.
  - `FFLUX` - Element nodal fluxes.
  - `MISC` - Element miscellaneous data (SMISC and NMISC).
- `NAR` - [Nodal-averaged result](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) items (includes all of the following):
  - `NDST` - Nodal-averaged stresses.
  - `NDEL` - Nodal-averaged elastic strains.
  - `NDPL` - Nodal-averaged plastic strains.
  - `NDCR` - Nodal-averaged creep strains.
  - `NDTH` - Nodal-averaged thermal and swelling strains.

## Notes

Identifies the type of data to be retrieved from the results file for placement into the database through commands such as [[set|SET]], [[subset|SUBSET]], and [[append|APPEND]]. **INRES** is a companion command to the [[outres|OUTRES]] command controlling data written to the database and the results file. Since the **INRES** command can only flag data that has already been written to the results file, care should be taken when using the [[outres|OUTRES]] command to include all data you wish to retrieve for postprocessing later on.

The `Item` = ALL option includes all NAR items. For more information, see [Nodal-Averaged Results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_INRES.html
