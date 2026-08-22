---
apdl: "RSTMAC"
method: rstmac
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.rstmac
generated: 2026-08-22
tags: [mapdl-command]
---

# RSTMAC

PyMAPDL: `mapdl.rstmac(file1='', lstep1='', sbstep1='', file2='', lstep2='', sbstep2='', maclim='', cname='', keyprint='', **kwargs)`

Calculates modal assurance criterion (MAC/FRF) and matches nodal solutions from two results files or from one results file and one universal format file.

## Parameters

**file1**: File name ( 248 characters maximum) corresponding to the first results file ( `.rst` or `.rstp` file). If the file name does not contain the extension, it defaults to `rst`.

**lstep1**

Load step number of the results to be read in `File1`.

- `N` - Reads load step `N`. Defaults to 1.

**sbstep1**

Substep number of the results to be read in `File1`.

- `N` - Reads substep `N`. Only valid for MAC.
- `All` - Reads all substeps. This value is the default.

**file2**: File name ( 248 characters maximum) corresponding to the second file ( `.rst`, `.rstp`, or `.unv` file). If the file name does not contain the extension, it defaults to `rst`.

**lstep2**

Load step number of the results to be read in `File2`.

- `N` - Reads load step `N`. Defaults to 1.

**sbstep2**

Substep number of the results to be read in `File2`.

- `N` - Reads substep `N`. Only valid for MAC.
- `All` - Reads all substeps. This value is the default.

**maclim**: Smallest acceptable criterion value. Must be (equation omitted) 0 and (equation omitted) 1. The default value is 0.90.

**cname**: Name of the component from the first file ( `File1` ). The component must be based on nodes. If unspecified, all nodes are matched and used for MAC calculations. If a component name is specified, only nodes included in the specified component are used. Not applicable to node mapping ( `Option` = NODMAP on [[macopt|MACOPT]] ).

**keyprint**

Printout options:

- `0` - Printout matched solutions table. This value is the default.
- `1` - Printout matched solutions table and full MAC table.
- `2` - Printout matched solutions table, full MAC table and matched nodes table.

## Notes

The **RSTMAC** command allows the comparison of the solutions from either:

- Two different results files. Valid only for MAC calculations.
- One result file ( `.rst` ) and one universal format file ( `.unv` ).

Either the modal assurance criterion (MAC) or the frequency response function (FRF) correlation method is used. (For more details see [POST1 - Modal Assurance Criterion (MAC)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_post16.html#eqff29ac61-1393 - 4410-9090-572b02773534) [POST1 - Frequency response function correlation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thryFRF120.html#eqcaaee52b-1bb5-4b48-a411-6a162a579399)

The meshes read from `File1` and `File2` may be different. The nodes of `File1` are matched with the nodes of `File2` based on either node location (default) or node number. The solutions are compared for the identified pair of matched nodes. The nodes can also be mapped and the solutions interpolated from `File1`. See the [[macopt|MACOPT]] command for all options.

Units and coordinate systems must be the same for both models.

Results may be real or complex; however, if results in `File1` have a different type than results in `File2`, only the real parts of the solutions are taken into account in MAC calculations. The analysis type can be arbitrary for MAC while only harmonic analysis is supported for FRF criteria calculations.

Non-structural degrees of freedom can be considered. Degrees of freedom can vary between `File1` and `File2`, but at least one common degree of freedom must exist.

The solutions read on the results files are not all written to the database; therefore, subsequent plotting or printing of solutions is not possible. A [[set|SET]] command must be issued after the **RSTMAC** command to post-process each solution.

The corresponding database file ( `.db` ) for `File1` on **RSTMAC** must be resumed before running the command in the following cases:

- A component ( `Cname` ) is used on **RSTMAC**.
- The nodes are mapped ( [[macopt|MACOPT]],NODMAP,YES).
- The nodes are matched using a relative tolerance ( [[macopt|MACOPT]],RELTOLN).

**RSTMAC** comparison on cyclic symmetry analysis works only if the number of sectors on `File1` and `File2` are the same, and the database is saved after the solution is finished. Also, a comparison cannot be made between cyclic symmetry results and the full 360 degree model results ( `File1` - cyclic solution, `File2` - full 360 degree model solution). Comparing cyclic symmetry solutions written on a selected set of nodes ( [[outres|OUTRES]] ) is not supported.

The modal assurance criterion values can be retrieved as parameters using the [[get|*GET]] command ( `Entity` = **RSTMAC** ).

FRF correlation is only supported for the comparison of an `.rst` and a `.unv` file. All substeps are considered for both files to define the frequency domain for criteria calculations. The printout options consist of listing the table of the criterion results for each frequency in the frequency domain ( `KeyPrint` = 0, 1, or 2) and the matched nodes table ( `KeyPrint` = 2).

**Example Usage**

For a detailed discussion on using RSTMAC with examples see [Comparing Nodal Solutions From Two Models (RSTMAC)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_4.html#) RSTMAC ) in the [Basic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS19.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RSTMAC.html
