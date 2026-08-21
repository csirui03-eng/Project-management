# Double wall impedance tube model

Axisymmetric MAPDL model of a double wall in a 100 mm impedance tube.
Code: `D:\Pyansys projects\Double wall test script\double_wall.py`. The
module docstring carries a condensed copy of this note — update it from
here before closing a session.

## System

Two identical walls in a rigid tube, each a **piston on a surround**: MDF
disc (0–45 mm) suspended by a silicone annulus (45–50 mm) clamped at the
tube wall. Air gap between walls; air columns either side. Mass-air-mass
resonator measured for normal-incidence transmission loss.

## Cross-section (r–z, axis at left)

| Layer (bottom → top) | Region | Extent |
| --- | --- | --- |
| upstream air | `AIR_UP_A` | y = 0 → 100 mm (source line splits it at y = ys) |
| wall 1 | `W1_SOLID_A` + `W1_EDGE_A` | 5 mm thick; solid 0–45 mm, edge 45–50 mm |
| gap air | `AIR_GAP_A` | 40 mm |
| wall 2 | `W2_SOLID_A` + `W2_EDGE_A` | 5 mm thick |
| downstream air | `AIR_DOWN_A` | 100 mm |

X = radial, Y = tube axis, axis on X = 0. All SI.

## Materials

| Slot | Material | Values |
| --- | --- | --- |
| 1 | MDF | E = 3.2 GPa, ν = 0.25, ρ = 750 kg/m³ |
| 2 | Silicone (Shore 30A) | E = 1.1 MPa, ν = 0.47, ρ = 1100 kg/m³ |
| 3 | Air | ρ = 1.225 kg/m³, c = 340 m/s |

Element types: 1 = PLANE183 axisymmetric (structure), 2 = FLUID29 coupled
(interface air layer), 3 = FLUID29 uncoupled (interior air).

## Boundary inventory — every edge has one job

- **y = 0 (inlet)** — anechoic absorber; eats down-going source radiation
  and wall reflections. Pretends the tube continues forever.
- **y = ys (source line)** — interior mass-source sheet; the only energy
  input. Radiates both ways; down-going half dies in the inlet absorber.
- **y = y5 (outlet)** — anechoic absorber; transmitted wave purely outgoing.
- **x = 0 (axis)** — nothing; axisymmetric formulation handles it.
- **x = r_tube, air** — nothing; unloaded acoustic boundary is naturally
  rigid = hard tube wall, for free.
- **x = r_tube, wall rims** — clamped (D, both DOFs); the one structural BC.
- **air–wall faces** — FSI flags on the wetted fluid faces; where the two
  physics couple.

## Measurement

- Two virtual mics upstream between ys and wall 1 (spacing < λ/2 over the
  band) decompose incident vs reflected — same as the physical two-mic method.
- One mic downstream: anechoic outlet means transmitted wave only.
- TL = 20·log10 |p_inc / p_trans|.

## Open items

- [ ] Split upstream air rectangle at ys; name `SOURCE_L`
- [ ] Verify FLUID29 flags against its element page before writing them:
  keyopt numbering (axisym / structure-present), IMPD absorber recipe
  (MU admittance), FLOW mass-source syntax
- [ ] Attributes + mesh (per component), then line components + loads
- [ ] Element size: fluid needs ≥ ~6 el./λ at 4 kHz → ≤ ~14 mm; silicone
  edge needs 2–3 elements across its 5 mm — edge governs locally
