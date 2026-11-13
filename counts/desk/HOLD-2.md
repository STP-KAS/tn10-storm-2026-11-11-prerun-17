OBSERVATION

Not scored. No payment of ours in pre-run 17: families only, on the desk's private node, plus our own heavy lane at the N shown per minute.

# HOLD-2, desk, pre-run 17

> Our own TN10 testing: what we observed in this run, on our own desk node. Counts only. Included is what the desk's private TN10 node accepted on chain, read by the desk counter, by accepting chain block time. Mini's files are a second read.

HOLD-2 in pre-run 17 is the duel, part 1 (both lanes N=30; each lane's rate moved each minute by the same duel rule): L30x2-duel-1 12 whole minutes. Families only for payments (no payment of ours); our own heavy lane ran at the N and rate shown per minute (N = how many lane chains may each hold one ready transaction in the mempool). The HOLD file names are kept so the bot's and Mini's gates read as in earlier pre-runs. Not scored.

Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder: floor (families 1–4) 100 sompi/gram on the desk's private node, r150 (families 5–8) 150 sompi/gram on the desk's private node, r300 (families 9–12) 300 sompi/gram on the desk's private node, r450 (families 13–16) 450 sompi/gram on the desk's private node. No payment sender was started.

## Tiers against the mempool, per minute

| Minute (UTC) | Lane 1 N / rate | Lane 2 N / rate | floor (100) | r150 (150) | r300 (300) | r450 (450) | Our heavy in mempool / ready | Our heavy landed, lane 1 / lane 2 | Lane submits OK, lane 1 / lane 2 | Outside heavy at 100 (>200k mass) / ready | Outside at 100, n | Ready mass, blocks | Mempool | Fee estimate priority |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 2026-11-13T01:57 | 30 / 150 | 30 / 150 | 68 | 123 | 189 | 203 | 51 / 51 | 253 / 263 | 260 / 268 | - / - | - | 38.50 | 195 | 376.4 |
| 2026-11-13T01:58 | 30 / 150 | 30 / 150 | 58 | 120 | 186 | 198 | 57 / 57 | 256 / 249 | 252 / 245 | - / - | - | 42.08 | 152 | 396.2 |
| 2026-11-13T01:59 | 30 / 150 | 30 / 150 | 84 | 138 | 185 | 199 | 57 / 57 | 255 / 246 | 256 / 249 | - / - | - | 40.94 | 150 | 353.5 |
| 2026-11-13T02:00 | 30 / 120 | 30 / 120 | 114 | 160 | 201 | 209 | 58 / 58 | 282 / 277 | 279 / 273 | - / - | - | 41.54 | 120 | 336.9 |
| 2026-11-13T02:01 | 30 / 120 | 30 / 120 | 133 | 168 | 197 | 213 | 54 / 54 | 294 / 294 | 296 / 291 | - / - | - | 37.62 | 108 | 326.3 |
| 2026-11-13T02:02 | 30 / 100 | 30 / 100 | 137 | 180 | 210 | 212 | 55 / 55 | 290 / 282 | 293 / 287 | - / - | - | 38.22 | 104 | 331.8 |
| 2026-11-13T02:03 | 30 / 100 | 30 / 100 | 130 | 174 | 193 | 201 | 58 / 58 | 263 / 280 | 260 / 280 | - / - | - | 40.12 | 106 | 307.1 |
| 2026-11-13T02:04 | 30 / 100 | 30 / 100 | 124 | 165 | 188 | 202 | 55 / 55 | 288 / 278 | 291 / 282 | - / - | - | 39.09 | 118 | 278.5 |
| 2026-11-13T02:05 | 30 / 100 | 30 / 100 | 141 | 179 | 202 | 202 | 53 / 53 | 292 / 282 | 290 / 279 | - / - | - | 38.81 | 117 | 320.6 |
| 2026-11-13T02:06 | 30 / 100 | 30 / 100 | 135 | 178 | 206 | 212 | 57 / 57 | 287 / 297 | 284 / 292 | - / - | - | 39.06 | 107 | 307.4 |
| 2026-11-13T02:07 | 30 / 100 | 30 / 100 | 132 | 169 | 201 | 206 | 56 / 56 | 297 / 293 | 301 / 300 | - / - | - | 39.35 | 104 | 327.4 |
| 2026-11-13T02:08 | 30 / 100 | 30 / 100 | 129 | 174 | 204 | 206 | 54 / 54 | 275 / 270 | 273 / 264 | - / - | - | 38.76 | 115 | 326.7 |

Lane 1 and lane 2 N / rate are the caps the runner set for that minute (N lane chains each, each chain with at most one ready transaction in the mempool) and each lane's fee rate (in the duel, the rate in effect at the start of the minute). Our heavy in mempool / ready is the probe's median count of our own lane entries; our heavy landed is what the desk counter read as accepted on chain from our lane in the minute; lane submits OK is the lane's own log. Hops are what the desk counter read as accepted on chain in that minute, per tier. Ready mass, blocks, is the median of the probe's samples in the minute (block limit 500,000). Outside at 100 is the median count of mempool entries not in our logs (our lane is in our logs) paying 100 sompi/gram, and heavy is how many of those had a mass over 200,000 (median of samples). The outside stream is not attributed to anyone.

## Chain, desk counter

| Minute (UTC) | Included, all non-coinbase | Our payments included | Floor hops (100) | R150 hops (150) | R300 hops (300) | R450 hops (450) | Other traffic | Chain blocks | DAA gap max | Sink age max, ms | Final after, s | Counter |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| 2026-11-13T01:57 | 4,105 | 0 | 68 | 123 | 189 | 203 | 3,008 | 292 | 1 | 523 | 21 | kept pace |
| 2026-11-13T01:58 | 4,198 | 0 | 58 | 120 | 186 | 198 | 3,134 | 273 | 0 | 648 | 20 | kept pace |
| 2026-11-13T01:59 | 4,162 | 0 | 84 | 138 | 185 | 199 | 3,056 | 276 | 1 | 516 | 20 | kept pace |
| 2026-11-13T02:00 | 4,203 | 0 | 114 | 160 | 201 | 209 | 2,966 | 331 | 0 | 503 | 20 | kept pace |
| 2026-11-13T02:01 | 4,245 | 0 | 133 | 168 | 197 | 213 | 2,950 | 358 | 1 | 384 | 19 | kept pace |
| 2026-11-13T02:02 | 4,261 | 0 | 137 | 180 | 210 | 212 | 2,961 | 357 | 0 | 433 | 20 | kept pace |
| 2026-11-13T02:03 | 4,227 | 0 | 130 | 174 | 193 | 201 | 2,995 | 344 | 1 | 534 | 20 | kept pace |
| 2026-11-13T02:04 | 4,200 | 0 | 124 | 165 | 188 | 202 | 2,965 | 352 | 1 | 616 | 19 | kept pace |
| 2026-11-13T02:05 | 4,214 | 0 | 141 | 179 | 202 | 202 | 2,921 | 359 | 1 | 434 | 20 | kept pace |
| 2026-11-13T02:06 | 4,311 | 0 | 135 | 178 | 206 | 212 | 3,012 | 361 | 1 | 629 | 20 | kept pace |
| 2026-11-13T02:07 | 4,215 | 0 | 132 | 169 | 201 | 206 | 2,932 | 360 | 1 | 369 | 20 | kept pace |
| 2026-11-13T02:08 | 4,209 | 0 | 129 | 174 | 204 | 206 | 2,965 | 338 | 1 | 470 | 20 | kept pace |

Coinbase is taken out as one per merged blue block (on this node a chain block's accepted list carries the coinbase of each blue block it merges). Other traffic is the rest: other users' load, the genesis, and anything not in our logs.

## Hop rate per cohort, as built

Floor (families 1–4, desk private node): 100 sompi/gram per hop. R150 (families 5–8, desk private node): 150 sompi/gram per hop. R300 (families 9–12, desk private node): 300 sompi/gram per hop. R450 (families 13–16, desk private node): 450 sompi/gram per hop. In pre-run 17 that rate is on the hop's node-side mass (kit21): the builder is asked for a bill rate on its own mass so that fee / node mass is the tier's rate.

| Tier | Node rate as built, median (min–max) | Bill rate, median | Node mass, median (min–max) | Node rate in the desk mempool, lowest–highest (probe) |
|---|---|---:|---|---|
| floor (100) | 100.16 (100–100.32) | 313 | 40,823 (40,377–42,177) | 100–100.32 |
| r150 (150) | 150.16 (150–150.32) | 470 | 40,836 (40,383–42,221) | 150–150.32 |
| r300 (300) | 300.16 (300–300.32) | 940 | 40,863 (40,403–42,417) | 300–300.31 |
| r450 (450) | 450.16 (450–450.32) | 1412 | 40,920 (40,423–42,603) | 450–450.32 |

Node rate as built is kit21's fee / node mass (rusty-kaspa v2.1.0 storage mass with UTXO plurality, or compute or transient/2 if larger). In the desk mempool the probe divides the node's fee by the larger of the storage and compute mass the node reports.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 4 (258), 5 (205), 3 (190), 6 (171), 7 (166), 11 (165), 14 (161), 13 (157), 15 (152), 12 (152), 8 (139), 10 (139), and 11 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | R150 OK / att / rate rej / full rej / waiting | R300 OK / att / rate rej / full rej / waiting | R450 OK / att / rate rej / full rej / waiting | Family stalls logged | Family node mempool-high marks | Clean |
|---|---:|---:|---:|---:|---:|---|---|---|---|---:|---:|---|
| 2026-11-13T01:57 | 0 | 0 | 0 | 0 | 0 | 68 / 313 / 0 / 0 / 4 | 124 / 342 / 0 / 0 / 5 | 189 / 373 / 0 / 0 / 4 | 203 / 380 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:58 | 0 | 0 | 0 | 0 | 0 | 58 / 309 / 0 / 0 / 4 | 119 / 334 / 0 / 0 / 4 | 184 / 372 / 0 / 0 / 2 | 198 / 372 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:59 | 0 | 0 | 0 | 0 | 0 | 83 / 322 / 0 / 0 / 3 | 138 / 355 / 0 / 0 / 4 | 186 / 370 / 0 / 0 / 3 | 196 / 379 / 0 / 0 / 1 | 0 | 0 | yes |
| 2026-11-13T02:00 | 0 | 0 | 0 | 0 | 0 | 115 / 339 / 0 / 0 / 4 | 160 / 350 / 0 / 0 / 4 | 202 / 385 / 0 / 0 / 4 | 212 / 386 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T02:01 | 0 | 0 | 0 | 0 | 0 | 133 / 341 / 0 / 0 / 4 | 168 / 364 / 0 / 0 / 4 | 197 / 376 / 0 / 0 / 4 | 213 / 382 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T02:02 | 0 | 0 | 0 | 0 | 0 | 137 / 340 / 0 / 0 / 4 | 180 / 353 / 0 / 0 / 4 | 210 / 377 / 0 / 0 / 4 | 212 / 381 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T02:03 | 0 | 0 | 0 | 0 | 0 | 129 / 341 / 0 / 0 / 3 | 174 / 363 / 0 / 0 / 4 | 193 / 376 / 0 / 0 / 4 | 201 / 381 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T02:04 | 0 | 0 | 0 | 0 | 0 | 125 / 336 / 0 / 0 / 4 | 165 / 355 / 0 / 0 / 4 | 188 / 373 / 0 / 0 / 4 | 202 / 379 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T02:05 | 0 | 0 | 0 | 0 | 0 | 141 / 344 / 0 / 0 / 4 | 179 / 364 / 0 / 0 / 4 | 202 / 379 / 0 / 0 / 4 | 202 / 382 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T02:06 | 0 | 0 | 0 | 0 | 0 | 134 / 341 / 0 / 0 / 3 | 176 / 366 / 0 / 0 / 2 | 202 / 375 / 0 / 0 / 0 | 208 / 382 / 0 / 0 / 0 | 0 | 0 | yes |
| 2026-11-13T02:07 | 0 | 0 | 0 | 0 | 0 | 132 / 344 / 0 / 0 / 3 | 169 / 352 / 0 / 0 / 2 | 205 / 377 / 0 / 0 / 4 | 210 / 373 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T02:08 | 0 | 0 | 0 | 0 | 0 | 128 / 338 / 0 / 0 / 2 | 175 / 358 / 0 / 0 / 3 | 200 / 378 / 0 / 0 / 0 | 202 / 375 / 0 / 0 / 0 | 0 | 0 | yes |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

A mempool-high mark means the family node read a mempool at or over 90,000. In pre-run 17 that does not stop the families: the skip does not apply to them. A skip, if one were set, is dirt with its reason (node-skip-fam) for every minute it covers, and it clears when the mempool falls back under the line.

Within 10 percent means 0 to 0 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender reads and submits every tier on the desk's private node, which the desk counter reads. The kept public kaspads are read for sync and DAA only; no payment of ours went to them.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). 3 payment senders per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 621996513 | 0 | 0 | 0 | 32 |
| 5 | yes | 621996513 | 0 | 0 | 0 | 36 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 1383 of 1383 | 1599 | 3912 |
| r150 | 1927 of 1927 | 1275 | 2277 |
| r300 | 2358 of 2358 | 1085 | 1575 |
| r450 | 2459 of 2459 | 1038 | 1500 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end. Every tier has the same hop shape and the same node; only the rate differs.

## Mempool and template, desk node (probe)

| Minute (UTC) | Samples | Mempool | Ready (no parent in mempool) | Ready mass, blocks of 500k | Other traffic in mempool | Other ready | Other at 100, n | Other at 100, mean mass | Our payments in mempool | Our heavy in mempool / ready | Floor in mempool / ready | R150 in mempool / ready | R300 in mempool / ready | R450 in mempool / ready | Template txs | Template storage mass | Template txs over 100k storage mass | Template: payments | Template: our heavy | Template: floor | Template: r150 | Template: r300 | Template: r450 | Template: other | Fee estimate priority / normal / low | Public 1 mempool | Public 5 mempool |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|
| 2026-11-13T01:57 | 3 | 195 | 195 | 38.50 | 134 | 134 | - | - | 0 | 51 / 51 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 9 | 470,598 | 1 | 0 | 1 | 0 | 0 | 2 | 3 | 3 | 376.4 / 180.3 / 114.1 | 189 | 195 |
| 2026-11-13T01:58 | 3 | 152 | 198 | 42.08 | 133 | 133 | - | - | 0 | 57 / 57 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 12 | 470,881 | 1 | 0 | 1 | 0 | 1 | 1 | 4 | 6 | 396.2 / 181.8 / 114.3 | 184 | 184 |
| 2026-11-13T01:59 | 3 | 150 | 160 | 40.94 | 89 | 89 | - | - | 0 | 57 / 57 | 3 / 3 | 4 / 4 | 4 / 4 | 4 / 4 | 8 | 471,478 | 1 | 0 | 1 | 0 | 0 | 1 | 3 | 2 | 353.5 / 178.3 / 114.0 | 148 | 160 |
| 2026-11-13T02:00 | 3 | 120 | 129 | 41.54 | 54 | 54 | - | - | 0 | 58 / 58 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 14 | 408,834 | 0 | 0 | 0 | 0 | 1 | 4 | 4 | 4 | 336.9 / 176.6 / 113.8 | 112 | 120 |
| 2026-11-13T02:01 | 3 | 108 | 112 | 37.62 | 45 | 45 | - | - | 0 | 54 / 54 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 8 | 472,250 | 1 | 0 | 1 | 0 | 0 | 1 | 3 | 2 | 326.3 / 175.4 / 113.7 | 106 | 105 |
| 2026-11-13T02:02 | 2 | 104 | 144 | 38.22 | 73 | 73 | - | - | 0 | 55 / 55 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 8 | 473,773 | 1 | 0 | 1 | 0 | 1 | 2 | 3 | 2 | 331.8 / 176.0 / 113.8 | 133 | 133 |
| 2026-11-13T02:03 | 3 | 106 | 108 | 40.12 | 45 | 45 | - | - | 0 | 58 / 58 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 8 | 471,790 | 1 | 0 | 1 | 0 | 0 | 2 | 3 | 2 | 307.1 / 173.0 / 113.5 | 146 | 146 |
| 2026-11-13T02:04 | 3 | 118 | 118 | 39.09 | 49 | 49 | - | - | 0 | 55 / 55 | 4 / 4 | 4 / 4 | 3 / 3 | 4 / 4 | 8 | 470,633 | 1 | 0 | 1 | 0 | 1 | 2 | 2 | 2 | 278.5 / 168.8 / 113.1 | 127 | 110 |
| 2026-11-13T02:05 | 3 | 117 | 117 | 38.81 | 45 | 45 | - | - | 0 | 53 / 53 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 10 | 451,435 | 0 | 0 | 0 | 0 | 1 | 2 | 4 | 4 | 320.6 / 174.7 / 113.6 | 104 | 107 |
| 2026-11-13T02:06 | 3 | 107 | 117 | 39.06 | 47 | 47 | - | - | 0 | 57 / 57 | 3 / 3 | 3 / 3 | 4 / 4 | 4 / 4 | 9 | 472,509 | 1 | 0 | 1 | 0 | 1 | 2 | 4 | 3 | 307.4 / 173.1 / 113.5 | 89 | 103 |
| 2026-11-13T02:07 | 3 | 104 | 113 | 39.35 | 41 | 41 | - | - | 0 | 56 / 56 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 9 | 471,653 | 1 | 0 | 1 | 0 | 0 | 2 | 2 | 3 | 327.4 / 175.6 / 113.7 | 88 | 102 |
| 2026-11-13T02:08 | 3 | 115 | 115 | 38.76 | 45 | 45 | - | - | 0 | 54 / 54 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 10 | 406,557 | 0 | 0 | 0 | 0 | 0 | 4 | 4 | 3 | 326.7 / 175.5 / 113.7 | 101 | 114 |

Read by the probe on the desk's private TN10 node every 20 s, read-only; each cell is the median of that minute's samples. Pre-run 17: ready count and ready mass come from the full mempool read up to 10,000 entries and from the node's own figures (getFeeEstimateExperimental, verbose) above that, where the per-class columns stay blank (the node's wRPC replies are capped at 128 MiB, about 12,500 entries). Ready means no parent in the mempool: in rusty-kaspa v2.1.0 only those are in the selector's frontier. Ready mass is compared with one block's mass limit (500,000): at or under 1 the selector takes all ready transactions best-first; over 1 it samples at random weighted by (fee/mass)^3 (over 4, sample_inplace). Mass is the larger of compute and storage mass, as the v2.1.0 selector normalises it (transient mass is not in the RPC). Other traffic is every mempool entry not in our sender logs (our heavy lane is its own class, our heavy); its fee rate is the node's fee over that mass. Template transactions carry no id in the RPC, so each is matched to a mempool entry by its first input. The template is the desk node's own getBlockTemplate (never submitted): what this node would put in a block at that moment, not a miner's template. The fee estimate is the node's getFeeEstimate, read only; no sender reads it. Public mempool is getInfo's mempool size on each kept public kaspad.
