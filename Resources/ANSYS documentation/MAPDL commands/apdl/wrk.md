---
apdl: "*WRK"
method: wrk
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.wrk
generated: 2026-08-22
tags: [mapdl-command]
---

# *WRK

PyMAPDL: `mapdl.wrk(num='', **kwargs)`

Sets the active workspace number.

## Parameters

**num**: Number of the active memory workspace for APDLMath vector and matrices. All the following APDLMath vectors and matrices will belong to this memory workspace, until the next call to the **\*WRK** command. By default, all the APDLMath objects belong to workspace number 1.

## Notes

### Argument descriptions

- `num : str` - Number of the active memory workspace for APDLMath vector and matrices. All the following APDLMath vectors and matrices will belong to this memory workspace, until the next call to the **\*WRK** command. By default, all the APDLMath objects belong to workspace number 1.

This feature enables you to associate a set of vector and matrices in a given memory workspace, so that you can easily manage the free step:

``` apdl
*VEC,V,D,ALLOC,5             ! V belongs to the default Workspace 1

\*WRK,2                                      ! Set the active workspace as the number 2

\*VEC,W,D,IMPORT,FULL,file.full,RHS  ! W belongs to the Workspace 2
\*SMAT,K,D,IMPORT,FULL,file.full,STIFF       ! K belongs to the Workspace 2
\*DMAT,M,ALLOC,10,10                         ! M belongs to the Workspace 2
...
\*FREE,WRK,2                 ! W, K and M are deleted, but not V

\*PRINT,V
```

This feature can be useful to free all the temporary APDLMath variables inside a MACRO in one call.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_WRK.html
