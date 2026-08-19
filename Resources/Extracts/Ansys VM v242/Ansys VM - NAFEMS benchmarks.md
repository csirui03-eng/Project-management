---
source: Ansys Mechanical APDL Verification Manual, Release 2024 R2, ANSYS Inc.
pages: "NAFEMS benchmarks vmnr01-1 to vmnr03-1"
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Despite the slice label, these 24 pages are Part IV of the manual, the NRC Piping Benchmarks: twelve seismic piping problems, each present twice. The parent page (VMNR01-1 style) models the problem with current pipe technology (PIPE288/PIPE289/ELBOW290), defers the whole test case description to its companion, and reports Mechanical APDL results only. The -a companion (VMNR01-1-a style) is the legacy-element build (PIPE16/PIPE18) and carries everything reusable: the problem description, the FE model figure, material and geometric properties, the loading, and the target-versus-APDL ratio tables. Every benchmark runs a modal solve followed by a response spectrum solve and checks frequencies, displacements and rotations, reactions, and element section forces against NUREG reference results. The 01 series (seven problems, NUREG/CR-1677 Vol 1, 1980) uses uniform support motion; the 02 series (four problems, NUREG/CR-1677 Vol 2, 1985) uses independent support motion solved as two or three cases (envelope spectrum, ISM with SRSS, ISM with absolute sum); the single 03 problem (NUREG/CR-6645, 1999) exercises missing mass and Lindley rigid response corrections.

## Key ideas
- Twelve benchmarks, each duplicated: legacy-element -a page with full description and target comparisons, parent page with current elements and APDL-only results (VMNR01-1, VMNR01-1-a).
- Analysis pattern is uniform across the slice: modal (ANTYPE = 2) then spectrum (ANTYPE = 8) (VMNR01-1).
- Parent pages state only "For test case description... refer to" the -a page; read the -a page first (VMNR01-1).
- Vol 1 problems apply a uniform acceleration response spectrum via SV and FREQ commands (VMNR01-1-a).
- Vol 2 problems apply independent support excitation via SPVAL and SPFREQ; envelope case still uses SV and FREQ (VMNR02-1-a).
- 02-1 to 02-3 solve three cases (envelope, ISM SRSS, ISM absolute sum); 02-4 solves two (envelope, ISM absolute sum), matching its two input listings (VMNR02-4-a).
- Vol 1 models lump the total mass into MASS21 point masses at named nodes (VMNR01-1-a).
- COMBIN14 spring-dampers represent hangers and snubbers from 01-3 onwards; stiffnesses are tabulated by real constant set (VMNR01-3-a).
- 01-3 is an expanded 01-1 with several anchors and a branch connection representing a real piping system (VMNR01-3-a).
- 01-4 resembles a two-loop reactor: elastically supported vessel, two steam generators, four primary pumps, three and four foot diameter piping (VMNR01-4-a).
- 01-5 is an in-line structure between two anchors; 01-7 is a multi-branched configuration with four anchor points and two distinct excitation spectra sets (VMNR01-5-a, VMNR01-7-a).
- 02-1 is a 3.5 inch water line between two elevations, fifteen-mode approximation, spectrum weighting 1.0, 0.667, 0.0 in X, Y, Z (VMNR02-1-a).
- 02-2 groups its supports into four groups matched to four excitation sets, twenty-five-mode approximation (VMNR02-2-a).
- 02-3 simulates safety injection piping; four spectra sets with the vertical component varying per set, horizontal identical, fifteen-mode approximation (VMNR02-3-a).
- 02-4 is a three-branch, three-anchor subsystem from an actual plant; supports range from soft to virtually rigid; fifty-mode approximation (VMNR02-4-a).
- 03-1 (the BM3 model) uses the first 14 modes, X-direction excitation, SRSS combination, a 75-point input spectrum, lumped mass formulation; case 1 adds missing mass, case 2 adds Lindley rigid response on top (VMNR03-1-a).
- Every VM-NR1677 -a page warns that element forces and moments along Y and Z are flipped between Mechanical APDL and the NRC reference (VMNR01-1-a).
- Agreement for uniform-support problems sits at ratio 1.00 within rounding; ISM absolute sum cases drift further, up to 1.142 on one reaction (VMNR01-1-a, VMNR02-1-a).

