---
source: Ansys Mechanical APDL Verification Manual, Release 2024 R2, ANSYS Inc.
pages: Part I front matter
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
This slice is the table of contents and Chapter 1 of the Verification Manual. The chapter states what the manual is for: demonstrating Mechanical APDL elements and capabilities on simple problems with "classical" or readily obtainable theoretical solutions, so that agreement with theory builds user confidence. It sets the ground rules for every VM case that follows: how cases were selected, how results are compared (ratio to target), what accuracy to expect, where the input files live, and the fixed format each case uses. The manual as a whole is organised as Part I (this introduction plus test cases VM1 to VM321), Part II (benchmark study descriptions), Part III (NAFEMS benchmarks), Part IV (NRC piping benchmarks), and appendices A to D holding the input listings for each of those four groups (Hlp_V_VMTOC.html). The chapter closes with the symbol list, the units list, and an index from element number to test case.

## Key ideas
- Purpose: demonstrate a wide range of elements and capabilities on problems with known theoretical solutions; close agreement is intended to build confidence in the program (Hlp_V_CH1.html).
- The manual is a small subset of the Ansys Quality Assurance test library; comparisons are against theory, experiment, or independent calculation (Hlp_V_CH1_3.html).
- Most cases solve within the limits of the educational product; some need specific Ansys products (Hlp_V_CH1_3.html).
- Ansys Quality Assurance Services: a subscription giving input data, output data, comparator software, and procedures for automated testing on the customer's own machines (Hlp_V_CH1_3.html).
- Cases are found through index topics, the element-number index, or text search of the online documentation (Hlp_V_CH1_4.html).
- Input files (.dat and .cdb) are download-only from release 23.1; they are no longer installed with the product (Hlp_V_CH1_7.html).
- Enter listings with the /INPUT command, never by manual command-line entry; formatting commands and nested macros break otherwise (Hlp_V_CH1_7.html).
- The cases are verification, not tutorials; step-by-step instruction lives in the other Mechanical APDL manuals and seminar notes (Hlp_V_CH1_6.html).
- Exact match with closed-form theory is neither practical nor desirable; models aim for engineering accuracy with few elements and iterations (Hlp_V_CH1_8.html).
- Comparisons are reported as a ratio, Mechanical APDL result to target, except where the target is zero or non-numerical (Hlp_V_CH1_10.html).
- Reference answers given without sign are restored with sign; where references give only results, input data are back-calculated from a convenient solution point (Hlp_V_CH1_10.html).
- Nonlinear, iterative, or convergence-controlled cases are the most likely to show machine-dependent trailing-digit differences (Hlp_V_CH1_10.html).
- The same problem is sometimes solved several ways to verify different elements or capabilities (Hlp_V_CH1_9.html).
- References are well known textbooks where possible, journals where no textbook solution exists (Hlp_V_CH1_11.html).
- Fixed case format: description, references, figures, assumptions and notes, target and result with ratio, input listing, optional graphics and cross references (Hlp_V_CH1_12.html).
- Notation: {A} vector, [K] matrix, |a| absolute value, ln natural log, log base 10 (Hlp_V_CH1_13.html).
- Cases need only minimum memory and short run times; benchmark run times depend on chosen parameters (Hlp_V_CH1_14.html).

## Numbers worth citing
- 321 verification cases, VM1 to VM321, listed in the manual contents (Hlp_V_VMTOC.html).
- Average accuracy of the result comparisons: within 1 to 2 % of the target solution, per the manual's own survey (Hlp_V_CH1_8.html).
- All results and input listings correspond to Ansys 2024 R2; the case file bundle is VM2024R2_MAPDL.zip (Hlp_V_CH1_7.html).
- Mechanical APDL (formerly Ansys) in commercial use since 1970 (Hlp_V_CH1.html).
- Slide-rule accuracy example, problem 3: reference 10,200 psi, hand recalculation 10,152.258 psi, Mechanical APDL 10,152 psi (Hlp_V_CH1_10.html).
- A result printed as 0.01234 in the manual may appear as 0.012335271 on other hardware (Hlp_V_CH1_10.html).

## Definitions introduced
- Ratio (Mechanical APDL:Target) - the normalised comparison reported for each case, program result over target value (Hlp_V_CH1_10.html).
- Engineering accuracy - reasonably accurate agreement obtained with a low number of elements and iterations (Hlp_V_CH1_8.html).
- Figure conventions - node numbers upright, keypoint numbers italic, line numbers italic with prefix L, element numbers circled, area numbers boxed, volume numbers in a hexagon (Hlp_V_CH1_13.html).

## Figures and tables to return to
- Abbreviation and symbol table (unnumbered) - the symbol meanings assumed by all 321 case descriptions, from a for acceleration to omega for circular frequency (Hlp_V_CH1_15_1.html).
- Units abbreviation table (unnumbered) - unit shorthand used throughout, AbAmpere to Ohm (Hlp_V_CH1_15_2.html).
- Index by Element Number (unnumbered table) - element name plus analysis-type keyword to test case numbers, with hyperlinks; the fastest route from an element to its verification cases (Hlp_V_CH1_IDXELEMNUM.html).

## Where to find what
| Topic | Pages |
| --- | --- |
| Manual contents: Parts I to IV, appendices A to D, VM1 to VM321 | Hlp_V_VMTOC.html |
| Chapter overview, purpose of the manual, program history | Hlp_V_CH1.html |
| Program overview: element library, PREP7, postprocessors | Hlp_V_CH1_2.html |
| Program verification, QA test library, QA Services | Hlp_V_CH1_3.html |
| Finding test cases of interest | Hlp_V_CH1_4.html |
| Accessing input files, download link, /INPUT usage, appendix links | Hlp_V_CH1_7.html |
| Verification Manual versus other documentation | Hlp_V_CH1_6.html |
| Expected results, engineering accuracy, 1 to 2 % figure | Hlp_V_CH1_8.html |
| Test case selection and method of solution | Hlp_V_CH1_9.html |
| Numerical comparisons, ratios, machine dependence | Hlp_V_CH1_10.html |
| Choice of references | Hlp_V_CH1_11.html |
| Test case format | Hlp_V_CH1_12.html |
| Symbols, nomenclature, figure conventions | Hlp_V_CH1_13.html |
| Memory requirements and run times | Hlp_V_CH1_14.html |
| Abbreviation and symbol list | Hlp_V_CH1_15_1.html |
| Units abbreviation list | Hlp_V_CH1_15_2.html |
| Index by element number | Hlp_V_CH1_IDXELEMNUM.html |

## Links
[[Ansys]], [[Mechanical APDL]], [[Finite element method]], [[Verification and validation]], [[NAFEMS]]

## Flags
- Hlp_V_CH1_IDXELEMNUM.html (142 KB) is the element-number-to-test-case index; only its first 150 lines were read to characterise it. Open it directly when hunting cases for a given element; do not duplicate it into notes.
- Suspected erratum in that index: under BEAM188, the Prestress row displays VM127 but links to Hlp_V_VM77.html.
- Section 1.2 says the product applicability of test cases "can be determined from the following table", but no table is present on the page (Hlp_V_CH1_3.html).
- File numbering does not follow section numbering: section 1.4 sits in Hlp_V_CH1_7.html and section 1.5 in Hlp_V_CH1_6.html; there is no Hlp_V_CH1_5.html.
- Continues in neighbouring slices: the 321 VM case descriptions (Hlp_V_VM1.html onward) and the Part II to IV benchmark material (Hlp_V_CH2_*.html and later) are handled by other agents; appendices A to D are input listings only.
