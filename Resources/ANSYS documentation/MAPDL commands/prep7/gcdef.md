---
apdl: "GCDEF"
method: gcdef
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.gcdef
generated: 2026-08-22
tags: [mapdl-command]
---

# GCDEF

PyMAPDL: `mapdl.gcdef(option='', sect1='', sect2='', matid='', realid='', sect1end='', sect2end='', **kwargs)`

Defines interface interactions between general contact surfaces.

## Parameters

**option**

Option to be performed.

- `(blank)` - Retain the previous `Option` setting between `SECT1` and `SECT2`.

- `AUTO` - Define auto asymmetric contact between surfaces `SECT1` and `SECT2`.

- `SYMM` - Define symmetric contact between surfaces `SECT1` and `SECT2`.

- `ASYM` - Define asymmetric contact with `SECT1` as the source (contact) surface and `SECT2` as the target surface.

- `EXCL` - Exclude contact between surfaces `SECT1` and `SECT2`. `MATID`, `REALID`, `SECT1END`, and `SECT2END` are ignored.

- `DELETE` - Remove the given definition from the **GCDEF** table. `MATID`, `REALID`, `SECT1END`, and `SECT2END` are ignored.

  Note that **GCDEF**,DELETE,ALL,ALL does not remove the entire **GCDEF** table; it merely removes any existing **GCDEF**,,ALL,ALL definitions, while leaving intact any existing **GCDEF** definitions that are more specific.

  To remove the entire **GCDEF** table, issue **GCDEF**,DELETE,TOTAL.

  It is good practice to list all definitions using **GCDEF**,LIST before and after a **GCDEF**,DELETE command.

- `LIST` - List stored **GCDEF** data entries. `MATID` and `REALID` are ignored.

  **GCDEF**,LIST lists all defined interactions. **GCDEF**,LIST, `SECT1`, `SECT2` lists the entry for the specific `SECT1` / `SECT2` interaction. **GCDEF**,LIST,ALL,ALL lists only the ALL,ALL entry (if any).

- `TABLE` - List interpreted general contact definitions in tabular format. `MATID` and `REALID` are ignored.

  By default, rows/columns of the table that match neighboring rows/columns are compressed to simplify the table. Issue **GCDEF**,TABLE,TOTAL to list the entire **GCDEF** table without removal of duplicate rows and columns.

- `TABLESOL` - List a table showing actual interactions considered during solution. This option is only available after the [[solve|SOLVE]] command. `MATID` and `REALID` are ignored.

  The table shows MAT and REAL entries considered during the solution (actual contact may or may not have occurred). This is in contrast to **GCDEF**,TABLE, which shows the user specifications. For auto asymmetric contact, TABLESOL indicates which of the possible contact versus target surface combinations was considered.

**sect1**, **sect2**

Section numbers representing contact ( `SECT1` ) and target ( `SECT2` ) general contact surfaces (no defaults). (In most cases, the actual determination of contact versus target surfaces takes place during [[solve|SOLVE]].)

A node component name is also valid input for `SECT1` and `SECT2`. The component name is not stored. Instead, the program loops through all valid section IDs found in the component and creates **GCDEF** entries for all possible SECT1/SECT2 combinations that result. These entries are reflected in the `Option` = LIST and TABLE output. Section IDs can be further controlled by adding an extension (EDGE, FACE, VERT, TOP, or BOT) to the end of the component name. See in the [Contact Technology Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctec_flpressexamp.html) for more information.

The following labels are also valid input:

- `SELF` - Self contact.
- `ALL` - All general contact sections IDs.
- `ALL_EDGE` - Section IDs of all `CONTA177` general contact line elements (which may be on the edges of 3D solid and shell base elements, or on beam base elements).
- `ALL_FACE` - Section IDs of all general contact elements on faces of solid or shell base elements (both top and bottom faces of shell elements).
- `ALL_VERT` - Section IDs of all `CONTA175` general contact vertex elements (which may be on convex corners of solid and shell base elements, and on endpoints of beam base elements).
- `ALL_TOP` - Section IDs of all general contact elements on top faces of shell base elements, and faces of solid base elements.
- `ALL_BOT` - Section IDs of general contact elements on bottom faces of shell base elements, and faces of solid base elements.

The ALL labels apply to all defined general contact element section IDs in the model without regard to the select status of the elements or attached nodes.

See `SECT1` / `SECT2` Interactions for a description of how the various inputs for `SECT1` and `SECT2` are interpreted.

**matid**

Material ID number for general contact interaction properties at the `SECT1` / `SECT2` interface. If zero or blank, the previous setting of `MATID` for `SECT1` / `SECT2` (if any) is retained.

As an example, you could specify "always bonded" contact behavior at the interface by setting `MATID` to 2 and issuing the command [[tb|TB]],INTER,2,,,ABOND.

The coefficient of friction MU is also defined by `MATID`. Since the default is `MATID` = 0, frictionless contact (MU = 0) is assumed by default.

**realid**

Real constant ID number for general contact interaction properties at the `SECT1` / `SECT2` interface. If zero or blank, the previous setting of `REALID` for `SECT1` / `SECT2` (if any) is retained.

As an example, you could specify contact stiffness (FKN) = 10 at the interface by setting `REALID` to 14 and issuing the command [[r|R]],14,,,10.

**sect1end**, **sect2end**: Last section number in the range. For `Option` = LIST, TABLE, or TABLESOL, data entries are processed for contact section numbers in the range from `SECT1` to `SECT1END`, and target section numbers in the range from `SECT2` to `SECT2END`. `SECT1END` and `SECT2END` are ignored for all other `Option` labels.

## Notes

**GCDEF** defines the interface interaction between general contact surfaces identified by `SECT1` and `SECT2`. **GCDEF** commands are order independent in most cases.

**GCDEF** definitions should be issued after [[gcgen|GCGEN]]. They are saved in the database and are written to and read from `.CDB` files.

See [General Contact](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctec_toolsgencont.html)

****SECT1/ SECT2 Interactions****

The most specific types of general contact definitions are those described below:

- `SECT1` = any valid general surface section ID and `SECT2` = any different valid general surface section ID: `Option`, `MATID`, and `REALID` apply to general surface interactions between `SECT1` and `SECT2`. This is one of the most specific types of general contact definitions and is never overridden.
- `SECT1` = any valid general surface section ID and `SECT2` = `SECT1` : `Option`, `MATID`, and `REALID` apply to general surface self contact interactions involving `SECT1`. This is one of the most specific types of general contact definitions and is never overridden.

The remaining general contact definition types can be overridden by the above two general contact definition types:

- `SECT1` = ALL and `SECT2` = ALL: `Option`, `MATID`, and `REALID` apply to all general surface interactions, except where overridden by a more specific **GCDEF** command.
- `SECT1` = ALL and `SECT2` = SELF or `SECT1` = SELF and `SECT2` = ALL: `Option`, `MATID`, and `REALID` apply to all general surface self contact interactions, except where overridden by a more specific **GCDEF** command.
- `SECT1` = ALL and `SECT2` = any valid general surface section ID: `Option`, `MATID`, and `REALID` apply to all general surface interactions that include `SECT2`, except where overridden by a more specific **GCDEF** command.
- `SECT1` = any valid general surface section ID and `SECT2` = ALL: `Option`, `MATID`, and `REALID` apply to all general surface interactions that include `SECT1`, except where overridden by a more specific **GCDEF** command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GCDEF.html
