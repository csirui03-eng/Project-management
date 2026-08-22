---
apdl: "LCSUM"
method: lcsum
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.lcsum
generated: 2026-08-22
tags: [mapdl-command]
---

# LCSUM

PyMAPDL: `mapdl.lcsum(lab='', **kwargs)`

Specifies whether to process non-summable items in load case operations.

## Parameters

**lab**

Combination option

- `(blank)` - Only combine summable items \[default\].
- `ALL` - Combine all items including non summable items.

## Notes

Allows non-summable items (e.g. plastic strains) to be included in load combinations. Issue **LCSUM**,ALL before the first load case operation ( **LC** `XX` command). May also be used to include nonsummable items in the appending of a results file ( [[rappnd|RAPPND]] command).

For details on using load case combination, see [Creating and Combining Load Cases](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_4.html#bassummtlm51499325)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LCSUM.html
