---
apdl: "NLDPOST"
method: nldpost
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.nldpost
generated: 2026-08-22
tags: [mapdl-command]
---

# NLDPOST

PyMAPDL: `mapdl.nldpost(label='', key='', fileid='', prefix='', **kwargs)`

Gets element component information from nonlinear diagnostic files.

## Parameters

**label**

Specifies the type of command operation:

- `EFLG` - Element flag for nonlinear diagnostics.
- `NRRE` - Newton-Raphson residuals.

**key**

Specifies the command action:

- `STAT` - List information about the diagnostic files ( `Jobname.ndxxx` or `Jobname.nrxxx` ) in the current directory.

  For `Label` = EFLG, the listing gives a summary that associates the loadstep, substep, time, equilibrium iteration number, cumulative iteration number, and the number of elements that fail each criteria with a specific file ID ( `Jobname.ndxxx` ). Use the list to create element components (via the CM option) based on the cumulative iteration number.

  For `Label` = NRRE, the listing provides a summary that associates the loadstep, substep, time, equilibrium iteration number, and cumulative iteration number with a specific file ID ( `Jobname.nrxxx` ). Use the list to identify the respective file ID for creating Newton-Raphson residual contour plots ( [[plnsol|PLNSOL]],NRRE,..., `FileID` ).

- `DEL` - Delete `Jobname.ndxxx` or `Jobname.nrxxx` files in the working directory, if any exist.

- `CM` - Create components for elements that violate criteria. This value is valid only when `Label` = EFLG.

**fileid**

Valid only when `Label` = EFLG and `Key` = CM, this value specifies file IDs:

- `IDnum` - The file ID number. Creates the element components from the diagnostic files corresponding to the specified file ID number in the working directory.
- `ALL` - Creates element components from all available diagnostic files residing in the working directory. This value is the default if you do not specify an `IDnum` value.

**prefix**: Sets the prefix name for components. Specify up to 21 alphanumeric characters.

## Notes

Based on the nonlinear diagnostic results (created via the [[nldiag|NLDIAG]],EFLG command), the **NLDPOST** command creates element components with predefined names.

The following table lists the diagnostic criteria and component names (with specified prefix and without). Here `xxx` corresponds to the file ID ( `FileID` ) of `Jobname.ndxxx` or `Jobnamenrxxx`.

(table not available in the PyMAPDL source, see the Ansys help page)

If you have trouble viewing specific element components, see [Viewing Hidden Element Components](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS7_4.html#)

For more information, see Performing Nonlinear Diagnostics.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NLDPOST.html
