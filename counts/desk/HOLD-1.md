OBSERVATION

Not scored. No payment of ours in pre-run 17: families only, on the desk's private node, plus our own heavy lane at the N shown per minute.

# HOLD-1, desk, pre-run 17

> Our own TN10 testing: what we observed in this run, on our own desk node. Counts only. Included is what the desk's private TN10 node accepted on chain, read by the desk counter, by accepting chain block time. Mini's files are a second read.

HOLD-1 in pre-run 17 is lane 1 N=30 at 150 and lane 2 N=30 at 150 (the reference, no escalation): L30x2-r150-ref 12 whole minutes. Families only for payments (no payment of ours); our own heavy lane ran at the N and rate shown per minute (N = how many lane chains may each hold one ready transaction in the mempool). The HOLD file names are kept so the bot's and Mini's gates read as in earlier pre-runs. Not scored.

Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder: floor (families 1–4) 100 sompi/gram on the desk's private node, r150 (families 5–8) 150 sompi/gram on the desk's private node, r300 (families 9–12) 300 sompi/gram on the desk's private node, r450 (families 13–16) 450 sompi/gram on the desk's private node. No payment sender was started.

## Tiers against the mempool, per minute

| Minute (UTC) | Lane 1 N / rate | Lane 2 N / rate | floor (100) | r150 (150) | r300 (300) | r450 (450) | Our heavy in mempool / ready | Our heavy landed, lane 1 / lane 2 | Lane submits OK, lane 1 / lane 2 | Outside heavy at 100 (>200k mass) / ready | Outside at 100, n | Ready mass, blocks | Mempool | Fee estimate priority |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 2026-11-13T01:45 | 30 / 150 | 30 / 150 | 74 | 117 | 176 | 191 | 51 / 51 | 225 / 246 | 252 / 271 | - / - | - | 32.28 | 149 | 402.1 |
| 2026-11-13T01:46 | 30 / 150 | 30 / 150 | 73 | 129 | 187 | 209 | 58 / 58 | 263 / 272 | 266 / 277 | - / - | - | 38.25 | 159 | 389.1 |
| 2026-11-13T01:47 | 30 / 150 | 30 / 150 | 72 | 126 | 188 | 198 | 52 / 52 | 277 / 243 | 275 / 240 | - / - | - | 35.94 | 133 | 371.1 |
| 2026-11-13T01:48 | 30 / 150 | 30 / 150 | 71 | 124 | 193 | 206 | 58 / 58 | 246 / 261 | 243 / 259 | - / - | - | 40.99 | 161 | 361.7 |
| 2026-11-13T01:49 | 30 / 150 | 30 / 150 | 76 | 123 | 191 | 197 | 56 / 56 | 262 / 294 | 267 / 296 | - / - | - | 40.67 | 204 | 379.9 |
| 2026-11-13T01:50 | 30 / 150 | 30 / 150 | 81 | 138 | 190 | 207 | 58 / 58 | 276 / 288 | 276 / 288 | - / - | - | 42.20 | 147 | 378.9 |
| 2026-11-13T01:51 | 30 / 150 | 30 / 150 | 78 | 122 | 190 | 195 | 58 / 58 | 240 / 267 | 240 / 270 | - / - | - | 40.74 | 180 | 384.3 |
| 2026-11-13T01:52 | 30 / 150 | 30 / 150 | 71 | 123 | 188 | 204 | 53 / 53 | 269 / 268 | 267 / 268 | - / - | - | 38.62 | 151 | 380.3 |
| 2026-11-13T01:53 | 30 / 150 | 30 / 150 | 68 | 130 | 195 | 211 | 57 / 57 | 283 / 269 | 279 / 266 | - / - | - | 41.16 | 173 | 385.8 |
| 2026-11-13T01:54 | 30 / 150 | 30 / 150 | 74 | 123 | 185 | 201 | 58 / 58 | 233 / 280 | 237 / 281 | - / - | - | 40.99 | 163 | 366.3 |
| 2026-11-13T01:55 | 30 / 150 | 30 / 150 | 67 | 134 | 187 | 196 | 54 / 54 | 266 / 269 | 266 / 265 | - / - | - | 39.94 | 164 | 385.9 |
| 2026-11-13T01:56 | 30 / 150 | 30 / 150 | 80 | 135 | 192 | 210 | 52 / 52 | 267 / 275 | 263 / 277 | - / - | - | 38.29 | 147 | 341.9 |

Lane 1 and lane 2 N / rate are the caps the runner set for that minute (N lane chains each, each chain with at most one ready transaction in the mempool) and each lane's fee rate (in the duel, the rate in effect at the start of the minute). Our heavy in mempool / ready is the probe's median count of our own lane entries; our heavy landed is what the desk counter read as accepted on chain from our lane in the minute; lane submits OK is the lane's own log. Hops are what the desk counter read as accepted on chain in that minute, per tier. Ready mass, blocks, is the median of the probe's samples in the minute (block limit 500,000). Outside at 100 is the median count of mempool entries not in our logs (our lane is in our logs) paying 100 sompi/gram, and heavy is how many of those had a mass over 200,000 (median of samples). The outside stream is not attributed to anyone.

