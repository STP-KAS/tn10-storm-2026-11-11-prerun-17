> **Experimental. We are just trying this.** [Disclaimer](../DISCLAIMER.md) · This page does not start a machine. Pre-run 17. Not Wednesday. Not Tuesday. Not pre-run 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, or 16.

# Targets

There is no T0. There is no public clock. There is no latest minute. Nothing in pre-run 17 is scored: every step is an observation of whole minutes.

The hash file comes first and does not wait for the open. Nothing else in this page starts until the gates are true: Mini's TN10 node is synced with DAA moving; the desk's private TN10 node is up from its own data (PowerShell 7, no wipe) and synced; no Tuesday, Wednesday, or pre-run 1 to 16 runner is up; the operator has armed (no paste; see the README); our heavy lane's calibration on the node passed; and this repo's `logs/PRE-RUN-OPEN.md` is on origin.

## Order

1. **Nodes live.** Both TN10 nodes synced, DAA moving. No wipe.
2. **Calibration.** One lane transaction, read back from the desk mempool: node storage mass within 1 percent of our SDK's, fee rate 99–101. Otherwise the lane does not run and that is recorded.
3. **Hashes first.** [hashes/SIXTEEN.md](../hashes/README.md): sixteen rows, family label, tier, sha256 of the lowercase hex covenant id, and an On origin line.
4. **Families.** The sixteen covenant families start on the desk's private node, 1.2 hop/s offered. No payment sender of ours is started.
5. **Our two heavy lanes** start at N = 0 and follow one timeline of whole minutes set by the runner:

| Order | File | Lane 1 | Lane 2 | Length |
|---:|---|---|---|---|
| 1 | BASE | 0 (control) | 0 (control) | 12 whole minutes |
| 2 | HOLD-1 (the reference) | 30 at 150 | 30 at 150 | 12 whole minutes |
| 3 | HOLD-2 (duel, part 1) | 30, duel rule | 30, duel rule | 12 whole minutes |
| 4 | HOLD-3 (duel, parts 2 and 3) | 30, duel rule | 30, duel rule | 2 × 12 whole minutes |
| 5 | HOLD-3 (one-sided variant) | 30, from 150, never steps down | 30, from 150, duel rule | 12 whole minutes |
| 6 | drain, HOLD-4 | 0 | 0 | the pinned minute; the bot sends only on a free third public kaspad, or files `NO SEND` |
| 7 | RETURN (after-duel control) | 0 | 0 | 12 whole minutes |
| 8 | tail | families and lanes stopped, the counter reads on | | 5 minutes |

The lanes' N changes on the minute boundary, on a timeline fixed when the lanes start, so a step file's render never stretches a lane step. The minutes between HOLD-3's end and the pinned minute are the start of the drain; they are in `counts/chain/TIMELINE.md`. **Push-back on the first sketch:** a "reference both fixed at 150" step is HOLD-1 (each lane's reference is taken from it, so it is not a second, separate step); the one-sided variant goes inside HOLD-3 so the bot's pin and Mini's gates stay where they were; and the duel keeps its 36 minutes in one piece before it.

## Cohorts (families, node rates): the bystanders

| Cohort | Families | Rate, sompi/gram of node mass | Weight against the outside stream at 100, (rate/100)^3 |
|---|---|---:|---:|
| floor | 1–4 | 100, fixed | 1.00 |
| r150 | 5–8 | 150, fixed | 3.38 |
| r300 | 9–12 | 300, fixed | 27.0 |
| r450 | 13–16 | 450, fixed | 91.1 |

A hop is about 41,100–41,300 node mass (storage mass; compute 9,123), a lane transaction about 266,700. The rate is fee ÷ the node's mass (kit21's pricing, kept in kit24). kit24 is kit23 with this table; no family reads a live rate in this run.

## The duel rule

