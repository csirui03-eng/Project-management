---
apdl: "/DECRYPT"
method: decrypt
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.encryption_decryption.EncryptionDecryption.decrypt
generated: 2026-08-22
tags: [mapdl-command]
---

# /DECRYPT

PyMAPDL: `mapdl.decrypt(key1='', key2='', **kwargs)`

Controls decryption of command input.

## Parameters

**key1**: Key to decrypt the encrypted input created by [[encrypt|/ENCRYPT]]. The only valid label is PASSWORD.

**key2**

Key to decrypt the encrypted input or to set the global encryption key. The following are valid inputs:

- If `Key2` = OPENSSL or is blank, then decryption commences and the previously set global encryption key is used for decryption.
- If `Key2` has a value, then that value is set as the global encryption key.
- If `Key2` = OFF, then the global encryption password previously set by the command **/DECRYPT**,PASSWORD, `Key2` is reset.

## Notes

When decrypting an encrypted input, `/DECRYPT,PASSWORD,OPENSSL` must appear as the first line of the encrypted file. The line is inserted automatically when you issue [[encrypt|/ENCRYPT]] to create the encrypted file.

To read an encrypted file, enter **/DECRYPT**,PASSWORD, `Key2` anywhere in the standard input file to set the global encryption key. The encryption key must be set before reading in the encrypted input.

**/DECRYPT** is also valid when entered in the Command Input Window of the Mechanical APDL user interface.

See [Encrypting Command Input and Other Data](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_apdl/apdl_encryptmat.html) **/DECRYPT** and performing encryption and decryption.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DECRYPT.html