## Chain, desk counter

| Minute (UTC) | Included, all non-coinbase | Our payments included | Floor hops (100) | R150 hops (150) | R300 hops (300) | R450 hops (450) | Other traffic | Chain blocks | DAA gap max | Sink age max, ms | Final after, s | Counter |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| 2026-11-13T01:45 | 3,937 | 0 | 74 | 117 | 176 | 191 | 2,912 | 262 | 1 | 451 | 20 | kept pace |
| 2026-11-13T01:46 | 4,308 | 0 | 73 | 129 | 187 | 209 | 3,175 | 302 | 0 | 478 | 19 | kept pace |
| 2026-11-13T01:47 | 4,075 | 0 | 72 | 126 | 188 | 198 | 2,974 | 286 | 1 | 444 | 20 | kept pace |
| 2026-11-13T01:48 | 4,027 | 0 | 71 | 124 | 193 | 206 | 2,927 | 274 | 1 | 514 | 20 | kept pace |
| 2026-11-13T01:49 | 4,079 | 0 | 76 | 123 | 191 | 197 | 2,939 | 310 | 0 | 617 | 20 | kept pace |
| 2026-11-13T01:50 | 4,129 | 0 | 81 | 138 | 190 | 207 | 2,950 | 316 | 0 | 536 | 21 | kept pace |
| 2026-11-13T01:51 | 4,000 | 0 | 78 | 122 | 190 | 195 | 2,909 | 283 | 0 | 532 | 19 | kept pace |
| 2026-11-13T01:52 | 4,102 | 0 | 71 | 123 | 188 | 204 | 2,981 | 297 | 2 | 577 | 20 | kept pace |
| 2026-11-13T01:53 | 4,140 | 0 | 68 | 130 | 195 | 211 | 2,987 | 312 | 1 | 761 | 21 | kept pace |
| 2026-11-13T01:54 | 4,036 | 0 | 74 | 123 | 185 | 201 | 2,942 | 289 | 0 | 444 | 20 | kept pace |
| 2026-11-13T01:55 | 4,104 | 0 | 67 | 134 | 187 | 196 | 2,987 | 313 | 0 | 457 | 20 | kept pace |
| 2026-11-13T01:56 | 4,055 | 0 | 80 | 135 | 192 | 210 | 2,901 | 302 | 1 | 418 | 20 | kept pace |

