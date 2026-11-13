> **Experimental. We are just trying this.** [Disclaimer](DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value.
>
> **This is the playbook for pre-run 17.** It is not Wednesday. It is not Tuesday. It is not pre-run 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, or 16. It does not start a machine and it does not arm one.

# Playbook

Who does what, and the gates before each machine may start. The plan is [plan/PLAN.md](plan/PLAN.md), the locks are [locks/LOCKED.md](locks/LOCKED.md), and the go files are the three GO pages. This page does not override them.

## Oversight

TN10 ops oversees this rehearsal end to end: Mini, the desk (Build), and the bot. TN10 only. Never mainnet. Do not edit the Tuesday repo, the Wednesday repo, or pre-run 1's to 16's go files. Do not write `REVIEW_CLOSED`.

For pre-run 17 the operator does not paste. On 2026-11-12 he asked TN10 ops for covenant pre-runs under congestion and competition, pre-run 11 and then 12, 13 or more as needed (voice, 09:06 and 09:09 Brussels time), and at 10:04 in chat said "Keep exploring". That is the arm. The agents start their runners once the gates are facts.

## Start gates

1. **Mini node synced.** Existing TN10 kaspad, existing data, no wipe. `isSynced` true, DAA moving.
2. **Desk node synced.** Existing private TN10 kaspad, existing data, loopback only, started with `pwsh`. No wipe. Synced, DAA moving.
3. **No other runner.** No earlier runner, waiter, or counter on any machine. Lane above the abort line. The desk's private candidate list is present and not empty (`HELD candidates-missing` otherwise).
4. **Hashes.** `hashes/SIXTEEN.md` with sixteen rows and an On origin line, from [tools/sixteen](tools/sixteen/README.md).
5. **Open.** The desk pushes `logs/PRE-RUN-OPEN.md`. Mini then pushes `logs/MINI-ARMED.md`.
6. **Counter, families, senders.** The desk runner starts the counter on its private node and waits for its start line (`HELD counter-down` otherwise). Then the genesis from the bundle that wrote `hashes/SIXTEEN.md`, the families, and the payment steps.

## Who does what

| Who | Role | What not to do |
|---|---|---|
| **Desk (Build)** | Sends the sixteen families (four fixed tiers, one path, one build, kit24) and runs our own two heavy lanes in one lane process (the operator's OK, calibrated first). No payments. Its private TN10 node counts what the chain accepted (lock line (iv)) and its probe reads the mempool (xii). Publishes `hashes/SIXTEEN.md`, `logs/PRE-RUN-OPEN.md`, `counts/desk/` per step, `counts/chain/TIMELINE.md` and `MEMPOOL.md` after the tail, and `logs/METHOD.md`. | Do not stop or wipe the desk node. No Windows PowerShell 5.1, no `KaspaPublicNode`, no miner, no devnet. No 8- or 32-family publisher. No second runner. Never restart the runner mid-run. No payment sender. No heavy lane other than the runner's own lane process (which carries both lanes). |
| **Mini** | Second chain read on its own node. Does not send, mine, or hold a key. Publishes `logs/MINI-ARMED.md`, then `counts/mini/` when the matching desk file is on origin. | Do not wipe. Do not repeat the desk's head as Mini's. |
| **Bot (TN10 ops)** | Sends payments in the HOLD-4 minute only, on a synced public kaspad that is not one the desk kept, or publishes a legal `NO SEND`. | Do not send in any other step. One waiter. No local node. |

## Status when this repo was opened

Not a gate. Read on 2026-11-13 between 00:52Z and 01:10Z. This is our own TN10 testing; status lines are what we read on our own machines.

- Mini: existing TN10 kaspad 2.1.0 up, no wipe. Pre-run 16's Mini runner ended on its own at 2026-11-13T00:47:34Z.
- Desk: existing private TN10 kaspad 2.1.0 up with `pwsh`, no wipe. It is not stopped for this pre-run. No pre-run 16 runner or child is running. `serve.mjs` and its keeper are not touched.
- Box: no local TN10 node. No bot waiter running.
- **Family lane** (key 0), read 00:52Z: 3,124 coins over 3 tKAS, 21,125 usable tKAS (abort line 18,000), 329 small coins. **Refilled from the payment pile** 00:56:38Z (new `refill17.mjs`): 70 transactions, none rejected, 1,400 pile coins (29,870 tKAS) to key 0 at the same sizes (20 in, 20 out each, so storage mass stays near 0), 3.22 tKAS in fees. **Consolidated** 00:56:57Z: 5 transactions, none rejected, 329 small coins (755 tKAS) into 28, 0.38 tKAS in fees. **Push-back on the plan:** we moved about 30,000 tKAS, not 100,000. Key 0 needs about 8,000 tKAS for this run's families; the pile funds the two lanes, and if the duel spirals to the 2,000 cap the lanes together burn about 3,000 tKAS a minute there, so we kept about 119,800 tKAS in the pile.
- Keys 1–15 got a fresh genesis coin from the family lane (15 transactions at 00:57:06Z, none rejected). After: key 0 4,537 coins over 3 tKAS, 47,265 usable tKAS, no small coins; the payment pile 5,674 coins of about 26 tKAS. Amounts and ids are in private notes.
- **Hop calibration on the node** (kit24), 00:57:33Z: one calibration covenant on key 0 (launch path `…-p17-cal`, not one of the sixteen families and not in `SIXTEEN.md`), its genesis, then two hops built by the family path and submitted on the desk's private node, each read back from the desk mempool:

| Hop | Builder bill rate (on 13,046) | kit24 storage mass | Node storage mass | Node compute mass | Fee, sompi | Node rate (fee ÷ node mass) |
|---|---:|---:|---:|---:|---:|---:|
| family 1 at 100 | 316 | 41,142 | 41,142 | 9,123 | 4,122,536 | 100.20 |
| family 13 (r450) at 450 | 1,425 | 41,311 | 41,311 | 9,123 | 18,590,550 | 450.01 |

  Storage mass matched to the unit and both node rates were within 1 percent of the asked rate (and not under it), so the families may run on kit24.
- **Our heavy lanes' calibration** (one lane process carries both lanes; one transaction shape): at 2,000, 00:57:40Z: SDK storage mass 266,768, node storage mass 266,768 (0.00 percent off), compute 2,036, node rate 2,000.00 (fee 5.34 tKAS). At 100, 00:57:44Z: 266,670 on both sides, node rate 100.00. The sink key is pre-runs 13–16's (it holds their parked outputs, about 92,000, not swept).
- **The probe's mempool read**, 00:50–00:53Z on the desk node: a full `getMempoolEntries` reply measured 96,731,110 bytes for 9,050 entries (about 10.7 KB each). The node's wRPC server caps one message at 128 MiB (rusty-kaspa v2.1.0 `rpc/wrpc/server/src/service.rs`, `MAX_WRPC_MESSAGE_SIZE`), which is about 12,500 entries: that is where pre-run 16's read dropped. The node's own figures (`getFeeEstimateExperimental`, verbose) answered in 3 ms with 78 ready transactions and 13,711,902 ready mass, against 78 and 13,711,186 from the full read at the same moment. The probe now takes the light read every sample and the full list only up to 10,000 entries.
- Re-read 2026-11-13T01:01Z: on the desk only the private kaspad, `serve.mjs`, its keeper and their shells run (untouched); on Mini only its TN10 kaspad. No runner, waiter or counter is up.
- Known risks, not fixed mid-run:
  - Our lanes slow other TN10 users' transactions at fees up to about their own rates while they run. If the duel drives the rates up, more of them wait. The operator OK'd our lane; the rates are capped at 2,000, the fees at 90,000 tKAS, the cap guard puts a spiral back to 150 after 4 minutes at the cap, and both lanes step down to zero at the end.
  - The outside heavy fee-100 stream may also be there. It takes heavy places from both lanes alike; the duel log shows both lanes' landings every minute.
  - The rule reacts to the minute just closed and takes effect about 22 seconds into the next one, so the rates lag the landings by about one minute.
  - About one heavy transaction fits a block, so heavies (ours and outside) together land at most near 600 a minute.
  - Each family is a chain of hops, so a hop waits for its parent whatever its fee.
  - The probe reads the desk node's mempool and template, not a miner's. Above 10,000 mempool entries its per-class columns are blank by design (the ready figures stay).
  - Only two unique public kaspads answered in every check so far, and the desk keeps both, so the bot is expected to file `NO SEND no-free-node`.

## Offline rehearsal, recorded before `PRE-RUN-OPEN`

Rehearsal `p17-a` ran on the desk against the fake node (no network for the sends), 2026-11-13 01:03:54Z to 01:27:00Z, with 2-minute lane steps (`STORM_LANE_MIN=2`, `STORM_RET_MIN=2`) and the probe's full read capped at 5,000 entries, using this pre-run's lane, counter, probe, kit24 and family-fee files and the runner as it was before the one-sided change below.

- Preflight passed; genesis 16 of 16 live; `FEE_SPLIT` verified floor 100, r150 150, r300 300, r450 450; `LANE_PLAN` BASE N0, HOLD-1 the reference (30 + 30 at 150), HOLD-2 and HOLD-3 the duel, the one-sided step, then the drain.
- Both lanes submitted from one process with no rejections, no losses and no orphan retries (650 + 650 OK a minute against the fake node); the counter split our landings into lane 1 and lane 2 (hv1, hv2) and the four tiers; the step files show both lanes' N and rate.
- The duel controller wrote its reference (from the HOLD-1 minutes), a decision every duel minute, the segment starts and the segment-change hold to `logs/duel.log`, with no `ERROR` line. The fake node lands both lanes the same, so in the rehearsal both lanes stepped down together from 150 to 100, which matches the offline run of the controller in the plan's addendum.
- The probe's light read (`getFeeEstimateExperimental`, verbose) was written every sample. Its over-cap path was tested separately on the live node, read-only, with the cap set below the mempool size: the full read was skipped, ready count, ready mass and ready blocks came from the light read, our lane's count from the by-address read, and the template read still ran.
- Every step file, TIMELINE, MEMPOOL and METHOD published to the rehearsal's local origin; `RUNNER_EXIT 0`.
- After the rehearsal, still before the run, the one-sided step was changed (lane 1 greedy, target 110 percent of its reference; see the plan's addendum). That change touches only the target value lane 1 uses in that step; it was run in the offline controller test (`tools/sim/dueltest17.mjs`), not in the rehearsal.

## Status after the live run

AFTER_PLACEHOLDER

### Public statement

We run our own two heavy lanes on TN10 in this pre-run, with the operator's OK, 30 chains each: 12 minutes both at 150, then 48 minutes at rates our duel rule sets between 100 and 2,000 sompi/gram. While they run, other TN10 users' transactions paying up to about the lanes' rates wait longer on the nodes that see them, and more of them wait if the duel climbs. The figures for this run are added here after it. This is our own testing; tKAS has no value.

## When something breaks

Append a worked fix to [locks/LOCKED.md](locks/LOCKED.md) in the form that page shows, and a repair line to `logs/FIXES.md`. If the run dies before RETURN, write `logs/FAILED.md`, stop every runner, waiter, and counter, and do not resume. The next attempt is a new repo that starts from this repo's lock file.
