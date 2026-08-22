---
apdl: "MODCONT"
method: modcont
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.modcont
generated: 2026-08-22
tags: [mapdl-command]
---

# MODCONT

PyMAPDL: `mapdl.modcont(mlskey='', enforcedkey='', fastlv='', **kwargs)`

Specify additional modal analysis options.

## Parameters

**mlskey**

Multiple load step key:

- `OFF` - Perform the modal analysis (compute the eigenvalues and the load vector) for each load step. (default)
- `ON` - Perform the modal analysis (compute the eigenvalues and the load vector) only for the first load step; form the load vector for each subsequent load step (without repeating the eigenvalue calculations) and write all load vectors to the `Jobname.MODE` file for downstream mode- superposition analyses.

**enforcedkey**

Enforced motion key:

- `OFF` - Do not calculate enforced static modes. (default)
- `ON` - Calculate enforced static modes and write them to the `Jobname.MODE` file.

**fastlv**

Fast load vector generation key; valid only when `MLSkey` = ON:

- `OFF` - Do not activate fast load vector generation (default).
- `ON` - Activate fast load vector generation. This option is only supported when each load vector is based on a unique element surface load ( [[sfe|SFE]] ) applied on one element, and the element result superposition key is activated ( `MSUPkey` = YES on [[mxpand|MXPAND]] ).

## Notes

Specifies additional modal analysis ( [[antype|ANTYPE]],MODAL) options.

Use the [[lvscale|LVSCALE]] command to apply the desired load in a mode-superposition transient or harmonic analysis.

When `MSUPkey` = YES on the [[mxpand|MXPAND]] command, the maximum number of load vectors allowed in the `Jobname.MODE` file defaults to 1000. To increase this limit, use the command [[config|/CONFIG]],NUMLV. When `FastLV` = ON, the limit is automatically set to 1x10 <sup>6</sup> and cannot be changed.

The maximum number of load vectors that can be used in the downstream mode-superposition transient or harmonic analysis is the number of load vectors written in the `Jobname.MODE` file.

[Generation of multiple loads](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR_SMSUP.html#) ( `MLSkey` = ON) is supported by the Block Lanczos, PCG Lanczos, Supernode, Subspace, Unsymmetric, and QRDAMP mode extraction methods.

The [enforced motion calculation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR_SMSUP.html#) ( `EnforcedKey` = ON) is supported by the Block Lanczos, Supernode, Subspace, and QRDAMP mode extraction methods.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MODCONT.html
