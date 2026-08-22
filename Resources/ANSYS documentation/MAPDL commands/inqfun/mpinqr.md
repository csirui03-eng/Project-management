---
apdl: "MPINQR"
method: mpinqr
group: inqfun
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.inq_func.inq_function.mpinqr
generated: 2026-08-22
tags: [mapdl-command]
---

# MPINQR

PyMAPDL: `mapdl.mpinqr(mat, iprop, key, pname='__tmpvar__', **kwargs)`

Get information about a material property.

> [!WARNING]
> **DISCLAIMER**: This function is un-documented in the official ANSYS Command Reference Guide. Hence its support is limited and it use is not encouraged. **Please use it with caution.**

## Parameters

**mat**: Material number should be 0 for key=11, `DB_NUMDEFINED(12)`, `DB_MAXDEFINED(14)`, and `DB_MAXRECLENG(15)`.

**iprop**

Property reference number (See Table-1 in the Notes section).

If iprop = 0, test for existence of any material property with this material number (with key = `DB_SELECTED(1)`).

**key**

Key as to the information needed about material property.

- `DB_SELECTED(1)` - return select status:
  - 0 - material prop is undefined.
  - 1 - material prop is selected.
- `DB_NUMDEFINED(12)` - number of defined material properties
- `DB_MAXDEFINED(14)` - highest material property number defined
- `DB_MAXRECLENG(15)` - maximum record length (dp words)
- 2 - return length (dp words)
- 3 - return number of temp. values
- 11 - return void percent (integer)

**pname**: Name of the variable where the queried value is stored.

****kwargs**: Extra arguments to be passed to `Mapdl.run <ansys.mapdl.core.Mapdl.run>`.

## Returns

`int or str`: Returned value of `mpinqr` is based on setting of key.

## Notes

The material properties are obtained from the `MP <ansys.mapdl.core.Mapdl.mp>` command labels, which are detailed below:

**MP command labels**

| Property | Key | Property | Key | Property | Key | Property | Key | Property | Key | Property | Key |
|----------|-----|----------|-----|----------|-----|----------|-----|----------|-----|----------|-----|
| EX       | 1   | DAMP     | 15  | PRYZ     | 29  | SBKX     | 43  | HGLS     | 57  | RH       | 71  |
| EY       | 2   | KXX      | 16  | PRXZ     | 30  | SBKY     | 44  | BVIS     | 58  | DXX      | 72  |
| EZ       | 3   | KYY      | 17  | MURX     | 31  | SBKZ     | 45  | QRAT     | 59  | DYY      | 73  |
| NUXY     | 4   | KZZ      | 18  | MURY     | 32  | SONC     | 46  | REFT     | 60  | DZZ      | 74  |
| NUYZ     | 5   | RSVX     | 19  | MURZ     | 33  | DMPS     | 47  | CTEX     | 61  | BETX     | 75  |
| NUXZ     | 6   | RSVY     | 20  | PERX     | 34  | ELIM     | 48  | CTEY     | 62  | BETY     | 76  |
| GXY      | 7   | RSVZ     | 21  | PERY     | 35  | USR1     | 49  | CTEZ     | 63  | BETZ     | 77  |
| GYZ      | 8   |          | 22  | PERZ     | 36  | USR2     | 50  | THSX     | 64  | CSAT     | 78  |
| GXZ      | 9   | HF       | 23  | MGXX     | 37  | USR3     | 51  | THSY     | 65  | CREF     | 79  |
| ALPX     | 10  | VISC     | 24  | MGYY     | 38  | USR4     | 51  | THSZ     | 66  | CVH      | 80  |
| ALPY     | 11  | EMIS     | 25  | MGZZ     | 39  | FLUI     | 53  | DMPR     | 67  | UMID     | 81  |
| ALPZ     | 12  | ENTH     | 26  | EGXX     | 40  | ORTH     | 54  | LSSM     | 68  | UVID     | 82  |
| DENS     | 13  | LSST     | 27  | EGYY     | 41  | CABL     | 55  | BETD     | 69  |          |     |
| MU       | 14  | PRXY     | 28  | EGZZ     | 42  | RIGI     | 56  | ALPD     | 70  |          |     |

see `TB <ansys.mapdl.core.Mapdl.tb>` command for more information.
