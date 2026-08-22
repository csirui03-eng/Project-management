---
apdl: "SAVE"
method: save
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.set_up.SetUp.save
generated: 2026-08-22
tags: [mapdl-command]
---

# SAVE

PyMAPDL: `mapdl.save(fname='', ext='', slab='', **kwargs)`

Saves all current database information.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to DB if `Fname` is blank.

**slab**

Mode for saving the database:

- `ALL` - Save the model data, solution data and post data (element tables, etc.). This value is the default.
- `MODEL` - Save the model data (solid model, finite element model, loadings, etc.) only.
- `SOLU` - Save the model data and the solution data (nodal and element results).

## Notes

Saves all current database information to a file ( `File.DB` ). In interactive mode, an existing `File.DB` is first written to a backup file ( `File.DBB` ). In batch mode, an existing `File.DB` is replaced by the current database information with no backup. The command should be issued periodically to ensure a current file backup in case of a system "crash" or a "line drop." It may also be issued before a "doubtful" command so that if the result is not what was intended the database may be easily restored to the previous state. A save may be time consuming for large models. Repeated use of this command overwrites the previous data on the file (but a backup file is first written during an interactive run). When issued from within POST1, the nodal boundary conditions in the database (which were read from the results file) will overwrite the nodal boundary conditions existing on the database file.

Internal nodes may be created during solution (for example, via the mixed u-P formulation or generalized plane strain option for [current-technology elements](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/EL2oldnewtable.html#EL2curtechelembenefits), the Lagrangian multiplier method for contact elements or the `MPC184` elements, or the quadratic or cubic option of the `BEAM188` and `PIPE288` elements). It is sometimes necessary to save the internal nodes in the database for later operations, such as cutting boundary interpolations ( [[cbdof|CBDOF]] ) for [submodeling](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/Hlp_G_ADV4_5.html). To do so, issue the **SAVE** command after the first [[solve|SOLVE]] command.

In general, saving after solving is always a good practice.

If radiosity surface elements ( `SURF251` or `SURF252` ) are present in the model, a radiosity mapping data file, `Fname.RSM,` is also saved when the **SAVE** command is issued. For more information, see [Advanced Radiosity Options](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_the/Hlp_G_THEadvrad.html#themultrsymm)

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SAVE.html
