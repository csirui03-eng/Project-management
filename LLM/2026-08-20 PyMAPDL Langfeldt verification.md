# PyMAPDL setup and Langfeldt verification — 2026-08-20

LLM session record. Code lives in `D:\mam-fem` (own git repo, hand-versioned);
this note is the vault-side summary.

## What was established

- **Environment**: the machine runs Ansys Student **2026 R1 (v261)**, not the
  2024 R2 the VM extracts document. PyMAPDL 0.74.1 auto-discovers it; gRPC on
  127.0.0.1:50052. Plot calls need `pip install "ansys-mapdl-core[graphics]"`
  (installed). Kernel: "Python (PyAnsys)", kernelspec `pyansys`.
- **Solver benchmark**: VM157 (acoustic modal, FLUID30) reproduced — amplitude
  ratio 0.447 vs target 0.450, ratio 1.007. All 534 VM decks ship inside
  PyMAPDL (`ansys.mapdl.core.examples.vmfiles`); the Student install has none.
  Strip `/EXIT`, `/SHOW`, `JPGPRF`, `/VERIFY` before `mapdl.input()`.
- **Builder**: parametric Langfeldt cell (20×20 mm PEI, 25 µm, T = 160 N/m,
  0.2 g steel disc R = 2 mm), pure-script geometry, topology-based selection
  (`LSEL,S,EXT` rim; inverse → interface arcs → disc), components rebuilt each
  call. Bare-membrane check: FE f₁₁ = 2509.8 Hz vs analytical 2509.8 Hz.
- **Tension**: INISTATE biaxial σ = T/h → static solve → linear perturbation
  (`PERTURB,MODAL` / `PERTURB,HARM`). Membrane-only SHELL181 has zero bending
  stiffness, so a plain modal/harmonic on the unstressed model is singular —
  the two-step solve is forced, not optional.

## Langfeldt verification result

Both sides compute TL the way Langfeldt's analytical model does: in-vacuo
response under uniform pressure → effective surface mass → 
t = 1/(1 + iω·m_eff/(2ρ₀c₀)). No FEM fluid involved.

| TL(100 Hz) | Galerkin (MATLAB port) | FE density-patch | FE rigid disc |
|---|---|---|---|
| centred | 26.07 dB | 26.03 dB | **26.07 dB** |
| offset +5 mm | 26.35 dB | 26.31 dB | **26.35 dB** |

- First-resonance dips: Galerkin 276/299 Hz, FE rigid 270/300 Hz (10 Hz
  grid), FE density-patch 260/280 Hz.
- **Decision (John): rigid disc is the way to go** — CERIG transverse rigid
  plane + MASS21 with rotary inertia. It reproduces the Galerkin curve across
  100–4000 Hz; the density-patch model runs ~6% low on f₁ and grows spurious
  internal patch modes above 1 kHz.
- The Galerkin port replaced the singular-B block eigenproblem with exact
  null-space constraint enforcement (same physics; MATLAB's `eigs(σ=1)`
  skirted the issue, scipy's ARPACK and dense QZ both drowned in it).

![[tl_comparison.png]]

## Open question

Week 5 acceptance record: COMSOL direct solve gave **TL(100 Hz) = 27.3 dB**.
Both in-vacuo models here give **26.1 dB**. The 1.2 dB gap sits between the
two references, not in MAPDL. Candidate causes: COMSOL includes air
mass-loading (real fluid columns), or 27.3 was a digitised read of Fig. 6a.
Resolve against the paper figure directly.

## MAPDL gotchas (paid for in errors)

- Linear-perturbation results go to `file.rstp`; POST1 reads `file.rst`
  unless told `FILE,file,rstp`. **No error is raised — you silently read the
  static base solution.**
- Undamped harmonic + real load writes no imaginary result sets; `SET,,,,1`
  is a hard error. Guard it.
- A crashed PyMAPDL script leaves `ansys261.exe` alive holding `file.lock`,
  blocking the next launch. Wrap runs in `try/finally: mapdl.exit()`.
- CERIG's master node must be in the active selection — `NSLA` narrowing
  deselects it. The stale-selection trap from the paradigm notes, live.

## Next milestone

Acoustic column via FSI (FLUID30/220 + PML), starting decks VM177/VM282.
End target: TL vs Langfeldt Fig. 6a/6b with real fluid loading — which may
also settle the 27.3 vs 26.1 dB question.
