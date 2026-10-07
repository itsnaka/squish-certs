# SQUISH: 13 smaller packings of n unit squares in a square (2026-10-07)

Packings of n unit squares in a square of smaller side than the best known, as listed on the Squares
Project's known-best table (https://jlevy.github.io/squares/), read 2026-10-07. Counts: 123, 126, 129, 153, 154, 155, 179, 208, 237, 238, 239, 258, 263.

| n | our side | known best | improvement | type vs the record |
|---|---|---|---|---|
| 123 | 11.600907778516340 | 11.601384658376 | 4.769e-04 | rearrangement |
| 126 | 11.773303606607240 | 11.774735132388 | 1.432e-03 | rearrangement |
| 129 | 11.879375206711128 | 11.881306218090 | 1.931e-03 | new geometry |
| 153 | 12.879679373332963 | 12.881666757009 | 1.987e-03 | new alignment |
| 154 | 12.926562245853538 | 12.931663721167 | 5.101e-03 | new alignment |
| 155 | 12.952503202604512 | 12.955619592134 | 3.116e-03 | new alignment |
| 179 | 13.891312565740697 | 13.895341069976 | 4.029e-03 | new geometry |
| 208 | 14.924518772032818 | 14.926534459699 | 2.016e-03 | rearrangement |
| 237 | 15.903676235190628 | 15.911191683002 | 7.515e-03 | new geometry |
| 238 | 15.926146857012470 | 15.931725503591 | 5.579e-03 | new geometry |
| 239 | 15.949313169729190 | 15.953819333481 | 4.506e-03 | new alignment |
| 258 | 16.563448002139153 | 16.571067811865 | 7.620e-03 | new alignment |
| 263 | 16.740446480042869 | 16.742270262025 | 1.824e-03 | rearrangement |

Sides to 40 digits, exact fractions, and the sources of the known bests: `summary.csv`.

## Contents
Each `nNNN/` folder holds:
* `nNNN.cert.json`: the exact certificate. Every square's centre (x, y) is a rational and its angle is given by
  the rational t = tan(theta/2), so cos = (1-t^2)/(1+t^2) and sin = 2t/(1+t^2) exactly and every square is
  exactly a unit square; the box is [0, S]^2 with S the exact fraction `s_exact`;
* `nNNN.cert.txt`: the same packing in Ellsworth's text format at 40 digits (box centred at the origin), the input
  of his check_packing.py;
* `nNNN.svg`, `nNNN.cert50.txt`: a drawing made from the certificate at 50 digits;
* `nNNN_vs_record.png`: the record packing this was compared with and this packing, to one scale;
* `check_packing_output.txt`: check_packing.py's output on `nNNN.cert.txt`.

## Verification
1. **Exact rational check** (SQUISH): every pair of squares close enough to touch is tested with the
   separating-axis theorem in exact rational arithmetic, and every square against the box; S is the exact
   extent. All pass, in seconds each.
2. **David Ellsworth's check_packing.py** on `nNNN.cert.txt`: `Epsilon: 1E-40 · Container: OK · Overlaps: NONE ·
   VALID` for all. Rerun: `python check_packing.py nNNN/nNNN.cert.txt` (under a second each).
The two share only the certificate data (the 40-digit file rounds the exact one outward); they are separate code
by separate authors.

## How they were found
SQUISH (SQuare-packing Using Iterative Shrink-Hopping): an overlap-penalty energy relaxed by L-BFGS inside a
shrink-and-repair basin-hopping search, a sparse-LP polish, and the exact certificate above. How each packing was
found is in `summary.csv` (`found_by`); most come from propagation: our own certified packing of a neighbouring
n with squares removed or added, searched toward smaller boxes and polished. Record packings were read with
Ellsworth's parse_svg_packing.py; no other party's packings were used as starting points.

## Not done
Upper bounds only: no optimality claim, no analytic (minimal-polynomial) form of the sides, no formal proof. The
checks above were run by us.
