---
apdl: "MODIFY"
method: modify
group: aux3
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux3.results_files.ResultsFiles.modify
generated: 2026-08-22
tags: [mapdl-command]
---

# MODIFY

PyMAPDL: `mapdl.modify(set_='', lstep='', iter_='', cumit='', time='', ktitle='', **kwargs)`

Changes the listed values of the data in a set.

## Parameters

**set_**: Set of data in results file to be modified.

**lstep**: The new load step number.

**iter_**: The new load substep number.

**cumit**: The new cumulative iteration.

**time**: The new time/frequency value.

**ktitle**

Indicates if the set title should be modified.

- `0` - Keep the original title.
- `1` - Change the title to the title specified with the most current [[title|/TITLE]] command.

## Notes

Use this command to change the listed values in a data set in a results file. Using this command does not change any actual model data; it affects only the values listed in the results file.

The **MODIFY** command is valid only in the results file editing processor (auxiliary processor AUX3), and, like the other AUX3 commands, it only affects the data steps index (DSI), time (TIM), loadstep, substep and cumulative step iteration (LSP) records in the results file.

**Example Usage** If you start with the following results file:

``` apdl
SET   TIME/FREQ    LOAD STEP   SUBSTEP  CUMULATIVE
 1     1.0000          1          1         1
 first load set

 2     2.0000           2          1         2
 second load set

 3     3.0000           3          1         3
 third load set

 4     4.0000           4          1         4
 fourth load set
```

and you then issue the following commands:

``` apdl
/title, modified title for set number 3
modify,3,5,2,5,4.5,1
```

The modified results file would look like this:

``` apdl
SET   TIME/FREQ    LOAD STEP   SUBSTEP  CUMULATIVE
 1     1.0000          1          1         1
 first load set

 2     2.0000           2          1         2
 second load set

 3     4.5000           5          2         5
 modified title for set number 3

 4     4.0000           4          1         4
 fourth load set
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MODIFY.html
