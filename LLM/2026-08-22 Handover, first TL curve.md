# Handover: first TL curve and the solver lifecycle sessions

Next chat opens by discussing the first transmission loss result and where to take the model. Written 2026-08-22, roughly 01:30. Two threads ran tonight: solver lifecycle debugging (now settled, see notes) and the TL pipeline (built and producing physics).

## The headline result

`D:\Pyansys projects\LLM\double_wall_tl.png` (data in `double_wall_tl.npz` beside it). FE transmission loss of the double wall, 50 to 2000 Hz, 5 Hz steps, against the classical limp double leaf curve. Four features, all consistent with a double leaf whose panels sit on edge springs:

- Low frequency divergence: FE climbs to about 48 dB at 50 Hz where limp theory falls toward zero. Stiffness controlled region from the silicone edge. This is the springs on the side signature John asked to see.
- The mass air mass dip moved up and split: limp theory says one dip at about 220 Hz, FE shows two (about 280 and 350 Hz) with a hump between. Edge stiffness raises the resonance, spring plus air gap coupling splits it into in phase and anti phase piston modes.
- Above about 900 Hz the FE curve rides the classical curve. Mass controlled region, mutual sanity check.
- Sharp pole zero pair at about 1610 Hz, unexplained. Candidate: first bending mode of the MDF disc against the surround. A modal analysis of the wet structure would settle it.
- Measured upstream |B/A| is about 1.0 in the high TL band: the wall reflection, present in the data exactly as the classical formulation writes it in. Two mic decomposition (section averaged pressures, mics at y = 60 and 80 mm) separates incident from reflected.

## What was built tonight (all verified on the live server)

- Source line split: `h_src = 30 mm` in DW_GEOM, upstream air is two rectangles meeting at ys, `SOURCE_L` line component picked by centroid height. Verified: 8 areas, AIR_UP_A holds two, SOURCE_L holds line 3.
- Build completion in `double_wall.py`: attributes per component, mesh (air 5 mm, MDF 2.5 mm, silicone edge 1.7 mm; 708 elements, 94 structure, 84 coupled fluid, 530 uncoupled), coupled interface layer by ESLN conversion of air elements sharing structure nodes, FSI flags on wetted faces, IMPD flag plus MU = 1 anechoic ends, rim clamps at x = r_tube.
- `D:\Pyansys projects\LLM\tl_sweep.py`: FLOW source on SOURCE_L, full harmonic sweep (unsymmetric, HROPT FULL), POST26 extraction, two mic decomposition, classical limp overlay, plot. Rerun postprocessing without resolving via `--no-solve`.

## Doc verified recipes (from the v18.2 element reference mirror at mm.bme.hu, not memory)

- FLUID29 KEYOPT(3): 0 planar, 1 axisymmetric, 2 axiharmonic. KEYOPT(2): 0 structure present (UX, UY, PRES, unsymmetric), 1 absent (PRES only).
- Absorber: MU is the material knob (boundary admittance, 0 none to 1 full), the IMPD face flag (value 1) chooses where. MU sits on the air material, only flagged faces consume it.
- FLOW is a nodal F load, real and imaginary allowed, on a 360 degree basis in axisymmetric.
- FSI face flag on interface fluid elements couples structure motion and fluid pressure. Auto flagging exists as fallback, we flag manually.

## Caveats worth remembering

- PLANE183 (quadratic) against FLUID29 (linear) couples through corner nodes only, midside nodes unmatched. Drop structure to PLANE182 if chasing decimals.
- FLOW applied uniform per node, not r weighted, so the source sheet is not a clean plane wave at birth. Near field junk decays well before the mics (30 mm clearance, decay exp(-3.83 y/R)).
- Mic pair spacing 20 mm: decomposition singular only near 8.5 kHz, far above the band.
- The aplot chatter `[84, 89, 109]` remains untraced, still cosmetic.

## Solver lifecycle: settled, recorded in vault notes

The night's other half. Key lesson: the solver is a separate OS process, kernel restarts do not touch it, and while alive it holds file.lock open (Windows then blocks a second launch in the same run_location). Full story and the four start routes in `Ansys\Solver at start.md`. Related: `Ansys\Environment set up.md` (env and kernel model), `Ansys\Interactive viewer.md` (plotting stack requirements). Notebook cell 0 is now attach or launch and worked first try. A status first cell exists in the Solver at start note if John wants it pasted in.

## Working agreements made tonight

