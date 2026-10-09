# SQUISH: 15 new packings, and 2 smaller packings of counts already ours (2026-10-09)

Packings of n unit squares in a square of smaller side than the best known, as listed on the Squares
Project's known-best table (https://jlevy.github.io/squares/), read 2026-10-09. Counts (new): 131, 153, 207, 209, 232, 236, 259, 263, 269, 270, 292, 302, 303, 305, 307.

| n | our side | known best | improvement | type vs the record |
|---|---|---|---|---|
| 131 | 11.949659588035860 | 11.951150044912 | 1.490e-03 | rearrangement |
| 153 | 12.872029849081180 | 12.879679373329 | 7.650e-03 | new alignment |
| 207 | 14.885506308841677 | 14.887992258303 | 2.486e-03 | new alignment |
| 209 | 14.946223654487919 | 14.949617952200 | 3.394e-03 | new alignment |
| 232 | 15.767428349941841 | 15.778174593052 | 1.075e-02 | new alignment |
| 236 | 15.863955747159267 | 15.867800839420 | 3.845e-03 | rearrangement |
| 259 | 16.591378145497698 | 16.602568490493 | 1.119e-02 | rearrangement |
| 263 | 16.733166007899883 | 16.740419679539 | 7.254e-03 | rearrangement |
| 269 | 16.901513582189132 | 16.905967058584 | 4.453e-03 | new geometry |
| 270 | 16.929780126241171 | 16.937807228446 | 8.027e-03 | new alignment |
| 292 | 17.591378145497900 | 17.597249391156 | 5.871e-03 | new geometry |
| 302 | 17.872029849081179 | 17.881306218096 | 9.276e-03 | new geometry |
| 303 | 17.913065462738532 | 17.920312372920 | 7.247e-03 | new geometry |
| 305 | 17.951196144147385 | 17.952959459016 | 1.763e-03 | new alignment |
| 307 | 17.980862784054691 | 17.981030548633 | 1.678e-04 | rearrangement |

**Also: smaller packings of two counts already registered to us (154, 237).** These are not Mondrian compositions:
each is a nearby search from our own packing registered in jlevy/squares#401, and replaces it.

| n | our side | our registered packing (#401) | smaller by |
|---|---|---|---|
| 154 | 12.923070202301140 | 12.926562245854 | 3.492e-03 |
| 237 | 15.902989220874966 | 15.903676235191 | 6.870e-04 |

Sides to 40 digits, exact fractions, the sources of the known bests and the pieces each packing uses: `summary.csv`.
`sources/`: certificates of three of our earlier, unfiled packings (n = 155, 240, 306) that pieces were taken from.

## Contents
Each `nNNN/` folder holds:
* `nNNN.cert.json`: the exact certificate. Every square's centre (x, y) is a rational and its angle is given by
  the rational t = tan(theta/2), so cos = (1-t^2)/(1+t^2) and sin = 2t/(1+t^2) exactly and every square is
  exactly a unit square; the box is [0, S]^2 with S the exact fraction `s_exact`;
* `nNNN.cert.txt`: the same packing in Ellsworth's text format at 50 digits (box centred at the origin), the input
  of his check_packing.py;
* `nNNN.svg`, `nNNN.cert50.txt`: a drawing made from the certificate at 50 digits;
* `nNNN_vs_record.png`: the record packing this was compared with and this packing, to one scale;
* `check_packing_output.txt`: check_packing.py's output on `nNNN.cert.txt`.

## Verification
1. **Exact rational check** (SQUISH): every pair of squares close enough to touch is tested with the
   separating-axis theorem in exact rational arithmetic, and every square against the box; S is the exact
   extent. All pass, in seconds each.
2. **David Ellsworth's check_packing.py** on `nNNN.cert.txt`: `Epsilon: 1E-50 · Container: OK · Overlaps: NONE ·
   VALID` for all. Rerun: `python check_packing.py nNNN/nNNN.cert.txt` (under a second each).
The two share only the certificate data (the 50-digit file rounds the exact one outward); they are separate code
by separate authors.

## Mondrian
The 15 new ones were found by Mondrian, SQUISH's composition method: known packings are cut into rectangular
pieces (sub-packings), two pieces are placed in opposite corners of a box with whole rows and columns of unit
squares filling the rest, and where the composed layout sits just above the record, a search that repairs
its seams can bring it below.

## Pieces
Each of the 15 new packings uses a piece of each of the packings named in `summary.csv` (`found_by`), with the number of squares
taken from each and where to find that packing, followed by a nearby search and/or a squeeze. The pieces come from
the Kingbird catalogue's s(5) and its former records for n = 11, 50, 152, 202 and 241; Francisco Couzo's s(182)
(register) and s(180) (jlevy/squares#451); ry-xu's s(123), s(129) and s(175) (jlevy/squares#432); our s(130),
s(208), s(209) (#401) and s(88) (#422); and three of our unfiled packings, of n = 155, 240 and 306, whose
certificates are in `sources/`.

## Finishing
Before certification, each packing's contact equations (corner on edge, corner on wall) were solved at 60 digits,
and the rational certificate drawn from that solution with a clearance of 1e-32 (n = 263 and 292: about 1e-14). So
each S is within about 1e-30 of the bottom of its arrangement (1e-14 for 263 and 292).

## Not done
Upper bounds only: no optimality claim, no analytic (minimal-polynomial) form of the sides, no formal proof. The
checks above were run by us.
