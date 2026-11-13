OBSERVATION

Not scored. No payment of ours in pre-run 17: families only, on the desk's private node, plus our own heavy lane at the N shown per minute.

# BASE, desk, pre-run 17

> Our own TN10 testing: what we observed in this run, on our own desk node. Counts only. Included is what the desk's private TN10 node accepted on chain, read by the desk counter, by accepting chain block time. Mini's files are a second read.

BASE in pre-run 17 is both lanes N=0 (control): N0-control 12 whole minutes. Families only for payments (no payment of ours); our own heavy lane ran at the N and rate shown per minute (N = how many lane chains may each hold one ready transaction in the mempool). The HOLD file names are kept so the bot's and Mini's gates read as in earlier pre-runs. Not scored.

Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder: floor (families 1–4) 100 sompi/gram on the desk's private node, r150 (families 5–8) 150 sompi/gram on the desk's private node, r300 (families 9–12) 300 sompi/gram on the desk's private node, r450 (families 13–16) 450 sompi/gram on the desk's private node. No payment sender was started.

## Tiers against the mempool, per minute

| Minute (UTC) | Lane 1 N / rate | Lane 2 N / rate | floor (100) | r150 (150) | r300 (300) | r450 (450) | Our heavy in mempool / ready | Our heavy landed, lane 1 / lane 2 | Lane submits OK, lane 1 / lane 2 | Outside heavy at 100 (>200k mass) / ready | Outside at 100, n | Ready mass, blocks | Mempool | Fee estimate priority |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 2026-11-13T01:33 | 0 / 100 | 0 / 100 | 192 | 204 | 206 | 204 | 0 / 0 | 0 / 0 | 0 / 0 | - / - | - | 1.23 | 15 | 167.3 |
| 2026-11-13T01:34 | 0 / 100 | 0 / 100 | 193 | 196 | 203 | 199 | 0 / 0 | 0 / 0 | 0 / 0 | - / - | - | 1.40 | 6 | 168.9 |
| 2026-11-13T01:35 | 0 / 100 | 0 / 100 | 187 | 181 | 180 | 177 | 0 / 0 | 0 / 0 | 0 / 0 | - / - | - | 1.23 | 15 | 221.0 |
| 2026-11-13T01:36 | 0 / 100 | 0 / 100 | 200 | 199 | 201 | 203 | 0 / 0 | 0 / 0 | 0 / 0 | - / - | - | 1.24 | 15 | 171.3 |
| 2026-11-13T01:37 | 0 / 100 | 0 / 100 | 198 | 203 | 205 | 199 | 0 / 0 | 0 / 0 | 0 / 0 | - / - | - | 1.32 | 16 | 180.9 |
| 2026-11-13T01:38 | 0 / 100 | 0 / 100 | 193 | 199 | 202 | 196 | 0 / 0 | 0 / 0 | 0 / 0 | - / - | - | 1.07 | 13 | 140.0 |
| 2026-11-13T01:39 | 0 / 100 | 0 / 100 | 185 | 193 | 190 | 188 | 0 / 0 | 0 / 0 | 0 / 0 | - / - | - | 1.23 | 16 | 178.5 |
| 2026-11-13T01:40 | 0 / 100 | 0 / 100 | 195 | 197 | 197 | 190 | 0 / 0 | 0 / 0 | 0 / 0 | - / - | - | 1.52 | 17 | 179.2 |
| 2026-11-13T01:41 | 0 / 100 | 0 / 100 | 187 | 185 | 189 | 191 | 0 / 0 | 0 / 0 | 0 / 0 | - / - | - | 1.32 | 12 | 178.4 |
| 2026-11-13T01:42 | 0 / 100 | 0 / 100 | 181 | 184 | 192 | 192 | 0 / 0 | 0 / 0 | 0 / 0 | - / - | - | 0.65 | 8 | 100.0 |
| 2026-11-13T01:43 | 0 / 100 | 0 / 100 | 177 | 177 | 187 | 186 | 0 / 0 | 0 / 0 | 0 / 0 | - / - | - | 1.20 | 9 | 137.9 |
| 2026-11-13T01:44 | 0 / 100 | 0 / 100 | 177 | 185 | 186 | 188 | 0 / 0 | 0 / 0 | 0 / 0 | - / - | - | 1.50 | 16 | 183.2 |