## Numbers worth citing
- Fundamental frequency targets (Hz, modal solve): 28.530 (VMNR01-1-a); 8.712 (VMNR01-2-a); 9.360 (VMNR01-3-a); 6.133 (VMNR01-4-a); 4.036 (VMNR01-5-a); 6.391 (VMNR01-6-a); 5.034 (VMNR01-7-a); 6.042 (VMNR02-1-a); 9.360 (VMNR02-2-a); 7.238 (VMNR02-3-a); 2.612 (VMNR02-4-a); 2.910 (VMNR03-1-a).
- Benchmark 1 pipe: E = 24.00 x 10^6 psi, Nu = 0.3, OD = 7.288 in, wall = 0.241 in, bend radius = 36.30 in; nine nodal masses 0.0104 to 0.0503 lb-sec^2/in (VMNR01-1-a).
- Benchmark 2 pipe: E = 27.8999 x 10^6 psi, density = 2.587991718e-10 lb-sec^2/in^4 (as printed; suspect), OD = 2.375 in, wall = 0.154 in (VMNR01-2-a).
- 02-1: E = 0.258 x 10^8 psi, G = 0.992 x 10^7 psi, density = 1.042868 x 10^-3 lb-sec^2/in^4; OD = 3.5 in, wall = 0.216 in, bend radius = 48.003 in; spring supports K = 0.2 x 10^8 and 0.2 x 10^5 lb/in (VMNR02-1-a).
- 03-1: three pipe sizes, OD 3.5/4.5/8.625 in with walls 0.216/0.237/0.322 in; densities 1.043/1.107/1.253 x 10^-3 lb-sec^2/in^4; support stiffnesses 1.0 x 10^5 to 1.0 x 10^20 lb/in; ZPA = 0.54 g (VMNR03-1-a).
- Modal frequency ratios APDL/target are 0.998 to 1.009 across all twelve benchmarks; worst spectrum-solve ratio in the slice is 1.142 (FX at node 46, ISM absolute sum) and low side 0.912 (Fz reactions, missing mass case) (VMNR02-1-a, VMNR03-1-a).

## Definitions introduced
- PX(I), PX(J) - section axial force at element end nodes I and J (VMNR01-1).
- VY, VZ - section shear forces along Y and Z at nodes I and J (VMNR01-1).
- TX - section torsional moment at nodes I and J (VMNR01-1).
- MY, MZ - section bending moments along Y and Z at nodes I and J (VMNR01-1).
- Envelope spectrum excitation - single enveloping spectrum applied to all supports (case 1 of the 02 series) (VMNR02-1-a).
- Independent support excitation - per-support-group spectra, combined by SRSS or by absolute sum (cases 2 and 3) (VMNR02-1-a).
- Missing mass effect - spectrum correction applied with ZPA = 0.54 g; method details not stated (VMNR03-1-a).
- Lindley method - named rigid-responses correction added in case 2; method details not stated (VMNR03-1-a).

## Figures and tables to return to
- Figures 619 to 630 - the twelve FE model sketches, one per benchmark, all on -a pages; the only place the node and element numbering used in the results tables can be identified (VMNR01-1-a to VMNR03-1-a).
- Tables 34 to 94 - target versus Mechanical APDL versus ratio tables, legacy-element builds (-a pages).
- Tables 95 to 145 - Mechanical APDL-only results for the current-element builds (parent pages).
- Per benchmark: 01-1 Fig 619, T34-36/T95-97; 01-2 Fig 620, T37-39/T98-100; 01-3 Fig 621, T40-42/T101-103; 01-4 Fig 622, T43-45/T104-106; 01-5 Fig 623, T46-48/T107-109; 01-6 Fig 624, T49-51/T110-112; 01-7 Fig 625, T52-54/T113-115; 02-1 Fig 626, T55-64/T116-122; 02-2 Fig 627, T65-74/T123-129; 02-3 Fig 628, T75-84/T130-136; 02-4 Fig 629, T85-91/T137-141; 03-1 Fig 630, T92-94/T142-145.

