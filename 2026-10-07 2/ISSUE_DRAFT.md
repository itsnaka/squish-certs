Title: 13 new packings below the register at n = 123–263 (s(n) bounds 4.8e-04 … 7.6e-03 below the reported side): registration request

Following `packing/frontier/README.md#adding-or-reviewing-a-result`.

**Claim.** For 13 counts n, `s(n) ≤ S_n`, where `S_n` is the exact rational side of our certificate, below the register's current reported bound by 4.8e-04 to 7.6e-03. These are new packings, not optima of the register's packings. The counts are 123, 126, 129, 153, 154, 155, 179, 208, 237, 238, 239, 258, 263:

| n | S_n (to 15 digits) | register now | difference |
|---|---|---|---|
| 123 | 11.600907778516340 | 11.601384658376 | 4.769e-04 |
| 126 | 11.773303606607240 | 11.774735132388 | 1.432e-03 |
| 129 | 11.879375206711128 | 11.881306218090 | 1.931e-03 |
| 153 | 12.879679373332963 | 12.881666757009 | 1.987e-03 |
| 154 | 12.926562245853538 | 12.931663721167 | 5.101e-03 |
| 155 | 12.952503202604512 | 12.955619592134 | 3.116e-03 |
| 179 | 13.891312565740697 | 13.895341069976 | 4.029e-03 |
| 208 | 14.924518772032818 | 14.926534459699 | 2.016e-03 |
| 237 | 15.903676235190628 | 15.911191683002 | 7.515e-03 |
| 238 | 15.926146857012470 | 15.931725503591 | 5.579e-03 |
| 239 | 15.949313169729190 | 15.953819333481 | 4.506e-03 |
| 258 | 16.563448002139153 | 16.571067811865 | 7.620e-03 |
| 263 | 16.740446480042869 | 16.742270262025 | 1.824e-03 |

The exact fractions and 40-digit decimals are in `summary.csv`.

**Certificate.** <https://github.com/USER/REPO/tree/COMMIT/FOLDER> (commit COMMIT), one folder per n. `nNNN.cert.json` is a rational packing: n unit squares given by rational centres (x, y) and rational `t = tan(θ/2)`, so `(cos θ, sin θ) = ((1−t²)/(1+t²), 2t/(1+t²))` holds exactly, inside the box [0, S_n]², with `s_exact` the exact fraction S_n. `nNNN.cert.txt` is the same packing in Ellsworth's text format at 40 digits (box centred at the origin), the input of his check_packing.py. `nNNN.svg` is drawn from a 50-digit rendering (`nNNN.cert50.txt`).

**Checking.**
- SQUISH's exact checker (stdlib `Fraction`): every pair of squares close enough to touch is tested with the separating-axis theorem in exact rational arithmetic, and every square against the box; S_n is the exact extent. All pass, in seconds each.
- David Ellsworth's `check_packing.py` on `nNNN.cert.txt`: `Epsilon: 1E-40, Container: OK, Overlaps: NONE, VALID` for all, under a second each. Its output is in each folder (`check_packing_output.txt`).

**What the checkers share.** Only the certificate data (the 40-digit file is an outward rounding of the exact one). Different authors and code.

**Not done.**
- The certificates prove only the upper bounds. The packings were polished to numerical optima, but no KKT, interval or local-optimality evidence is given.
- No closed forms or minimal polynomials.
- Checks were run by us only.

**Lineage and credit.** Built on David Ellsworth's records and tools (record packings read with his parse_svg_packing.py). How each packing was found is in `summary.csv`. Most came from seeding with a certified packing of a neighbouring count, squares removed (or, for a distant count that count's record was built from, carved down to or grafted into that record), followed by a basin-hopping search and polish. The seeds of n = 123, 126, 129, 155, 179, 208, 237, 239, 258, 263 were published packings by Francisco Couzo, read from the Squares Project tracker, as `summary.csv` records for each; the others were our own certified packings. Credit: <YOUR NAME>, with SQUISH (SQuare-packing Using Iterative Shrink-Hopping).

**AI assistance.** <IN YOUR OWN WORDS>