Lane 1 and lane 2 N / rate are the caps the runner set for that minute (N lane chains each, each chain with at most one ready transaction in the mempool) and each lane's fee rate (in the duel, the rate in effect at the start of the minute). Our heavy in mempool / ready is the probe's median count of our own lane entries; our heavy landed is what the desk counter read as accepted on chain from our lane in the minute; lane submits OK is the lane's own log. Hops are what the desk counter read as accepted on chain in that minute, per tier. Ready mass, blocks, is the median of the probe's samples in the minute (block limit 500,000). Outside at 100 is the median count of mempool entries not in our logs (our lane is in our logs) paying 100 sompi/gram, and heavy is how many of those had a mass over 200,000 (median of samples). The outside stream is not attributed to anyone.

## Chain, desk counter

| Minute (UTC) | Included, all non-coinbase | Our payments included | Floor hops (100) | R150 hops (150) | R300 hops (300) | R450 hops (450) | Other traffic | Chain blocks | DAA gap max | Sink age max, ms | Final after, s | Counter |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| 2026-11-13T01:33 | 3,909 | 0 | 192 | 204 | 206 | 204 | 3,163 | 374 | 0 | 458 | 20 | kept pace |
| 2026-11-13T01:34 | 4,089 | 0 | 193 | 196 | 203 | 199 | 3,343 | 351 | 2 | 365 | 20 | kept pace |
| 2026-11-13T01:35 | 3,854 | 0 | 187 | 181 | 180 | 177 | 3,164 | 340 | 1 | 344 | 19 | kept pace |
| 2026-11-13T01:36 | 3,823 | 0 | 200 | 199 | 201 | 203 | 3,070 | 339 | 2 | 671 | 20 | kept pace |
| 2026-11-13T01:37 | 3,912 | 0 | 198 | 203 | 205 | 199 | 3,161 | 355 | 1 | 288 | 20 | kept pace |
| 2026-11-13T01:38 | 3,868 | 0 | 193 | 199 | 202 | 196 | 3,120 | 342 | 1 | 413 | 20 | kept pace |
| 2026-11-13T01:39 | 3,872 | 0 | 185 | 193 | 190 | 188 | 3,152 | 360 | 0 | 335 | 20 | kept pace |
| 2026-11-13T01:40 | 3,893 | 0 | 195 | 197 | 197 | 190 | 3,151 | 379 | 0 | 544 | 20 | kept pace |
| 2026-11-13T01:41 | 3,776 | 0 | 187 | 185 | 189 | 191 | 3,072 | 338 | 1 | 551 | 20 | kept pace |
| 2026-11-13T01:42 | 3,883 | 0 | 181 | 184 | 192 | 192 | 3,170 | 349 | 1 | 596 | 21 | kept pace |
| 2026-11-13T01:43 | 3,826 | 0 | 177 | 177 | 187 | 186 | 3,129 | 278 | 1 | 810 | 19 | kept pace |
| 2026-11-13T01:44 | 3,845 | 0 | 177 | 185 | 186 | 188 | 3,149 | 276 | 0 | 734 | 20 | kept pace |

