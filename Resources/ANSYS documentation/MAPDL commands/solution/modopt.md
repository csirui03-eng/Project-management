---
apdl: "MODOPT"
method: modopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.modopt
generated: 2026-08-22
tags: [mapdl-command]
---

# MODOPT

PyMAPDL: `mapdl.modopt(method='', nmode='', freqb='', freqe='', cpxmod='', nrmkey='', modtype='', blocksize='', freqmod='', **kwargs)`

Specifies modal analysis options.

## Parameters

**method**

Mode-extraction method to be used for the modal analysis.

- `LANB` - Block Lanczos
- `LANPCG` - PCG Lanczos
- `SNODE` - Supernode modal solver
- `SUBSP` - Subspace algorithm
- `UNSYM` - Unsymmetric matrix
- `DAMP` - Damped system
- `QRDAMP` - Damped system using QR algorithm

**nmode**

The number of modes to extract. The value can depend on the value supplied for `Method`. `NMODE` has no default and must be specified. If `Method` = LANB, LANPCG, or SNODE, the number of modes that can be extracted can equal the DOFs in the model after the application of all boundary conditions.

For `Method` = LANB, SUBSP and UNSYM, you can specify `NMODE` = ALL to extract all eigenvalues in a given frequency range. To use this option, you must also define the frequency range (that is, a `FREQE` value must be set).

Recommendation:

- When `Method` = LANPCG, `NMODE` should be less than 100 to be computationally efficient.
- When `Method` = SNODE, `NMODE` should be greater than 100 for 2D plane or 3D shell/beam models and greater than 250 for 3D solid elements to be computationally efficient.

**freqb**

The beginning, or lower end, of the frequency range (or eigenvalue range if `FREQMOD` is specified) of interest.

For `Method` = LANB, SUBSP, UNSYM, DAMP, and QRDAMP, `FREQB` also represents the first shift point for the eigenvalue iterations. For UNSYM and DAMP, the default = -1.0 For other methods, the default is calculated internally.

Eigenvalue extraction is most accurate near the shift point. Multiple shift points are used internally in the LANB, SUBSP, UNSYM, and QRDAMP methods. For the LANB, LANPCG, SUBSP, UNSYM, DAMP, and QRDAMP methods with a positive `FREQB` value, eigenvalues are output beginning at the shift point and increase in magnitude. For the UNSYM and DAMP methods with a negative `FREQB` value, eigenvalues are output beginning at zero magnitude and increase.

Choosing higher `FREQB` values with the LANPCG and SNODE methods may lead to inefficient solution times because these methods will find all eigenvalues between zero and `FREQB` before finding the requested modes between `FREQB` and `FREQE`.

**freqe**

The ending, or upper end, of the frequency range (or eigenvalue range if `FREQMOD` is specified) of interest (in Hz). Default = 100 Hz when `Method` = SNODE. The default for all other methods is to calculate all modes, regardless of their maximum frequency.

To maintain solution efficiency, do not set the `FREQE` value too high; for example, not higher than 5000 Hz for an industrial problem. The higher the `FREQE` value used for the SNODE method, the more accurate the solution and the more eigenvalues produced; however, the solution time also increases. For example, if `FREQE` is set to 1e8, it causes the underlying supernodal structures to find all possible eigenvalues of each group of supernodes, requiring excessive solution time. The accuracy of the SNODE solution is controlled by `FREQE` and by the `RangeFact` value on the [[snoption|SNOPTION]] command.

**cpxmod**

Complex eigenmode key. (Valid only when `Method` = QRDAMP or `Method` = UNSYM).

- `AUTO` - Determine automatically if the eigensolutions are real or complex and output them accordingly (default when `Method` = UNSYM). Not supported for `Method` = QRDAMP.
- `ON or CPLX` - Calculate and output complex eigenmode shapes.
- `OFF or REAL` - Do not calculate complex eigenmode shapes (default). This setting is required if a mode- superposition analysis is intended after the modal analysis for `Method` = QRDAMP.

**nrmkey**

Mode shape normalization key:

- `OFF` - Normalize the mode shapes to the mass matrix (default). This option is invalid for damped modal cyclic symmetry ( `Method` = DAMP or QRDAMP with the [[cyclic|CYCLIC]] command).

