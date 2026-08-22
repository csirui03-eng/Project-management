---
group: solution
generated: 2026-08-22
tags: [mapdl-command-index]
---

# Solution commands

These commands are used to load and solve the model.

334 commands. Back to [[MAPDL commands]].

| Command | Method | Summary |
|---|---|---|
| [[abextract\|ABEXTRACT]] | `abextract` | Extracts the alpha-beta damping multipliers for Rayleigh damping. |
| [[accoption\|ACCOPTION]] | `accoption` | Specifies GPU accelerator capability options. |
| [[acel\|ACEL]] | `acel` | Specifies the linear acceleration of the global Cartesian reference frame for the analysis. |
| [[adams\|ADAMS]] | `adams` | Performs solutions and writes flexible body information to a modal neutral file ( `Jobname.MNF` ) for use in an ADAMS analysis. |
| [[addam\|ADDAM]] | `addam` | Specifies the acceleration spectrum computation constants for the analysis of shock resistance of shipboard structures. |
| [[airl\|AIRL]] | `airl` | Specifies that automatic inertia relief calculations are to be performed. |
| [[alphad\|ALPHAD]] | `alphad` | Defines the mass matrix multiplier for damping. |
| [[ambeam\|AMBEAM]] | `ambeam` | For multiple-beam printers, specifies the number of beams in an [additive manufacturing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_cal.html) analysis. |
| [[ambuild\|AMBUILD]] | `ambuild` | Specifies printer parameters for the build and other options in an [additive manufacturing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_cal.html) analysis. |
| [[amenv\|AMENV]] | `amenv` | Specifies the build-environment thermal boundary conditions in an [additive manufacturing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_cal.html) analysis. |
| [[ammat\|AMMAT]] | `ammat` | Specifies the melting and relaxation temperatures of the build material in an [additive manufacturing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_cal.html) analysis. |
| [[ampowder\|AMPOWDER]] | `ampowder` | Specifies the thermal conditions of the powder in an [additive manufacturing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_cal.html) analysis. |
| [[amresult\|AMRESULT]] | `amresult` | Specifies [additive manufacturing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_cal.html) result data written to a `.txt` None file. |
| [[amstep\|AMSTEP]] | `amstep` | Specifies the process-sequence steps in an additive manufacturing analysis. |
| [[amsupports\|AMSUPPORTS]] | `amsupports` | Specifies information about the supports in an [additive manufacturing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_cal.html) analysis. |
| [[amtype\|AMTYPE]] | `amtype` | Specifies the printing process in an [additive manufacturing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_cal.html) analysis. |
| [[anpres\|ANPRES]] | `anpres` | Produces an animated sequence of the time-harmonic pressure variation of an engine-order excitation in a cyclic harmonic analysis. |
| [[antype\|ANTYPE]] | `antype` | Specifies the analysis type and restart status. |
| [[aport\|APORT]] | `aport` | Specifies input data for plane wave and acoustic duct ports. |
| [[arclen\|ARCLEN]] | `arclen` | Activates the arc-length method. |
| [[arctrm\|ARCTRM]] | `arctrm` | Controls termination of the solution when the arc-length method is used. |
| [[aremesh\|AREMESH]] | `aremesh` | Generates an area in which to create a new mesh for rezoning. |
| [[ascres\|ASCRES]] | `ascres` | Specifies the output type for an acoustic scattering analysis. |
| [[asifile\|ASIFILE]] | `asifile` | Writes or reads one-way acoustic-structural coupling data. |
| [[asol\|ASOL]] | `asol` | Specifies the acoustic solver with scattered field formulation. |
| [[atype\|ATYPE]] | `atype` | Specifies "Analysis types" as the subsequent status topic. |
| [[autots\|AUTOTS]] | `autots` | Specifies whether to use automatic time stepping or load stepping. |
| [[awave\|AWAVE]] | `awave` | Specifies input data for an acoustic incident wave. |
| [[bcsoption\|BCSOPTION]] | `bcsoption` | Sets memory option for the sparse solver. |
| [[betad\|BETAD]] | `betad` | Defines the stiffness matrix multiplier for damping. |
| [[bf\|BF]] | `bf` | Defines a nodal body-force load. |
| [[bfa\|BFA]] | `bfa` | Defines a body-force load on an area. |
| [[bfadele\|BFADELE]] | `bfadele` | Deletes body-force loads on an area. |
| [[bfalist\|BFALIST]] | `bfalist` | Lists the body-force loads on an area. |
| [[bfcum\|BFCUM]] | `bfcum` | Specifies that nodal body-force loads are to be accumulated. |
| [[bfdele\|BFDELE]] | `bfdele` | Deletes nodal body-force loads. |
| [[bfe\|BFE]] | `bfe` | Defines an element body-force load. |
| [[bfecum\|BFECUM]] | `bfecum` | Specifies whether to ignore subsequent element body force loads. |
| [[bfedele\|BFEDELE]] | `bfedele` | Deletes element body-force loads. |
| [[bfelist\|BFELIST]] | `bfelist` | Lists the element body-force loads. |
| [[bfescal\|BFESCAL]] | `bfescal` | Scales element body-force loads. |
| [[bfk\|BFK]] | `bfk` | Defines a body-force load at a keypoint. |
| [[bfkdele\|BFKDELE]] | `bfkdele` | Deletes body-force loads at a keypoint. |
| [[bfklist\|BFKLIST]] | `bfklist` | Lists the body-force loads at keypoints. |
| [[bfl\|BFL]] | `bfl` | Defines a body-force load on a line. |
| [[bfldele\|BFLDELE]] | `bfldele` | Deletes body-force loads on a line. |
| [[bflist\|BFLIST]] | `bflist` | Lists the body-force loads on nodes. |
| [[bfllist\|BFLLIST]] | `bfllist` | Lists the body-force loads on a line. |
| [[bfport\|BFPORT]] | `bfport` | Transfers a thermal body-force load (HGEN) from selected `MESH200` elements to reinforcing elements. |
| [[bfscale\|BFSCALE]] | `bfscale` | Scales body-force loads at nodes. |
| [[bftran\|BFTRAN]] | `bftran` | Transfers solid model body-force loads to the finite element model. |
| [[bfunif\|BFUNIF]] | `bfunif` | Assigns a uniform body-force load to all nodes. |
| [[bfv\|BFV]] | `bfv` | Defines a body-force load on a volume. |
| [[bfvdele\|BFVDELE]] | `bfvdele` | Deletes body-force loads on a volume. |
| [[bfvlist\|BFVLIST]] | `bfvlist` | Lists the body-force loads on a volume. |
| [[bioopt\|BIOOPT]] | `bioopt` | Specifies "Biot-Savart options" as the subsequent status topic. |
| [[biot\|BIOT]] | `biot` | Calculates the Biot-Savart source magnetic field intensity. |
| [[bucopt\|BUCOPT]] | `bucopt` | Specifies buckling analysis options. |
| [[campbell\|CAMPBELL]] | `campbell` | Prepares the result file for a subsequent Campbell diagram of a prestressed structure. |
| [[cecmod\|CECMOD]] | `cecmod` | Modifies the constant term of a constraint equation during solution. |
| [[cgloc\|CGLOC]] | `cgloc` | Specifies the origin location of the acceleration coordinate system. |
| [[cgomga\|CGOMGA]] | `cgomga` | Specifies the rotational velocity of the global origin. |
| [[cjump\|CJUMP]] | `cjump` | Initiates a [cycle-jump analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advcycjumpmethod.html#). |
| [[cload\|CLOAD]] | `cload` | Initiates a [cyclic-loading analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advcycloadprocess.html#). |
| [[cmacel\|CMACEL]] | `cmacel` | Specifies the translational acceleration of an element component |
| [[cmatrix\|CMATRIX]] | `cmatrix` | Performs electrostatic field solutions and calculates the self and mutual capacitances between multiple conductors. |
| [[cmdomega\|CMDOMEGA]] | `cmdomega` | Specifies the rotational acceleration of an element component about a user-defined rotational axis. |
| [[cmomega\|CMOMEGA]] | `cmomega` | Specifies the rotational velocity of an element component about a user-defined rotational axis. |
| [[cmrotate\|CMROTATE]] | `cmrotate` | Specifies the rotational velocity of an element component in a brake-squeal analysis. |
| [[cmsopt\|CMSOPT]] | `cmsopt` | Specifies component mode synthesis (CMS) analysis options. |
| [[cnkmod\|CNKMOD]] | `cnkmod` | Modifies contact element key options. |
| [[cntr\|CNTR]] | `cntr` | Redirects contact pair output quantities to a text file. |
| [[cnvtol\|CNVTOL]] | `cnvtol` | Sets convergence values for nonlinear analyses. |
| [[coriolis\|CORIOLIS]] | `coriolis` | Applies the Coriolis effect to a rotating structure. |
| [[coval\|COVAL]] | `coval` | Defines PSD cospectral values. |
| [[cqc\|CQC]] | `cqc` | Specifies the complete quadratic mode combination method. |
| [[crplim\|CRPLIM]] | `crplim` | Specifies the creep criterion for automatic time stepping. |
| [[cutcontrol\|CUTCONTROL]] | `cutcontrol` | Controls time-step cutback during a nonlinear solution. |
| [[d\|D]] | `d` | Defines degree-of-freedom constraints at nodes. |
| [[da\|DA]] | `da` | Defines degree-of-freedom constraints on areas. |
| [[dadele\|DADELE]] | `dadele` | Deletes degree-of-freedom constraints on an area. |
| [[dalist\|DALIST]] | `dalist` | Lists the DOF constraints on an area. |
| [[dampopt\|DAMPOPT]] | `dampopt` | Sets damped eigensolver options. |
| [[dcgomg\|DCGOMG]] | `dcgomg` | Specifies the rotational acceleration of the global origin. |
| [[dcum\|DCUM]] | `dcum` | Specifies that DOF constraint values are to be accumulated. |
| [[ddaspec\|DDASPEC]] | `ddaspec` | Specifies the shock spectrum computation constants for DDAM analysis. |
| [[ddele\|DDELE]] | `ddele` | Deletes degree-of-freedom constraints. |
| [[ddoption\|DDOPTION]] | `ddoption` | Sets domain decomposer option for a distributed-memory parallel (DMP) solution. |
| [[deact\|DEACT]] | `deact` | Specifies "Element birth and death" as the subsequent status topic. |
| [[deltim\|DELTIM]] | `deltim` | Specifies the time step sizes to be used for the current load step. |
| [[dflx\|DFLX]] | `dflx` | Imposes a uniform magnetic flux B on an edge-element electromagnetic model. |
| [[dfswave\|DFSWAVE]] | `dfswave` | Specifies the incident planar waves with random phases for a diffuse sound field. |
| [[dj\|DJ]] | `dj` | Specifies boundary conditions on the components of relative motion of a joint element. |
| [[djdele\|DJDELE]] | `djdele` | Deletes boundary conditions on the components of relative motion of a joint element. |
| [[djlist\|DJLIST]] | `djlist` | Lists boundary conditions applied to joint elements. |
| [[dk\|DK]] | `dk` | Defines DOF constraints at keypoints. |
| [[dkdele\|DKDELE]] | `dkdele` | Deletes DOF constraints at a keypoint. |
| [[dklist\|DKLIST]] | `dklist` | Lists the DOF constraints at keypoints. |
| [[dl\|DL]] | `dl` | Defines DOF constraints on lines. |
| [[dldele\|DLDELE]] | `dldele` | Deletes DOF constraints on a line. |
| [[dlist\|DLIST]] | `dlist` | Lists DOF constraints. |
| [[dllist\|DLLIST]] | `dllist` | Lists DOF constraints on a line. |
| [[dmpext\|DMPEXT]] | `dmpext` | Extracts modal damping coefficients in a specified frequency range. |
| [[dmpoption\|DMPOPTION]] | `dmpoption` | Specifies distributed-memory parallel ( DMP ) file combination options. |
| [[dmprat\|DMPRAT]] | `dmprat` | Sets a modal damping ratio. |
| [[dmpstr\|DMPSTR]] | `dmpstr` | Sets constant structural damping data. |
| [[domega\|DOMEGA]] | `domega` | Specifies the rotational acceleration of the structure. |
| [[dscale\|DSCALE]] | `dscale` | Scales DOF constraint values. |
| [[dspoption\|DSPOPTION]] | `dspoption` | Sets memory option for the sparse solver. |
| [[dsum\|DSUM]] | `dsum` | Specifies the double sum mode combination method. |
| [[dsym\|DSYM]] | `dsym` | Specifies symmetry or antisymmetry degree-of-freedom constraints on nodes. |
| [[dtran\|DTRAN]] | `dtran` | Transfers solid model DOF constraints to the finite element model. |
| [[dval\|DVAL]] | `dval` | Defines values at enforced motion base. |
| [[dynopt\|DYNOPT]] | `dynopt` | Specifies "Dynamic analysis options" as the subsequent status topic. |
| [[ealive\|EALIVE]] | `ealive` | Reactivates an element (for the birth and death capability). |
| [[ekill\|EKILL]] | `ekill` | Deactivates an element (for the birth and death capability). |
| [[ematwrite\|EMATWRITE]] | `ematwrite` | Forces the writing of all the element matrices to `Jobname.emat` None. |
| [[eqslv\|EQSLV]] | `eqslv` | Specifies the type of equation solver. |
| [[eresx\|ERESX]] | `eresx` | Specifies extrapolation of integration-point results. |
| [[estif\|ESTIF]] | `estif` | Specifies the matrix multiplier for deactivated elements. |
| [[exbopt\|EXBOPT]] | `exbopt` | Specifies `.EXB` file output options in a CMS generation pass. |
| [[expass\|EXPASS]] | `expass` | Specifies an expansion pass of an analysis. |
| [[expsol\|EXPSOL]] | `expsol` | Specifies the solution to be expanded for mode-superposition analyses or substructure analyses. |
| [[f\|F]] | `f` | Defines force loads at nodes. |
| [[fcum\|FCUM]] | `fcum` | Specifies that force loads are to be accumulated. |
| [[fdele\|FDELE]] | `fdele` | Deletes force loads on nodes. |
| [[fj\|FJ]] | `fj` | Specify forces or moments on the components of the relative motion of a joint element. |
| [[fjdele\|FJDELE]] | `fjdele` | Deletes forces (or moments) on the components of the relative motion of a joint element. |
| [[fjlist\|FJLIST]] | `fjlist` | Lists forces and moments applied on joint elements. |
| [[fk\|FK]] | `fk` | Defines force loads at keypoints. |
| [[fkdele\|FKDELE]] | `fkdele` | Deletes force loads at a keypoint. |
| [[fklist\|FKLIST]] | `fklist` | Lists the forces at keypoints. |
| [[flist\|FLIST]] | `flist` | Lists force loads on the nodes. |
| [[fluread\|FLUREAD]] | `fluread` | Reads one-way Fluent-to-Mechanical APDL coupling data via a `.cgns` file with one-side fast Fourier transformation complex pressure peak value. |
| [[freq\|FREQ]] | `freq` | Defines the frequency points for the [[sv|SV]] vs. **FREQ** tables. |
| [[frqscl\|FRQSCL]] | `frqscl` | Turns on automatic scaling of the entire mass matrix and frequency range for modal analyses. |
| [[fscale\|FSCALE]] | `fscale` | Scales force load values in the database. |
| [[ftran\|FTRAN]] | `ftran` | Transfers solid model forces to the finite element model. |
| [[gap\|GAP]] | `gap` | Specifies "mode-superposition transient gap conditions" as the subsequent status topic. |
| [[gauge\|GAUGE]] | `gauge` | Gauges the problem domain for a magnetic edge-element formulation. |
| [[genopt\|GENOPT]] | `genopt` | Specifies "General options" as the subsequent status topic. |
| [[gmatrix\|GMATRIX]] | `gmatrix` | Performs electric field solutions and calculates the self and mutual conductance between multiple conductors. |
| [[gp\|GP]] | `gp` | Defines a gap condition for transient analyses. |
| [[gpdele\|GPDELE]] | `gpdele` | Deletes gap conditions. |
| [[gplist\|GPLIST]] | `gplist` | Lists the gap conditions. |
| [[grp\|GRP]] | `grp` | Specifies the grouping mode combination method. |
| [[gsbdata\|GSBDATA]] | `gsbdata` | Specifies the constraints or applies the load at the ending point for generalized plane strain option. |
| [[gslist\|GSLIST]] | `gslist` | When using generalized plane strain, lists the input data or solutions. |
| [[gst\|/GST]] | `gst` | Enables the Graphical Solution Tracking (GST) feature. |
| [[harfrq\|HARFRQ]] | `harfrq` | Defines the frequency range in a harmonic analysis. |
| [[hemiopt\|HEMIOPT]] | `hemiopt` | Specifies options for Hemicube view factor calculation. |
| [[hrexp\|HREXP]] | `hrexp` | Specifies the phase angle for the harmonic analysis expansion pass. |
| [[hrocean\|HROCEAN]] | `hrocean` | Perform the harmonic ocean wave procedure (HOWP). |
| [[hropt\|HROPT]] | `hropt` | Specifies harmonic analysis options. |
| [[hrout\|HROUT]] | `hrout` | Specifies the harmonic analysis output options. |
| [[ic\|IC]] | `ic` | Specifies initial conditions at nodes. |
| [[icdele\|ICDELE]] | `icdele` | Deletes initial conditions at nodes. |
| [[iclist\|ICLIST]] | `iclist` | Lists the initial conditions. |
| [[icrotate\|ICROTATE]] | `icrotate` | Specifies initial velocity at nodes as a sum of rotation about an axis and translation. |
| [[inrtia\|INRTIA]] | `inrtia` | Specifies Inertial loads as the subsequent status topic. |
| [[invopt\|INVOPT]] | `invopt` | Enables or disables inverse solving for the current load step. |
| [[irlf\|IRLF]] | `irlf` | Specifies that inertia relief calculations are to be performed. |
| [[kbc\|KBC]] | `kbc` | Specifies ramped or stepped loading within a load step. |
| [[kryopt\|KRYOPT]] | `kryopt` | Specifies solution options for a Krylov method harmonic analysis. |
| [[kuse\|KUSE]] | `kuse` | Specifies whether or not to reuse factorized matrices. |
| [[lanboption\|LANBOPTION]] | `lanboption` | Specifies Block Lanczos eigensolver options. |
| [[ldread\|LDREAD]] | `ldread` | Reads results from the results file and applies them as loads. |
| [[lnsrch\|LNSRCH]] | `lnsrch` | Activates a line search to be used with Newton-Raphson. |
| [[lsclear\|LSCLEAR]] | `lsclear` | Clears loads and load step options from the database. |
| [[lsdele\|LSDELE]] | `lsdele` | Deletes load step files. |
| [[lsoper\|LSOPER]] | `lsoper` | Specifies "Load step operations" as the subsequent status topic. |
| [[lsread\|LSREAD]] | `lsread` | Reads load and load step option data into the database. |
| [[lssolve\|LSSOLVE]] | `lssolve` | Reads and solves multiple load steps. |
| [[lswrite\|LSWRITE]] | `lswrite` | Writes load and load step option data to a file. |
| [[lumpm\|LUMPM]] | `lumpm` | Specifies a lumped mass matrix formulation. |
| [[lvscale\|LVSCALE]] | `lvscale` | Scales the load vector for mode-superposition analyses. |
| [[m\|M]] | `m` | Defines master degrees of freedom (MDOFs) for superelement generation analyses. |
| [[magopt\|MAGOPT]] | `magopt` | Specifies options for a 3D magnetostatic field analysis. |
| [[magsolv\|MAGSOLV]] | `magsolv` | Specifies magnetic solution options and initiates the solution. |
| [[map2dto3d\|MAP2DTO3D]] | `map2dto3d` | Initiates a 2D to 3D analysis and maps variables. |
| [[mapsolve\|MAPSOLVE]] | `mapsolve` | Maps solved node and element solutions from an original mesh to a new mesh. |
| [[mapvar\|MAPVAR]] | `mapvar` | Defines tensors and vectors in user-defined state variables for rezoning and in 2D to 3D analyses. |
| [[mascale\|MASCALE]] | `mascale` | Activates scaling of the entire system matrix. |
| [[master\|MASTER]] | `master` | Specifies "Master DOF" as the subsequent status topic. |
| [[mcfopt\|MCFOPT]] | `mcfopt` | Specifies options for the Modal Coordinates File ( `Jobname.mcf` ). |
| [[mdamp\|MDAMP]] | `mdamp` | Defines the damping ratios as a function of mode. |
| [[mdele\|MDELE]] | `mdele` | Deletes master degrees of freedom. |
| [[mdplot\|MDPLOT]] | `mdplot` | Plots frequency-dependent modal damping coefficients calculated by DMPEXT. |
| [[mgen\|MGEN]] | `mgen` | Generates additional MDOF from a previously defined set. |
| [[midtol\|MIDTOL]] | `midtol` | Sets midstep residual criterion values for structural transient analyses. |
| [[mlist\|MLIST]] | `mlist` | Lists the MDOF of freedom. |
| [[mmass\|MMASS]] | `mmass` | Specifies the missing mass response calculation. |
| [[modcont\|MODCONT]] | `modcont` | Specify additional modal analysis options. |
| [[moddir\|MODDIR]] | `moddir` | Enables remote read-only usage of modal analysis files or substructuring analysis files. |
| [[mode\|MODE]] | `mode` | Specifies the harmonic loading term for this load step. |
| [[modopt\|MODOPT]] | `modopt` | Specifies modal analysis options. |
| [[modseloption\|MODSELOPTION]] | `modseloption` | Specifies the criteria for selecting the modes to be expanded. |
| [[monitor\|MONITOR]] | `monitor` | Controls contents of variable fields in the nonlinear solution monitor file. |
| [[mrpm\|MRPM]] | `mrpm` | Defines the revolutions per minute (RPM) for a machine rotation. |
| [[msave\|MSAVE]] | `msave` | Sets the solver memory saving option. This option only applies to the PCG solver (including PCG Lanczos). |
| [[msolve\|MSOLVE]] | `msolve` | Starts multiple solutions for an acoustic analysis. |
| [[mxpand\|MXPAND]] | `mxpand` | Specifies modal or buckling analysis expansion options. |
| [[ncnv\|NCNV]] | `ncnv` | Sets the key to terminate an analysis. |
| [[neqit\|NEQIT]] | `neqit` | Specifies the maximum number of equilibrium iterations for nonlinear analyses. |
| [[nladaptive\|NLADAPTIVE]] | `nladaptive` | Defines the criteria under which the mesh is refined or modified during a nonlinear solution. |
| [[nldiag\|NLDIAG]] | `nldiag` | Sets nonlinear diagnostics functionality. |
| [[nlgeom\|NLGEOM]] | `nlgeom` | Includes large-deflection effects in a static or full transient analysis. |
| [[nlhist\|NLHIST]] | `nlhist` | Specify results items to track during solution. |
| [[nlmesh\|NLMESH]] | `nlmesh` | Controls remeshing in [nonlinear adaptivity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVREZ.html). |
| [[nlopt\|NLOPT]] | `nlopt` | Specifies "Nonlinear analysis options" as the subsequent status topic. |
| [[nrlsum\|NRLSUM]] | `nrlsum` | Specifies the Naval Research Laboratory (NRL) sum mode combination method. |
| [[nropt\|NROPT]] | `nropt` | Specifies the Newton-Raphson options in a static or full transient analysis. |
| [[nsubst\|NSUBST]] | `nsubst` | Specifies the number of substeps to be taken this load step. |
| [[numexp\|NUMEXP]] | `numexp` | Specifies solutions to be expanded from mode-superposition analyses or substructure analyses. |
| [[ocdata\|OCDATA]] | `ocdata` | Defines an ocean load using non-table data. |
| [[ocdelete\|OCDELETE]] | `ocdelete` | Deletes a previously defined ocean load. |
| [[oclist\|OCLIST]] | `oclist` | Summarizes all currently defined ocean loads. |
| [[ocread\|OCREAD]] | `ocread` | Reads externally defined ocean data. |
| [[octable\|OCTABLE]] | `octable` | Defines an ocean load using table data. |
| [[octype\|OCTYPE]] | `octype` | Specifies the type of ocean load data to follow. |
| [[oczone\|OCZONE]] | `oczone` | Specifies the type of ocean zone data to follow. |
| [[omega\|OMEGA]] | `omega` | Specifies the rotational velocity of the structure. |
| [[opncontrol\|OPNCONTROL]] | `opncontrol` | Sets decision parameter for automatically increasing the time step interval in a pure thermal analysis. |
| [[osresult\|OSRESULT]] | `osresult` | Controls the selected result data written to the database. |
| [[outaero\|OUTAERO]] | `outaero` | Outputs the superelement matrices and load vectors to formatted files for aeroelastic analysis. |
| [[outgeom\|OUTGEOM]] | `outgeom` | Controls geometry-related data written to the results file. |
| [[outopt\|OUTOPT]] | `outopt` | Specifies "Output options" as the subsequent status topic. |
| [[outpr\|OUTPR]] | `outpr` | Controls the solution printout. |
| [[outres\|OUTRES]] | `outres` | Controls the solution-result data written to the database. |
| [[pcgopt\|PCGOPT]] | `pcgopt` | Controls PCG solver options. |
| [[perturb\|PERTURB]] | `perturb` | Sets linear perturbation analysis options. |
| [[pfact\|PFACT]] | `pfact` | Calculates participation factors for the PSD or multi-point response spectrum table. |
| [[pivcheck\|PIVCHECK]] | `pivcheck` | Controls the behavior of an analysis when a negative or zero equation solver pivot value is encountered. |
| [[pred\|PRED]] | `pred` | Activates a predictor in a nonlinear analysis. |
| [[prscontrol\|PRSCONTROL]] | `prscontrol` | Specifies whether to include pressure load stiffness in the element stiffness formation. |
| [[pscontrol\|PSCONTROL]] | `pscontrol` | Enables or disables shared-memory parallel operations. |
| [[psdcom\|PSDCOM]] | `psdcom` | Specifies the power spectral density mode combination method. |
| [[psdfrq\|PSDFRQ]] | `psdfrq` | Defines the frequency points for the input spectrum tables PSDVAL vs. PSDFRQ for PSD analysis. |
| [[psdgraph\|PSDGRAPH]] | `psdgraph` | Displays input PSD curves. |
| [[psdres\|PSDRES]] | `psdres` | Controls solution output written to the results file from a PSD analysis. |
| [[psdspl\|PSDSPL]] | `psdspl` | Defines a partially correlated excitation in a PSD analysis. |
| [[psdunit\|PSDUNIT]] | `psdunit` | Defines the type of input PSD. |
| [[psdval\|PSDVAL]] | `psdval` | Defines PSD values. |
| [[psdwav\|PSDWAV]] | `psdwav` | Defines a wave propagation excitation in a PSD analysis. |
| [[psolve\|PSOLVE]] | `psolve` | Directs the program to perform a partial solution. |
| [[pstres\|PSTRES]] | `pstres` | Specifies whether prestress effects are calculated or included. |
| [[qdval\|QDVAL]] | `qdval` | Defines PSD quadspectral values. |
| [[qrdopt\|QRDOPT]] | `qrdopt` | Specifies additional QRDAMP modal analysis options. |
| [[qsopt\|QSOPT]] | `qsopt` | Specifies quasi static radiation options. |
| [[radopt\|RADOPT]] | `radopt` | Specifies Radiosity Solver options. |
| [[rate\|RATE]] | `rate` | Specifies whether the effect of creep strain rate will be used in the solution of a load step. |
| [[rdec\|RDEC]] | `rdec` | Defines the decimation parameters used by the radiosity solver method. |
| [[remesh\|REMESH]] | `remesh` | Specifies the starting and ending remeshing points, and other options, for rezoning. |
| [[rescontrol\|RESCONTROL]] | `rescontrol` | Controls file writing for multiframe restarts. |
| [[resvec\|RESVEC]] | `resvec` | Calculates or includes residual vectors or residual responses |
| [[rezone\|REZONE]] | `rezone` | Initiates the rezoning process, sets rezoning options, and rebuilds the database. |
| [[rigid\|RIGID]] | `rigid` | Specifies known rigid body modes (if any) of the model. |
| [[rigresp\|RIGRESP]] | `rigresp` | Specifies the rigid response calculation. |
| [[rock\|ROCK]] | `rock` | Specifies a rocking response spectrum. |
| [[rose\|ROSE]] | `rose` | Specifies the Rosenblueth mode combination method. |
| [[rsopt\|RSOPT]] | `rsopt` | Creates or loads the radiosity mapping data file for `SURF251` or `SURF252` element types. |
| [[rstcontrol\|RSTCONTROL]] | `rstcontrol` | Controls whether element single value results are written to the results file. |
| [[rstoff\|RSTOFF]] | `rstoff` | Offsets node or element IDs in the FE geometry record. |
| [[rsurf\|RSURF]] | `rsurf` | Generates the radiosity surface elements and stores them in the database. |
| [[rsymm\|RSYMM]] | `rsymm` | Defines symmetry, rotation, or extrusion parameters for the radiosity method. |
| [[sbclist\|SBCLIST]] | `sbclist` | Lists solid model boundary conditions. |
| [[sbctran\|SBCTRAN]] | `sbctran` | Transfers solid model loads and boundary conditions to the FE model. |
| [[scopt\|SCOPT]] | `scopt` | Specifies System Coupling options. |
| [[sed\|SED]] | `sed` | Defines the excitation direction for response spectrum and PSD analyses. |
| [[seexp\|SEEXP]] | `seexp` | Specifies options for the substructure expansion pass. |
| [[semiimplicit\|SEMIIMPLICIT]] | `semiimplicit` | Specifies parameters for a semi-implicit solution. |
| [[seopt\|SEOPT]] | `seopt` | Specifies substructure analysis options. |
| [[sf\|SF]] | `sf` | Defines surface loads on nodes. |
| [[sfa\|SFA]] | `sfa` | Specifies surface loads on the selected areas. |
| [[sfadele\|SFADELE]] | `sfadele` | Deletes surface loads from areas. |
| [[sfalist\|SFALIST]] | `sfalist` | Lists the surface loads for the specified area. |
| [[sfbeam\|SFBEAM]] | `sfbeam` | Specifies surface loads on beam and pipe elements. |
| [[sfcontrol\|SFCONTROL]] | `sfcontrol` | Defines structural surface-load properties on selected elements and nodes for subsequent loading commands. |
| [[sfcum\|SFCUM]] | `sfcum` | Specifies that surface loads are to be accumulated. |
| [[sfdele\|SFDELE]] | `sfdele` | Deletes surface loads. |
| [[sfe\|SFE]] | `sfe` | Defines surface loads on elements. |
| [[sfedele\|SFEDELE]] | `sfedele` | Deletes surface loads from elements. |
| [[sfelist\|SFELIST]] | `sfelist` | Lists the surface loads for elements. |
| [[sffun\|SFFUN]] | `sffun` | Specifies a varying surface load. |
| [[sfgrad\|SFGRAD]] | `sfgrad` | Specifies a gradient (slope) for surface loads. |
| [[sfl\|SFL]] | `sfl` | Specifies surface loads on lines of an area. |
| [[sfldele\|SFLDELE]] | `sfldele` | Deletes surface loads from lines. |
| [[sflist\|SFLIST]] | `sflist` | Lists surface loads. |
| [[sfllist\|SFLLIST]] | `sfllist` | Lists the surface loads for lines. |
| [[sfscale\|SFSCALE]] | `sfscale` | Scales surface loads on elements. |
| [[sftran\|SFTRAN]] | `sftran` | Transfer the solid model surface loads to the finite element model. |
| [[smbody\|SMBODY]] | `smbody` | Specifies "Body loads on the solid model" as the subsequent status topic. |
| [[smcons\|SMCONS]] | `smcons` | Specifies "Constraints on the solid model" as the subsequent status topic. |
| [[smfor\|SMFOR]] | `smfor` | Specifies "Forces on the solid model" as the subsequent status topic. |
| [[smsurf\|SMSURF]] | `smsurf` | Specifies "Surface loads on the solid model" as the subsequent status topic. |
| [[snoption\|SNOPTION]] | `snoption` | Specifies Supernode (SNODE) eigensolver options. |
| [[soloption\|SOLOPTION]] | `soloption` | Specifies solution transition options. |
| [[soluopt\|SOLUOPT]] | `soluopt` | Specifies "Solution options" as the subsequent status topic. |
| [[solve\|SOLVE]] | `solve` | Starts a solution. |
| [[spcnod\|SPCNOD]] | `spcnod` | Defines a space node for radiation using the Radiosity method. |
| [[spctemp\|SPCTEMP]] | `spctemp` | Defines a free-space ambient temperature for radiation using the Radiosity method. |
| [[spdamp\|SPDAMP]] | `spdamp` | Defines input spectrum damping in a multi-point response spectrum analysis. |
| [[spfreq\|SPFREQ]] | `spfreq` | Defines the frequency points for the input spectrum tables [[spval|SPVAL]] vs. **SPFREQ** for multi- point spectrum analysis. |
| [[spgraph\|SPGRAPH]] | `spgraph` | Displays input spectrum curves for MPRS analysis. |
| [[spopt\|SPOPT]] | `spopt` | Selects the spectrum type and other spectrum options. |
| [[sptopt\|SPTOPT]] | `sptopt` | Specifies "Spectrum analysis options" as the subsequent status topic. |
| [[spunit\|SPUNIT]] | `spunit` | Defines the type of multi-point response spectrum. |
| [[spval\|SPVAL]] | `spval` | Defines multi-point response spectrum values. |
| [[srss\|SRSS]] | `srss` | Specifies the square root of sum of squares mode combination method. |
| [[ssopt\|SSOPT]] | `ssopt` | Defines a solution option for soil analysis. |
| [[sstif\|SSTIF]] | `sstif` | Activates stress stiffness effects in a nonlinear analysis. |
| [[stabilize\|STABILIZE]] | `stabilize` | Activates stabilization for all elements that support nonlinear stabilization. |
| [[subopt\|SUBOPT]] | `subopt` | Specifies Subspace (SUBSP) eigensolver options. |
| [[sv\|SV]] | `sv` | Defines spectrum values to be associated with frequency points. |
| [[svplot\|SVPLOT]] | `svplot` | Displays input spectrum curves. |
| [[svtyp\|SVTYP]] | `svtyp` | Defines the type of single-point response spectrum. |
| [[synchro\|SYNCHRO]] | `synchro` | Specifies whether the excitation frequency is synchronous or asynchronous with the rotational velocity of a structure. |
| [[thexpand\|THEXPAND]] | `thexpand` | Enables or disables thermal loading |
| [[thopt\|THOPT]] | `thopt` | Specifies nonlinear transient thermal solution options. |
| [[time\|TIME]] | `time` | Sets the time for a load step. |
| [[timint\|TIMINT]] | `timint` | Turns on transient effects. |
| [[tintp\|TINTP]] | `tintp` | Defines transient integration parameters. |
| [[toffst\|TOFFST]] | `toffst` | Specifies the temperature offset from absolute zero to zero. |
| [[tref\|TREF]] | `tref` | Defines the reference temperature for thermal strain calculations. |
| [[trnopt\|TRNOPT]] | `trnopt` | Specifies transient analysis options. |
| [[tsres\|TSRES]] | `tsres` | Defines an array of key times at which the time-stepping strategy changes. |
| [[tunif\|TUNIF]] | `tunif` | Assigns a uniform temperature to all nodes. |
| [[upcoord\|UPCOORD]] | `upcoord` | Modifies the coordinates of the active set of nodes, based on the current displacements. |
| [[usrcal\|USRCAL]] | `usrcal` | Allows user-solution subroutines to be activated or deactivated. |
| [[v2dopt\|V2DOPT]] | `v2dopt` | Specifies 2D/axisymmetric view factor calculation options. |
| [[vddam\|VDDAM]] | `vddam` | Specifies the velocity spectrum computation constants for the analysis of shock resistance of shipboard structures. |
| [[vfopt\|VFOPT]] | `vfopt` | Specifies options for the view factor file and calculates view factors. |
| [[wrfull\|WRFULL]] | `wrfull` | Stops solution after assembling global matrices. |
| [[wsprings\|WSPRINGS]] | `wsprings` | Creates weak springs on corner nodes of a bounding box of the currently selected elements. |
