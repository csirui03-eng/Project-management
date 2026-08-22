---
group: prep7
generated: 2026-08-22
tags: [mapdl-command-index]
---

# Preprocessing commands

These commands are used to create and set up the model.

518 commands. Back to [[MAPDL commands]].

| Command | Method | Summary |
|---|---|---|
| [[a\|A]] | `a` | Defines an area by connecting keypoints. |
| [[aadd\|AADD]] | `aadd` | Adds separate areas to create a single area. |
| [[aatt\|AATT]] | `aatt` | Associates element attributes with the selected, unmeshed areas. |
| [[accat\|ACCAT]] | `accat` | Concatenates multiple areas in preparation for mapped meshing. |
| [[aclear\|ACLEAR]] | `aclear` | Deletes nodes and area elements associated with selected areas. |
| [[adele\|ADELE]] | `adele` | Deletes unmeshed areas. |
| [[adgl\|ADGL]] | `adgl` | Lists keypoints of an area that lie on a parametric degeneracy. |
| [[adpci\|ADPCI]] | `adpci` | Defines parameters associated with adaptive crack initiation. |
| [[adrag\|ADRAG]] | `adrag` | Generates areas by dragging a line pattern along a path. |
| [[aerocoeff\|AEROCOEFF]] | `aerocoeff` | Computes the aero-damping and stiffness coefficients and writes them to an APDL array. |
| [[aesize\|AESIZE]] | `aesize` | Specifies the element size to be meshed onto areas. |
| [[afillt\|AFILLT]] | `afillt` | Generates a fillet at the intersection of two areas. |
| [[aflist\|AFLIST]] | `aflist` | Lists the current data in the database. |
| [[afsurf\|AFSURF]] | `afsurf` | Generates surface elements overlaid on the surface of existing solid elements and assigns the extra node as the closest fluid element node. |
| [[agen\|AGEN]] | `agen` | Generates additional areas from a pattern of areas. |
| [[aglue\|AGLUE]] | `aglue` | Generates new areas by "gluing" areas. |
| [[aina\|AINA]] | `aina` | Finds the intersection of areas. |
| [[ainp\|AINP]] | `ainp` | Finds the pairwise intersection of areas. |
| [[ainv\|AINV]] | `ainv` | Finds the intersection of an area with a volume. |
| [[al\|AL]] | `al` | Generates an area bounded by previously defined lines. |
| [[alist\|ALIST]] | `alist` | Lists the defined areas. |
| [[amap\|AMAP]] | `amap` | Generates a 2D mapped mesh based on specified area corners. |
| [[amesh\|AMESH]] | `amesh` | Generates nodes and area elements within areas. |
| [[anorm\|ANORM]] | `anorm` | Reorients area normals. |
| [[aoffst\|AOFFST]] | `aoffst` | Generates an area, offset from a given area. |
| [[aovlap\|AOVLAP]] | `aovlap` | Overlaps areas. |
| [[aplot\|APLOT]] | `aplot` | Displays the selected areas. |
| [[aptn\|APTN]] | `aptn` | Partitions areas. |
| [[areas\|AREAS]] | `areas` | Specifies "Areas" as the subsequent status topic. |
| [[arefine\|AREFINE]] | `arefine` | Refines the mesh around specified areas. |
| [[areverse\|AREVERSE]] | `areverse` | Reverses the normal of an area, regardless of its connectivity or mesh status. |
| [[arotat\|AROTAT]] | `arotat` | Generates cylindrical areas by rotating a line pattern about an axis. |
| [[arscale\|ARSCALE]] | `arscale` | Generates a scaled set of areas from a pattern of areas. |
| [[arsym\|ARSYM]] | `arsym` | Generates areas from an area pattern by symmetry reflection. |
| [[asba\|ASBA]] | `asba` | Subtracts areas from areas. |
| [[asbl\|ASBL]] | `asbl` | Subtracts lines from areas. |
| [[asbv\|ASBV]] | `asbv` | Subtracts volumes from areas. |
| [[asbw\|ASBW]] | `asbw` | Subtracts the intersection of the working plane from areas (divides areas). |
| [[askin\|ASKIN]] | `askin` | Generates an area by "skinning" a surface through guiding lines. |
| [[asub\|ASUB]] | `asub` | Generates an area using the shape of an existing area. |
| [[asum\|ASUM]] | `asum` | Calculates and prints geometry statistics of the selected areas. |
| [[atran\|ATRAN]] | `atran` | Transfers a pattern of areas to another coordinate system. |
| [[bellow\|BELLOW]] | `bellow` | Defines a bellows in a piping run. |
| [[bend\|BEND]] | `bend` | Defines a bend in a piping run. |
| [[blc4\|BLC4]] | `blc4` | Creates a rectangular area or block volume by corner points. |
| [[blc5\|BLC5]] | `blc5` | Creates a rectangular area or block volume by center and corner points. |
| [[block\|BLOCK]] | `block` | Creates a block volume based on working plane coordinates. |
| [[bool\|BOOL]] | `bool` | Specifies "Booleans" as the subsequent status topic. |
| [[boptn\|BOPTN]] | `boptn` | Specifies Boolean operation options. |
| [[branch\|BRANCH]] | `branch` | Defines the starting point for a piping branch. |
| [[bsax\|BSAX]] | `bsax` | Specifies the axial strain and axial force relationship for beam sections. |
| [[bsm1\|BSM1]] | `bsm1` | Specifies the bending curvature and moment relationship in plane XZ for beam sections. |
| [[bsm2\|BSM2]] | `bsm2` | Specifies the bending curvature and moment relationship in plane XY for beam sections. |
| [[bsmd\|BSMD]] | `bsmd` | Specifies mass per unit length for a nonlinear general beam section. |
| [[bsplin\|BSPLIN]] | `bsplin` | Generates a single line from a spline fit to a series of keypoints. |
| [[bss1\|BSS1]] | `bss1` | Specifies the transverse shear strain and force relationship in plane XZ for beam sections. |
| [[bss2\|BSS2]] | `bss2` | Specifies the transverse shear strain and force relationship in plane XY for beam sections. |
| [[bste\|BSTE]] | `bste` | Specifies a thermal expansion coefficient for a nonlinear general beam section. |
| [[bstq\|BSTQ]] | `bstq` | Specifies the cross section twist and torque relationship for beam sections. |
| [[btol\|BTOL]] | `btol` | Specifies the Boolean operation tolerances. |
| [[cbmd\|CBMD]] | `cbmd` | Specifies preintegrated section mass matrix for composite-beam sections. |
| [[cbmx\|CBMX]] | `cbmx` | Specifies preintegrated cross-section stiffness for composite beam sections. |
| [[cbte\|CBTE]] | `cbte` | Specifies a thermal expansion coefficient for a composite beam section. |
| [[cbtmp\|CBTMP]] | `cbtmp` | Specifies a temperature for composite-beam input. |
| [[cdopt\|CDOPT]] | `cdopt` | Specifies format to be used for archiving geometry. |
| [[cdread\|CDREAD]] | `cdread` | Reads a file of solid model and database information into the database. |
| [[cdwrite\|CDWRITE]] | `cdwrite` | Writes geometry and load database items to a file. |
| [[ce\|CE]] | `ce` | Defines a constraint equation relating degrees of freedom. |
| [[cecheck\|CECHECK]] | `cecheck` | Check constraint equations and couplings for rigid body motions. |
| [[cecyc\|CECYC]] | `cecyc` | Generates the constraint equations for a cyclic symmetry analysis |
| [[cecycms\|CECYCMS]] | `cecycms` | Generates the constraint equations for a [multistage cyclic symmetry analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/ans_mstag_introTheory.html). |
| [[cedele\|CEDELE]] | `cedele` | Deletes constraint equations. |
| [[ceims\|CEIMS]] | `ceims` | Generates constraint equations at the interstage boundary in a [multistage cyclic symmetry analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/ans_mstag_introTheory.html). |
| [[ceintf\|CEINTF]] | `ceintf` | Generates constraint equations at an interface. |
| [[celist\|CELIST]] | `celist` | Lists the constraint equations. |
| [[center\|CENTER]] | `center` | Defines a node at the center of curvature of 2 or 3 nodes. |
| [[ceqn\|CEQN]] | `ceqn` | Specifies "Constraint equations" as the subsequent status topic. |
| [[cerig\|CERIG]] | `cerig` | Defines a rigid region. |
| [[cesel\|CESEL]] | `cesel` | Selects constraint equations via predefined reference numbers. |
| [[cesgen\|CESGEN]] | `cesgen` | Generates a set of constraint equations from existing sets. |
| [[cgrow\|CGROW]] | `cgrow` | Specifies crack-growth options in a fracture analysis. |
| [[check\|CHECK]] | `check` | Checks current database items for completeness. |
| [[chkmsh\|CHKMSH]] | `chkmsh` | Checks area and volume entities for previous meshes. |
| [[cint\|CINT]] | `cint` | Defines parameters associated with fracture-parameter calculations. |
| [[circle\|CIRCLE]] | `circle` | Generates circular arc lines. |
| [[clrmshln\|CLRMSHLN]] | `clrmshln` | Clears meshed entities. |
| [[cncheck\|CNCHECK]] | `cncheck` | Provides and/or adjusts the initial status of contact pairs. |
| [[con4\|CON4]] | `con4` | Creates a conical volume anywhere on the working plane. |
| [[cone\|CONE]] | `cone` | Creates a conical volume centered about the working plane origin. |
| [[couple\|COUPLE]] | `couple` | Specifies "Node coupling" as the subsequent status topic. |
| [[cp\|CP]] | `cp` | Defines (or modifies) a set of coupled degrees of freedom. |
| [[cpcyc\|CPCYC]] | `cpcyc` | Couples the two side faces of a cyclically symmetric model for loadings that are the same on every segment. |
| [[cpdele\|CPDELE]] | `cpdele` | Deletes coupled degree of freedom sets. |
| [[cpintf\|CPINTF]] | `cpintf` | Defines coupled degrees of freedom at an interface. |
| [[cplgen\|CPLGEN]] | `cplgen` | Generates sets of coupled nodes from an existing set. |
| [[cplist\|CPLIST]] | `cplist` | Lists the coupled degree of freedom sets. |
| [[cpmerge\|CPMERGE]] | `cpmerge` | Merges different couple sets with duplicate degrees of freedom into one couple set. |
| [[cpngen\|CPNGEN]] | `cpngen` | Defines, modifies, or adds to a set of coupled degrees of freedom. |
| [[cpsel\|CPSEL]] | `cpsel` | Selects coupled degree-of-freedom sets via predefined reference numbers. |
| [[cpsgen\|CPSGEN]] | `cpsgen` | Generates sets of coupled nodes from existing sets. |
| [[cycexpand\|/CYCEXPAND]] | `cycexpand` | Graphically expands displacements, stresses and strains of a cyclically symmetric model. |
| [[cycfreq\|CYCFREQ]] | `cycfreq` | Specifies solution options for a cyclic symmetry mode-superposition harmonic analysis. |
| [[cyclic\|CYCLIC]] | `cyclic` | Specifies a cyclic symmetry analysis. |
| [[cycopt\|CYCOPT]] | `cycopt` | Specifies solution options for a cyclic symmetry analysis. |
| [[cyl4\|CYL4]] | `cyl4` | Creates a circular area or cylindrical volume anywhere on the working plane. |
| [[cyl5\|CYL5]] | `cyl5` | Creates a circular area or cylindrical volume by end points. |
| [[cylind\|CYLIND]] | `cylind` | Creates a cylindrical volume centered about the working plane origin. |
| [[czdel\|CZDEL]] | `czdel` | Edits or clears cohesive zone sections. |
| [[czmesh\|CZMESH]] | `czmesh` | Create and mesh an interface area composed of cohesive zone elements. |
| [[damorph\|DAMORPH]] | `damorph` | Move nodes in selected areas to conform to structural displacements. |
| [[demorph\|DEMORPH]] | `demorph` | Move nodes in selected elements to conform to structural displacements. |
| [[desize\|DESIZE]] | `desize` | Controls default element sizes. |
| [[dflab\|/DFLAB]] | `dflab` | Changes degree-of-freedom labels for user custom elements. |
| [[dof\|DOF]] | `dof` | Adds degrees of freedom to the current DOF set. |
| [[dvmorph\|DVMORPH]] | `dvmorph` | Move nodes in selected volumes to conform to structural displacements. |
| [[e\|E]] | `e` | Defines an element by node connectivity. |
| [[ecpchg\|ECPCHG]] | `ecpchg` | Optimizes degree-of-freedom usage in a coupled acoustic model. |
| [[edadapt\|EDADAPT]] | `edadapt` | Activates adaptive meshing in an explicit dynamic analysis. |
| [[edale\|EDALE]] | `edale` | Assigns mesh smoothing to explicit dynamic elements that use |
| [[edasmp\|EDASMP]] | `edasmp` | Creates a part assembly to be used in an explicit dynamic analysis. |
| [[edbound\|EDBOUND]] | `edbound` | Defines a boundary plane for sliding or cyclic symmetry. |
| [[edbvis\|EDBVIS]] | `edbvis` | Specifies global bulk viscosity coefficients for an explicit dynamics |
| [[edbx\|EDBX]] | `edbx` | Creates a box shaped volume to be used in a contact definition for |
| [[edcadapt\|EDCADAPT]] | `edcadapt` | Specifies adaptive meshing controls for an explicit dynamic analysis. |
| [[edcgen\|EDCGEN]] | `edcgen` | Specifies contact parameters for an explicit dynamics analysis. |
| [[edclist\|EDCLIST]] | `edclist` | Lists contact entity specifications in an explicit dynamics analysis. |
| [[edcmore\|EDCMORE]] | `edcmore` | Specifies additional contact parameters for a given contact definition |
| [[edcnstr\|EDCNSTR]] | `edcnstr` | Defines various types of constraints for an explicit dynamic analysis. |
| [[edcontact\|EDCONTACT]] | `edcontact` | Specifies contact surface controls for an explicit dynamics analysis. |
| [[edcpu\|EDCPU]] | `edcpu` | Specifies CPU time limit for an explicit dynamics analysis. |
| [[edcrb\|EDCRB]] | `edcrb` | Constrains two rigid bodies to act as one in an explicit dynamics |
| [[edcsc\|EDCSC]] | `edcsc` | Specifies whether to use subcycling in an explicit dynamics analysis. |
| [[edcts\|EDCTS]] | `edcts` | Specifies mass scaling and scale factor of computed time step for an |
| [[edcurve\|EDCURVE]] | `edcurve` | Specifies data curves for an explicit dynamic analysis. |
| [[eddamp\|EDDAMP]] | `eddamp` | Defines mass weighted (Alpha) or stiffness weighted (Beta) damping for |
| [[eddbl\|EDDBL]] | `eddbl` | Selects a numerical precision type of the explicit dynamics analysis. |
| [[eddc\|EDDC]] | `eddc` | Deletes or deactivates/reactivates contact surface specifications in an |
| [[eddrelax\|EDDRELAX]] | `eddrelax` | Activates initialization to a prescribed geometry or dynamic relaxation |
| [[eddump\|EDDUMP]] | `eddump` | Specifies output frequency for the explicit dynamic restart file |
| [[edele\|EDELE]] | `edele` | Deletes selected elements from the model. |
| [[edenergy\|EDENERGY]] | `edenergy` | Specifies energy dissipation controls for an explicit dynamics |
| [[edfplot\|EDFPLOT]] | `edfplot` | Allows plotting of explicit dynamics forces and other load symbols. |
| [[edgcale\|EDGCALE]] | `edgcale` | Defines global ALE controls for an explicit dynamic analysis. |
| [[edhgls\|EDHGLS]] | `edhgls` | Specifies the hourglass coefficient for an explicit dynamics analysis. |
| [[edhist\|EDHIST]] | `edhist` | Specifies time-history output for an explicit dynamic analysis. |
| [[edhtime\|EDHTIME]] | `edhtime` | Specifies the time-history output interval for an explicit dynamics |
| [[edint\|EDINT]] | `edint` | Specifies number of integration points for explicit shell and beam |
| [[edipart\|EDIPART]] | `edipart` | Defines inertia for rigid parts in an explicit dynamics analysis. |
| [[edis\|EDIS]] | `edis` | Specifies stress initialization in an explicit dynamic full restart |
| [[edlcs\|EDLCS]] | `edlcs` | Defines a local coordinate system for use in explicit dynamics |
| [[edload\|EDLOAD]] | `edload` | Specifies loads for an explicit dynamics analysis. |
| [[edmp\|EDMP]] | `edmp` | Defines material properties for an explicit dynamics analysis. |
| [[ednb\|EDNB]] | `ednb` | Defines a nonreflecting boundary in an explicit dynamic analysis. |
| [[edndtsd\|EDNDTSD]] | `edndtsd` | Allows smoothing of noisy data for explicit dynamics analyses and |
| [[ednrot\|EDNROT]] | `ednrot` | Applies a rotated coordinate nodal constraint in an explicit dynamics |
| [[edopt\|EDOPT]] | `edopt` | Specifies the type of output for an explicit dynamics analysis. |
| [[edout\|EDOUT]] | `edout` | Specifies time-history output (ASCII format) for an explicit dynamics |
| [[edpart\|EDPART]] | `edpart` | Configures parts for an explicit dynamics analysis. |
| [[edpc\|EDPC]] | `edpc` | Selects and plots explicit dynamic contact entities. |
| [[edpl\|EDPL]] | `edpl` | Plots a time dependent load curve in an explicit dynamic analysis. |
| [[edpvel\|EDPVEL]] | `edpvel` | Applies initial velocities to parts or part assemblies in an explicit |
| [[edrc\|EDRC]] | `edrc` | Specifies rigid/deformable switch controls in an explicit dynamic |
| [[edrd\|EDRD]] | `edrd` | Switches a part from deformable to rigid or from rigid to deformable in |
| [[edri\|EDRI]] | `edri` | Defines inertia properties for a new rigid body that is created when a |
| [[edrst\|EDRST]] | `edrst` | Specifies the output interval for an explicit dynamic analysis. |
| [[edrun\|EDRUN]] | `edrun` | Specify LS-DYNA serial or parallel processing. |
| [[edshell\|EDSHELL]] | `edshell` | Specifies shell computation controls for an explicit dynamics analysis. |
| [[edsolv\|EDSOLV]] | `edsolv` | Specifies "explicit dynamics solution" as the subsequent status topic. |
| [[edsp\|EDSP]] | `edsp` | Specifies small penetration checking for contact entities in an |
| [[edstart\|EDSTART]] | `edstart` | Specifies status (new or restart) of an explicit dynamics analysis. |
| [[edterm\|EDTERM]] | `edterm` | Specifies termination criteria for an explicit dynamic analysis. |
| [[edtp\|EDTP]] | `edtp` | Plots explicit elements based on their time step size. |
| [[edvel\|EDVEL]] | `edvel` | Applies initial velocities to nodes or node components in an explicit |
| [[edweld\|EDWELD]] | `edweld` | Defines a massless spotweld or generalized weld for use in an explicit |
| [[edwrite\|EDWRITE]] | `edwrite` | Writes explicit dynamics input to an LS-DYNA input file. |
| [[eembed\|EEMBED]] | `eembed` | Generates bonded connections between intersecting elements. |
| [[eextrude\|EEXTRUDE]] | `eextrude` | Extrudes 2D plane elements into 3D solids during a 2D to 3D analysis. |
| [[egen\|EGEN]] | `egen` | Generates elements from an existing pattern. |
| [[egid\|EGID]] | `egid` | Specifies a global identifier for a set of `MESH200` elements. |
| [[einfin\|EINFIN]] | `einfin` | Generates structural infinite elements from selected nodes. |
| [[eintf\|EINTF]] | `eintf` | Defines two-node elements between coincident or offset nodes. |
| [[elbow\|ELBOW]] | `elbow` | Specifies degrees of freedom to be coupled for end release and applies section constraints to elbow elements. |
| [[elem\|ELEM]] | `elem` | Specifies "Elements" as the subsequent status topic. |
| [[elist\|ELIST]] | `elist` | Lists the elements and their attributes. |
| [[emid\|EMID]] | `emid` | Adds or removes midside nodes. |
| [[emodif\|EMODIF]] | `emodif` | Modifies a previously defined element. |
| [[emore\|EMORE]] | `emore` | Adds more nodes to the just-defined element. |
| [[emsel\|EMSEL]] | `emsel` | Selects a group of [reinforcing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_compreinfdirectemb.html) members via a predefined global identifier. |
| [[emsym\|EMSYM]] | `emsym` | Specifies circular symmetry for electromagnetic sources. |
| [[emtgen\|EMTGEN]] | `emtgen` | Generates a set of `TRANS126` elements. |
| [[emunit\|EMUNIT]] | `emunit` | Specifies the system of units for magnetic field problems. |
| [[en\|EN]] | `en` | Defines an element by its number and node connectivity. |
| [[endrelease\|ENDRELEASE]] | `endrelease` | Specifies degrees of freedom to be decoupled for end release. |
| [[engen\|ENGEN]] | `engen` | Generates elements from an existing pattern. |
| [[enorm\|ENORM]] | `enorm` | Reorients shell element normals or line element node connectivity. |
| [[ensym\|ENSYM]] | `ensym` | Generates elements by symmetry reflection. |
| [[eorient\|EORIENT]] | `eorient` | Reorients solid element normals. |
| [[eplot\|EPLOT]] | `eplot` | Produces an element display. |
| [[eread\|EREAD]] | `eread` | Reads elements from a file. |
| [[erefine\|EREFINE]] | `erefine` | Refines the mesh around specified elements. |
| [[ereinf\|EREINF]] | `ereinf` | Generates reinforcing elements from selected existing (base) elements. |
| [[errang\|ERRANG]] | `errang` | Specifies the element range to be read from a file. |
| [[escheck\|ESCHECK]] | `escheck` | Perform element shape checking for a selected element set. |
| [[esize\|ESIZE]] | `esize` | Specifies the default number of line divisions. |
| [[esurf\|ESURF]] | `esurf` | Generates elements overlaid on the free faces of selected nodes. |
| [[esym\|ESYM]] | `esym` | Generates elements from a pattern by a symmetry reflection. |
| [[esys\|ESYS]] | `esys` | Sets the element coordinate system attribute pointer. |
| [[et\|ET]] | `et` | Defines a local element type from the element library. |
| [[etchg\|ETCHG]] | `etchg` | Changes element types to their corresponding types. |
| [[etcontrol\|ETCONTROL]] | `etcontrol` | Control the element technologies used in element formulation (for applicable elements). |
| [[etdele\|ETDELE]] | `etdele` | Deletes element types. |
| [[etlist\|ETLIST]] | `etlist` | Lists currently defined element types. |
| [[etype\|ETYPE]] | `etype` | Specifies "Element types" as the subsequent status topic. |
| [[ewrite\|EWRITE]] | `ewrite` | Writes elements to a file. |
| [[extopt\|EXTOPT]] | `extopt` | Controls options relating to the generation of volume elements from area elements. |
| [[fatigue\|FATIGUE]] | `fatigue` | Specifies "Fatigue data status" as the subsequent status topic. |
| [[fc\|FC]] | `fc` | Provides failure criteria information and activates a data table to input temperature-dependent stress and strain limits. |
| [[fccheck\|FCCHECK]] | `fccheck` | Checks both the strain and stress input criteria for all materials. |
| [[fcdele\|FCDELE]] | `fcdele` | Deletes previously defined failure criterion data for the given material. |
| [[fclist\|FCLIST]] | `fclist` | To list what the failure criteria is that you have input. |
| [[febody\|FEBODY]] | `febody` | Specifies "Body loads on elements" as the subsequent status topic. |
| [[fecons\|FECONS]] | `fecons` | Specifies "Constraints on nodes" as the subsequent status topic. |
| [[fefor\|FEFOR]] | `fefor` | Specifies "Forces on nodes" as the subsequent status topic. |
| [[fesurf\|FESURF]] | `fesurf` | Specifies "Surface loads on elements" as the subsequent status topic. |
| [[fill\|FILL]] | `fill` | Generates a line of nodes between two existing nodes. |
| [[flange\|FLANGE]] | `flange` | Defines a flange in a piping run. |
| [[fvmesh\|FVMESH]] | `fvmesh` | Generates nodes and tetrahedral volume elements from detached exterior area elements (facets). |
| [[gcdef\|GCDEF]] | `gcdef` | Defines interface interactions between general contact surfaces. |
| [[gcgen\|GCGEN]] | `gcgen` | Creates contact elements for general contact. |
| [[geometry\|GEOMETRY]] | `geometry` | Specifies "Geometry" as the subsequent status topic. |
| [[gsgdata\|GSGDATA]] | `gsgdata` | Specifies the reference point and defines the geometry in the fiber direction for the generalized plane strain element option. |
| [[gsum\|GSUM]] | `gsum` | Calculates and prints geometry items. |
| [[hptcreate\|HPTCREATE]] | `hptcreate` | Defines a hard point. |
| [[hptdelete\|HPTDELETE]] | `hptdelete` | Deletes selected hardpoints. |
| [[igesout\|IGESOUT]] | `igesout` | Writes solid model data to a file in IGES Version 5.1 format. |
| [[imesh\|IMESH]] | `imesh` | Generates nodes and interface elements along lines or areas. |
| [[inistate\|INISTATE]] | `inistate` | Defines initial-state data and parameters. |
| [[k\|K]] | `k` | Defines a keypoint. |
| [[katt\|KATT]] | `katt` | Associates attributes with the selected, unmeshed keypoints. |
| [[kbetw\|KBETW]] | `kbetw` | Creates a keypoint between two existing keypoints. |
| [[kcenter\|KCENTER]] | `kcenter` | Creates a keypoint at the center of a circular arc defined by three locations. |
| [[kclear\|KCLEAR]] | `kclear` | Deletes nodes and point elements associated with selected keypoints. |
| [[kdele\|KDELE]] | `kdele` | Deletes unmeshed keypoints. |
| [[kdist\|KDIST]] | `kdist` | Calculates and lists the distance between two keypoints. |
| [[kesize\|KESIZE]] | `kesize` | Specifies the edge lengths of the elements nearest a keypoint. |
| [[keyopt\|KEYOPT]] | `keyopt` | Sets element key options. |
| [[keypts\|KEYPTS]] | `keypts` | Specifies "Keypoints" as the subsequent status topic. |
| [[kfill\|KFILL]] | `kfill` | Generates keypoints between two keypoints. |
| [[kgen\|KGEN]] | `kgen` | Generates additional keypoints from a pattern of keypoints. |
| [[kl\|KL]] | `kl` | Generates a keypoint at a specified location on an existing line. |
| [[klist\|KLIST]] | `klist` | Lists the defined keypoints or hard points. |
| [[kmesh\|KMESH]] | `kmesh` | Generates nodes and point elements at keypoints. |
| [[kmodif\|KMODIF]] | `kmodif` | Modifies an existing keypoint. |
| [[kmove\|KMOVE]] | `kmove` | Calculates and moves a keypoint to an intersection. |
| [[knode\|KNODE]] | `knode` | Defines a keypoint at an existing node location. |
| [[kplot\|KPLOT]] | `kplot` | Displays the selected keypoints. |
| [[kpscale\|KPSCALE]] | `kpscale` | Generates a scaled set of (meshed) keypoints from a pattern of keypoints. |
| [[krefine\|KREFINE]] | `krefine` | Refines the mesh around specified keypoints. |
| [[kscale\|KSCALE]] | `kscale` | Generates a scaled pattern of keypoints from a given keypoint pattern. |
| [[kscon\|KSCON]] | `kscon` | Specifies a keypoint about which an area mesh will be skewed. |
| [[ksum\|KSUM]] | `ksum` | Calculates and prints geometry statistics of the selected keypoints. |
| [[ksymm\|KSYMM]] | `ksymm` | Generates a reflected set of keypoints. |
| [[ktran\|KTRAN]] | `ktran` | Transfers a pattern of keypoints to another coordinate system. |
| [[l\|L]] | `l` | Defines a line between two keypoints. |
| [[l2ang\|L2ANG]] | `l2ang` | Generates a line at an angle with two existing lines. |
| [[l2tan\|L2TAN]] | `l2tan` | Generates a line tangent to two lines. |
| [[lang\|LANG]] | `lang` | Generates a straight line at an angle with a line. |
| [[larc\|LARC]] | `larc` | Defines a circular arc. |
| [[larea\|LAREA]] | `larea` | Generates the shortest line between two keypoints on an area. |
| [[latt\|LATT]] | `latt` | Associates element attributes with the selected, unmeshed lines. |
| [[laylist\|LAYLIST]] | `laylist` | Lists real constants material properties for layered elements. |
| [[layplot\|LAYPLOT]] | `layplot` | Displays the layer stacking sequence for layered elements. |
| [[lccat\|LCCAT]] | `lccat` | Concatenates multiple lines into one line for mapped meshing. |
| [[lclear\|LCLEAR]] | `lclear` | Deletes nodes and line elements associated with selected lines. |
| [[lcomb\|LCOMB]] | `lcomb` | Combines adjacent lines into one line. |
| [[lcsl\|LCSL]] | `lcsl` | Divides intersecting lines at their point(s) of intersection. |
| [[ldele\|LDELE]] | `ldele` | Deletes unmeshed lines. |
| [[ldiv\|LDIV]] | `ldiv` | Divides a single line into two or more lines. |
| [[ldrag\|LDRAG]] | `ldrag` | Generates lines by sweeping a keypoint pattern along path. |
| [[lesize\|LESIZE]] | `lesize` | Specifies the divisions and spacing ratio on unmeshed lines. |
| [[lextnd\|LEXTND]] | `lextnd` | Extends a line at one end by using its slope. |
| [[lfillt\|LFILLT]] | `lfillt` | Generates a fillet line between two intersecting lines. |
| [[lfsurf\|LFSURF]] | `lfsurf` | Generates surface elements overlaid on the edge of existing solid elements and assigns the extra node as the closest fluid element node. |
| [[lgen\|LGEN]] | `lgen` | Generates additional lines from a pattern of lines. |
| [[lglue\|LGLUE]] | `lglue` | Generates new lines by "gluing" lines. |
| [[lina\|LINA]] | `lina` | Finds the intersection of a line with an area. |
| [[line\|LINE]] | `line` | Specifies "Lines" as the subsequent status topic. |
| [[linl\|LINL]] | `linl` | Finds the common intersection of lines. |
| [[linp\|LINP]] | `linp` | Finds the pairwise intersection of lines. |
| [[linv\|LINV]] | `linv` | Finds the intersection of a line with a volume. |
| [[llist\|LLIST]] | `llist` | Lists the defined lines. |
| [[lmesh\|LMESH]] | `lmesh` | Generates nodes and line elements along lines. |
| [[lovlap\|LOVLAP]] | `lovlap` | Overlaps lines. |
| [[lplot\|LPLOT]] | `lplot` | Displays the selected lines. |
| [[lptn\|LPTN]] | `lptn` | Partitions lines. |
| [[lrefine\|LREFINE]] | `lrefine` | Refines the mesh around specified lines. |
| [[lreverse\|LREVERSE]] | `lreverse` | Reverses the normal of a line, regardless of its connectivity or mesh status. |
| [[lrotat\|LROTAT]] | `lrotat` | Generates circular lines by rotating a keypoint pattern about an axis. |
| [[lsba\|LSBA]] | `lsba` | Subtracts areas from lines. |
| [[lsbl\|LSBL]] | `lsbl` | Subtracts lines from lines. |
| [[lsbv\|LSBV]] | `lsbv` | Subtracts volumes from lines. |
| [[lsbw\|LSBW]] | `lsbw` | Subtracts the intersection of the working plane from lines (divides lines). |
| [[lsscale\|LSSCALE]] | `lsscale` | Generates a scaled set of lines from a pattern of lines. |
| [[lstr\|LSTR]] | `lstr` | Defines a straight line irrespective of the active coordinate system. |
| [[lsum\|LSUM]] | `lsum` | Calculates and prints geometry statistics of the selected lines. |
| [[lsymm\|LSYMM]] | `lsymm` | Generates lines from a line pattern by symmetry reflection. |
| [[ltan\|LTAN]] | `ltan` | Generates a line at the end of, and tangent to, an existing line. |
| [[ltran\|LTRAN]] | `ltran` | Transfers a pattern of lines to another coordinate system. |
| [[mat\|MAT]] | `mat` | Sets the element material attribute pointer. |
| [[mater\|MATER]] | `mater` | Specifies "Material properties" as the subsequent status topic. |
| [[mcheck\|MCHECK]] | `mcheck` | Checks mesh connectivity. |
| [[meshing\|MESHING]] | `meshing` | Specifies "Meshing" as the subsequent status topic. |
| [[miter\|MITER]] | `miter` | Defines a mitered bend in a piping run. |
| [[modmsh\|MODMSH]] | `modmsh` | Controls the relationship of the solid model and the FE model. |
| [[mopt\|MOPT]] | `mopt` | Specifies meshing options. |
| [[morph\|MORPH]] | `morph` | Specifies morphing and remeshing controls. |
| [[move\|MOVE]] | `move` | Calculates and moves a node to an intersection. |
| [[mp\|MP]] | `mp` | Defines a linear material property as a constant or a function of temperature. |
| [[mpamod\|MPAMOD]] | `mpamod` | Modifies temperature-dependent secant coefficients of thermal expansion. |
| [[mpchg\|MPCHG]] | `mpchg` | Changes the material number attribute of an element. |
| [[mpcopy\|MPCOPY]] | `mpcopy` | Copies linear material model data from one material reference number to another. |
| [[mpdata\|MPDATA]] | `mpdata` | Defines property data to be associated with the temperature table. |
| [[mpdele\|MPDELE]] | `mpdele` | Deletes linear material properties. |
| [[mpdres\|MPDRES]] | `mpdres` | Reassembles existing material data with the temperature table. |
| [[mplib\|/MPLIB]] | `mplib` | Sets the default material library read and write paths. |
| [[mplist\|MPLIST]] | `mplist` | Lists linear material properties. |
| [[mpplot\|MPPLOT]] | `mpplot` | Plots linear material properties as a function of temperature. |
| [[mpread\|MPREAD]] | `mpread` | Reads a file containing material properties. |
| [[mptemp\|MPTEMP]] | `mptemp` | Defines a temperature table for material properties. |
| [[mptgen\|MPTGEN]] | `mptgen` | Adds temperatures to the temperature table by generation. |
| [[mptres\|MPTRES]] | `mptres` | Restores a temperature table previously defined. |
| [[mpwrite\|MPWRITE]] | `mpwrite` | Writes linear material properties in the database to a file (if the LIB option is not specified) or writes both linear and nonlinear material properties (if LIB is specified) from the database to a file. |
| [[mshape\|MSHAPE]] | `mshape` | For elements that support multiple shapes, specifies the element shape to be used for meshing. |
| [[mshcopy\|MSHCOPY]] | `mshcopy` | Simplifies the generation of meshes that have matching node element patterns on two different line groups (in 2D) or area groups (3D). |
| [[mshkey\|MSHKEY]] | `mshkey` | Specifies whether free meshing or mapped meshing should be used to mesh a model. |
| [[mshmid\|MSHMID]] | `mshmid` | Specifies placement of midside nodes. |
| [[mshpattern\|MSHPATTERN]] | `mshpattern` | Specifies pattern to be used for mapped triangle meshing. |
| [[msopt\|MSOPT]] | `msopt` | Specifies solution options for a [multistage cyclic symmetry analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/ans_mstag_introTheory.html). |
| [[mstole\|MSTOLE]] | `mstole` | Adds two extra nodes from `FLUID116` elements to `SURF151` or `SURF152` elements for convection analyses. |
| [[n\|N]] | `n` | Defines a node. |
| [[nang\|NANG]] | `nang` | Rotates a nodal coordinate system by direction cosines. |
| [[naxis\|NAXIS]] | `naxis` | Generates nodes for general axisymmetric element sections. |
| [[ndele\|NDELE]] | `ndele` | Deletes nodes. |
| [[ndist\|NDIST]] | `ndist` | Calculates and lists the distance between two nodes. |
| [[ndsurf\|NDSURF]] | `ndsurf` | Generates surface elements overlaid on the edge of existing elements and assigns the extra node as the closest fluid element node. |
| [[ngen\|NGEN]] | `ngen` | Generates additional nodes from a pattern of nodes. |
| [[nkpt\|NKPT]] | `nkpt` | Defines a node at an existing keypoint location. |
| [[nlist\|NLIST]] | `nlist` | Lists nodes. |
| [[nmodif\|NMODIF]] | `nmodif` | Modifies an existing node. |
| [[nodes\|NODES]] | `nodes` | Specifies "Nodes" as the subsequent status topic. |
| [[nooffset\|NOOFFSET]] | `nooffset` | Prevents the [[cdread|CDREAD]] command from offsetting specified data items |
| [[nora\|NORA]] | `nora` | Rotates nodal coordinate systems to surface normal |
| [[norl\|NORL]] | `norl` | Rotates nodal coordinate systems perpendicular to line normal |
| [[nplot\|NPLOT]] | `nplot` | Displays nodes. |
| [[nread\|NREAD]] | `nread` | Reads nodes from a file. |
| [[nrefine\|NREFINE]] | `nrefine` | Refines the mesh around specified nodes. |
| [[nrotat\|NROTAT]] | `nrotat` | Rotates nodal coordinate systems into the active system. |
| [[nrrang\|NRRANG]] | `nrrang` | Specifies the range of nodes to be read from the node file. |
| [[nscale\|NSCALE]] | `nscale` | Generates a scaled set of nodes from a pattern of nodes. |
| [[nsmooth\|NSMOOTH]] | `nsmooth` | Smooths selected nodes among selected elements. |
| [[nsvr\|NSVR]] | `nsvr` | Defines the number of variables for user-programmable element options. |
| [[nsym\|NSYM]] | `nsym` | Generates a reflected set of nodes. |
| [[numcmp\|NUMCMP]] | `numcmp` | Compresses the numbering of defined items. |
| [[nummrg\|NUMMRG]] | `nummrg` | Merges coincident or equivalently defined items. |
| [[numoff\|NUMOFF]] | `numoff` | Adds a number offset to defined items. |
| [[numstr\|NUMSTR]] | `numstr` | Establishes starting numbers for automatically numbered items. |
| [[nwrite\|NWRITE]] | `nwrite` | Writes nodes to a file. |
| [[pcirc\|PCIRC]] | `pcirc` | Creates a circular area centered about the working plane origin. |
| [[pcorro\|PCORRO]] | `pcorro` | Specifies the allowable exterior corrosion thickness for a piping run. |
| [[pdrag\|PDRAG]] | `pdrag` | Defines the external fluid drag loading for a piping run. |
| [[perbc2d\|PERBC2D]] | `perbc2d` | Generates periodic constraints for 2D planar magnetic field analyses. |
| [[pfluid\|PFLUID]] | `pfluid` | Defines the contained fluid density for a piping run. |
| [[pgap\|PGAP]] | `pgap` | Defines a spring-gap constraint in a piping run. |
| [[pinsul\|PINSUL]] | `pinsul` | Defines the external insulation constants in a piping run. |
| [[pipe\|PIPE]] | `pipe` | Specifies "Pipe modeling" as the subsequent status topic. |
| [[pmlopt\|PMLOPT]] | `pmlopt` | Defines perfectly matched layers (PMLs) or irregular perfectly matched layers (IPML). |
| [[pmlsize\|PMLSIZE]] | `pmlsize` | Determines number of PML or IPML layers. |
| [[poly\|POLY]] | `poly` | Creates a polygonal area based on working plane coordinate pairs. |
| [[popt\|POPT]] | `popt` | Selects the piping analysis standard for a piping run. |
| [[ppres\|PPRES]] | `ppres` | Defines the internal pressure for a piping run. |
| [[pri2\|PRI2]] | `pri2` | Creates a polygonal area or a prism volume by vertices (GUI). |
| [[prim\|PRIM]] | `prim` | Specifies "Solid model primitives" as the subsequent status topic. |
| [[prism\|PRISM]] | `prism` | Creates a prism volume based on working plane coordinate pairs. |
| [[psmesh\|PSMESH]] | `psmesh` | Creates and meshes a pretension section ( `PRETS179` ) or a preload section ( `MPC184` ). |
| [[pspec\|PSPEC]] | `pspec` | Defines pipe material and dimensions. |
| [[psprng\|PSPRNG]] | `psprng` | Defines a spring constraint in a piping run. |
| [[psys\|PSYS]] | `psys` | Sets the PML element coordinate system attribute pointer. |
| [[ptemp\|PTEMP]] | `ptemp` | Defines the pipe wall temperatures in a piping run. |
| [[ptxy\|PTXY]] | `ptxy` | Defines coordinate pairs for use in polygons and prisms. |
| [[punit\|PUNIT]] | `punit` | Selects the system of length units to be used in a piping run. |
| [[quad\|QUAD]] | `quad` | Generates a quadratic line of nodes from three nodes. |
| [[r\|R]] | `r` | Defines the element real constants. |
| [[race\|RACE]] | `race` | Defines a "racetrack" current source. |
| [[rbe3\|RBE3]] | `rbe3` | Distributes the force/moment applied at an independent node to a set of dependent nodes. |
| [[rcon\|RCON]] | `rcon` | Specifies "Real constants" as the subsequent status topic. |
| [[rdele\|RDELE]] | `rdele` | Deletes real constant sets. |
| [[real\|REAL]] | `real` | Sets the element real constant set attribute pointer. |
| [[rectng\|RECTNG]] | `rectng` | Creates a rectangular area anywhere on the working plane. |
| [[reduce\|REDUCE]] | `reduce` | Defines a reducer in a piping run. |
| [[rexport\|REXPORT]] | `rexport` | Exports displacements from an implicit run to ANSYS LS-DYNA. |
| [[rlist\|RLIST]] | `rlist` | Lists the real constant sets. |
| [[rmodif\|RMODIF]] | `rmodif` | Modifies real constant sets. |
| [[rmore\|RMORE]] | `rmore` | Adds real constants to a set. |
| [[rpoly\|RPOLY]] | `rpoly` | Creates a regular polygonal area centered about the working plane origin. |
| [[rpr4\|RPR4]] | `rpr4` | Creates a regular polygonal area or prism volume anywhere on the working plane. |
| [[rprism\|RPRISM]] | `rprism` | Creates a regular prism volume centered about the working plane origin. |
| [[rsmesh\|RSMESH]] | `rsmesh` | Generates a result section. |
| [[run\|RUN]] | `run` | Defines a pipe run. |
| [[sdelete\|SDELETE]] | `sdelete` | Deletes sections from the database. |
| [[se\|SE]] | `se` | Defines a superelement. |
| [[seccontrol\|SECCONTROL]] | `seccontrol` | Supplements or overrides default section properties. |
| [[secdata\|SECDATA]] | `secdata` | Describes the geometry of a section. |
| [[secfunction\|SECFUNCTION]] | `secfunction` | Specifies shell section thickness as a tabular function. |
| [[secjoint\|SECJOINT]] | `secjoint` | Defines local coordinate systems at joint element nodes and other data for joint elements. |
| [[seclib\|/SECLIB]] | `seclib` | Sets the default section library path for the [[secread|SECREAD]] command. |
| [[seclock\|SECLOCK]] | `seclock` | Specifies locks on the components of relative motion in a joint element. |
| [[secmodif\|SECMODIF]] | `secmodif` | Modifies a pretension section |
| [[secnum\|SECNUM]] | `secnum` | Sets the element section attribute pointer. |
| [[secoffset\|SECOFFSET]] | `secoffset` | Defines the section offset for cross sections. |
| [[secplot\|SECPLOT]] | `secplot` | Plots the geometry of a beam, pipe, shell, or reinforcing section to scale. |
| [[secread\|SECREAD]] | `secread` | Reads a custom section library or a user-defined section mesh into Mechanical APDL. |
| [[secstop\|SECSTOP]] | `secstop` | Specifies stops on the components of relative motion in a joint element. |
| [[sectype\|SECTYPE]] | `sectype` | Associates section type information with a section ID number. |
| [[secwrite\|SECWRITE]] | `secwrite` | Creates an ASCII file containing user mesh section information. |
| [[sedlist\|SEDLIST]] | `sedlist` | Lists the DOF solution of a superelement after the use pass. |
| [[selist\|SELIST]] | `selist` | Lists the contents of a superelement matrix file. |
| [[selm\|SELM]] | `selm` | Specifies "Superelements" as the subsequent status topic. |
| [[sesymm\|SESYMM]] | `sesymm` | Performs a symmetry operation on a superelement within the use pass. |
| [[setfgap\|SETFGAP]] | `setfgap` | Updates or defines the real constant table for squeeze film elements. |
| [[setran\|SETRAN]] | `setran` | Creates a superelement from an existing superelement. |
| [[sflex\|SFLEX]] | `sflex` | Sets flexibility factors for the currently defined pipe element section. |
| [[shpp\|SHPP]] | `shpp` | Controls element shape checking. |
| [[shsd\|SHSD]] | `shsd` | Creates or deletes a shell-solid interface to be used in shell-to-solid assemblies. |
| [[slist\|SLIST]] | `slist` | Summarizes the section properties for all defined sections in the current session. |
| [[sload\|SLOAD]] | `sload` | Loads a pretension section. |
| [[smrtsize\|SMRTSIZE]] | `smrtsize` | Specifies meshing parameters for automatic (smart) element sizing. |
| [[source\|SOURCE]] | `source` | Defines a default location for undefined nodes or keypoints. |
| [[sph4\|SPH4]] | `sph4` | Creates a spherical volume anywhere on the working plane. |
| [[sph5\|SPH5]] | `sph5` | Creates a spherical volume by diameter end points. |
| [[sphere\|SPHERE]] | `sphere` | Creates a spherical volume centered about the working plane origin. |
| [[spline\|SPLINE]] | `spline` | Generates a segmented spline through a series of keypoints. |
| [[splot\|SPLOT]] | `splot` | Displays the selected areas and a faceted view of their underlying surfaces |
| [[ssbt\|SSBT]] | `ssbt` | Specifies preintegrated bending thermal effects for shell sections. |
| [[ssln\|SSLN]] | `ssln` | Selects and displays small lines in the model. |
| [[ssmt\|SSMT]] | `ssmt` | Specifies preintegrated membrane thermal effects for shell sections. |
| [[sspa\|SSPA]] | `sspa` | Specifies a preintegrated membrane stiffness for shell sections. |
| [[sspb\|SSPB]] | `sspb` | Specifies a preintegrated coupling stiffness for shell sections. |
| [[sspd\|SSPD]] | `sspd` | Specifies a preintegrated bending stiffness for shell sections. |
| [[sspe\|SSPE]] | `sspe` | Specifies a preintegrated transverse shear stiffness for shell sections. |
| [[sspm\|SSPM]] | `sspm` | Specifies mass density for a preintegrated shell section. |
| [[sstate\|SSTATE]] | `sstate` | Defines a steady-state rolling analysis. |
| [[swadd\|SWADD]] | `swadd` | Adds more surfaces to an existing spot weld set. |
| [[swdel\|SWDEL]] | `swdel` | Deletes spot weld sets. |
| [[swgen\|SWGEN]] | `swgen` | Creates a new spot weld set. |
| [[swlist\|SWLIST]] | `swlist` | Lists spot weld sets. |
| [[tb\|TB]] | `tb` | Activates a data table for material properties or special element input. |
| [[tbcopy\|TBCOPY]] | `tbcopy` | Copies a data table from one material to another. |
| [[tbdata\|TBDATA]] | `tbdata` | Defines data for the material data table. |
| [[tbdele\|TBDELE]] | `tbdele` | Deletes previously defined material data tables. |
| [[tbeo\|TBEO]] | `tbeo` | Sets special options or parameters for material data tables. |
| [[tbfield\|TBFIELD]] | `tbfield` | Defines values of field variables for material data tables. |
| [[tbfplot\|TBFPLOT]] | `tbfplot` | Plots [material curve-fitting](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/Hlp_AM_GMCF.html) data. |
| [[tbft\|TBFT]] | `tbft` | Performs [material curve-fitting](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/Hlp_AM_GMCF.html) operations. |
| [[tbin\|TBIN]] | `tbin` | Sets parameters used for [interpolation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_loginterpscal.html#) of the material data tables. |
| [[tble\|TBLE]] | `tble` | Specifies "Data table properties" as the subsequent status topic. |
| [[tblist\|TBLIST]] | `tblist` | Lists the material data tables. |
| [[tbmodif\|TBMODIF]] | `tbmodif` | Modifies data for the material data table (GUI). |
| [[tbplot\|TBPLOT]] | `tbplot` | Displays the material data table. |
| [[tbpt\|TBPT]] | `tbpt` | Defines a point on a nonlinear data curve. |
| [[tbtemp\|TBTEMP]] | `tbtemp` | Defines a temperature for a material data table. |
| [[tchg\|TCHG]] | `tchg` | Converts 20-node degenerate tetrahedral elements to their 10-node non-degenerate counterparts. |
| [[tee\|TEE]] | `tee` | Defines a tee in a piping run. |
| [[timp\|TIMP]] | `timp` | Improves the quality of tetrahedral elements that are not associated with a volume. |
| [[torus\|TORUS]] | `torus` | Creates a toroidal volume. |
| [[transfer\|TRANSFER]] | `transfer` | Transfers a pattern of nodes to another coordinate system. |
| [[tshap\|TSHAP]] | `tshap` | Defines simple 2D and 3D geometric surfaces for target segment elements. |
| [[type\|TYPE]] | `type` | Sets the element type attribute pointer. |
| [[uimp\|UIMP]] | `uimp` | Defines constant material properties (GUI). |
| [[upgeom\|UPGEOM]] | `upgeom` | Adds displacements from a previous analysis and updates the geometry to the deformed configuration. |
| [[usrdof\|USRDOF]] | `usrdof` | Specifies the degrees of freedom for the user-defined element `USER300`. |
| [[usrelem\|USRELEM]] | `usrelem` | Specifies the characteristics of the user-defined element `USER300`. |
| [[v\|V]] | `v` | Defines a volume through keypoints. |
| [[va\|VA]] | `va` | Generates a volume bounded by existing areas. |
| [[vadd\|VADD]] | `vadd` | Adds separate volumes to create a single volume. |
| [[valve\|VALVE]] | `valve` | Defines a valve in a piping run. |
| [[vatt\|VATT]] | `vatt` | Associates element attributes with the selected, unmeshed volumes. |
| [[vclear\|VCLEAR]] | `vclear` | Deletes nodes and volume elements associated with selected volumes. |
| [[vdele\|VDELE]] | `vdele` | Deletes unmeshed volumes. |
| [[vdgl\|VDGL]] | `vdgl` | Lists keypoints of a volume that lie on a parametric degeneracy. |
| [[vdrag\|VDRAG]] | `vdrag` | Generates volumes by dragging an area pattern along a path. |
| [[veorient\|VEORIENT]] | `veorient` | Specifies brick element orientation for volume mapped (hexahedron) meshing. |
| [[vext\|VEXT]] | `vext` | Generates additional volumes by extruding areas. |
| [[vgen\|VGEN]] | `vgen` | Generates additional volumes from a pattern of volumes. |
| [[vglue\|VGLUE]] | `vglue` | Generates new volumes by "gluing" volumes. |
| [[vimp\|VIMP]] | `vimp` | Improves the quality of the tetrahedral elements in the selected volume(s). |
| [[vinp\|VINP]] | `vinp` | Finds the pairwise intersection of volumes. |
| [[vinv\|VINV]] | `vinv` | Finds the intersection of volumes. |
| [[vlist\|VLIST]] | `vlist` | Lists the defined volumes. |
| [[vlscale\|VLSCALE]] | `vlscale` | Generates a scaled set of volumes from a pattern of volumes. |
| [[vmesh\|VMESH]] | `vmesh` | Generates nodes and volume elements within volumes. |
| [[voffst\|VOFFST]] | `voffst` | Generates a volume, offset from a given area. |
| [[volumes\|VOLUMES]] | `volumes` | Specifies "Volumes" as the subsequent status topic. |
| [[vovlap\|VOVLAP]] | `vovlap` | Overlaps volumes. |
| [[vplot\|VPLOT]] | `vplot` | Displays the selected volumes. |
| [[vptn\|VPTN]] | `vptn` | Partitions volumes. |
| [[vrotat\|VROTAT]] | `vrotat` | Generates cylindrical volumes by rotating an area pattern about an axis. |
| [[vsba\|VSBA]] | `vsba` | Subtracts areas from volumes. |
| [[vsbv\|VSBV]] | `vsbv` | Subtracts volumes from volumes. |
| [[vsbw\|VSBW]] | `vsbw` | Subtracts intersection of the working plane from volumes (divides volumes). |
| [[vsum\|VSUM]] | `vsum` | Calculates and prints geometry statistics of the selected volumes. |
| [[vsweep\|VSWEEP]] | `vsweep` | Fills an existing unmeshed volume with elements by sweeping the mesh from an adjacent area through the volume. |
| [[vsymm\|VSYMM]] | `vsymm` | Generates volumes from a volume pattern by symmetry reflection. |
| [[vtran\|VTRAN]] | `vtran` | Transfers a pattern of volumes to another coordinate system. |
| [[wtbcreate\|WTBCREATE]] | `wtbcreate` | Creates a `USER300` element to model the turbine for full aeroelastic coupling analysis and specifies relevant settings for the analysis. |
| [[xfcrkmesh\|XFCRKMESH]] | `xfcrkmesh` | Defines a crack in the model when the crack surface is discretized by `MESH200` elements |
| [[xfdata\|XFDATA]] | `xfdata` | Defines a crack in the model by specifying nodal level set values |
| [[xfenrich\|XFENRICH]] | `xfenrich` | Defines parameters associated with crack propagation using XFEM |
| [[xflist\|XFLIST]] | `xflist` | Lists enrichment details and associated crack information |
