# SQUISH certs

certified packings of n unit squares in a square, found with SQUISH (SQuare-packing Using Iterative Shrink-Hopping), with exact rational certificates and the outputs of checks run. registration request: [jlevy/squares#401](https://github.com/jlevy/squares/issues/401)

## current packings

our smallest certified packing for each n, against the best known side on the [Squares Project tracker](https://jlevy.github.io/squares/) (read 2026-10-07):

| n | our side | best known | below it by | certificate |
|---|---|---|---|---|
| 108 | 10.920658939403 | 10.925919390161 | 5.260e-03 | [`squish-submission-2026-10-06/n108`](squish-submission-2026-10-06/n108/) |
| 123 | 11.600907778516 | 11.601384658376 | 4.769e-04 | [`squish-submission-2026-10-07/n123`](squish-submission-2026-10-07/n123/) |
| 126 | 11.773303606607 | 11.774735132388 | 1.432e-03 | [`squish-submission-2026-10-07/n126`](squish-submission-2026-10-07/n126/) |
| 129 | 11.879375206711 | 11.881306218090 | 1.931e-03 | [`squish-submission-2026-10-07/n129`](squish-submission-2026-10-07/n129/) |
| 130 | 11.904483032517 | 11.911187706549 | 6.705e-03 | [`squish-submission-2026-10-06/n130`](squish-submission-2026-10-06/n130/) |
| 153 | 12.879679373333 | 12.881666757009 | 1.987e-03 | [`squish-submission-2026-10-07/n153`](squish-submission-2026-10-07/n153/) |
| 154 | 12.926562245854 | 12.931663721167 | 5.101e-03 | [`squish-submission-2026-10-07/n154`](squish-submission-2026-10-07/n154/) |
| 155 | 12.952503202605 | 12.955619592134 | 3.116e-03 | [`squish-submission-2026-10-07/n155`](squish-submission-2026-10-07/n155/) |
| 179 | 13.891312565741 | 13.895341069976 | 4.029e-03 | [`squish-submission-2026-10-07/n179`](squish-submission-2026-10-07/n179/) |
| 180 | 13.923635004252 | 13.927888140498 | 4.253e-03 | [`squish-submission-2026-10-06/n180`](squish-submission-2026-10-06/n180/) |
| 208 | 14.924518772033 | 14.926534459699 | 2.016e-03 | [`squish-submission-2026-10-07/n208`](squish-submission-2026-10-07/n208/) |
| 209 | 14.949617952202 | 14.953939011857 | 4.321e-03 | [`squish-submission-2026-10-06/n209`](squish-submission-2026-10-06/n209/) |
| 237 | 15.903676235191 | 15.911191683002 | 7.515e-03 | [`squish-submission-2026-10-07/n237`](squish-submission-2026-10-07/n237/) |
| 238 | 15.926146857012 | 15.931725503591 | 5.579e-03 | [`squish-submission-2026-10-07/n238`](squish-submission-2026-10-07/n238/) |
| 239 | 15.949313169729 | 15.953819333481 | 4.506e-03 | [`squish-submission-2026-10-07/n239`](squish-submission-2026-10-07/n239/) |
| 258 | 16.563448002139 | 16.571067811865 | 7.620e-03 | [`squish-submission-2026-10-07/n258`](squish-submission-2026-10-07/n258/) |
| 263 | 16.740446480043 | 16.742270262025 | 1.824e-03 | [`squish-submission-2026-10-07/n263`](squish-submission-2026-10-07/n263/) |
| 303 | 17.920312372920 | 17.924341009851 | 4.029e-03 | [`squish-submission-2026-10-06/n303`](squish-submission-2026-10-06/n303/) |

## folders

| folder | contents |
|---|---|
| [`squish-submission-2026-10-06/`](squish-submission-2026-10-06/) | the first request (2026-10-06): 10 packings, n = 108, 126, 129, 130, 154, 155, 180, 209, 238, 303 |
| [`squish-submission-2026-10-07/`](squish-submission-2026-10-07/) | the update (2026-10-07): 13 packings, the new and the smaller ones below |

earlier folders are never changed: when a smaller packing is found, it goes in a new folder, and the table above says which one is current.

## what the 2026-10-07 update changed

**new (8 n):** 123, 153, 179, 208, 237, 239, 258, 263. none of these were in the first request.

**smaller packings for 5 n of the first request**, which replace the ones in `squish-submission-2026-10-06/` (those stay there, still valid but no longer our smallest):

| n | first request | now | smaller by |
|---|---|---|---|
| 126 | 11.773585291696 | 11.773303606607 | 2.817e-04 |
| 129 | 11.880893587646 | 11.879375206711 | 1.518e-03 |
| 154 | 12.928293657678 | 12.926562245854 | 1.731e-03 |
| 155 | 12.953677069353 | 12.952503202605 | 1.174e-03 |
| 238 | 15.929409027258 | 15.926146857012 | 3.262e-03 |

**unchanged (5 n):** 108, 130, 180, 209, 303; their current certificates are the ones in `squish-submission-2026-10-06/`.

## files in each `nNNN/` folder

| file | contents |
|---|---|
| `nNNN.cert.json` | the exact certificate: n unit squares with rational centres (x, y) and rational t = tan(θ/2), inside the box [0, s]², with `s_exact` the exact side as a fraction |
| `nNNN.cert.txt` | the same packing at 40 digits in David Ellsworth's text format (box centred at the origin): the input of his `check_packing.py` |
| `nNNN.cert50.txt` | the same at 50 digits, which the SVG is drawn from |
| `nNNN.svg` | a drawing of the packing |
| `nNNN_vs_record.png` | the packing beside the best known one, with how each square moved |
| `check_packing_output.txt` | the output of `check_packing.py` on `nNNN.cert.txt` at ε = 1e-40 (VALID for every one) |

to check one yourself: `python check_packing.py nNNN.cert.txt` from inside its folder, with Ellsworth's `check_packing.py`.
