---
group: post1
generated: 2026-08-22
tags: [mapdl-command-index]
---

# POST1 commands

These commands are used to postprocess the results with the database processor.

200 commands. Back to [[MAPDL commands]].

| Command | Method | Summary |
|---|---|---|
| [[ancntr\|ANCNTR]] | `ancntr` | Produces an animated sequence of a contoured deformed shape. |
| [[ancut\|ANCUT]] | `ancut` | Produces an animated sequence of Q-slices. |
| [[ancyc\|ANCYC]] | `ancyc` | Applies a traveling wave animation to graphics data in a modal cyclic symmetry analysis. |
| [[andata\|ANDATA]] | `andata` | Displays animated graphics data for nonlinear problems. |
| [[andscl\|ANDSCL]] | `andscl` | Produces an animated sequence of a deformed shape. |
| [[andyna\|ANDYNA]] | `andyna` | Produces an animated sequence of contour values through substeps. |
| [[anfile\|/ANFILE]] | `anfile` | Saves or resumes an animation sequence to or from a file. |
| [[anflow\|ANFLOW]] | `anflow` | Produces an animated sequence of a charged particle traveling in an electric or magnetic field. |
| [[anharm\|ANHARM]] | `anharm` | Produces an animated sequence of time-harmonic results or complex mode shapes. |
| [[anim\|ANIM]] | `anim` | Displays animated graphics data for linear problems. |
| [[anisos\|ANISOS]] | `anisos` | Produces an animated sequence of an isosurface. |
| [[anmode\|ANMODE]] | `anmode` | Produces an animated sequence of a mode shape. |
| [[antime\|ANTIME]] | `antime` | Generates a sequential contour animation over a range of time. |
| [[append\|APPEND]] | `append` | Reads data from the results file and appends it to the database. |
| [[avprin\|AVPRIN]] | `avprin` | Specifies how principal and vector sums are to be calculated. |
| [[avres\|AVRES]] | `avres` | Specifies how results data will be averaged when PowerGraphics is enabled. |
| [[bfint\|BFINT]] | `bfint` | Activates the body force interpolation operation. |
| [[calc\|CALC]] | `calc` | Specifies "Calculation settings" as the subsequent status topic. |
| [[cbdof\|CBDOF]] | `cbdof` | Activates cut-boundary interpolation (for submodeling). |
| [[cmsfile\|CMSFILE]] | `cmsfile` | Specifies a list of component mode synthesis (CMS) results files for plotting results on the assembly. |
| [[curr2d\|CURR2D]] | `curr2d` | Calculates current flow in a 2D conductor. |
| [[cyccalc\|CYCCALC]] | `cyccalc` | Calculates results from a cyclic harmonic mode-superposition analysis using the specifications defined by [[cycspec|CYCSPEC]]. |
| [[cycfiles\|CYCFILES]] | `cycfiles` | Specifies the data files where results are to be found for a cyclic symmetry mode-superposition harmonic analysis. |
| [[cycphase\|CYCPHASE]] | `cycphase` | Provides tools for determining minimum and maximum possible result values from frequency couplets produced in a modal cyclic symmetry analysis. |
| [[cycspec\|CYCSPEC]] | `cycspec` | Defines the set of result items for a subsequent [[cyccalc|CYCCALC]] command in postprocessing a cyclic harmonic mode-superposition analysis. |
| [[datadef\|DATADEF]] | `datadef` | Specifies "Directly defined data status" as the subsequent status topic. |
| [[define\|DEFINE]] | `define` | Specifies "Data definition settings" as the subsequent status topic. |
| [[desol\|DESOL]] | `desol` | Defines or modifies solution results at a node of an element. |
| [[detab\|DETAB]] | `detab` | Modifies element table results in the database. |
| [[display\|DISPLAY]] | `display` | Specifies "Display settings" as the subsequent status topic. |
| [[dnsol\|DNSOL]] | `dnsol` | Defines or modifies solution results at a node. |
| [[efacet\|/EFACET]] | `efacet` | Specifies the number of facets per element edge for PowerGraphics displays. |
| [[emagerr\|EMAGERR]] | `emagerr` | Calculates the relative error in an electrostatic or electromagnetic field analysis. |
| [[emf\|EMF]] | `emf` | Calculates the electromotive force (emf), or voltage drop along a predefined path. |
| [[emft\|EMFT]] | `emft` | Summarizes electromagnetic forces and torques. |
| [[ernorm\|ERNORM]] | `ernorm` | Controls error estimation calculations. |
| [[esort\|ESORT]] | `esort` | Sorts the element table. |
| [[etable\|ETABLE]] | `etable` | Fills a table of element values for further processing. |
| [[eusort\|EUSORT]] | `eusort` | Restores original order of the element table. |
| [[exoption\|EXOPTION]] | `exoption` | Specifies the [[exprofile|EXPROFILE]] options for the Mechanical APDL to Ansys CFX profile file transfer. |
| [[expand\|EXPAND]] | `expand` | Displays the results of a modal cyclic symmetry analysis. |
| [[slashexpand\|/EXPAND]] | `slashexpand` | Allows the creation of a larger graphic display than represented by the actual finite element analysis model. |
| [[exprofile\|EXPROFILE]] | `exprofile` | Exports Mechanical APDL interface data on selected nodes to an Ansys CFX Profile file. |
| [[exunit\|EXUNIT]] | `exunit` | Specifies the interface data unit labels to be written to the profile file from Mechanical APDL to Ansys CFX transfer. |
| [[fctyp\|FCTYP]] | `fctyp` | Activates or removes failure-criteria types for postprocessing. |
| [[fe\|FE]] | `fe` | Defines a set of fatigue event parameters. |
| [[felist\|FELIST]] | `felist` | Lists the fatigue event parameters. |
| [[file\|FILE]] | `file` | Specifies the data file where results are to be found. |
| [[fl\|FL]] | `fl` | Defines a set of fatigue location parameters. |
| [[fllist\|FLLIST]] | `fllist` | Lists the fatigue location parameters. |
| [[fluxv\|FLUXV]] | `fluxv` | Calculates the flux passing through a closed contour. |
| [[force\|FORCE]] | `force` | Selects the element nodal force type for output. |
| [[format\|/FORMAT]] | `format` | Specifies format controls for tables. |
| [[fp\|FP]] | `fp` | Defines the fatigue S vs. N and Sm vs. T tables. |
| [[fplist\|FPLIST]] | `fplist` | Lists the property table stored for fatigue evaluation. |
| [[fs\|FS]] | `fs` | Stores fatigue stress components at a node. |
| [[fsdele\|FSDELE]] | `fsdele` | Deletes a stress condition for a fatigue location, event, and loading. |
| [[fslist\|FSLIST]] | `fslist` | Lists the stresses stored for fatigue evaluation. |
| [[fsnode\|FSNODE]] | `fsnode` | Calculates and stores the stress components at a node for fatigue. |
| [[fsplot\|FSPLOT]] | `fsplot` | Displays a fatigue stress item for a fatigue location and event. |
| [[fssect\|FSSECT]] | `fssect` | Calculates and stores total linearized stress components. |
| [[fssparm\|FSSPARM]] | `fssparm` | Calculates reflection and transmission properties of a frequency selective surface. |
| [[fsum\|FSUM]] | `fsum` | Sums the nodal force and moment contributions of elements. |
| [[ftcalc\|FTCALC]] | `ftcalc` | Performs fatigue calculations for a given node location. |
| [[ftsize\|FTSIZE]] | `ftsize` | Defines the fatigue data storage array. |
| [[ftwrite\|FTWRITE]] | `ftwrite` | Writes all currently stored fatigue data on a file. |
| [[header\|/HEADER]] | `header` | Sets page and table heading print controls. |
| [[hfang\|HFANG]] | `hfang` | Defines or displays spatial angles of a spherical radiation surface for sound radiation parameter calculations. |
| [[hfsym\|HFSYM]] | `hfsym` | Indicates the presence of symmetry planes for the computation of acoustic fields in the near and far field domains (beyond the finite element region). |
| [[hrcplx\|HRCPLX]] | `hrcplx` | Computes and stores in the database the time-harmonic solution at a prescribed phase angle. |
| [[inres\|INRES]] | `inres` | Identifies the data to be retrieved from the results file. |
| [[irlist\|IRLIST]] | `irlist` | Prints inertia relief summary table. |
| [[kcalc\|KCALC]] | `kcalc` | Calculates stress intensity factors in fracture mechanics analyses. |
| [[layer\|LAYER]] | `layer` | Specifies the element layer for which data are to be processed. |
| [[lcabs\|LCABS]] | `lcabs` | Specifies absolute values for load case operations. |
| [[lcase\|LCASE]] | `lcase` | Reads a load case into the database. |
| [[lccalc\|LCCALC]] | `lccalc` | Specifies "Load case settings" as the subsequent status topic. |
| [[lcdef\|LCDEF]] | `lcdef` | Creates a load case from a set of results on a results file. |
| [[lcfact\|LCFACT]] | `lcfact` | Defines scale factors for load case operations. |
| [[lcfile\|LCFILE]] | `lcfile` | Creates a load case from an existing load case file. |
| [[lcoper\|LCOPER]] | `lcoper` | Performs load case operations. |
| [[lcsel\|LCSEL]] | `lcsel` | Selects a subset of load cases. |
| [[lcsum\|LCSUM]] | `lcsum` | Specifies whether to process non-summable items in load case operations. |
| [[lcwrite\|LCWRITE]] | `lcwrite` | Creates a load case by writing results to a load case file. |
| [[lczero\|LCZERO]] | `lczero` | Zeroes the results portion of the database. |
| [[macopt\|MACOPT]] | `macopt` | Specifies modal assurance criterion (MAC) or frequency response function (FRF) correlation criteria calculation options for [[rstmac|RSTMAC]]. |
| [[mmf\|MMF]] | `mmf` | Calculates the magnetomotive force along a path. |
| [[nforce\|NFORCE]] | `nforce` | Sums the nodal forces and moments of elements attached to nodes. |
| [[nldpost\|NLDPOST]] | `nldpost` | Gets element component information from nonlinear diagnostic files. |
| [[nsort\|NSORT]] | `nsort` | Sorts nodal data. |
| [[nusort\|NUSORT]] | `nusort` | Restores original order for nodal data. |
| [[padele\|PADELE]] | `padele` | Deletes a defined path. |
| [[page\|/PAGE]] | `page` | Defines the printout and screen page size. |
| [[paget\|PAGET]] | `paget` | Writes current path information into an array variable. |
| [[paput\|PAPUT]] | `paput` | Retrieves path information from an array variable. |
| [[paresu\|PARESU]] | `paresu` | Restores previously saved paths from a file. |
| [[pasave\|PASAVE]] | `pasave` | Saves selected paths to an external file. |
| [[path\|PATH]] | `path` | Defines a path name and establishes parameters for the path. |
| [[pcalc\|PCALC]] | `pcalc` | Forms additional labeled path items by operating on existing path items. |
| [[pcross\|PCROSS]] | `pcross` | Calculates the cross product of two path vectors along the current path. |
| [[pdef\|PDEF]] | `pdef` | Interpolates an item onto a path. |
| [[pdot\|PDOT]] | `pdot` | Calculates the dot product of two path vectors along the current path. |
| [[plas\|PLAS]] | `plas` | Plots a specified acoustic quantity during postprocessing of an acoustic analysis. |
| [[plcamp\|PLCAMP]] | `plcamp` | Plots Campbell diagram data for applications involving rotating structure dynamics. |
| [[plcfreq\|PLCFREQ]] | `plcfreq` | Plots the frequency response for the given [[cycspec|CYCSPEC]] specification. |
| [[plchist\|PLCHIST]] | `plchist` | Plots a histogram of the frequency response of each sector for the given [[cycspec|CYCSPEC]] specification. |
| [[plcint\|PLCINT]] | `plcint` | Plots the fracture parameter ( [[cint|CINT]] ) result data. |
| [[plcksurf\|PLCKSURF]] | `plcksurf` | Plots the Φ = 0 level set surface in an [XFEM-based crack analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#fracxfemreferences) |
| [[plcrack\|PLCRACK]] | `plcrack` | Displays cracking and crushing locations in [SOLID65](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_arch/Hlp_E_SOLID65.html#a5pNxq3a5mcm) elements. |
| [[pldisp\|PLDISP]] | `pldisp` | Displays the displaced structure. |
| [[plesol\|PLESOL]] | `plesol` | Displays solution results as discontinuous element contours. |
| [[pletab\|PLETAB]] | `pletab` | Displays element table items. |
| [[plf2d\|PLF2D]] | `plf2d` | Generates a contour line plot of equipotentials. |
| [[plfar\|PLFAR]] | `plfar` | Plots pressure far fields and far-field parameters. |
| [[plls\|PLLS]] | `plls` | Displays element table items as contoured areas along elements. |
| [[plmc\|PLMC]] | `plmc` | Plots the modal coordinates from a mode-superposition solution. |
| [[plnear\|PLNEAR]] | `plnear` | Plots the pressure in the near zone exterior to the equivalent source surface. |
| [[plnsol\|PLNSOL]] | `plnsol` | Displays solution results as continuous element contours. |
| [[plorb\|PLORB]] | `plorb` | Displays the orbital motion of a rotating structure |
| [[plpagm\|PLPAGM]] | `plpagm` | Displays path items along the path geometry. |
| [[plpath\|PLPATH]] | `plpath` | Displays path items on a graph. |
| [[plsect\|PLSECT]] | `plsect` | Displays membrane and membrane-plus-bending linearized stresses. |
| [[pltrac\|PLTRAC]] | `pltrac` | Displays a charged particle trace on an element display. |
| [[plvect\|PLVECT]] | `plvect` | Displays results as vectors. |
| [[plzz\|PLZZ]] | `plzz` | Plots the interference diagram from a cyclic modal analysis. |
| [[pmap\|PMAP]] | `pmap` | Creates mapping of the path geometry by defining path interpolation division points. |
| [[point\|POINT]] | `point` | Specifies "Point flow tracing settings" as the subsequent status topic. |
| [[powerh\|POWERH]] | `powerh` | Calculates the rms power loss in a conductor or lossy dielectric. |
| [[ppath\|PPATH]] | `ppath` | Defines a path by picking or defining nodes, or locations on the currently active working plane, or by entering specific coordinate locations. |
| [[prange\|PRANGE]] | `prange` | Determines the path range. |
| [[pras\|PRAS]] | `pras` | Prints a specified acoustic quantity during postprocessing of an acoustic analysis. |
| [[prcamp\|PRCAMP]] | `prcamp` | Prints Campbell diagram data for applications involving rotating structure dynamics. |
| [[prcint\|PRCINT]] | `prcint` | Lists fracture parameter ( [[cint|CINT]] ) results data. |
| [[prenergy\|PRENERGY]] | `prenergy` | Prints the total energies of a model or the energies of the specified components. |
| [[prerr\|PRERR]] | `prerr` | Prints SEPC and TEPC. |
| [[presol\|PRESOL]] | `presol` | Prints the solution results for elements. |
| [[pretab\|PRETAB]] | `pretab` | Prints the element table items. |
| [[prfar\|PRFAR]] | `prfar` | Prints acoustic far field parameters. |
| [[print\|PRINT]] | `print` | Specifies "Print settings" as the subsequent status topic. |
| [[priter\|PRITER]] | `priter` | Prints solution summary data. |
| [[prjsol\|PRJSOL]] | `prjsol` | Prints joint element output. |
| [[prmc\|PRMC]] | `prmc` | Prints the modal coordinates from a mode-superposition solution. |
| [[prnear\|PRNEAR]] | `prnear` | Prints the pressure in the near zone exterior to the equivalent source surface. |
| [[prnld\|PRNLD]] | `prnld` | Prints the summed element nodal loads. |
| [[prnsol\|PRNSOL]] | `prnsol` | Prints nodal solution results. |
| [[prorb\|PRORB]] | `prorb` | Prints the orbital motion characteristics of a rotating structure |
| [[prpath\|PRPATH]] | `prpath` | Prints path items along a geometry path. |
| [[prrfor\|PRRFOR]] | `prrfor` | Prints the constrained node reaction solution. Used with the [[force|FORCE]] command. |
| [[prrsol\|PRRSOL]] | `prrsol` | Prints the constrained node reaction solution. |
| [[prsect\|PRSECT]] | `prsect` | Calculates and prints linearized stresses along a section path. |
| [[prvect\|PRVECT]] | `prvect` | Prints results as vector magnitude and direction cosines. |
| [[psel\|PSEL]] | `psel` | Selects a path or paths. |
| [[pvect\|PVECT]] | `pvect` | Interpolates a set of items onto a path. |
| [[rappnd\|RAPPND]] | `rappnd` | Appends results data from the database to the results file. |
| [[rescombine\|RESCOMBINE]] | `rescombine` | Reads results from local results files into the database after a distributed-memory parallel solution. |
| [[reset\|RESET]] | `reset` | Resets all POST1 or POST26 specifications to initial defaults. |
| [[reswrite\|RESWRITE]] | `reswrite` | Appends results data from the database to a results file. |
| [[rmflvec\|RMFLVEC]] | `rmflvec` | Writes eigenvectors of fluid nodes to a file for use in damping parameter extraction. |
| [[rsplit\|RSPLIT]] | `rsplit` | Creates one or more results file(s) from the current results file based on subsets of elements. |
| [[rstmac\|RSTMAC]] | `rstmac` | Calculates modal assurance criterion (MAC/FRF) and matches nodal solutions from two results files or from one results file and one universal format file. |
| [[rsys\|RSYS]] | `rsys` | Activates a coordinate system for printout or display of element and nodal results. |
| [[sabs\|SABS]] | `sabs` | Specifies absolute values for element table operations. |
| [[sadd\|SADD]] | `sadd` | Forms an element table item by adding two existing items. |
| [[sallow\|SALLOW]] | `sallow` | Defines the allowable stress table for safety factor calculations. |
| [[senergy\|SENERGY]] | `senergy` | Determines the stored magnetic energy or co-energy. |
| [[set\|SET]] | `set` | Defines the data set to be read from the results file. |
| [[sexp\|SEXP]] | `sexp` | Forms an element table item by exponentiating and multiplying. |
| [[sfact\|SFACT]] | `sfact` | Allows safety factor or margin of safety calculations to be made. |
| [[sfcalc\|SFCALC]] | `sfcalc` | Calculates the safety factor or margin of safety. |
| [[shell\|SHELL]] | `shell` | Selects a shell element or shell layer location for results output. |
| [[smax\|SMAX]] | `smax` | Forms an element table item from the maximum of two other items. |
| [[smin\|SMIN]] | `smin` | Forms an element table item from the minimum of two other items. |
| [[smult\|SMULT]] | `smult` | Forms an element table item by multiplying two other items. |
| [[sort\|SORT]] | `sort` | Specifies "Sort settings" as the subsequent status topic. |
| [[spec\|SPEC]] | `spec` | Specifies "Miscellaneous specifications" as the subsequent status topic. |
| [[spmwrite\|SPMWRITE]] | `spmwrite` | Calculates the state-space matrices and writes them to the SPM file. |
| [[spoint\|SPOINT]] | `spoint` | Defines a point for force/moment summations or inertia calculation |
| [[ssum\|SSUM]] | `ssum` | Calculates and prints the sum of element table items. |
| [[subset\|SUBSET]] | `subset` | Reads results for the selected portions of the model. |
| [[sucalc\|SUCALC]] | `sucalc` | Create new result data by operating on two existing result data sets on a given surface. |
| [[sucr\|SUCR]] | `sucr` | Create a surface. |
| [[sudel\|SUDEL]] | `sudel` | Delete geometry information as well as any mapped results for specified surface. |
| [[sueval\|SUEVAL]] | `sueval` | Perform operations on a mapped item and store result in a scalar parameter. |
| [[suget\|SUGET]] | `suget` | Moves surface geometry and mapped results to an array parameter. |
| [[sumap\|SUMAP]] | `sumap` | Map results onto selected surface(s). |
| [[sumtype\|SUMTYPE]] | `sumtype` | Sets the type of summation to be used in the following load case operations. |
| [[supl\|SUPL]] | `supl` | Plot result data on all selected surfaces or on a specified surface. |
| [[supr\|SUPR]] | `supr` | Print global status, geometry information and/or result information. |
| [[suresu\|SURESU]] | `suresu` | Read a set of surface definitions and result items from a file and make them the current set. |
| [[susave\|SUSAVE]] | `susave` | Saves surface definitions to a file. |
| [[susel\|SUSEL]] | `susel` | Selects a subset of surfaces |
| [[suvect\|SUVECT]] | `suvect` | Create new result data by operating on two existing result vectors on a given surface. |
| [[tallow\|TALLOW]] | `tallow` | Defines the temperature table for safety factor calculations. |
| [[trpdel\|TRPDEL]] | `trpdel` | Deletes charged particle trace points. |
| [[trplis\|TRPLIS]] | `trplis` | Lists charged particle trace points. |
| [[trpoin\|TRPOIN]] | `trpoin` | Defines a point through which a charged particle trace will travel. |
| [[trtime\|TRTIME]] | `trtime` | Defines the options used for the [[pltrac|PLTRAC]] (charged particle trace) command. |
| [[vcross\|VCROSS]] | `vcross` | Forms element table items from the cross product of two vectors. |
| [[vdot\|VDOT]] | `vdot` | Forms an element table item from the dot product of two vectors. |
| [[vtkwrite\|VTKWRITE]] | `vtkwrite` | Writes the current displacement data to a `.VTK` file. |