- `ON` - Normalize the mode shapes to unity instead of to the mass matrix (default for damped modal cyclic symmetry \[ `Method` = DAMP or QRDAMP with the [[cyclic|CYCLIC]] command\]).

  If a subsequent spectrum or mode-superposition analysis is planned, the mode shapes should be normalized to the mass matrix ( `Nrmkey` = OFF).

**modtype**

Type of modes calculated by the eigensolver. Only applicable to the unsymmetric eigensolver.

- `` - Right eigenmodes (default).
- `BOTH` - Right and left eigenmodes. The left eigenmodes are written to `Jobname.LMODE`. This option must be activated if a mode-superposition analysis is intended.

**blocksize**

The block vector size to be used with the Block Lanczos or Subspace eigensolver (used only when `Method` = LANB or SUBSP). `BlockSize` must be an integer value between 0 and 16. When BlockSize = zero or blank, the code decides the block size internally (normally, a value of 8 is used for LANB and a value of 6 is used for SUBSP). Typically, higher `BlockSize` values are more efficient under each of the following conditions:

- When running in out-of-core mode and there is not enough physical memory to buffer all of the files written by the Block Lanczos or Subspace eigensolver (and thus, the time spent doing I/O is considerable).
- Many modes are requested (\>100).
- Higher-order solid elements dominate the model.

The memory usage only slightly increases as  
`BlockSize` is increased. It is recommended that you use a value divisible by 4 (4, 8, 12, or 16).

**freqmod**: The specified frequency when the solved eigenvalues are no longer frequencies (for example, the model has the Floquet periodic boundary condition). In a modal analysis, the Floquet periodic boundary condition (body load FPBC) is only valid for the acoustic elements `FLUID30`, `FLUID220`, and `FLUID221`.

## Notes

Specifies modal analysis ( [[antype|ANTYPE]],MODAL) options.

Additional options for specific eigensolvers are controlled by these commands:

- [[snoption|SNOPTION]] specifies options for the Supernode (SNODE) eigensolver.
- [[subopt|SUBOPT]] specifies options for the Subspace (SUBSP) eigensolver.
- [[qrdopt|QRDOPT]] specifies options for the QRDAMP eigensolver.
- [[dampopt|DAMPOPT]] specifies options for the damped (DAMP) eigensolver.
- [[lanboption|LANBOPTION]] specifies options for the Block Lanczos (LANB) eigensolver. For more difficult modal problems, you can specify an alternative version of the Block Lanczos eigensolver ( [[lanboption|LANBOPTION]], ALT1).

If `Method` = LANPCG, Mechanical APDL automatically switches to the PCG solver internally for this modal analysis. You can further control the efficiency of the PCG solver with the [[pcgopt|PCGOPT]] and [[eqslv|EQSLV]] commands.

For models that involve a non-symmetric element stiffness matrix, as in the case of a contact element with frictional contact, the QRDAMP eigensolver ( **MODOPT**, QRDAMP) extracts modes in the modal subspace formed by the eigenmodes from the symmetrized eigenproblem. The QRDAMP eigensolver symmetrizes the element stiffness matrix on the first pass of the eigensolution, and in the second pass, eigenmodes are extracted in the modal subspace of the first eigensolution pass. For such non-symmetric eigenproblems, you should verify the eigenvalue and eigenmode results using the non-symmetric matrix eigensolver ( **MODOPT**,UNSYM).

The DAMP and QRDAMP options cannot be followed by a subsequent spectrum analysis. The UNSYM method supports spectrum analysis when eigensolutions are real.

In a modal analysis, the Floquet periodic boundary condition (body load FPBC) is only valid for the acoustic elements `FLUID30`, `FLUID220`, and `FLUID221`.

For more details about mode shape normalization, see [Description of Analysis for Symmetric Undamped Systems](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc3.html#eq1a4e68e0-62f4-4fec-a234-4ec054188490)

This command is also valid in PREP7.

Distributed-Memory Parallel (DMP) Restriction All extraction methods are supported in a DMP solution. Block Lanczos, PCG Lanczos, SUBSP, UNSYM, DAMP, and QRDAMP are distributed eigensolvers that run a fully distributed solution. However, the Supernode eigensolver is not a distributed eigensolver; therefore, you will not see the full performance improvements with this method that you would with a fully distributed solution.

(table not available in the PyMAPDL source, see the Ansys help page)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MODOPT.html