Coinbase is taken out as one per merged blue block (on this node a chain block's accepted list carries the coinbase of each blue block it merges). Other traffic is the rest: other users' load, the genesis, and anything not in our logs.

## Hop rate per cohort, as built

Floor (families 1–4, desk private node): 100 sompi/gram per hop. R150 (families 5–8, desk private node): 150 sompi/gram per hop. R300 (families 9–12, desk private node): 300 sompi/gram per hop. R450 (families 13–16, desk private node): 450 sompi/gram per hop. In pre-run 17 that rate is on the hop's node-side mass (kit21): the builder is asked for a bill rate on its own mass so that fee / node mass is the tier's rate.

| Tier | Node rate as built, median (min–max) | Bill rate, median | Node mass, median (min–max) | Node rate in the desk mempool, lowest–highest (probe) |
|---|---|---:|---|---|
| floor (100) | 100.16 (100–100.32) | 314 | 40,864 (40,377–42,135) | 100–100.32 |
| r150 (150) | 150.17 (150–150.32) | 470 | 40,838 (40,383–42,240) | 150–150.32 |
| r300 (300) | 300.17 (300–300.32) | 940 | 40,856 (40,403–42,410) | 300–300.31 |
| r450 (450) | 450.16 (450–450.32) | 1412 | 40,916 (40,422–42,573) | 450–450.31 |

Node rate as built is kit21's fee / node mass (rusty-kaspa v2.1.0 storage mass with UTXO plurality, or compute or transient/2 if larger). In the desk mempool the probe divides the node's fee by the larger of the storage and compute mass the node reports.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 4 (286), 5 (276), 6 (229), 8 (223), 7 (221), 3 (219), 16 (178), 10 (170), 14 (168), 9 (164), 11 (158), 18 (158), and 13 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | R150 OK / att / rate rej / full rej / waiting | R300 OK / att / rate rej / full rej / waiting | R450 OK / att / rate rej / full rej / waiting | Family stalls logged | Family node mempool-high marks | Clean |
|---|---:|---:|---:|---:|---:|---|---|---|---|---:|---:|---|
| 2026-11-13T01:45 | 0 | 0 | 0 | 0 | 0 | 73 / 315 / 0 / 0 / 3 | 116 / 338 / 0 / 0 / 3 | 176 / 353 / 0 / 0 / 4 | 191 / 361 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:46 | 0 | 0 | 0 | 0 | 0 | 74 / 319 / 0 / 0 / 4 | 130 / 341 / 0 / 0 / 4 | 187 / 368 / 0 / 0 / 4 | 209 / 370 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:47 | 0 | 0 | 0 | 0 | 0 | 72 / 319 / 0 / 0 / 4 | 126 / 343 / 0 / 0 / 4 | 188 / 367 / 0 / 0 / 4 | 198 / 379 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:48 | 0 | 0 | 0 | 0 | 0 | 71 / 315 / 0 / 0 / 4 | 124 / 339 / 0 / 0 / 4 | 193 / 379 / 0 / 0 / 4 | 206 / 376 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:49 | 0 | 0 | 0 | 0 | 0 | 76 / 316 / 0 / 0 / 4 | 122 / 338 / 0 / 0 / 3 | 191 / 364 / 0 / 0 / 4 | 196 / 367 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-13T01:50 | 0 | 0 | 0 | 0 | 0 | 80 / 322 / 0 / 0 / 3 | 138 / 344 / 0 / 0 / 3 | 190 / 370 / 0 / 0 / 4 | 208 / 384 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:51 | 0 | 0 | 0 | 0 | 0 | 79 / 321 / 0 / 0 / 4 | 123 / 338 / 0 / 0 / 4 | 190 / 371 / 0 / 0 / 4 | 195 / 380 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:52 | 0 | 0 | 0 | 0 | 0 | 71 / 314 / 0 / 0 / 4 | 123 / 337 / 0 / 0 / 4 | 188 / 368 / 0 / 0 / 4 | 204 / 374 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:53 | 0 | 0 | 0 | 0 | 0 | 68 / 316 / 0 / 0 / 4 | 130 / 339 / 0 / 0 / 4 | 194 / 370 / 0 / 0 / 3 | 211 / 374 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:54 | 0 | 0 | 0 | 0 | 0 | 74 / 315 / 0 / 0 / 4 | 123 / 339 / 0 / 0 / 4 | 186 / 364 / 0 / 0 / 4 | 201 / 372 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:55 | 0 | 0 | 0 | 0 | 0 | 66 / 312 / 0 / 0 / 3 | 134 / 343 / 0 / 0 / 4 | 187 / 366 / 0 / 0 / 4 | 196 / 373 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:56 | 0 | 0 | 0 | 0 | 0 | 81 / 320 / 0 / 0 / 4 | 135 / 340 / 0 / 0 / 4 | 192 / 372 / 0 / 0 / 4 | 210 / 382 / 0 / 0 / 4 | 0 | 0 | yes |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

A mempool-high mark means the family node read a mempool at or over 90,000. In pre-run 17 that does not stop the families: the skip does not apply to them. A skip, if one were set, is dirt with its reason (node-skip-fam) for every minute it covers, and it clears when the mempool falls back under the line.

Within 10 percent means 0 to 0 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender reads and submits every tier on the desk's private node, which the desk counter reads. The kept public kaspads are read for sync and DAA only; no payment of ours went to them.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). 3 payment senders per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 621989193 | 0 | 0 | 0 | 32 |
| 5 | yes | 621989193 | 0 | 0 | 0 | 37 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 885 of 885 | 2471 | 7909 |
| r150 | 1524 of 1524 | 1635 | 3117 |
| r300 | 2262 of 2262 | 1136 | 1698 |
| r450 | 2425 of 2425 | 1069 | 1522 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end. Every tier has the same hop shape and the same node; only the rate differs.

## Mempool and template, desk node (probe)

| Minute (UTC) | Samples | Mempool | Ready (no parent in mempool) | Ready mass, blocks of 500k | Other traffic in mempool | Other ready | Other at 100, n | Other at 100, mean mass | Our payments in mempool | Our heavy in mempool / ready | Floor in mempool / ready | R150 in mempool / ready | R300 in mempool / ready | R450 in mempool / ready | Template txs | Template storage mass | Template txs over 100k storage mass | Template: payments | Template: our heavy | Template: floor | Template: r150 | Template: r300 | Template: r450 | Template: other | Fee estimate priority / normal / low | Public 1 mempool | Public 5 mempool |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|
| 2026-11-13T01:45 | 3 | 149 | 205 | 32.28 | 134 | 134 | - | - | 0 | 51 / 51 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 8 | 470,994 | 1 | 0 | 1 | 0 | 1 | 1 | 3 | 2 | 402.1 / 182.2 / 114.3 | 195 | 184 |
| 2026-11-13T01:46 | 3 | 159 | 159 | 38.25 | 85 | 85 | - | - | 0 | 58 / 58 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 8 | 469,980 | 1 | 0 | 1 | 0 | 0 | 2 | 3 | 2 | 389.1 / 181.3 / 114.2 | 165 | 176 |
| 2026-11-13T01:47 | 3 | 133 | 137 | 35.94 | 74 | 74 | - | - | 0 | 52 / 52 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 9 | 469,444 | 1 | 0 | 1 | 0 | 1 | 1 | 3 | 3 | 371.1 / 179.9 / 114.1 | 122 | 140 |
| 2026-11-13T01:48 | 3 | 161 | 161 | 40.99 | 91 | 91 | - | - | 0 | 58 / 58 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 8 | 472,585 | 1 | 0 | 1 | 0 | 1 | 1 | 3 | 2 | 361.7 / 179.1 / 114.0 | 153 | 140 |
| 2026-11-13T01:49 | 3 | 204 | 204 | 40.67 | 133 | 133 | - | - | 0 | 56 / 56 | 4 / 4 | 3 / 3 | 3 / 3 | 4 / 4 | 8 | 471,469 | 1 | 0 | 1 | 0 | 0 | 2 | 2 | 2 | 379.9 / 180.6 / 114.2 | 195 | 208 |
| 2026-11-13T01:50 | 3 | 147 | 148 | 42.20 | 73 | 73 | - | - | 0 | 58 / 58 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 8 | 471,777 | 1 | 0 | 1 | 0 | 1 | 2 | 3 | 2 | 378.9 / 180.5 / 114.2 | 160 | 160 |
| 2026-11-13T01:51 | 3 | 180 | 180 | 40.74 | 109 | 109 | - | - | 0 | 58 / 58 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 8 | 472,141 | 1 | 0 | 1 | 0 | 0 | 2 | 3 | 2 | 384.3 / 180.9 / 114.2 | 181 | 187 |
| 2026-11-13T01:52 | 3 | 151 | 153 | 38.62 | 84 | 84 | - | - | 0 | 53 / 53 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 9 | 471,241 | 1 | 0 | 1 | 0 | 0 | 2 | 3 | 3 | 380.3 / 180.6 / 114.2 | 129 | 141 |
| 2026-11-13T01:53 | 3 | 173 | 173 | 41.16 | 106 | 106 | - | - | 0 | 57 / 57 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 9 | 470,946 | 1 | 0 | 1 | 0 | 0 | 2 | 3 | 3 | 385.8 / 181.1 / 114.2 | 163 | 167 |
| 2026-11-13T01:54 | 3 | 163 | 175 | 40.99 | 99 | 99 | - | - | 0 | 58 / 58 | 3 / 3 | 4 / 4 | 2 / 2 | 4 / 4 | 8 | 430,414 | 1 | 0 | 1 | 0 | 0 | 1 | 3 | 3 | 366.3 / 179.4 / 114.1 | 175 | 177 |
| 2026-11-13T01:55 | 3 | 164 | 164 | 39.94 | 94 | 94 | - | - | 0 | 54 / 54 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 8 | 471,946 | 1 | 0 | 1 | 0 | 0 | 1 | 3 | 2 | 385.9 / 181.1 / 114.2 | 161 | 179 |
| 2026-11-13T01:56 | 3 | 147 | 147 | 38.29 | 83 | 83 | - | - | 0 | 52 / 52 | 4 / 4 | 2 / 2 | 3 / 3 | 2 / 2 | 8 | 470,785 | 1 | 0 | 1 | 0 | 0 | 2 | 2 | 2 | 341.9 / 177.1 / 113.9 | 129 | 134 |

Read by the probe on the desk's private TN10 node every 20 s, read-only; each cell is the median of that minute's samples. Pre-run 17: ready count and ready mass come from the full mempool read up to 10,000 entries and from the node's own figures (getFeeEstimateExperimental, verbose) above that, where the per-class columns stay blank (the node's wRPC replies are capped at 128 MiB, about 12,500 entries). Ready means no parent in the mempool: in rusty-kaspa v2.1.0 only those are in the selector's frontier. Ready mass is compared with one block's mass limit (500,000): at or under 1 the selector takes all ready transactions best-first; over 1 it samples at random weighted by (fee/mass)^3 (over 4, sample_inplace). Mass is the larger of compute and storage mass, as the v2.1.0 selector normalises it (transient mass is not in the RPC). Other traffic is every mempool entry not in our sender logs (our heavy lane is its own class, our heavy); its fee rate is the node's fee over that mass. Template transactions carry no id in the RPC, so each is matched to a mempool entry by its first input. The template is the desk node's own getBlockTemplate (never submitted): what this node would put in a block at that moment, not a miner's template. The fee estimate is the node's getFeeEstimate, read only; no sender reads it. Public mempool is getInfo's mempool size on each kept public kaspad.