## Where to find what
| Benchmark | Title | Analysis type | Elements | Reference |
|---|---|---|---|---|
| VM-NR1677-01-1 (+ -a) | NUREG/CR-1677 Vol 1, Benchmark Problem 1 | Modal + response spectrum | PIPE289, ELBOW290, MASS21; -a: PIPE16, PIPE18, MASS21 | NUREG/CR-1677 Vol 1 (1980), Problem 1, pp. 24-47 |
| VM-NR1677-01-2 (+ -a) | Vol 1, Benchmark Problem 2 | Modal + response spectrum | PIPE288, MASS21; -a: PIPE16, MASS21 | Vol 1, Problem 2, pp. 48-80 |
| VM-NR1677-01-3 (+ -a) | Vol 1, Benchmark Problem 3 | Modal + response spectrum | PIPE289, ELBOW290, COMBIN14, MASS21; -a: PIPE16, PIPE18, COMBIN14, MASS21 | Vol 1, Problem 3, pp. 81-121 |
| VM-NR1677-01-4 (+ -a) | Vol 1, Benchmark Problem 4 | Modal + response spectrum | PIPE289, ELBOW290, COMBIN14, MASS21; -a: PIPE16, PIPE18, COMBIN14, MASS21 | Vol 1, cited as "Problem 5", pp. 122-217 |
| VM-NR1677-01-5 (+ -a) | Vol 1, Benchmark Problem 5 | Modal + response spectrum | PIPE289, ELBOW290, COMBIN14, MASS21; -a: PIPE16, PIPE18, COMBIN14, MASS21 | Vol 1, cited as "Problem 1", pp. 218-262 |
| VM-NR1677-01-6 (+ -a) | Vol 1, Benchmark Problem 6 | Modal + response spectrum | PIPE289, ELBOW290, COMBIN14, MASS21; -a: PIPE16, PIPE18, COMBIN14, MASS21 | Vol 1, parent cites "Problem 1", pp. 263-327; -a cites "Problem 2, pp. 48-80" |
| VM-NR1677-01-7 (+ -a) | Vol 1, Benchmark Problem 7 | Modal + response spectrum | PIPE289, ELBOW290, MASS21; -a: PIPE16, PIPE18, COMBIN14, MASS21 | Vol 1, cited as "Problem 1", pp. 328-402 |
| VM-NR1677-02-1 (+ -a) | Vol 2, Benchmark Problem 1 | Modal + spectrum, 3 cases (envelope, ISM SRSS, ISM abs sum) | PIPE289, ELBOW290, COMBIN14; -a: PIPE16, PIPE18, COMBIN14 | NUREG/CR-1677 Vol 2 (1985), Problem 1, pp. 18-76 |
| VM-NR1677-02-2 (+ -a) | Vol 2, Benchmark Problem 2 | Modal + spectrum, 3 cases | PIPE289, ELBOW290, COMBIN14, MASS21; -a: PIPE16, PIPE18, COMBIN14, MASS21 | Vol 2, Problem 2, pp. 77-137 |
| VM-NR1677-02-3 (+ -a) | Vol 2, Benchmark Problem 3 | Modal + spectrum, 3 cases | PIPE289, ELBOW290, COMBIN14; -a: PIPE16, PIPE18, COMBIN14 | Vol 2, Problem 3, pp. 138-243 |
| VM-NR1677-02-4 (+ -a) | Vol 2, Benchmark Problem 4 | Modal + spectrum, 2 cases (envelope, ISM abs sum) | PIPE289, ELBOW290, COMBIN14, MASS21; -a: PIPE16, PIPE18, COMBIN14, MASS21 | Vol 2, cited as "Problem 1", pp. 244-445 |
| VM-NR6645-01-1 (+ -a) | NUREG/CR-6645 BM3 model | Modal + spectrum, 2 cases (missing mass; + Lindley rigid response) | PIPE288, ELBOW290, COMBIN14; -a: PIPE16, PIPE18, COMBIN14 | NUREG/CR-6645, Brookhaven, December 1999 |

## Links
[[Modal analysis]], [[Response spectrum method]], [[Independent support motion]], [[Missing mass correction]], [[Seismic analysis of piping]], [[Ansys Mechanical APDL]], [[NUREG-CR-1677]], [[NUREG-CR-6645]]

## Flags
- Slice mislabelled at assignment: the files are Part IV, NRC Piping Benchmarks (VM-NR1677 and VM-NR6645 series), not NAFEMS benchmarks. The frontmatter pages field keeps the assigned wording.
- Input listings exist as separate *txt.html pages (vm-nr1677-*-*txt.html, vm-nr6645-*txt.html); not read, per instruction.
- Reference numbering errata in the source: 01-4 cites "Problem 5"; 01-5, 01-6 (parent), 01-7 and 02-4 cite "Problem 1"; 01-6-a cites "Problem 2, Pages 48-80", which is Problem 2's range, contradicting its parent (pp. 263-327). Page ranges look consistent with the titles; the problem numbers do not.
- VMNR03-1-a errata: reference misspelt "NUREC/CR-6645"; E printed as "0.2.9 x 10^7 psi"; wall thickness "0..2160 in."; its test case cross-references Figure 619 (which belongs to VMNR01-1-a) while its own sketch is Figure 630; title block gives purpose "VM-NR6645-01-1-a" instead of a problem title.
- VMNR01-2-a density 2.587991718e-10 lb-sec^2/in^4 is seven orders below steel; suspected misprint, recorded as printed.
- Notation conflict, stated in every VM-NR1677 -a page: element forces and moments along Y and Z are flipped between Mechanical APDL and NRC results.
- Parent 01-7 lists no COMBIN14 while its -a build has it; parent 02-1 and 03-1 list no MASS21 while 01-series parents do; recorded as printed.
- Cross-references into neighbouring slices: all pages sit under the Part IV overview (vm_nrcbench.html); VMNR01-1-a follows "1.5 Demonstration Problem 3" (vnmr_prob3.html) in book order; both belong to the overview slice handled elsewhere. VMNR01-3-a cross-references VMNR01-1 within this slice; VMNR03-1-a cross-references VMNR01-1-a's Figure 619.
