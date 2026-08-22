---
apdl: "/FCLEAN"
method: fclean
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.files.Files.fclean
generated: 2026-08-22
tags: [mapdl-command]
---

# /FCLEAN

PyMAPDL: `mapdl.fclean(**kwargs)`

Deletes all local files in all processors in a distributed parallel processing run.

## Notes

Issue **/FCLEAN** to delete all local files having the current `Jobname` ( [[filname|/FILNAME]] ) and save disk space in a distributed parallel processing run. Like other file deletion commands, deletion happens immediately upon issuing this command. Different than other file deletion commands, it enables the convenience of deleting all `Jobname.\*` local files without having to issue separate commands specifying each file type.

All `.log` files except the master ( `Jobname0.log` ) are deleted.

> [!WARNING]
> Because **/FCLEAN** deletes all local files, it should only be issued if you are sure that none of those files are needed in any downstream analyses. Deleting files that are necessary for subsequent substeps, load steps, commands, or analyses will prevent continuation of the run. For example, since the local files are combined into global files when you issue [[finish|FINISH]] in the solution processor, issuing **/FCLEAN** before [[finish|FINISH]] in [[slashsolu|/SOLU]] will result in a program crash.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FCLEAN_sl.html
