# Los Angeles VPS Hosting: SixtyNet's Plans Start at $240/mo, Some Block Ports 80 and 443, and Annual Billing Cuts 13–17% (Full Plan and Price Table)

SixtyNet's cheapest Los Angeles VPS is LAX-STARTER: 2 cores, 2 GB RAM, 40 GB NVMe and 5 TB of traffic on a 2 Gbps premium port, listed at $240 per month, or $200 per month on annual billing. That is 16 to 32 times what a mainstream 2 GB LA slice costs from the big budget providers. What the price buys is a premium network port, DDoS protection on the LAX line, residential IPs on the Residential line, and AS9929 China routing on the Irvine line.

Below is the full plan table, then the parts that decide whether any of it fits you: which plans close ports 80 and 443, where the annual discount stops being a discount, what the refund language actually says, and what $3 to $15 buys in the same city if your budget is nowhere near $240.

> **Most people who need a US West Coast box facing Asia:** LAX-STARTER, $240/mo or $200/mo annual, 2 cores, 2 GB, 5 TB on a 2 Gbps port, DDoS protection included.
> **Need a US residential IP for accounts, streaming or scraping:** Residential-STARTER at $300/mo, with ports 80 and 443 closed.
> **Routing to mainland China on AS9929:** IRVINE-PRO-STARTER at $420/mo, and read the refund clause before you pay.
> 👉 [See the current SixtyNet Los Angeles plan list and annual rates](https://sixtynet.net/aff.php?aff=39)

## Every SixtyNet Los Angeles plan, with prices

Grouped by product line rather than page order. The second price is the annual-billing rate SixtyNet shows next to the monthly one; the discount ranges from 13% to 17% depending on the plan.

| Plan | Cores / RAM | NVMe | Traffic · port | Price (monthly · annual billing) | Order |
| --- | --- | --- | --- | --- | --- |
| LAX-STARTER | 2 / 2 GB | 40 GB | 5 TB · 2 Gbps | $240 · $200 | [ Order](https://sixtynet.net/aff.php?aff=39) |
| LAX-MICRO | 4 / 4 GB | 80 GB | 10 TB · 4 Gbps | $480 · $400 | [ Order](https://sixtynet.net/aff.php?aff=39) |
| LAX-MEDIUM | 8 / 8 GB | 160 GB | 20 TB · 10 Gbps | $960 · $800 | [ Order](https://sixtynet.net/aff.php?aff=39) |
| LAX-LARGE | 8 / 16 GB | 320 GB | 40 TB · 10 Gbps | $1,920 · $1,600 | [ Order](https://sixtynet.net/aff.php?aff=39) |
| LAX-Storage-500G | 4 / 4 GB | 300 GB + 200 GB RAID 10 | 10 TB · 10 Gbps | $480 · $400 | [ Order](https://sixtynet.net/aff.php?aff=39) |
| LAX storage, larger tier | 8 / 8 GB | 700 GB + 300 GB RAID 10 | 15 TB · 10 Gbps | not shown on the price block | [ Order](https://sixtynet.net/aff.php?aff=39) |
| Residential-STARTER | 2 / 2 GB | 40 GB | 5 TB · 2 Gbps | $300 · $260 | [ Order](https://sixtynet.net/aff.php?aff=39) |
| Residential-MICRO | 4 / 4 GB | 80 GB | 10 TB · 4 Gbps | $540 · $460 | [ Order](https://sixtynet.net/aff.php?aff=39) |
| Residential-MEDIUM | 8 / 8 GB | 160 GB | 20 TB · 10 Gbps | $1,020 · $860 | [ Order](https://sixtynet.net/aff.php?aff=39) |
| Residential-LARGE | 16 / 16 GB | 320 GB | 40 TB · 10 Gbps | $1,980 · $1,660 | [ Order](https://sixtynet.net/aff.php?aff=39) |
| IRVINE-PRO-STARTER | 2 / 2 GB | 40 GB | 5 TB · 2 Gbps | $420 · $350 | [ Order](https://sixtynet.net/aff.php?aff=39) |
| IRVINE-PRO-MICRO | 4 / 4 GB | 80 GB | 10 TB · 4 Gbps | $660 · $550 | [ Order](https://sixtynet.net/aff.php?aff=39) |
| Los Angeles China Unicom-Premium | BGP / bandwidth product | — | 100M base, 3× burst, 95th-percentile billing | $3,000 · $2,500 | [ Order](https://sixtynet.net/aff.php?aff=39) |

Four things the table compresses:

- **IOPS splits the tiers.** The 2-core and 4-core plans are rated at 12,500 IOPS; the 8-core and 16-core plans at 25,000. Doubling the disk throughput matters more than the extra cores for databases and busy WordPress installs.
- **DDoS protection is a LAX-line feature.** All four LAX plans and both storage plans list it. The Residential and Irvine Pro lines don't list it.
- **Residential IPs close ports 80 and 443.** SixtyNet states this on the price page for every Residential plan, citing IP risk control. IRVINE-PRO plans carry the same residential IP flag, plus a default-deny firewall (more below).
- **The last storage configuration has no price in the block.** Specs are listed (8 cores, 8 GB, 700 GB + 300 GB RAID 10, 15 TB) but you'll need to check the cart or ask support for the number.

The China Unicom-Premium entry isn't a VPS in the usual sense. It's a China Unicom AS9929 transit product with free BGP session setup, 3× burst on a 100M base, 95th-percentile billing and quarterly/annual payment discounts. It's for people announcing their own address space, not for someone who wants root on a server.

## Why the residential plans can't host a website

Ports 80 and 443 are closed on the Residential line, by SixtyNet's own description. That rules out ordinary web hosting: no plain inbound HTTP or HTTPS, so no public site, no Let's Encrypt HTTP validation on the standard port, no drop-in replacement for a normal web VPS.

What's left is outbound work that benefits from an IP which looks like a home connection: streaming service access, account and ad-ops work, price and content scraping, regional quality checks. A third-party test published in October 2025 ran a SixtyNet residential instance on Cox Communications upstream and reported a native US IP with strong streaming unlock results, ping blocked at the network level, no IPv6 support, AMD EPYC 7002 hardware and roughly 188 MB/s disk I/O. Those results describe the specific configuration tested, not the whole line, but they match what the product is sold for.

The IRVINE-PRO line adds a second constraint. SixtyNet describes those plans as rejecting all external probes and scans by default, with access restricted until you configure it, and only whitelisted or port-forwarded devices getting through. That's a hardened box you have to build firewall rules for before anything connects. It also carries the only refund sentence on the entire price page.

👉 [Check the Residential and Irvine Pro plan terms before ordering](https://sixtynet.net/aff.php?aff=39)

## The annual price is real; the refund policy needs a question

Every plan shows two numbers. The gap is 13% on Residential-STARTER ($300 to $260), 15% on Residential-MICRO, 16% on Residential-MEDIUM and Residential-LARGE, and 17% on the LAX and Irvine Pro lines. On the entry plan that's $480 saved across a year, and $960 on LAX-MICRO.

The page never states whether the lower figure is a monthly rate under a 12-month contract or a single yearly charge. The 17% saving only works out if it's the former, so treat $200 as a monthly rate you commit to for a year, and confirm the invoice total at checkout.

The bigger question is what happens if you cancel. SixtyNet publishes no general money-back window on its pricing page. The one refund statement visible is on the IRVINE-PRO plans: refunds are valid only as website balance. Prepay a year on that line and change your mind, and you're holding credit with the provider rather than your money back. For a $350 to $550 annual commitment, that's worth an email to support before you pay, especially if the plan has to pass a procurement review.

👉 [Compare the monthly and annual rate on the LAX-Starter plan](https://sixtynet.net/aff.php?aff=39)

## Why Los Angeles, and what latency to actually expect

Los Angeles is the main US landing point for trans-Pacific submarine cables, which is why it produces the lowest Asian latency of any US location. Published network figures from LA providers put LA-local round trips at 1–3 ms, the US West at 5–30 ms, the East Coast at 60–80 ms, Tokyo at roughly 110–150 ms and Singapore at 160–180 ms. Real numbers move with route and time of day.

That profile fits a few workloads well: an API or game backend that serves both US and Asian users from one place, a VPN or proxy endpoint, media delivery, or anything that needs a US IP for data-residency or geo-relevance reasons while staying close to Asia.

If your users are mostly in Japan or Korea, a Tokyo node will beat any LA node on latency, and SixtyNet doesn't sell one. SixtyNet's LA presence is built around the other direction: AS9929 on the Irvine line and a China Unicom Premium product for mainland China routing. That's the reason its prices sit where they do, and it's the reason someone comparing on CPU and RAM alone will find them inexplicable.

## What $3 to $15 buys in Los Angeles elsewhere

Four LA providers publish plans in that band. All figures are from their own pages, none of them include a SixtyNet-style China-optimised route.

| Provider | Entry | 2 GB tier | Notes |
| --- | --- | --- | --- |
| Cloudzy | 512 MB at $2.48/mo on a 50% promo, $4.95 regular | $7.48/mo promo, $14.95 regular | 14-day money-back, 60-second provisioning, us-lax-1 region |
| OliveVPS | $3.99/mo, Linux only | $7.99/mo, Linux and Windows | Coresite LA1 in downtown LA, 7-day refund, no free trial |
| ExtraVM | 1 GB at $4.50/mo | $8.00/mo | Digital Realty BUR10 in Burbank, DDoS protection included on every plan |
| INIZ | £4.50/mo | £8.00/mo | Priced in GBP, annual billing about 10% cheaper |

The 2 GB comparison is the honest one: $240 a month against $7.48 to $14.95. Those plans run on commodity transit with shared host resources and no China-optimised path. For a WordPress site aimed at US visitors, one of them does the job at a fraction of the cost, and Cloudzy's 14-day refund or OliveVPS's 7-day window gives you an exit if the box underperforms.

Two details from those pages are worth carrying into any purchase, including SixtyNet's. Cloudzy shows the promotional price and the regular price side by side, so the $2.48 is visibly a $4.95 plan on discount. OliveVPS's $3.99 tier is Linux-only; Windows costs $7.99 and up. Cheap headline prices tend to hide one of those two things.

## Who shouldn't buy SixtyNet in Los Angeles

- **A single site or blog with a US or global audience.** Any of the sub-$15 plans above handles it. You'd be paying for a premium route you aren't using.
- **A budget under $20 a month.** Nothing in this lineup starts there.
- **Windows.** The plan list doesn't mention Windows licensing or images. Ask support before assuming.
- **Anyone who needs a published street address.** SixtyNet names Los Angeles and, in a product name, Irvine. There's no facility name or address on the price page. ExtraVM publishes BUR10 in Burbank, OliveVPS publishes Coresite LA1; if facility transparency is a procurement requirement, those are the ones that answer it.
- **Anyone who needs a documented refund window.** Only the Irvine Pro balance clause is published. If a 7- or 14-day money-back guarantee is a hard requirement, the budget providers list it explicitly and SixtyNet doesn't.

## Picking a tier

Match the plan to the constraint that brought you here, not to the spec sheet.

- Need a DDoS-protected LA box with a premium port and 5 TB of traffic → LAX-STARTER at $240/mo, $200 on annual billing.
- Traffic above 20 TB, or a 10 Gbps port → LAX-MEDIUM (20 TB) or LAX-LARGE (40 TB).
- Bulk storage or backups → LAX-Storage-500G, which trades cores for a 500 GB RAID 10 volume with bonus capacity.
- A US residential IP for outbound work → Residential-STARTER, with ports 80 and 443 closed as designed.
- Mainland China routing on AS9929 → IRVINE-PRO-STARTER or MICRO, accepting the default-deny firewall and the balance-only refund.
- Announcing your own network in LA → the China Unicom-Premium product, priced at $3,000 monthly or $2,500 on annual terms.

Three things to confirm before paying: whether the annual rate is a monthly figure on a 12-month term or a single yearly charge; whether any refund applies to the specific plan you're buying; and whether the ports your workload needs are open on that line. The first two are invoice questions, and support answers them faster than a cancellation does.

👉 [Open SixtyNet's Los Angeles plan list and confirm current pricing](https://sixtynet.net/aff.php?aff=39)