- No direct edits to files John has open in JupyterLab. Notebook content is handed as paste blocks. Direct file edits only after checking the last save time, and only on his go if the save is not recent. This exists because an edit plus reload instruction destroyed his unsaved bottom cells once tonight.
- nproc = 2 means two ANSYS.exe ranks per session (distributed). Never kill ANSYS processes by name, one of them is the live worker.

## Next steps, in rough order

- Discuss the TL curve; decide whether the 1610 Hz pole zero pair warrants a modal analysis now.
- Consider PLANE182 for the structure (conforming with FLUID29) and r weighted FLOW if accuracy passes begin.
- Compare the dip pair against the AMM vault analytical models (piston on surround with edge stiffness rather than limp masses).
- Housekeeping: notebook filename still carries its leading space; Model overview checklist updated tonight, docstring backup refreshed.

## Standing arrangements (unchanged)

Two clients, one server on 50052, ALLSEL after every probe. Vault notes are the workshop copy, module docstring the condensed backup. Geometry loop: plain words, code, view, verify by counts.

## Addendum: setup audit findings (post handover, same night)

John asked for a pre solve setup audit and had me run it live. Verdict: the setup was correct, the audit's first tool was not.

- Element census exact (94 / 84 / 530), rim clamps 28 D entries (7 nodes, midside included, times 2 DOFs times 2 rims), FLOW on 11 source nodes.
- IMPD: 40 element face entries via SFELIST, both ends, value 1. Correct.
- FSI: SFLIST shows nothing because FSI flags are stored as ELEMENT face flags. The correct listing is `SFELIST,ALL,FSI` (shows 84 entries). SF,ALL,FSI is valid on FLUID29 and reports "N FLAGS SET" when issued. Audit cells must use SFELIST for both flags, never SFLIST counting.
- Solver warning census (file0.err): dominated by benign chatter (parameter redefinition from POST26 loops, empty selects from plot fetches). Launcher defaults noted: shape checking off, abort level altered (PyMAPDL standard). One watched item: "Both solid model and finite element model boundary conditions have been applied", 21 occurrences, source context unclear (likely plot/post machinery, not the solve). Check whether it recurs in a clean rebuild plus solve.

## Addendum 2: real time collaboration installed and verified

`jupyter-collaboration` 5.0.0 installed in the frontend env (kernel env untouched), Lab server restarted, closure tested at 01:31: a disk side edit appeared live in John's open tab with no reload, and its deletion propagated the same way. The notebook document now lives in the Jupyter server: John's browser state is always persisted and readable, and Claude's file edits flow into open tabs. The save then reload protocol is retired for the notebook. Residual care: avoid editing the same cell at the same moment, and watch the young RTC plus trame widget combination for misbehavior (uninstall is one pip command). The stray AppData Python 3.13 shadowed `jupyter server` once more during setup; the env's own `python -m jupyter_server` is the reliable call.

## State at close (final, 01:45)

The notebook now reproduces the whole pipeline and John has run it end to end from his side: sweep cell reports 390 frequencies, TL 0 to 88.5 dB (matching the second client run), TL plot renders inline.

Notebook layout at close, 10 cells: launch (attach or launch, HD viewer ratios), build (`%run -i double_wall.py`, full model through mesh and flags), domain viewer, component check, setup audit (SFELIST counts), material + mesh map (grid colored by `ansys_material_type`, edges on), element type map (`ansys_etype`, shows the coupled layer), BC map (clamp, source, absorber node sets marked with counts), TL sweep (`run(mapdl)`, or `solve=False` to reuse a solution), TL plot (FE vs classical limp).

Viewer sharpness: trame renders at canvas size times a ratio, default 1. Cell 0 now sets `pyvista.global_theme.trame.interactive_ratio = 2` and `still_ratio = 2` before any plot. The grid carries `ansys_material_type`, `ansys_etype`, `ansys_elem_num` as cell data, which is what the attribute maps color by.

Working method for the next session: RTC is live and verified. Read the notebook file for John's current state at any time (always current, no save request needed). Direct edits to the notebook flow into his open tab live. Avoid same cell simultaneous edits. The solver lifecycle notes, environment prerequisites, and this working method are all in the project CLAUDE.md and the Ansys vault notes.

Discussion agenda the new chat opens with:
1. The TL curve: the spring edge low frequency divergence, the split dip pair (~280 and 350 Hz), mass law convergence above 900 Hz.
2. The ~1610 Hz pole zero pair: run the modal analysis to identify it, or park it.
3. Accuracy passes if wanted: PLANE182 conformity, r weighted FLOW, mesh convergence.
4. Compare dips against the AMM vault piston on surround analytics.
5. Housekeeping: notebook filename leading space, the [84, 89, 109] chatter, the pyansys env's redundant jupyterlab install.
