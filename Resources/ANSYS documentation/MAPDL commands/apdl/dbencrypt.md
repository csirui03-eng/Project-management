---
apdl: "/DBENCRYPT"
method: dbencrypt
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.encryption_decryption.EncryptionDecryption.dbencrypt
generated: 2026-08-22
tags: [mapdl-command]
---

# /DBENCRYPT

PyMAPDL: `mapdl.dbencrypt(keya='', keyb='', datatype='', num1='', num2='', inc='', **kwargs)`

Controls encryption of material data in the database file.

## Parameters

**keya**: Encryption key A (32-character maximum). This key is used to encrypt the data in a one-level encryption or to control access to the data in a two-level encryption.

**keyb**: Encryption key B (32-character maximum). This key is used to encrypt the data in a two-level encryption. If `KeyB` is not specified, a one-level encryption is used to encrypt the data.

**datatype**: Type of data to encrypt. Must be set to MAT for material data.

**num1**, **num2**, **inc**: Encrypt materials from material number `NUM1` to `NUM2` (defaults to `NUM1` ) in steps of `INC` (defaults to 1). If `NUM1` = ALL (default), `NUM2` and `INC` are ignored.

## Notes

This command encrypts data in the database file. It must be issued before saving the database file ( [[save|SAVE]] command).

For a one-level encryption, specify only `KeyA` and set `NUM1` to ALL. ( `NUM2` and `INC` are not used.)

For a [two-level encryption](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_apdl/apdl_encryptmat.html#partial_access), specify both `KeyA` and `KeyB`. Also specify `NUM1`, `NUM2`, and `INC` as needed.

For more information about using **/DBENCRYPT** in the encryption/decryption procedure, see [Encrypting Material Data](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_apdl/apdl_encryptmat.html#apdl_encryptsteps_mat) [[dbdecrypt|/DBDECRYPT]] command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DBENCRYPT.html
