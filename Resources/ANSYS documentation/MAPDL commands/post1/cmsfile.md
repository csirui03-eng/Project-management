---
apdl: "CMSFILE"
method: cmsfile
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.cmsfile
generated: 2026-08-22
tags: [mapdl-command]
---

# CMSFILE

PyMAPDL: `mapdl.cmsfile(option='', fname='', ext='', cmskey='', **kwargs)`

Specifies a list of component mode synthesis (CMS) results files for plotting results on the assembly.

**Command default:**

If issued with no arguments, the **CMSFILE** command uses these defaults:

**CMSFILE**,ADD, `Jobname`,rst,ON

The command adds the component results file `Jobnamerst`.

## Parameters

**option**

Specifies the command operation:

- `ADD` - Add the specified component results file ( `Fname` ) to the list of files to plot. This option is the default.
- `DELETE` - Remove the specified component results file ( `Fname` ) from the list of files to plot.
- `LIST` - List all specified component results files.
- `CLEAR` - Clear all previous files added.
- `ALL` - Add all component results ( `.rst` ) files from the working directory to the list of files to plot.

**fname**: The file name (with full directory path) of the component results file. The default file name is the `Jobname` (specified via the [[filname|/FILNAME]] command).

**ext**: The file name ( `Fname` ) extension. The default extension is `rst`.

**cmskey**

Valid only when adding a results file ( `Option` = ADD or ALL), this key specifies whether or not to check the specified `.rst` file to determine if it was created via a CMS expansion pass:

- `ON` - Check (default).
- `OFF` - Do not check.

## Notes

The **CMSFILE** command specifies the list of component mode synthesis (CMS) results files to include when plotting the mode shape of an assembly.

During postprocessing ( [[post1|/POST1]] ) of a CMS analysis, issue the **CMSFILE** command to point to component results files of interest. (You can issue the command as often as needed to include all or some of the component results files.) Issue the [[set|SET]] command to acquire the frequencies and mode shapes from substeps for all specified results files. Execute a plot ( [[plnsol|PLNSOL]] ) or print ( [[prnsol|PRNSOL]] ) operation to display the mode shape of the entire assembly.

When you specify a results file to add to the plot list, the default behavior of the command ( `CmsKey` = ON) is to first verify that the file is from a CMS analysis and that the frequencies of the result sets on the file match the frequencies on the first file in the list. If `CmsKey` = OFF, you can add any `.rst` file to the list of files to plot, even if the file was not expanded via a CMS expansion pass.

If `CmsKey` = ON (default), output from the command appears as: `ADD CMS FILE =` filename.rst `CmsKey` = OFF, output from the command appears as: `ADD FILE =` filename.rst

If `Option` = DELETE or CLEAR, you must clear the database ( [[clear|/CLEAR]] ), then re-enter the postprocessor ( [[post1|/POST1]] ) and issue a [[set|SET]] command for the change to take effect on subsequent plots.

Clearing the database does not clear the list of files specified via the **CMSFILE** command. Specify `Option` = CLEAR to clear the list of files.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CMSFILE.html
