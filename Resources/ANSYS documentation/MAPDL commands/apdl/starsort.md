---
apdl: "*SORT"
method: starsort
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.starsort
generated: 2026-08-22
tags: [mapdl-command]
---

# *SORT

PyMAPDL: `mapdl.starsort(name='', sorttype='', val1='', val2='', **kwargs)`

Sorts the values of the specified vector.

## Parameters

**name**: Name of the vector to be sorted. This vector can contain real or complex values.

**sorttype**

Criteria used to sort the values:

- `VALUE` - Values are sorted based on their real value (default).
- `ABS` - Values are sorted based on their absolute value.
- `PERM` - Values are sorted based on the input permutation vector ( `Val1` ).

**val1**

Name of the permutation vector used to sort the values. This must be a vector of integer values that was created with the [[vec|*VEC]] command. The size of this permutation vector must be identical to the size of the vector to be sorted.

This permutation vector is required when using `Method` = PERM.

**val2**

Order of the sort operation:

- `0` - Increasing order (default).
- `1` - Decreasing order.

## Notes

### Argument descriptions

- `name : str` - Name of the vector to be sorted. This vector can contain real or complex values.
- `sorttype : str` - Criteria used to sort the values:
  - `VALUE` - Values are sorted based on their real value (default).
  - `ABS` - Values are sorted based on their absolute value.
  - `PERM` - Values are sorted based on the input permutation vector ( `Val1` ).
- `val1, val2 : str` - Additional input. The meaning of `Val1`, `Val2` varies depending on the specified `SortType`. See below for details.

**The following** `Valx` fields are used with `SortType` = VALUE or ABS:

- `val1 : str` - Name of the vector in which permutation values will be saved (optional). This should be an empty vector of type integer that was created with the [[vec|*VEC]] command. The size of this permutation vector must be identical to the size of the vector to be sorted. After the sort, this vector contains the permutation used to sort the values.
- `val2 : str` - Order of the sort operation:
  - `0` - Increasing order (default).
  - `1` - Decreasing order.

**The following** `Valx` fields are used with `Method` = PERM:

- `val1 : str` - Name of the permutation vector used to sort the values. This must be a vector of integer values that was created with the [[vec|*VEC]] command. The size of this permutation vector must be identical to the size of the vector to be sorted.

  This permutation vector is required when using `Method` = PERM.

The examples below demonstrate using **\*SORT** to sort the values of an input vector.

The following input:

``` apdl
*VEC,V,I,ALLOC,5
V(1)=5,-3,2,0,-1
*SORT,V,VALUE
*PRINT,V
```

generates this output:

``` apdl
-3        -1         0         2         5
```

To reverse the order, this input:

``` apdl
*SORT,V,VALUE,,1
*PRINT,V
```

generates this output:

``` apdl
5         2         0        -1        -3
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SORT_st.html
