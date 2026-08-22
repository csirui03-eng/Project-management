---
apdl: "/ENCRYPT"
method: encrypt
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.encryption_decryption.EncryptionDecryption.encrypt
generated: 2026-08-22
tags: [mapdl-command]
---

# /ENCRYPT

PyMAPDL: `mapdl.encrypt(key='', fname='', ext='', **kwargs)`

Controls encryption of command input.

## Parameters

**key**: Encryption key used to encrypt the data (32-character maximum). A character parameter may be used. If the key is unspecified, encryption is turned off.

**fname**: Name of file (including directory path) where the encrypted commands are written (248-character maximum for both file name and directory). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name.

**ext**: File name extension (eight-character maximum).

## Notes

This command opens the encrypted file specified by `Fname` and `Ext` for writing encrypted input commands.

Issuing this command results in a new file that overwrites any data in an existing file by the same name. When the encrypted file is written, the first line in the file is `/DECRYPT`,PASSWORD,OPENSSL and the last line is `/DECRYPT`.

See [Encrypting Command Input and Other Data](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_apdl/apdl_encryptmat.html) **/ENCRYPT** and performing encryption and decryption.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ENCRYPT.html
