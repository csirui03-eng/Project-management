---
apdl: "EXOPTION"
method: exoption
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.exoption
generated: 2026-08-22
tags: [mapdl-command]
---

# EXOPTION

PyMAPDL: `mapdl.exoption(ldtype='', option='', value='', **kwargs)`

Specifies the [[exprofile|EXPROFILE]] options for the Mechanical APDL to Ansys CFX profile file transfer.

## Parameters

**ldtype**

Load type:

- `SURF` - Surface load
- `VOLU` - Volume load

**option**

Surface options:

- `Precision` - Number of significant digits for the fractional part of real data
- `Connectivity` - Key to include face connectivity in the exported profile file

Volume options:

- `Precision` - Number of significant digits after the decimal for real data

**value**

Specify the value for either Precision or Connectivity.

For Precision, specify the number of significant digits. Can be any value between 1 to 20, default 8. When 0 or an invalid value is specified, the program will use the default value of 8 and issue a warning message.

For Connectivity, specify the key to include the element face connectivity data for surface loads (does not support volume loads):

- `OFF` - Do not include the connectivity data in the exported file (default)
- `ON` - Include the connectivity data in the exported file

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EXOPTION.html