Coinbase is taken out as one per merged blue block (on this node a chain block's accepted list carries the coinbase of each blue block it merges). Other traffic is the rest: other users' load, the genesis, and anything not in our logs.

## Hop rate per cohort, as built

Floor (families 1–4, desk private node): 100 sompi/gram per hop. R150 (families 5–8, desk private node): 150 sompi/gram per hop. R300 (families 9–12, desk private node): 300 sompi/gram per hop. R450 (families 13–16, desk private node): 450 sompi/gram per hop. In pre-run 17 that rate is on the hop's node-side mass (kit21): the builder is asked for a bill rate on its own mass so that fee / node mass is the tier's rate.

| Tier | Node rate as built, median (min–max) | Bill rate, median | Node mass, median (min–max) | Node rate in the desk mempool, lowest–highest (probe) |
|---|---|---:|---|---|
| floor (100) | 100.16 (100–100.32) | 314 | 40,842 (40,376–42,152) | 100–100.31 |
| r150 (150) | 150.16 (150–150.32) | 470 | 40,830 (40,383–42,218) | 150–150.32 |
| r300 (300) | 300.16 (300–300.32) | 941 | 40,883 (40,403–42,408) | 300–300.32 |
| r450 (450) | 450.17 (450–450.32) | 1410 | 40,861 (40,422–42,592) | 450.01–450.32 |

Node rate as built is kit21's fee / node mass (rusty-kaspa v2.1.0 storage mass with UTXO plurality, or compute or transient/2 if larger). In the desk mempool the probe divides the node's fee by the larger of the storage and compute mass the node reports.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 7 (272), 6 (258), 8 (256), 5 (255), 4 (255), 10 (250), 9 (239), 11 (195), 3 (190), 17 (179), 19 (178), 20 (177), and 15 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | R150 OK / att / rate rej / full rej / waiting | R300 OK / att / rate rej / full rej / waiting | R450 OK / att / rate rej / full rej / waiting | Family stalls logged | Family node mempool-high marks | Clean |
|---|---:|---:|---:|---:|---:|---|---|---|---|---:|---:|---|
| 2026-11-13T01:33 | 0 | 0 | 0 | 0 | 0 | 192 / 373 / 0 / 0 / 4 | 204 / 379 / 0 / 0 / 4 | 206 / 382 / 0 / 0 / 4 | 204 / 376 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:34 | 0 | 0 | 0 | 0 | 0 | 192 / 374 / 0 / 0 / 3 | 193 / 368 / 0 / 0 / 1 | 199 / 369 / 0 / 0 / 0 | 195 / 369 / 0 / 0 / 0 | 0 | 0 | yes |
| 2026-11-13T01:35 | 0 | 0 | 0 | 0 | 0 | 188 / 371 / 0 / 0 / 4 | 184 / 373 / 0 / 0 / 4 | 184 / 370 / 0 / 0 / 4 | 181 / 371 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:36 | 0 | 0 | 0 | 0 | 0 | 200 / 378 / 0 / 0 / 4 | 199 / 367 / 0 / 0 / 4 | 201 / 365 / 0 / 0 / 4 | 203 / 366 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:37 | 0 | 0 | 0 | 0 | 0 | 198 / 381 / 0 / 0 / 4 | 203 / 380 / 0 / 0 / 4 | 204 / 378 / 0 / 0 / 3 | 199 / 381 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:38 | 0 | 0 | 0 | 0 | 0 | 191 / 368 / 0 / 0 / 2 | 198 / 373 / 0 / 0 / 3 | 201 / 379 / 0 / 0 / 2 | 195 / 377 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-13T01:39 | 0 | 0 | 0 | 0 | 0 | 187 / 370 / 0 / 0 / 4 | 194 / 369 / 0 / 0 / 4 | 192 / 368 / 0 / 0 / 4 | 185 / 365 / 0 / 0 / 0 | 0 | 0 | yes |
| 2026-11-13T01:40 | 0 | 0 | 0 | 0 | 0 | 195 / 365 / 0 / 0 / 4 | 197 / 367 / 0 / 0 / 4 | 197 / 371 / 0 / 0 / 4 | 194 / 374 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:41 | 0 | 0 | 0 | 0 | 0 | 187 / 368 / 0 / 0 / 4 | 185 / 365 / 0 / 0 / 4 | 189 / 367 / 0 / 0 / 4 | 191 / 371 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:42 | 0 | 0 | 0 | 0 | 0 | 181 / 358 / 0 / 0 / 4 | 184 / 361 / 0 / 0 / 4 | 192 / 368 / 0 / 0 / 4 | 192 / 367 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:43 | 0 | 0 | 0 | 0 | 0 | 176 / 355 / 0 / 0 / 3 | 177 / 357 / 0 / 0 / 4 | 187 / 363 / 0 / 0 / 4 | 186 / 363 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T01:44 | 0 | 0 | 0 | 0 | 0 | 178 / 355 / 0 / 0 / 4 | 185 / 369 / 0 / 0 / 4 | 186 / 372 / 0 / 0 / 4 | 188 / 372 / 0 / 0 / 4 | 0 | 0 | yes |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

A mempool-high mark means the family node read a mempool at or over 90,000. In pre-run 17 that does not stop the families: the skip does not apply to them. A skip, if one were set, is dirt with its reason (node-skip-fam) for every minute it covers, and it clears when the mempool falls back under the line.

Within 10 percent means 0 to 0 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender reads and submits every tier on the desk's private node, which the desk counter reads. The kept public kaspads are read for sync and DAA only; no payment of ours went to them.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). 3 payment senders per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 621982370 | 0 | 0 | 0 | 32 |
| 5 | yes | 621982370 | 0 | 0 | 0 | 37 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 2265 of 2265 | 1087 | 1614 |
| r150 | 2303 of 2303 | 1079 | 1585 |
| r300 | 2338 of 2338 | 1065 | 1566 |
| r450 | 2313 of 2313 | 1066 | 1564 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end. Every tier has the same hop shape and the same node; only the rate differs.

## Mempool and template, desk node (probe)

| Minute (UTC) | Samples | Mempool | Ready (no parent in mempool) | Ready mass, blocks of 500k | Other traffic in mempool | Other ready | Other at 100, n | Other at 100, mean mass | Our payments in mempool | Our heavy in mempool / ready | Floor in mempool / ready | R150 in mempool / ready | R300 in mempool / ready | R450 in mempool / ready | Template txs | Template storage mass | Template txs over 100k storage mass | Template: payments | Template: our heavy | Template: floor | Template: r150 | Template: r300 | Template: r450 | Template: other | Fee estimate priority / normal / low | Public 1 mempool | Public 5 mempool |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|
| 2026-11-13T01:33 | 3 | 15 | 15 | 1.23 | 0 | 0 | - | - | 0 | 0 / 0 | 4 / 4 | 4 / 4 | 4 / 4 | 3 / 3 | 12 | 491,831 | 0 | 0 | 0 | 1 | 3 | 4 | 3 | 0 | 167.3 / 138.5 / 109.2 | 2 | 15 |
| 2026-11-13T01:34 | 3 | 6 | 17 | 1.40 | 2 | 2 | - | - | 0 | 0 / 0 | 4 / 4 | 4 / 4 | 4 / 4 | 3 / 3 | 13 | 489,055 | 0 | 0 | 0 | 2 | 3 | 4 | 3 | 1 | 168.9 / 139.2 / 109.3 | 50 | 50 |
| 2026-11-13T01:35 | 3 | 15 | 15 | 1.23 | 1 | 1 | - | - | 0 | 0 / 0 | 4 / 4 | 4 / 4 | 4 / 4 | 3 / 3 | 12 | 451,812 | 0 | 0 | 0 | 1 | 3 | 4 | 3 | 1 | 221.0 / 156.6 / 111.7 | 8 | 8 |
| 2026-11-13T01:36 | 3 | 15 | 16 | 1.24 | 1 | 1 | - | - | 0 | 0 / 0 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 13 | 492,539 | 0 | 0 | 0 | 3 | 2 | 4 | 4 | 1 | 171.3 / 140.2 / 109.4 | 13 | 13 |
| 2026-11-13T01:37 | 3 | 16 | 16 | 1.32 | 0 | 0 | - | - | 0 | 0 / 0 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 12 | 492,641 | 0 | 0 | 0 | 1 | 3 | 4 | 4 | 0 | 180.9 / 143.9 / 110.0 | 0 | 3 |
| 2026-11-13T01:38 | 3 | 13 | 13 | 1.07 | 1 | 1 | - | - | 0 | 0 / 0 | 3 / 3 | 4 / 4 | 3 / 3 | 3 / 3 | 12 | 492,092 | 0 | 0 | 0 | 2 | 3 | 3 | 3 | 1 | 140.0 / 125.5 / 106.8 | 52 | 13 |
| 2026-11-13T01:39 | 3 | 16 | 16 | 1.23 | 1 | 1 | - | - | 0 | 0 / 0 | 3 / 3 | 4 / 4 | 4 / 4 | 4 / 4 | 12 | 489,557 | 0 | 0 | 0 | 1 | 3 | 4 | 4 | 1 | 178.5 / 143.0 / 109.9 | 1 | 14 |
| 2026-11-13T01:40 | 3 | 17 | 17 | 1.52 | 2 | 2 | - | - | 0 | 0 / 0 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 12 | 489,558 | 0 | 0 | 0 | 1 | 2 | 4 | 4 | 0 | 179.2 / 143.3 / 109.9 | 13 | 23 |
| 2026-11-13T01:41 | 3 | 12 | 16 | 1.32 | 0 | 0 | - | - | 0 | 0 / 0 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 12 | 492,774 | 0 | 0 | 0 | 1 | 3 | 4 | 4 | 0 | 178.4 / 143.0 / 109.9 | 0 | 5 |
| 2026-11-13T01:42 | 3 | 8 | 8 | 0.65 | 0 | 0 | - | - | 0 | 0 / 0 | 4 / 4 | 2 / 2 | 0 / 0 | 2 / 2 | 8 | 327,024 | 0 | 0 | 0 | 1 | 2 | 0 | 2 | 0 | 100.0 / 100.0 / 100.0 | 14 | 8 |
| 2026-11-13T01:43 | 3 | 9 | 14 | 1.20 | 1 | 1 | - | - | 0 | 0 / 0 | 4 / 4 | 3 / 3 | 3 / 3 | 3 / 3 | 11 | 475,668 | 0 | 0 | 0 | 1 | 3 | 3 | 3 | 1 | 137.9 / 124.4 / 106.5 | 0 | 16 |
| 2026-11-13T01:44 | 3 | 16 | 18 | 1.50 | 2 | 2 | - | - | 0 | 0 / 0 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 13 | 486,376 | 0 | 0 | 0 | 1 | 2 | 4 | 4 | 1 | 183.2 / 144.8 / 110.1 | 7 | 11 |

Read by the probe on the desk's private TN10 node every 20 s, read-only; each cell is the median of that minute's samples. Pre-run 17: ready count and ready mass come from the full mempool read up to 10,000 entries and from the node's own figures (getFeeEstimateExperimental, verbose) above that, where the per-class columns stay blank (the node's wRPC replies are capped at 128 MiB, about 12,500 entries). Ready means no parent in the mempool: in rusty-kaspa v2.1.0 only those are in the selector's frontier. Ready mass is compared with one block's mass limit (500,000): at or under 1 the selector takes all ready transactions best-first; over 1 it samples at random weighted by (fee/mass)^3 (over 4, sample_inplace). Mass is the larger of compute and storage mass, as the v2.1.0 selector normalises it (transient mass is not in the RPC). Other traffic is every mempool entry not in our sender logs (our heavy lane is its own class, our heavy); its fee rate is the node's fee over that mass. Template transactions carry no id in the RPC, so each is matched to a mempool entry by its first input. The template is the desk node's own getBlockTemplate (never submitted): what this node would put in a block at that moment, not a miner's template. The fee estimate is the node's getFeeEstimate, read only; no sender reads it. Public mempool is getInfo's mempool size on each kept public kaspad.
