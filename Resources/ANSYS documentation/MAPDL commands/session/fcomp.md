---
apdl: "/FCOMP"
method: fcomp
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.files.Files.fcomp
generated: 2026-08-22
tags: [mapdl-command]
---

# /FCOMP

PyMAPDL: `mapdl.fcomp(ident='', level='', **kwargs)`

Specifies file-compression options.

## Parameters

**ident**

Mechanical APDL file identifier. There is no default. Valid labels are:

- `RST` - Results file.
- `DB` - Database file.
- `RNNN` - Restart file.
- `OSAV` - File created during a nonlinear analysis that contains a copy of `ESAV` file from the last converged substep.

**level**

Compression level:

- `SPARSE` - Use a sparsification scheme for file compression (default).
- `0` - No file compression occurs.
- `n` - A zlib-based file compression occurs using level number `n`, which ranges from 1 to 5.

## Notes

Specifies file compression options for results files ( `.rst`, `.rstp`, `.rth`, and `.rmg` files), database files ( `.db` and `.rdb` ), certain restart files ( `.Rnnn` ), and the `.osav` file created during a nonlinear analysis. (See [Program- Generated Files](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS18_4.html#aHXtsq2aaldm) [[set|SET]] command or the [[resume|RESUME]] command).

For results files compressed using the sparsification scheme ( `LEVEL` = SPARSE, which is the default), use the `*XPL` command to uncompress the file. For third party tools that need to read the results file, use the method described in [Accessing Mechanical APDL Binary Files](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Hlp_P_INT2_1.html#intlargeintget)

See in the [Basic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS19.html) for more details.

This command is valid only at the Begin Level.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FCOMP_sl.html
