---
group: apdl
generated: 2026-08-22
tags: [mapdl-command-index]
---

# APDL commands

These commands make up the ANSYS Parametric Design Language (APDL).

84 commands. Back to [[MAPDL commands]].

| Command | Method | Summary |
|---|---|---|
| [[abbr\|*ABBR]] | `abbr` | Defines an abbreviation. |
| [[abbres\|ABBRES]] | `abbres` | Reads abbreviations from a coded file. |
| [[abbsav\|ABBSAV]] | `abbsav` | Writes the current abbreviation set to a coded file. |
| [[afun\|*AFUN]] | `afun` | Specifies units for angular functions in parameter expressions. |
| [[axpy\|*AXPY]] | `axpy` | Performs the matrix operation M2= v2M1 + w2M2. |
| [[cfclos\|*CFCLOS]] | `cfclos` | Closes the "command" file. |
| [[cfopen\|*CFOPEN]] | `cfopen` | Opens a "command" file. |
| [[cfwrite\|*CFWRITE]] | `cfwrite` | Writes a Mechanical APDL command (or similar string) to a "command" file. |
| [[comp\|*COMP]] | `comp` | Compresses a matrix using a specified algorithm. |
| [[create\|*CREATE]] | `create` | Opens (creates) a macro file. |
| [[dbdecrypt\|/DBDECRYPT]] | `dbdecrypt` | Controls decryption of material data in the database file. |
| [[dbencrypt\|/DBENCRYPT]] | `dbencrypt` | Controls encryption of material data in the database file. |
| [[decrypt\|/DECRYPT]] | `decrypt` | Controls decryption of command input. |
| [[dim\|*DIM]] | `dim` | Defines an array parameter and its dimensions. |
| [[dmat\|*DMAT]] | `dmat` | Creates a dense matrix. |
| [[dot\|*DOT]] | `dot` | Computes the dot (or inner) product of two vectors. |
| [[eigen\|*EIGEN]] | `eigen` | Performs a modal solution with unsymmetric or damping matrices. |
| [[encrypt\|/ENCRYPT]] | `encrypt` | Controls encryption of command input. |
| [[end\|*END]] | `end` | Closes a macro file. |
| [[starexit\|*EXIT]] | `starexit` | Exits a do-loop. |
| [[export\|*EXPORT]] | `export` | Exports a matrix to a file in the specified format. |
| [[fft\|*FFT]] | `fft` | Computes the fast Fourier transformation of a specified matrix or vector. |
| [[free\|*FREE]] | `free` | Deletes a matrix or a solver object and frees its memory allocation. |
| [[get\|*GET]] | `get` | Retrieves a value and stores it as a scalar parameter or part of an array parameter. |
| [[hprod\|*HPROD]] | `hprod` | Performs a Hadamard vector product (C = A∘B). |
| [[init\|*INIT]] | `init` | Initializes a vector or matrix. |
| [[inquire\|/INQUIRE]] | `inquire` | Returns system information to a parameter. |
| [[starinquire\|*INQUIRE]] | `starinquire` | Retrieves properties of an existing APDL Math object. |
| [[itengine\|*ITENGINE]] | `itengine` | Performs a solution using an iterative solver. |
| [[lsbac\|*LSBAC]] | `lsbac` | Performs the solve (forward/backward substitution) of a factorized linear system. |
| [[lsdump\|*LSDUMP]] | `lsdump` | Dumps a linear solver engine to a binary File. |
| [[lsengine\|*LSENGINE]] | `lsengine` | Creates a linear solver engine. |
| [[lsfactor\|*LSFACTOR]] | `lsfactor` | Performs the numerical factorization of a linear solver system. |
| [[lsrestore\|*LSRESTORE]] | `lsrestore` | Restores a linear solver engine from a binary file. |
| [[merge\|*MERGE]] | `merge` | Merges two dense matrices or vectors into one. |
| [[mfouri\|*MFOURI]] | `mfouri` | Calculates the coefficients for, or evaluates, a Fourier series. |
| [[mfun\|*MFUN]] | `mfun` | Copies or transposes an array parameter matrix. |
| [[mkdir\|/MKDIR]] | `mkdir` | Creates a directory. |
| [[moper\|*MOPER]] | `moper` | Performs matrix operations on array parameter matrices. |
| [[msg\|*MSG]] | `msg` | Writes an output message via the Mechanical APDL message subroutine. |
| [[mult\|*MULT]] | `mult` | Performs the matrix multiplication M3 = M1 <sup>(T1)</sup> \*M2 <sup>(T2)</sup>. |
| [[mwrite\|*MWRITE]] | `mwrite` | Writes a matrix to a file in a formatted sequence. |
| [[nrm\|*NRM]] | `nrm` | Computes the norm of the specified matrix or vector. |
| [[parres\|PARRES]] | `parres` | Reads parameters from a file. |
| [[parsav\|PARSAV]] | `parsav` | Writes parameters to a file. |
| [[pmacro\|/PMACRO]] | `pmacro` | Specifies that macro contents be written to the session log file. |
| [[starprint\|*PRINT]] | `starprint` | Prints the matrix values to a file. |
| [[psearch\|/PSEARCH]] | `psearch` | Specifies a directory to be searched for "unknown command" macro files. |
| [[remove\|*REMOVE]] | `remove` | Suppresses rows or columns of a dense matrix or a vector. |
| [[starrename\|*RENAME]] | `starrename` | Renames an existing vector or matrix. |
| [[rmdir\|/RMDIR]] | `rmdir` | Removes (deletes) a directory. |
| [[scal\|*SCAL]] | `scal` | Scales a vector or matrix by a constant. |
| [[starset\|*SET]] | `starset` | Assigns values to user-named parameters. |
| [[smat\|*SMAT]] | `smat` | Creates a sparse matrix. |
| [[starsort\|*SORT]] | `starsort` | Sorts the values of the specified vector. |
| [[sread\|*SREAD]] | `sread` | Reads a file into a string array parameter. |
| [[starstatus\|*STATUS]] | `starstatus` | Lists the current parameters and abbreviations. |
| [[taxis\|*TAXIS]] | `taxis` | Defines table index numbers. |
| [[slashtee\|/TEE]] | `slashtee` | Writes a list of commands to a specified file at the same time that the commands are being executed. |
| [[toper\|*TOPER]] | `toper` | Operates on table parameters. |
| [[tread\|*TREAD]] | `tread` | Reads data from an external file into a table array parameter. |
| [[ucmd\|/UCMD]] | `ucmd` | Assigns a user-defined command name. |
| [[ulib\|*ULIB]] | `ulib` | Identifies a macro library file. |
| [[use\|*USE]] | `use` | Executes a macro file. |
| [[vabs\|*VABS]] | `vabs` | Applies the absolute value function to array parameters. |
| [[vcol\|*VCOL]] | `vcol` | Specifies the number of columns in matrix operations. |
| [[vcum\|*VCUM]] | `vcum` | Allows array parameter results to add to existing results. |
| [[vec\|*VEC]] | `vec` | Creates a vector. |
| [[vfact\|*VFACT]] | `vfact` | Applies a scale factor to array parameters. |
| [[vfill\|*VFILL]] | `vfill` | Fills an array parameter. |
| [[vfun\|*VFUN]] | `vfun` | Performs a function on a single array parameter. |
| [[starvget\|*VGET]] | `starvget` | Retrieves values and stores them into an array parameter. |
| [[vitrp\|*VITRP]] | `vitrp` | Forms an array parameter by interpolation of a table. |
| [[vlen\|*VLEN]] | `vlen` | Specifies the number of rows to be used in array parameter operations. |
| [[vmask\|*VMASK]] | `vmask` | Specifies an array parameter as a masking vector. |
| [[voper\|*VOPER]] | `voper` | Operates on two array parameters. |
| [[starvplot\|*VPLOT]] | `starvplot` | Graphs columns (vectors) of array parameters. |
| [[starvput\|*VPUT]] | `starvput` | Restores array parameter values into the Mechanical APDL database. |
| [[vread\|*VREAD]] | `vread` | Reads data and produces an array parameter vector or matrix. |
| [[vscfun\|*VSCFUN]] | `vscfun` | Determines properties of an array parameter. |
| [[vstat\|*VSTAT]] | `vstat` | Lists the current specifications for the array parameters. |
| [[vwrite\|*VWRITE]] | `vwrite` | Writes data to a file in a formatted sequence. |
| [[wait\|/WAIT]] | `wait` | Causes a delay before the reading of the next command. |
| [[wrk\|*WRK]] | `wrk` | Sets the active workspace number. |
