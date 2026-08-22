---
apdl: "/DBDECRYPT"
method: dbdecrypt
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.encryption_decryption.EncryptionDecryption.dbdecrypt
generated: 2026-08-22
tags: [mapdl-command]
---

# /DBDECRYPT

PyMAPDL: `mapdl.dbdecrypt(keya='', keyb='', datatype='', num1='', num2='', inc='', **kwargs)`

Controls decryption of material data in the database file.

## Parameters

**keya**: Decryption key A (32-character maximum). This key is used to decrypt the data in a one-level encryption or to control access to the data in a two-level encryption. Leave this field blank if you do not have key A.

**keyb**: Decryption key B (32-character maximum). This key is used to decrypt the data in a two-level encryption. Leave this field blank if the database file is encrypted with one-level encryption.

**datatype**: Type of data to decrypt. Must be set to MAT for material data.

**num1**, **num2**, **inc**: Decrypt materials from material number `NUM1` to `NUM2` (defaults to `NUM1` ) in steps of `INC` (defaults to 1). If `NUM1` = ALL (default), `NUM2` and `INC` are ignored.

## Notes

This command decrypts data in the database file. It must be issued before resuming the database file ( [[resume|RESUME]] command). Only `KeyA` is required for a one-level encryption. For a [two-level encryption](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_apdl/apdl_encryptmat.html#partial_access), inputting `KeyB` gives you partial access to the data. Inputting both `KeyA` and `KeyB` gives you full access.

For more information about using **/DBDECRYPT** in the encryption/decryption procedure, see [Encrypting Material Data](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_apdl/apdl_encryptmat.html#apdl_encryptsteps_mat) [[dbencrypt|/DBENCRYPT]] command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DBDECRYPT.html
