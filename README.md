> **Experimental. We are just trying this.** [Disclaimer](DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value.
>
> **This is a pre-run. Pre-run 17.** It is not the Wednesday run. It is not the Tuesday run. It is not pre-run 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, or 16. A read does not start a runner.

# tn10-storm-2026-11-11-prerun-17

**Pre-run 17 of the Wednesday neuron.** The neuron stays [tn10-storm-2026-11-11](https://github.com/STP-KAS/tn10-storm-2026-11-11). This repo does not edit that repo, does not write `REVIEW_CLOSED`, and does not set or move a clock for it. [tn10-storm-2026-11-10](https://github.com/STP-KAS/tn10-storm-2026-11-10) (Tuesday) is not edited from here either.

> **Our own testing.** This is our own Kaspa Testnet-10 testing, run on our own machines and nodes. What these pages report is what we observed in this run; it is not a claim of how TN10 or Kaspa behave in general.

**Where this starts.** Pre-runs 1 to 4 failed and are closed. Pre-runs 5 to 12 finished through RETURN and are closed. Pre-run 13 ran through the pinned HOLD-4 minute and failed in RETURN on its coin-count abort line; it is closed. Pre-runs 14, 15 and 16 finished through RETURN and are closed. The index of all of them is the [pre-run 2 README](https://github.com/STP-KAS/tn10-storm-2026-11-11-prerun-2#pre-runs-in-this-rehearsal); the cumulative findings are in [tn-master](https://github.com/STP-KAS/tn-master). This repo starts from [pre-run 16's locks/LOCKED.md](https://github.com/STP-KAS/tn10-storm-2026-11-11-prerun-16/blob/016a560/locks/LOCKED.md) at commit 016a560, copied here as [locks/LOCKED.md](locks/LOCKED.md), with a pre-run 17 section added at the end.

## What pre-run 16 left open

[Pre-run 16](https://github.com/STP-KAS/tn10-storm-2026-11-11-prerun-16) let a covenant chain (nine families) and our own heavy lane both raise their fee rate whenever they fell behind, under one rule. As we observed it, the rates settled near a ratio of two (covenant side 188–294, lane 120–188) and did not spiral. But the covenant side was far lighter than the lane (about 17 million mass a minute against about 120 million), so when it paid more it took nothing the lane would miss, and the lane never had a reason to climb. A spiral needs each side's step up to hurt the other. That was the open question: **what happens when the two sides are the same size?**

## What pre-run 17 tries: a heavy-against-heavy duel

The question: **when two heavy lanes of the same size and shape both raise their rate whenever they fall behind, does the rate settle, spiral to the cap, or does one side give up? How fast, at what cost per landed transaction, and what does it do to fixed-rate bystanders and to other TN10 users?**

> **We run our own heavy lanes on TN10 again, and they slow other TN10 users' transactions.** In this pre-run we submit two bounded streams of our own heavy transactions (about 266,700 storage mass each, 30 chains per lane, 60 in all, at rates our duel rule sets between 100 and 2,000 sompi/gram) from our own test coins. While they run, other TN10 users' transactions paying up to about the lanes' rates wait longer, and if the duel climbs, more of them wait. The operator gave the explicit OK for our lane (2026-11-12), said tKAS is not a limit and asked us to test at will. The lanes are calibrated on the node first (at 100 and at 2,000), capped by ready count, by a per-minute submit cap, by a rate cap and by a spend cap, stepped down to zero at the end, and every step is in this repo. This is our own testing; tKAS has no value.

- **Both sides are ours and the same shape.** Lane 1 and lane 2 are two sets of 30 chains in one lane process on the desk, each transaction about 266,700 storage mass, from the same key-16 pile. Only one such transaction fits a 500,000 block, so the two lanes (and any outside heavy) share about 600 heavy places a minute: what one lane wins, the other loses.
- **One rule for both, once a minute** (desk runner, from the counter's final line for the minute just closed): if a lane's landed count is under **90 percent** of its own reference, its rate goes up × 1.25 (cap **2,000**); if it is at or over 90 percent for **2 minutes in a row**, it goes down × 0.8 (floor **100**). A minute that is unread, partial or lagging holds both. Each lane's reference is its own median in HOLD-1 (minutes 2–12, both lanes at 150). Each lane sees only its own landings, as a wallet would. Every decision is logged (`logs/duel.log`, published after the run).
- **Cap guard.** If both lanes sit at 2,000 for 4 decided minutes in a row, the runner records it (`CAP_REACHED`: minutes since the start, fees so far) and puts both back to 150, so a spiral can show again and the spend stays bounded.
- **The one-sided variant**, as a separate 12-minute step at the end of HOLD-3: both back to 150, the same rule, except that lane 1 is greedy: it wants 110 percent of its reference instead of 90 percent, and it never steps down (changed before the run, see the plan).
- **Bystanders.** The sixteen covenant families run at four fixed rates, node rates: floor (1–4) **100**, r150 (5–8) **150**, r300 (9–12) **300**, r450 (13–16) **450**. None of them moves.
- **Calibrated on the node before the open.** One hop at 100 and one at 450, and one lane transaction at 2,000 and one at 100, read back from the desk mempool: see [PLAYBOOK.md](PLAYBOOK.md#status-when-this-repo-was-opened).
- **Steps on one timeline, 12 whole minutes each:** BASE (both lanes N = 0, 12 minutes), HOLD-1 (lane 1 and lane 2 each N = 30 at 150, no escalation: the reference, 12 minutes), HOLD-2 and the first 24 minutes of HOLD-3 (the duel: both lanes N = 30, 36 minutes in all, each lane's rate moved each minute by the duel rule), the last 12 minutes of HOLD-3 (the one-sided variant: both lanes back to 150, lane 1 never steps down), then both lanes N = 0 (the drain and the after-duel control) through the pinned HOLD-4 minute and RETURN (12 minutes), then the counter's 5-minute tail. All are `OBSERVATION`. The HOLD file names are kept so the bot's and Mini's gates read as before.
- **Guards.** The lanes keep pre-run 16's guards (pause at N + 2 entries, hold at mempool 90,000 or ready mass over 80 blocks, stop on a non-timing rejection or a drift from the calibration, 1,200 submits a minute, now per lane) with the fee cap at **90,000 tKAS**, the moved cap at 100,000 and the pile floor at 15,000 (pre-run 16: 40,000 / 45,000 / 100,000; key 0 was refilled from the pile before this run). The family lane's abort line stays **18,000 usable tKAS**.
- **The probe's mempool read is fixed.** In pre-run 16 it failed above about 13,000 entries. We measured one full reply at about 96.7 MB for 9,050 entries; the node's wRPC server caps a reply at 128 MiB, so about 12,500 entries is the most one reply can carry. The probe now reads the node's own ready count and ready mass every sample (a few milliseconds), and the full list only up to 10,000 entries.
- **What this can and cannot say.** Both lanes are ours, on one node, with one rule and fixed references; the outside heavy fee-100 stream may be there too. It can show how this rule behaves for two equal heavy lanes on this node in these minutes. It cannot say how other people's wallets, other rules or other nodes would behave.

The prediction, written before the run, is in [plan/PLAN.md](plan/PLAN.md#prediction-written-before-the-run).

All locked lines from earlier pre-runs stay, except where the pre-run 17 block in [locks/LOCKED.md](locks/LOCKED.md) says what changes and why.

## Machines

| Machine | Go file | First sentence |
|---|---|---|
| Desk | [GO-DESK.md](GO-DESK.md) | DESK. I send and count on pre-run 17. This is not Wednesday. |
| Mini | [GO-MINI.md](GO-MINI.md) | MINI. I count pre-run 17 as the second read. I do not send. This is not Wednesday. |
| Bot | [GO-BOT.md](GO-BOT.md) | GROKBOT. I send payments on the pre-run 17 HOLD-4 only. I do not count. This is not Wednesday. |

The operator does not paste. On 2026-11-12 he asked TN10 ops for covenant pre-runs under congestion and competition, pre-run 11 and then 12, 13 or more as needed (voice, 09:06 and 09:09 Brussels time), and at 10:04 in chat said "Keep exploring". For our own heavy lane he gave the explicit OK in chat at about 11:08 and 11:10 Brussels time ("Do whatever you think is needed", then "No need to keep it short. Tn is for testing. Test at will"), and at 15:19 he said tKAS is not a limit ("Use all the tkas you want"). At 23:26 Brussels time he asked "Can we solve the fee escalation open question?", and at 23:28 said "launch run until you’re happy … Use all the tkas you want", and at about 23:30 "Yes keep going. At will." That is the arm for pre-run 17, its two heavy lanes and the duel. The agents start the runners once the gates are facts. [GO.md](GO.md) is the map, [PLAYBOOK.md](PLAYBOOK.md) has the roles and gates, and [plan/PLAN.md](plan/PLAN.md) has the targets and the reasons.

## Gates, in order

No clock. Each gate is a fact read from a node or from origin.

1. Mini's TN10 node is up from its own data, synced, DAA moving.
2. The desk's private TN10 node is up from its own data (PowerShell 7), synced, DAA moving.
3. No other runner or waiter is up. The family lane is above its abort line (18,000 usable tKAS). The desk's private candidate list is present.
4. `hashes/SIXTEEN.md` is on origin: sixteen rows and an On origin line, from the sixteen-family path.
5. The desk pushes `logs/PRE-RUN-OPEN.md`; Mini pushes `logs/MINI-ARMED.md`.
6. The probe and the desk counter are up. Then the families, our heavy lane at N = 0, and the observation steps on the lane's timeline.

Before the open: the hop calibration (node rate within 1 percent of 100 and of 450) and the lane's calibration (at 2,000 and at 100) passed.

## What a decent result is

- `hashes/SIXTEEN.md` on origin before the first family submit.
- Every step file on origin, each with hops per minute for the four tiers (floor, r150, r300, r450), each tier's node rate, each lane's N and rate, our heavy (lane 1 and lane 2 apart) and the outside heavy apart, and the probe's table for the same minutes.
- `counts/chain/TIMELINE.md` and `counts/chain/MEMPOOL.md` after the tail, and RETURN on origin.
- The duel's rate path for both lanes, minute by minute, and an answer to the question (settled, spiralled, or one side gave up), with the time to the cap and the cost if it spiralled, or an honest "not answered" with the reason.
- A HOLD-4 desk file, a bot file or a legal `NO SEND`, and a Mini file.
- The spend and the leftovers (the parked sink outputs, not swept) stated in the write-up.
- No id, txid, key, address, host, or port in this repo.

A miss stays in this repo. A next attempt is a new repo and starts from this repo's lock file.

**Part of [tn-master](https://github.com/STP-KAS/tn-master).** The rule is [docs/NEURON.md](https://github.com/STP-KAS/tn-master/blob/main/docs/NEURON.md). This pre-run is its own row. It is not row 47.