Once a minute, at 22 seconds past the minute or later (the counter's line for the minute just closed is final about 20 seconds after it ends), the desk runner reads that minute and moves both rates:

| Side | What it is | Metric | Reference |
|---|---|---|---|
| A | lane 1, 30 chains | lane 1 transactions landed in the minute | lane 1's median in HOLD-1 minutes 2–12 (both at 150) |
| B | lane 2, 30 chains | lane 2 transactions landed in the minute | lane 2's median in HOLD-1 minutes 2–12 |

- metric under 90 percent of the reference: rate × 1.25, rounded, at most 2,000;
- at or over 90 percent for 2 minutes in a row: rate × 0.8, rounded, at least 100;
- otherwise unchanged. An unread, partial or lagging minute holds both rates.
- **cap guard:** 4 decided minutes in a row with both at 2,000 → `CAP_REACHED` (minutes since the start or the last reset, fees so far), both back to 150, counters cleared.
- **one-sided variant** (last 12 minutes of HOLD-3): both start again at 150 with cleared counters; lane 1's down step is switched off.

Both lanes start the duel at 150. Each rule only sees its own lane's landings; it does not see the other lane's rate. The new rates take effect about 22 seconds into the next minute, so each minute after a change is a mix of the old and the new rate. The per-minute snapshot of both rates and every decision are in `logs/duel.log`. Which lane submits first alternates every second, so neither lane always goes first.

## Prediction, written before the run

In rusty-kaspa v2.1.0 (below) a block is filled by weighted random sampling, weight (fee/mass)^3 per transaction, once the ready set is over one block. Only one lane transaction fits a block, so lane 1, lane 2 and the outside heavy stream share about 600 heavy places a minute; in pre-run 16 one lane of 60 at 150 landed about 486 a minute. Our expectations:

- **The duel ratchets, but mostly does not run away.** When one lane steps up to 188 against 150, its weight per transaction is about 1.95 times the other's, so it should take a clearly larger share and push the other under 90 percent, which steps that one up too. A lane that is behind steps up at once; a lane that is ahead needs two good minutes to step down. That asymmetry should give an **upward drift**: we expect a leapfrog sawtooth, with the ratio between the two rates mostly between 1 and 1.25 and the level rising.
- **What holds it back:** once both lanes are well above the outside stream (at 100) there is little left to take from it, and when both are at the same rate they split the heavy places about evenly, each near or above its reference. Then both see good minutes and step down. So we expect the level to wander in a band, most likely somewhere between 150 and 600, rather than climb steadily to 2,000. Our best guess: **no spiral to the cap in the 36 symmetric minutes**, with a median rate per lane of about 200–400.
- **What would make it spiral:** if the minute-to-minute noise in landings (in pre-run 16 the lane alone swung between 79 and 108 percent of its reference at a fixed rate) keeps putting one lane or the other under 90 percent, the up steps will outnumber the down steps and the pair will climb. If we see a steady climb, the time to the cap from 150 is at least 12 steps up (150 × 1.25^12 ≈ 2,180), so at least about 12 minutes.
- **The one-sided variant should climb.** A lane that never steps down only goes up when it falls behind, and the other lane can only win back its share by going up too. We expect both to climb in that step, and a real chance that they reach the cap within its 12 minutes.
- **Bystanders.** The fixed tiers should lose more the higher the lanes go: floor (100) badly whenever the lanes run, r150 badly once the lanes are above about 150, r300 and r450 only when the lanes pass about 300 and 450. If the lanes reach 2,000, every fixed tier should slow (but a chained hop still lands, as in pre-runs 14–16).
- **Other users** at up to about the lanes' rate lose more the higher the lanes go; at 150 about what pre-runs 15–16 saw (about 10–13 percent less of other traffic landed on our node).
- **Cost.** At 150 a lane transaction costs about 0.40 tKAS; at 300 about 0.80; at 2,000 about 5.34. If the pair spirals to the cap, both lanes together would burn about 3,000 tKAS a minute there.

## Our heavy lanes

- **Shape.** One input (the chain's own coin, from the payment key), two plain pay-to-key outputs: 0.0375 tKAS to a dedicated sink key of ours, and the change back into the chain. Storage mass about 266,670 (KIP-9: 10^12 / 3,750,000 sompi for the small output, the change and input terms nearly cancel). Compute mass about 2,000. Fee rate × mass: about 0.40 tKAS at 150, 2.67 at 1,000 and 5.34 at the 2,000 cap.
- **Why this shape.** Our SDK counts every output at UTXO plurality 1 (pre-run 12's source check); plain outputs have plurality 1 on the node too, so the two agree. A covenant output (plurality 2) would be under-read by the SDK by a factor of four.
- **Two lanes, one process.** Lane 1 uses chain slots 1–100 and lane 2 slots 101–200 of one lane process, one node connection and one key-16 pile; each has its own N, rate and submit bucket (1,200 a minute, 20 a second), and lane 2's ids are logged apart so the counter reads lane 1 and lane 2 landed separately (hv1, hv2).
- **Ready count.** A chain's next transaction goes out only after the previous one has left the desk mempool. So each lane has at most N entries in the mempool and all are ready. About one 267,000-mass transaction fits a 500,000 block, so at about 10 blocks a second the chain takes at most about 600 heavy transactions a minute, shared with any outside heavy. At 30 + 30 the two lanes hold about 32 blocks of ready mass.
- **Money.** Only from the payment key (key 16: 7,074 coins, 149,647 tKAS, before this run's refill of key 0, which moved 1,400 of them, 29,870 tKAS; 5,674 coins of about 26 tKAS, about 119,800 tKAS, after). Each chain takes one pile coin and runs it down to under 2 tKAS, then takes the next. The family lane (key 0) is not touched by the heavy lane. The operator said tKAS is not a limit; the caps stay as guards, and the spend is logged.
- **Caps.** 1,200 lane submits a minute; pause above N + 2 lane entries for three probe samples; hold at mempool 90,000 or ready mass over 80 blocks; rate at most **2,000**; stop at **90,000** tKAS of fees or **100,000** tKAS moved, or the pile estimate under **15,000** tKAS (pre-run 16: 40,000 / 45,000 / 100,000); stop on any rejection that is not a timing one, or if the node's rate or mass on our own entries drifts from the calibration.
- **Not swept in this run.** The 0.0375 tKAS sink outputs (pre-runs 13 to 16's, about 92,000, and this run's) stay where they are, on the same sink key. A sweep is a separate, later, logged step.

## Why this shape

- Pre-run 16's duel was lopsided (a light covenant side against a heavy lane), so it could not spiral. Two equal heavy lanes compete for the same scarce thing, the one heavy place per block, so a step up by one is a loss for the other: the case where a spiral is possible.
- HOLD-1 gives each lane a reference at the duel's starting point (both at 150); BASE gives the bystanders' reference.
- Four fixed tiers (100, 150, 300, 450) show what the duel does to covenant users who do not escalate, at a low, a level, a high and a very high rate.
- 36 symmetric minutes in one piece so a slow ratchet has time to show, then the one-sided variant. The 2,000 cap, the cap guard and the 90,000 tKAS fee cap keep a runaway bounded; if the lanes meet the fee cap they stop, and that is recorded as "gave up (budget)".
- No payments: the only load is the families, our lanes and whatever other TN10 traffic is there.

## What we read

For each minute: each lane's N and rate and every duel decision (`logs/duel.log`); lane 1 and lane 2 landed (counter) and their share; hops per tier and each tier's node rate (as built and as the probe read it in the mempool) (desk counter, accepted on chain); our heavy in the mempool and ready (probe), our heavy landed (counter), lane submits (the lane's log); outside heavy at 100 (probe, entries not in our logs); the ready mass in blocks of 500,000 (from the full mempool read up to 10,000 entries, from the node's own figures above); the mempool size and the fee estimate. Mini is a second read of the hops.

## Selection rule

The desk node and the public kaspads answered serverVersion 2.1.0. In rusty-kaspa tag v2.1.0 (commit 01b532e8b553523216471682649693af92f0fd16), `mining/src/mempool/model/frontier.rs` takes every ready transaction best-first while the ready set's mass fits one block, and otherwise samples at random with weight (fee/mass)^3 (`ALPHA = 3`). Only a transaction with no parent in the mempool is ready, so a chained hop is not a candidate until its parent is out of the mempool. A higher fee raises the odds of being drawn; it does not buy a place in a queue. This is the source's rule, read from the code; the run reads the desk node's own template, not a miner's.

Abort line **18,000 usable tKAS** (key 0 coins over 3 tKAS, less 3 tKAS each). The coin count is logged, not a gate (pre-run 13 tripped on change fragments). Key 0 was consolidated before the open. Do not lower it.
