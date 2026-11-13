> **Experimental. We are just trying this.** [Disclaimer](../DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value.
>
> Our own testing. What we observed in this run, on our own nodes. Not a claim about how TN10 or Kaspa behave in general. No key, seed, txid, covenant id, address, host or port.

# Lessons, pre-run 17

Written after the run stopped, 2026-11-13, from the files on origin and the desk's own logs (read-only). Times are UTC unless marked Brussels.

## Short version

- **Pre-run 17 failed before RETURN.** At 02:12:41Z, three minutes into the second part of the duel, the family lane (key 0) fell under its abort line: 17,396 usable tKAS against 18,000. The runner stopped everything itself and put [logs/FAILED.md](FAILED.md) on origin (02:12:48Z). The run is not resumed; a next attempt is a new repo. HOLD-3, HOLD-4, RETURN and the one-sided variant were not observed.
- **The cause is ours, in the setup.** Before the open we refilled key 0 with about 29,870 tKAS (to 47,265 usable). That was sized on fees. It should have been sized on how fast the families use key 0's coins: about 1.06 usable tKAS per OK hop in this run (29,892 usable for 28,206 OK hops), about 56,000 over pre-run 16's run. At this run's pace (about 690 OK hops a minute, about 730 usable tKAS a minute) the planned run (about 90 minutes of families, through RETURN) needed about 65,000 usable; we had about 29,000 above the line. The abort line did its job.
- **What we did see, 15 minutes of the symmetric duel:** both lanes stepped *down*, 150 → 120 → 100, within four minutes, and sat at the 100 floor for the rest (10 minutes), splitting the heavy places about 50/50 (lane 1's share 48–51 percent). Neither lane was ever under 90 percent of its reference (lowest 91), so the rule never stepped either one up. **No spiral, no cap, nobody gave up.** This is what the offline run of the controller predicted before the run (the addendum in [plan/PLAN.md](../plan/PLAN.md)), and the opposite of our first guess.
- Our two lanes slowed other TN10 users' transactions while they ran (below).

## The question

Pre-run 16's duel was lopsided (a light covenant side against our heavy lane) and settled near twice the lane's rate. Pre-run 17 put **two equal heavy lanes of our own** against each other (30 chains each, about 266,700 storage mass a transaction, one rule for both), with four fixed-rate covenant tiers as bystanders (floor 100, r150 150, r300 300, r450 450, four families each): does the rate settle, spiral to the 2,000 cap, or does one side give up?

The rule, once a minute, each lane reading only its own landings: under 90 percent of its own reference → × 1.25 (cap 2,000); at or over 90 percent two minutes running → × 0.8 (floor 100); otherwise unchanged. References from HOLD-1 (both at 150), minutes 2–12: **lane 1 266, lane 2 269** landed a minute.

## What happened

- Before the open: the probe's mempool read was fixed (light node figures above 10,000 entries; the 128 MiB wRPC reply cap explains pre-run 16's failure at about 13,000), key 0 refilled from the payment pile (1,400 coins, 29,870 tKAS, fees 3.22) and its small coins consolidated (329 into 28, fees 0.38), keys 1–15 funded, hop calibration at 100 and 450 and lane calibration at 100 and 2,000 matched the node. An offline run of the controller code changed the one-sided variant before the run (lane 1 greedy). Offline rehearsal p17-a exited 0. The bot's free check ran once, read-only, before arming.
- Live run: desk runner 01:30:40Z. BASE 01:33–01:44 (both lanes 0), HOLD-1 01:45–01:56 (both 30 at 150: the reference), HOLD-2 = duel part 1 01:57–02:08, HOLD-3 from 02:09. Every published minute kept pace and was clean; no repair, no restart. BASE, HOLD-1 and HOLD-2 are on origin for the desk and for Mini.
- **02:12:41Z: `LANE_COINS_LOW coins=2436 usable=17396`, `FAILED the family lane reached the abort line`, `RUN_STOP reason=failed`.** The families, both lanes, the counter and the probe stopped; no process of the run was left on the desk. The private TN10 kaspad was not stopped. Mini's runner saw FAILED.md and stopped (02:13:04Z); the bot's waiter saw it and stopped (02:12:53Z), and sent nothing.
- The outside heavy fee-100 stream that was present in pre-runs 14–16 was **absent** all run (mempool 6–17 entries in BASE, about 100–200 with our lanes). So our two lanes were the only heavy traffic we saw.
- Inclusion up to the stop (the counter's own totals): hops 28,136 landed of 28,206 OK, lane 15,055 of 15,160 OK; the rest were in the minute open at the stop (02:12, not counted). 0 lane rejects, 0 lost.

## The rate path

| Part | Minutes | Lane 1 | Lane 2 |
|---|---|---|---|
| HOLD-1 reference | 01:45–01:56 | 150 | 150 |
| Duel 1 | 01:57–02:08 | 150 150 150 120 120 100 100 100 100 100 100 100 | the same |
| Duel 2 (stopped after 3 minutes) | 02:09–02:11 | 100 100 100 | the same |

Rates are those in effect at each minute's start (a decision lands about 22 s into the next minute). Decisions: both lanes 150 → 120 on the 01:58 minute (96 and 93 percent of their references, the second good minute), both 120 → 100 on the 02:00 minute (106 and 103 percent). From then on both were at the floor and the rule had nothing left to do. 0 steps up, 2 steps down each. Lane landings in the duel: lane 1 253–297, lane 2 246–297 a minute, 91–112 percent of their references.

**It settled at the floor; it did not spiral.** The two lanes were the same, followed the same rule, and split the heavy places evenly, so both kept seeing good minutes and both stepped down. Minute-to-minute noise (about ±8 percent here) did not reach the 90 percent line once.

## Landing and cost

| Part | Lane rates | Floor % BASE | R150 % BASE | R300 % BASE | R450 % BASE | Lane 1 / 2 landed, median | Other traffic, median | Fee est. priority, median |
|---|---|---:|---:|---:|---:|---:|---:|---:|
| BASE (12 min) | 0 / 0 | 100 (93–106) | 100 (91–105) | 100 (93–106) | 100 (92–107) | — | 3,152 | 175 |
| HOLD-1 ref (12) | 150 / 150 | 39 (35–43) | 64 (60–71) | 97 (90–100) | 106 (100–110) | 265 / 269 | 2,946 | 380 |
| Duel, 150 → 120 (01:57–02:01, 5) | 150–120 | 44 (31–70) | 71 (62–86) | 97 (95–103) | 106 (103–111) | 256 / 263 | 3,008 | 354 |
| Duel at 100 / 100 (02:02–02:11, 10) | 100 / 100 | 70 (65–74) | 89 (85–93) | 104 (97–108) | 108 (105–111) | 288 / 282 | 2,965 | 314 |

BASE per family: floor 47.4, r150 48.6, r300 48.6, r450 47.9 hops a minute.

- With both lanes at 150, a hop at the lanes' own rate (r150) kept 64 percent of BASE, twice the rate (r300) 97, three times (r450) 100–110: the "about twice" reading of pre-runs 14–16 again, here against 30 + 30 at about 40 blocks of ready mass.
- When the lanes stepped down to 100, every fixed tier did better: floor from 39 to 70 percent, r150 from 64 to 89. The lanes did not land less: they landed a little *more* (about 285 each against 265), but the node also merged more blocks a minute in those minutes (median 636 against 570 in HOLD-1), and the lanes' landings per merged block stayed about the same (0.90 against 0.93). So we cannot say how much of the bystanders' gain was the lower lane rate and how much was the extra blocks.
- Cost per lane transaction (lane log, fees ÷ OK): 0.397 tKAS at 150, 0.303 at 120, 0.267 at 100. In this duel both sides ended up paying a third less than at the reference for slightly more landings.

## Theory against what we observed

| Written before the run ([plan/PLAN.md](../plan/PLAN.md)) | Observed (15 duel minutes, then the stop) |
|---|---|
| First guess: an upward drift, a leapfrog sawtooth, median 200–400. | No: both stepped down to 100 in four minutes. |
| Addendum (offline run of the controller code): in a pure two-lane world the symmetric rule drifts down to 100/100; a spiral there would surprise us; bystanders might push both back up. | Yes, the drift down. The bystanders did not push the lanes back up: at 100 the lanes still landed 103–112 percent of their references. |
| The one-sided variant (lane 1 greedy) should climb. | Not observed: the run stopped before it. |
| Fixed tiers lose more the higher the lanes go. | Consistent with what we saw over 100–150; no higher rates were reached. |
| Other users lose about 10–13 percent of landings at 150. | About 6–7 percent here (below), with no outside stream. |

## Our lanes slowed other TN10 users

During the 27 lane minutes (12 at 150, 15 in the duel at 150 → 100), other traffic landed on our desk node had a median of 2,946 a minute at 150 and 2,965 at 100, against 3,152 in BASE: about 6–7 percent lower. There was no outside heavy stream this time, so "other traffic" is other users' load (and the genesis), not a stream of its own. The node's priority fee estimate read a median of 380 with our lanes at 150 and 314 at 100, against 175 in BASE. Our own floor hops at 100, a stand-in for a low-fee user, ran at 35–43 percent of BASE while the lanes were at 150 and 65–74 percent at 100. We did this on purpose, with the operator's OK, in bounded steps, and it is in this repo's [public statement](../PLAYBOOK.md#public-statement). The lanes stopped with the run at 02:12:41Z (60 of their transactions were still in the mempool then; we did not read them after).

## Bot

The bot sent nothing. Its waiter was still waiting for desk HOLD-3 when FAILED.md reached origin; it logged `HALT logs/FAILED.md on origin` at 02:12:53Z and its finisher published nothing. There is no `counts/bot/HOLD-4.md` in this run: no pinned minute was set, so neither a send nor a `NO SEND` was due. The free check ran once, read-only, before arming (01:05:45Z): kept nodes 1 and 5, 2 distinct kaspads, no free node.

## Mini

Mini read every published minute in full (12 / 12 / 12) and matched the desk in **144 of 144** cohort cells (floor / r150 / r300 / r450 per minute), with 0 late removals. Its runner stopped on FAILED.md; its TN10 kaspad was not wiped or restarted.

## Spend

| Item | tKAS |
|---|---:|
| Our two heavy lanes, fees | 5,117.08 (lane 1 2,535.82, lane 2 2,581.25); 568.50 parked on our sink key, not swept |
| Family hops, fees (floor / r150 / r300 / r450) | 3,132.89 (217.45 / 409.51 / 982.72 / 1,523.21), node mass about 41,000 a hop |
| Refill of key 0 and consolidation before the open | 3.60 (3.22 + 0.38); the refill moved 29,870 tKAS between our own keys |
| Calibrations | a handful of single transactions |
| Bot | 0 |
| **About** | **8,250** |

Family submit results other than OK were `already_spent` and `orphan` only (the builder's waiting retries); 0 rate or full rejects. tKAS is not a limit (operator, 12 Nov).

Keys after the stop (read-only status): key 0 2,433 coins over 3 tKAS, **17,373 usable** (abort line 18,000), **2,104 small coins** (0 before the run: change fragments); keys 1–15 have no genesis coin; payment pile 5,438 coins.

## Quirks

- The probe's mempool fix held: every sample read (the mempool stayed under 250 entries, so the full read ran each time; the light path was not needed live).
- The node merged more blocks a minute from about 02:00Z (600–650 against 540–570 before), which helps every class at once; see above.
- Pre-run 13 also failed on this abort line, then from change fragments with plenty of tKAS left. This time the line was reached by real use of key 0's coins plus fragments.

## What this seems to show

- Two equal heavy lanes on the same "pay more when behind, a little less when fine" rule did not bid each other up. They split the heavy places evenly, both kept seeing good minutes, and both stepped down to the floor within four minutes. A symmetric rule with a 90 percent line and a two-minute down step seems to need something that hurts *both* sides (an outside stream, a target above an even share) before it climbs.
- With both lanes at 150, about twice their rate was again enough for a covenant hop to keep its BASE pace.
- What this cannot say: 15 duel minutes, then the stop; both sides ours on one rule with fixed references; one node's view; no outside stream; the one-sided (greedy) variant never ran. We are just testing.

## Every minute (BASE, HOLD-1, HOLD-2, and HOLD-3 to the stop)

Rates in effect at the minute's start; decisions are the duel log's (rate before → after, applied about 22 s into the next minute). Merged blocks is the counter's coinbase count (one per merged blue block). The HOLD-3 minutes are from the desk's local logs (counter final lines and probe samples); they were never published as a step file.

| Min (UTC) | Step | Lane 1 / lane 2 rate in effect | Floor / fam (% BASE) | R150 / fam | R300 / fam | R450 / fam | Lane 1 landed | Lane 2 landed | Lane 1 / 2, % of ref | Lane 1 decision | Lane 2 decision | Other traffic | Merged blocks | Ready, blocks | Fee est. priority |
|---|---|---|---:|---:|---:|---:|---:|---:|---|---|---|---:|---:|---:|---:|
| 01:33 | BASE | 0 / 0 | 48.0 (101%) | 51.0 (105%) | 51.5 (106%) | 51.0 (107%) | 0 | 0 | — | — | — | 3,163 | 553 | 1.2 | 167.3 |
| 01:34 | BASE | 0 / 0 | 48.2 (102%) | 49.0 (101%) | 50.8 (104%) | 49.8 (104%) | 0 | 0 | — | — | — | 3,343 | 541 | 1.4 | 168.9 |
| 01:35 | BASE | 0 / 0 | 46.8 (99%) | 45.2 (93%) | 45.0 (93%) | 44.2 (92%) | 0 | 0 | — | — | — | 3,164 | 505 | 1.2 | 221.0 |
| 01:36 | BASE | 0 / 0 | 50.0 (106%) | 49.8 (102%) | 50.2 (103%) | 50.8 (106%) | 0 | 0 | — | — | — | 3,070 | 543 | 1.2 | 171.3 |
| 01:37 | BASE | 0 / 0 | 49.5 (104%) | 50.8 (104%) | 51.2 (105%) | 49.8 (104%) | 0 | 0 | — | — | — | 3,161 | 544 | 1.3 | 180.9 |
| 01:38 | BASE | 0 / 0 | 48.2 (102%) | 49.8 (102%) | 50.5 (104%) | 49.0 (102%) | 0 | 0 | — | — | — | 3,120 | 508 | 1.1 | 140.0 |
| 01:39 | BASE | 0 / 0 | 46.2 (98%) | 48.2 (99%) | 47.5 (98%) | 47.0 (98%) | 0 | 0 | — | — | — | 3,152 | 540 | 1.2 | 178.5 |
| 01:40 | BASE | 0 / 0 | 48.8 (103%) | 49.2 (101%) | 49.2 (101%) | 47.5 (99%) | 0 | 0 | — | — | — | 3,151 | 550 | 1.5 | 179.2 |
| 01:41 | BASE | 0 / 0 | 46.8 (99%) | 46.2 (95%) | 47.2 (97%) | 47.8 (100%) | 0 | 0 | — | — | — | 3,072 | 542 | 1.3 | 178.4 |
| 01:42 | BASE | 0 / 0 | 45.2 (96%) | 46.0 (95%) | 48.0 (99%) | 48.0 (100%) | 0 | 0 | — | — | — | 3,170 | 543 | 0.7 | 100.0 |
| 01:43 | BASE | 0 / 0 | 44.2 (93%) | 44.2 (91%) | 46.8 (96%) | 46.5 (97%) | 0 | 0 | — | — | — | 3,129 | 472 | 1.2 | 137.9 |
| 01:44 | BASE | 0 / 0 | 44.2 (93%) | 46.2 (95%) | 46.5 (96%) | 47.0 (98%) | 0 | 0 | — | — | — | 3,149 | 467 | 1.5 | 183.2 |
| 01:45 | HOLD-1 | 150 / 150 | 18.5 (39%) | 29.2 (60%) | 44.0 (90%) | 47.8 (100%) | 225 | 246 | — | — | — | 2,912 | 525 | 32.3 | 402.1 |
| 01:46 | HOLD-1 | 150 / 150 | 18.2 (39%) | 32.2 (66%) | 46.8 (96%) | 52.2 (109%) | 263 | 272 | — | — | — | 3,175 | 566 | 38.2 | 389.1 |
| 01:47 | HOLD-1 | 150 / 150 | 18.0 (38%) | 31.5 (65%) | 47.0 (97%) | 49.5 (103%) | 277 | 243 | — | — | — | 2,974 | 549 | 35.9 | 371.1 |
| 01:48 | HOLD-1 | 150 / 150 | 17.8 (37%) | 31.0 (64%) | 48.2 (99%) | 51.5 (108%) | 246 | 261 | — | — | — | 2,927 | 542 | 41.0 | 361.7 |
| 01:49 | HOLD-1 | 150 / 150 | 19.0 (40%) | 30.8 (63%) | 47.8 (98%) | 49.2 (103%) | 262 | 294 | — | — | — | 2,939 | 603 | 40.7 | 379.9 |
| 01:50 | HOLD-1 | 150 / 150 | 20.2 (43%) | 34.5 (71%) | 47.5 (98%) | 51.8 (108%) | 276 | 288 | — | — | — | 2,950 | 607 | 42.2 | 378.9 |
| 01:51 | HOLD-1 | 150 / 150 | 19.5 (41%) | 30.5 (63%) | 47.5 (98%) | 48.8 (102%) | 240 | 267 | — | — | — | 2,909 | 554 | 40.7 | 384.3 |
| 01:52 | HOLD-1 | 150 / 150 | 17.8 (37%) | 30.8 (63%) | 47.0 (97%) | 51.0 (107%) | 269 | 268 | — | — | — | 2,981 | 574 | 38.6 | 380.3 |
| 01:53 | HOLD-1 | 150 / 150 | 17.0 (36%) | 32.5 (67%) | 48.8 (100%) | 52.8 (110%) | 283 | 269 | — | — | — | 2,987 | 593 | 41.2 | 385.8 |
| 01:54 | HOLD-1 | 150 / 150 | 18.5 (39%) | 30.8 (63%) | 46.2 (95%) | 50.2 (105%) | 233 | 280 | — | — | — | 2,942 | 559 | 41.0 | 366.3 |
| 01:55 | HOLD-1 | 150 / 150 | 16.8 (35%) | 33.5 (69%) | 46.8 (96%) | 49.0 (102%) | 266 | 269 | — | — | — | 2,987 | 578 | 39.9 | 385.9 |
| 01:56 | HOLD-1 | 150 / 150 | 20.0 (42%) | 33.8 (69%) | 48.0 (99%) | 52.5 (110%) | 267 | 275 | — | — | — | 2,901 | 584 | 38.3 | 341.9 |
| 01:57 | HOLD-2 | 150 / 150 | 17.0 (36%) | 30.8 (63%) | 47.2 (97%) | 50.8 (106%) | 253 | 263 | 95% / 98% | 150->150 | 150->150 | 3,008 | 562 | 38.5 | 376.4 |
| 01:58 | HOLD-2 | 150 / 150 | 14.5 (31%) | 30.0 (62%) | 46.5 (96%) | 49.5 (103%) | 256 | 249 | 96% / 93% | 150->120 | 150->120 | 3,134 | 543 | 42.1 | 396.2 |
| 01:59 | HOLD-2 | 150 / 150 | 21.0 (44%) | 34.5 (71%) | 46.2 (95%) | 49.8 (104%) | 255 | 246 | 96% / 91% | 120->120 | 120->120 | 3,056 | 547 | 40.9 | 353.5 |
| 02:00 | HOLD-2 | 120 / 120 | 28.5 (60%) | 40.0 (82%) | 50.2 (103%) | 52.2 (109%) | 282 | 277 | 106% / 103% | 120->100 | 120->100 | 2,966 | 616 | 41.5 | 336.9 |
| 02:01 | HOLD-2 | 120 / 120 | 33.2 (70%) | 42.0 (86%) | 49.2 (101%) | 53.2 (111%) | 294 | 294 | 111% / 109% | 100->100 | 100->100 | 2,950 | 647 | 37.6 | 326.3 |
| 02:02 | HOLD-2 | 100 / 100 | 34.2 (72%) | 45.0 (93%) | 52.5 (108%) | 53.0 (111%) | 290 | 282 | 109% / 105% | 100->100 | 100->100 | 2,961 | 642 | 38.2 | 331.8 |
| 02:03 | HOLD-2 | 100 / 100 | 32.5 (69%) | 43.5 (89%) | 48.2 (99%) | 50.2 (105%) | 263 | 280 | 99% / 104% | 100->100 | 100->100 | 2,995 | 613 | 40.1 | 307.1 |
| 02:04 | HOLD-2 | 100 / 100 | 31.0 (65%) | 41.2 (85%) | 47.0 (97%) | 50.5 (105%) | 288 | 278 | 108% / 103% | 100->100 | 100->100 | 2,965 | 615 | 39.1 | 278.5 |
| 02:05 | HOLD-2 | 100 / 100 | 35.2 (74%) | 44.8 (92%) | 50.5 (104%) | 50.5 (105%) | 292 | 282 | 110% / 105% | 100->100 | 100->100 | 2,921 | 630 | 38.8 | 320.6 |
| 02:06 | HOLD-2 | 100 / 100 | 33.8 (71%) | 44.5 (92%) | 51.5 (106%) | 53.0 (111%) | 287 | 297 | 108% / 110% | 100->100 | 100->100 | 3,012 | 643 | 39.1 | 307.4 |
| 02:07 | HOLD-2 | 100 / 100 | 33.0 (70%) | 42.2 (87%) | 50.2 (103%) | 51.5 (108%) | 297 | 293 | 112% / 109% | 100->100 | 100->100 | 2,932 | 653 | 39.4 | 327.4 |
| 02:08 | HOLD-2 | 100 / 100 | 32.2 (68%) | 43.5 (89%) | 51.0 (105%) | 51.5 (108%) | 275 | 270 | 103% / 100% | 100->100 | 100->100 | 2,965 | 606 | 38.8 | 326.7 |
| 02:09 | HOLD-3 | 100 / 100 | 32.2 (68%) | 42.2 (87%) | 49.2 (101%) | 52.0 (109%) | 273 | 278 | 103% / 103% | 100->100 | 100->100 | 3,044 | 600 | 38.3 | 301.3 |
| 02:10 | HOLD-3 | 100 / 100 | 35.0 (74%) | 43.2 (89%) | 50.5 (104%) | 51.5 (108%) | 297 | 291 | 112% / 108% | 100->100 | 100->100 | 3,063 | 653 | 37.0 | 284.5 |
| 02:11 | HOLD-3 | 100 / 100 | 34.2 (72%) | 41.8 (86%) | 49.5 (102%) | 53.0 (111%) | 275 | 297 | 103% / 110% | 100->100 | 100->100 | 2,943 | 641 | 38.8 | 326.9 |

## What a next attempt could try (not opened)

- **Size key 0 on use, not on fees:** about 1.06 usable tKAS per OK hop; for 16 families over about 90 minutes, at least about 70,000 usable at the open, and consolidate its 2,104 small coins first.
- Run the one-sided (greedy) variant first, or alone, since it is the part that can climb.
- A symmetric duel that can climb needs a reason for both to fall short at once: a target over an even share, or an outside heavy stream.
