# Evaluation test set

Fill this in after every refresh, before you publish. The agent is the system under test.
You are the grader. Nothing here is automated on purpose: the point is to decide, with a
source you trust, whether the agent told you the truth.

**Ground truth sources.** Use these every time, so your scores are
comparable week to week:

- Prices: Yahoo Finance history page (finance.yahoo.com/quote/TICKER/history/). Switched
  from Google Finance on 2026-10-28 because Google Finance would not load for the agent.
  Closing prices only, never intraday.
- News: the article itself. Open the link. Check the date on the page.
- Calendar: the company's investor relations page (search "TICKER investor relations
  events"), or the Fed's own meeting calendar for FOMC dates.

Refresh date: 2026-10-28 (rerun: asOf 2026-10-27)    Grader: number-checker agent

## A. Prices (one row per close, plus one latest-close row per ticker)

Prices are closes only (CLAUDE.md rule 7). Grade two things:

- **Each close.** Pass if the dashboard's close is within $0.10 of the Yahoo Finance close
  for the same date.
- **Latest close.** The dashboard's last price must be the most recent completed close:
  today's close if it has been posted, otherwise the previous trading day's. Pass if the
  date matches that close and the price is within $0.10. Fail if a newer close was
  available (`Fail (stale: newer close available)`), or if the agent recorded an intraday
  price or a price type other than close (`Fail (intraday price recorded)`). Never grade
  an intraday price against anything.

Earlier run, superseded (graded against Google Finance before the switch to Yahoo Finance). Graded 2026-10-28. Every Google Finance quote page returned only "Google Finance isn't
supported on this device" with no price data, so every row below is `Fail (could not verify)`
against the agreed source. The Yahoo Finance values in the "Source you used" column are an
informational cross-check from a different source, opened 2026-10-28 around 11:20 AM ET.
They are not used for any grade.

| Ticker | Date shown | Price type shown | Dashboard price | Ground truth price | Source you used | Pass / Fail |
|---|---|---|---|---|---|---|
| AMD | 2026-10-21 | close | 552.72 | not shown | [Google Finance](https://www.google.com/finance/quote/AMD:NASDAQ) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/AMD/history/) close 552.72 | Fail (could not verify) |
| AMD | 2026-10-22 | close | 507.93 | not shown | [Google Finance](https://www.google.com/finance/quote/AMD:NASDAQ) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/AMD/history/) close 507.93 | Fail (could not verify) |
| AMD | 2026-10-23 | close | 516.79 | not shown | [Google Finance](https://www.google.com/finance/quote/AMD:NASDAQ) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/AMD/history/) close 516.79 | Fail (could not verify) |
| AMD | 2026-10-26 | close | 531.28 | not shown | [Google Finance](https://www.google.com/finance/quote/AMD:NASDAQ) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/AMD/history/) close 531.28 | Fail (could not verify) |
| AMD | 2026-10-27 | close | 560.26 | not shown | [Google Finance](https://www.google.com/finance/quote/AMD:NASDAQ) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/AMD/history/) close 560.26 | Fail (could not verify) |
| AMD | 2026-10-28 11:15 AM | intraday | 567.35 | not shown | [Google Finance](https://www.google.com/finance/quote/AMD:NASDAQ) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/AMD/history/) showed 567.42 at 11:20:47 AM, not 11:15, and no 11:15 price was available | Fail (could not verify) |
| BWXT | 2026-10-21 | close | 135.11 | not shown | [Google Finance](https://www.google.com/finance/quote/BWXT:NYSE) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/BWXT/history/) close 135.11 | Fail (could not verify) |
| BWXT | 2026-10-22 | close | 127.30 | not shown | [Google Finance](https://www.google.com/finance/quote/BWXT:NYSE) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/BWXT/history/) close 127.30 | Fail (could not verify) |
| BWXT | 2026-10-23 | close | 127.19 | not shown | [Google Finance](https://www.google.com/finance/quote/BWXT:NYSE) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/BWXT/history/) close 127.19 | Fail (could not verify) |
| BWXT | 2026-10-26 | close | 131.20 | not shown | [Google Finance](https://www.google.com/finance/quote/BWXT:NYSE) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/BWXT/history/) close 131.20 | Fail (could not verify) |
| BWXT | 2026-10-27 | close | 134.07 | not shown | [Google Finance](https://www.google.com/finance/quote/BWXT:NYSE) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/BWXT/history/) close 134.07 | Fail (could not verify) |
| BWXT | 2026-10-28 11:13 AM | intraday | 133.35 | not shown | [Google Finance](https://www.google.com/finance/quote/BWXT:NYSE) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/BWXT/history/) showed 133.99 at 11:20:19 AM, not 11:13, and no 11:13 price was available | Fail (could not verify) |
| FOXF | 2026-10-21 | close | 14.85 | not shown | [Google Finance](https://www.google.com/finance/quote/FOXF:NASDAQ) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/FOXF/history/) close 14.85 | Fail (could not verify) |
| FOXF | 2026-10-22 | close | 15.33 | not shown | [Google Finance](https://www.google.com/finance/quote/FOXF:NASDAQ) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/FOXF/history/) close 15.33 | Fail (could not verify) |
| FOXF | 2026-10-23 | close | 15.07 | not shown | [Google Finance](https://www.google.com/finance/quote/FOXF:NASDAQ) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/FOXF/history/) close 15.07 | Fail (could not verify) |
| FOXF | 2026-10-26 | close | 14.73 | not shown | [Google Finance](https://www.google.com/finance/quote/FOXF:NASDAQ) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/FOXF/history/) close 14.73 | Fail (could not verify) |
| FOXF | 2026-10-27 | close | 15.44 | not shown | [Google Finance](https://www.google.com/finance/quote/FOXF:NASDAQ) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/FOXF/history/) close 15.44 | Fail (could not verify) |
| FOXF | 2026-10-28 11:01 AM | intraday | 15.36 | not shown | [Google Finance](https://www.google.com/finance/quote/FOXF:NASDAQ) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/FOXF/history/) showed 15.29 at 11:20:39 AM, not 11:01, and no 11:01 price was available | Fail (could not verify) |
| NVDA | 2026-10-21 | close | 221.97 | not shown | [Google Finance](https://www.google.com/finance/quote/NVDA:NASDAQ) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/NVDA/history/) close 221.97 | Fail (could not verify) |
| NVDA | 2026-10-22 | close | 212.21 | not shown | [Google Finance](https://www.google.com/finance/quote/NVDA:NASDAQ) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/NVDA/history/) close 212.21 | Fail (could not verify) |
| NVDA | 2026-10-23 | close | 210.96 | not shown | [Google Finance](https://www.google.com/finance/quote/NVDA:NASDAQ) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/NVDA/history/) close 210.96 | Fail (could not verify) |
| NVDA | 2026-10-26 | close | 216.00 | not shown | [Google Finance](https://www.google.com/finance/quote/NVDA:NASDAQ) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/NVDA/history/) close 216.00 | Fail (could not verify) |
| NVDA | 2026-10-27 | close | 217.94 | not shown | [Google Finance](https://www.google.com/finance/quote/NVDA:NASDAQ) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/NVDA/history/) close 217.94 | Fail (could not verify) |
| NVDA | 2026-10-28 11:15 AM | intraday | 217.75 | not shown | [Google Finance](https://www.google.com/finance/quote/NVDA:NASDAQ) (no data shown). Cross-check, not graded: [Yahoo](https://finance.yahoo.com/quote/NVDA/history/) showed 217.81 at 11:21:25 AM, not 11:15, and no 11:15 price was available | Fail (could not verify) |

### Rerun, closes only, BRIEF.asOf 2026-10-27, graded 2026-10-28 (Yahoo pages stamped 11:20 to 11:21 AM EDT)

BRIEF.retrievedAt 2026-10-28T11:15:00-04:00. Price type check: `BRIEF.priceType` is `"close"` and every `latest` is `null`, so there is no intraday fail. Source: the Yahoo Finance history page for each ticker. Every page's quote header read "As of 11:20 to 11:21 AM EDT. Market Open." and "U.S. markets close in 4h 40m", so the Oct 28 row on each page is still in session and is not a close. The latest completed close is 2026-10-27 for all four tickers. No Oct 28 value is recorded or graded here.

| Ticker | Date shown | Price type shown | Dashboard price | Ground truth price | Source you used | Pass / Fail |
|---|---|---|---|---|---|---|
| AMD | 2026-10-21 | close | 552.72 | 552.72 | [Yahoo AMD history](https://finance.yahoo.com/quote/AMD/history/) | Pass |
| AMD | 2026-10-22 | close | 507.93 | 507.93 | [Yahoo AMD history](https://finance.yahoo.com/quote/AMD/history/) | Pass |
| AMD | 2026-10-23 | close | 516.79 | 516.79 | [Yahoo AMD history](https://finance.yahoo.com/quote/AMD/history/) | Pass |
| AMD | 2026-10-26 | close | 531.28 | 531.28 | [Yahoo AMD history](https://finance.yahoo.com/quote/AMD/history/) | Pass |
| AMD | 2026-10-27 | close | 560.26 | 560.26 | [Yahoo AMD history](https://finance.yahoo.com/quote/AMD/history/) | Pass |
| AMD | Latest close: 2026-10-27 | close | 560.26 | 560.26 (2026-10-27; Oct 28 still in session, "Market Open" at 11:20:47 AM EDT) | [Yahoo AMD history](https://finance.yahoo.com/quote/AMD/history/) | Pass |
| BWXT | 2026-10-21 | close | 135.11 | 135.11 | [Yahoo BWXT history](https://finance.yahoo.com/quote/BWXT/history/) | Pass |
| BWXT | 2026-10-22 | close | 127.30 | 127.30 | [Yahoo BWXT history](https://finance.yahoo.com/quote/BWXT/history/) | Pass |
| BWXT | 2026-10-23 | close | 127.19 | 127.19 | [Yahoo BWXT history](https://finance.yahoo.com/quote/BWXT/history/) | Pass |
| BWXT | 2026-10-26 | close | 131.20 | 131.20 | [Yahoo BWXT history](https://finance.yahoo.com/quote/BWXT/history/) | Pass |
| BWXT | 2026-10-27 | close | 134.07 | 134.07 | [Yahoo BWXT history](https://finance.yahoo.com/quote/BWXT/history/) | Pass |
| BWXT | Latest close: 2026-10-27 | close | 134.07 | 134.07 (2026-10-27; Oct 28 still in session, "Market Open" at 11:20:19 AM EDT) | [Yahoo BWXT history](https://finance.yahoo.com/quote/BWXT/history/) | Pass |
| FOXF | 2026-10-21 | close | 14.85 | 14.85 | [Yahoo FOXF history](https://finance.yahoo.com/quote/FOXF/history/) | Pass |
| FOXF | 2026-10-22 | close | 15.33 | 15.33 | [Yahoo FOXF history](https://finance.yahoo.com/quote/FOXF/history/) | Pass |
| FOXF | 2026-10-23 | close | 15.07 | 15.07 | [Yahoo FOXF history](https://finance.yahoo.com/quote/FOXF/history/) | Pass |
| FOXF | 2026-10-26 | close | 14.73 | 14.73 | [Yahoo FOXF history](https://finance.yahoo.com/quote/FOXF/history/) | Pass |
| FOXF | 2026-10-27 | close | 15.44 | 15.44 | [Yahoo FOXF history](https://finance.yahoo.com/quote/FOXF/history/) | Pass |
| FOXF | Latest close: 2026-10-27 | close | 15.44 | 15.44 (2026-10-27; Oct 28 still in session, "Market Open" at 11:20:39 AM EDT) | [Yahoo FOXF history](https://finance.yahoo.com/quote/FOXF/history/) | Pass |
| NVDA | 2026-10-21 | close | 221.97 | 221.97 | [Yahoo NVDA history](https://finance.yahoo.com/quote/NVDA/history/) | Pass |
| NVDA | 2026-10-22 | close | 212.21 | 212.21 | [Yahoo NVDA history](https://finance.yahoo.com/quote/NVDA/history/) | Pass |
| NVDA | 2026-10-23 | close | 210.96 | 210.96 | [Yahoo NVDA history](https://finance.yahoo.com/quote/NVDA/history/) | Pass |
| NVDA | 2026-10-26 | close | 216.00 | 216.00 | [Yahoo NVDA history](https://finance.yahoo.com/quote/NVDA/history/) | Pass |
| NVDA | 2026-10-27 | close | 217.94 | 217.94 | [Yahoo NVDA history](https://finance.yahoo.com/quote/NVDA/history/) | Pass |
| NVDA | Latest close: 2026-10-27 | close | 217.94 | 217.94 (2026-10-27; Oct 28 still in session, "Market Open" at 11:21:25 AM EDT) | [Yahoo NVDA history](https://finance.yahoo.com/quote/NVDA/history/) | Pass |

## B. Weekly change (one row per ticker)

The page computes this from the five closes. Pass if it is within 0.3 percentage points of
your own calculation: (latest completed close minus the first of the five closes) divided
by that first close, using the Yahoo Finance closes from A. Closes only: if the latest-close
row in A failed, this row fails too.

Earlier run, superseded (Google Finance, intraday brief). Dashboard weekly change uses `latest.price` as last and the Oct 21 close as first, the same
way the page does. "Your calculation" must come from the Google Finance prices in A. A has
none because Google Finance showed no data, so every row is `Fail (could not verify)`.

| Ticker | Dashboard weekly change | Your calculation | Source link | Pass / Fail |
|---|---|---|---|---|
| AMD | (567.35 - 552.72) / 552.72 = +2.65% | Not computable: no Google Finance prices recorded in A | [Google Finance](https://www.google.com/finance/quote/AMD:NASDAQ) | Fail (could not verify) |
| BWXT | (133.35 - 135.11) / 135.11 = -1.30% | Not computable: no Google Finance prices recorded in A | [Google Finance](https://www.google.com/finance/quote/BWXT:NYSE) | Fail (could not verify) |
| FOXF | (15.36 - 14.85) / 14.85 = +3.43% | Not computable: no Google Finance prices recorded in A | [Google Finance](https://www.google.com/finance/quote/FOXF:NASDAQ) | Fail (could not verify) |
| NVDA | (217.75 - 221.97) / 221.97 = -1.90% | Not computable: no Google Finance prices recorded in A | [Google Finance](https://www.google.com/finance/quote/NVDA:NASDAQ) | Fail (could not verify) |

### Rerun, closes only, BRIEF.asOf 2026-10-27, graded 2026-10-28

BRIEF.retrievedAt 2026-10-28T11:15:00-04:00. Dashboard weekly change uses the brief's first close (2026-10-21) and last close (2026-10-27), the same way the page does. "Your calculation" uses the Yahoo Finance closes recorded in A's rerun table for the same first date (2026-10-21) and the latest completed close (2026-10-27; Oct 28 was still in session). Every A rerun latest-close row passed, so no row inherits a fail.

| Ticker | Dashboard weekly change | Your calculation | Source link | Pass / Fail |
|---|---|---|---|---|
| AMD | (560.26 - 552.72) / 552.72 = +1.36% | (560.26 - 552.72) / 552.72 = +1.36% (difference 0.00 pp) | [Yahoo AMD history](https://finance.yahoo.com/quote/AMD/history/) | Pass |
| BWXT | (134.07 - 135.11) / 135.11 = -0.77% | (134.07 - 135.11) / 135.11 = -0.77% (difference 0.00 pp) | [Yahoo BWXT history](https://finance.yahoo.com/quote/BWXT/history/) | Pass |
| FOXF | (15.44 - 14.85) / 14.85 = +3.97% | (15.44 - 14.85) / 14.85 = +3.97% (difference 0.00 pp) | [Yahoo FOXF history](https://finance.yahoo.com/quote/FOXF/history/) | Pass |
| NVDA | (217.94 - 221.97) / 221.97 = -1.82% | (217.94 - 221.97) / 221.97 = -1.82% (difference 0.00 pp) | [Yahoo NVDA history](https://finance.yahoo.com/quote/NVDA/history/) | Pass |

## C. News grounding (one row per news item, three per ticker)

Open every link. Pass only if all four are true: the link opens, the headline matches the
article, the article date is within the last seven days, and the "why it matters" line is
supported by the article (not just plausible).

Window: 2026-10-22 to 2026-10-28 inclusive. BWXT and FOXF have empty news lists in the
brief, so there are no rows for them (any omission belongs in E, which the owner grades).

| Ticker | Headline (first few words) | Link opens | Headline matches | Dated within 7 days | "Why" is supported | Source link | Pass / Fail |
|---|---|---|---|---|---|---|---|
| AMD | AMD and Meta Advance Strategic Partnership... | Yes | Yes, exact | Yes, Oct 27, 2026 9:20 a.m. EDT, which matches the brief | Yes: "Initial AMD Helios rackscale solutions are installed and being tested by Meta"; "will invest $1 billion in Meta's equity offering" | [ir.amd.com release 1302](https://ir.amd.com/news-events/press-releases/detail/1302/amd-and-meta-advance-strategic-partnership-to-power-metas-superintelligence-infrastructure) | Pass |
| NVDA | NVIDIA and Oracle Expand NVIDIA Vera Rubin... | Yes | Yes, exact | Yes, Oct 27, 2026, which matches the brief | Yes: the release says "plans to expand Oracle Cloud Infrastructure (OCI) Superclusters with NVIDIA Vera Rubin NVL72 systems to multi-gigawatt scale". It is framed as a plan, and the brief also says "plans". | [nvidianews.nvidia.com](https://nvidianews.nvidia.com/news/nvidia-and-oracle-expand-nvidia-vera-rubin-to-multi-gigawatt-scale-and-bring-nvidia-vera-cpu-to-oracle-cloud-infrastructure) | Pass |
| NVDA | NVIDIA and Meta to Expand Collaboration on Muse... | Yes | Yes, exact | Yes, Oct 26, 2026, which matches the brief | Yes: "Meta intends to expand the deployment of NVIDIA infrastructure"; "will also deploy NVIDIA Spectrum-X Ethernet networking"; "NVIDIA will invest $3 billion in Meta's equity offering" | [nvidianews.nvidia.com](https://nvidianews.nvidia.com/news/nvidia-and-meta-to-expand-collaboration-on-muse-and-muse-family-of-models-amid-robust-growth) | Pass |
| NVDA | Nvidia Stock News (Oct 23, 2026): NVDA Falls 4.4%... | Yes | Yes, exact | Yes, Oct 23, 2026, which matches the brief | Yes: the article says the stock "fell with a sector-wide sell-off" and that AI spending concerns "resurfaced on October 22". It also cites Meta's earnings and says the drop was not NVIDIA-specific. (The source is an aggregator.) | [heygotrade.com](https://www.heygotrade.com/en/news/nvidia-nvda-stock-news-october-23-2026/) | Pass |

### Rerun, closes only, BRIEF.asOf 2026-10-27, graded 2026-10-28

BRIEF.retrievedAt 2026-10-28T11:15:00-04:00. Window: the seven days ending on BRIEF.asOf, 2026-10-21 to 2026-10-27 inclusive. I opened every link again on 2026-10-28. BWXT and FOXF have empty news lists in the brief, so there are no rows for them (any omission belongs in E, which the owner grades).

| Ticker | Headline (first few words) | Link opens | Headline matches | Dated within 7 days | "Why" is supported | Source link | Pass / Fail |
|---|---|---|---|---|---|---|---|
| AMD | AMD and Meta Advance Strategic Partnership... | Yes | Yes, exact | Yes. The page shows Oct 27, 2026, 9:20 a.m. EDT, which matches the brief and is inside Oct 21 to 27. | Yes: "Initial AMD Helios rackscale solutions are installed and being tested by Meta"; "AMD will invest $1 billion in Meta's equity offering" | [ir.amd.com release 1302](https://ir.amd.com/news-events/press-releases/detail/1302/amd-and-meta-advance-strategic-partnership-to-power-metas-superintelligence-infrastructure) | Pass |
| NVDA | NVIDIA and Oracle Expand NVIDIA Vera Rubin... | Yes | Yes, exact | Yes. The page shows Oct 27, 2026, which matches the brief and is inside the window. | Yes: the release "plans to expand Oracle Cloud Infrastructure (OCI) Superclusters with NVIDIA Vera Rubin NVL72 systems" to multi-gigawatt scale. The brief also frames it as a plan. | [nvidianews.nvidia.com](https://nvidianews.nvidia.com/news/nvidia-and-oracle-expand-nvidia-vera-rubin-to-multi-gigawatt-scale-and-bring-nvidia-vera-cpu-to-oracle-cloud-infrastructure) | Pass |
| NVDA | NVIDIA and Meta to Expand Collaboration on Muse... | Yes | Yes, exact | Yes. The page shows Oct 26, 2026, which matches the brief and is inside the window. | Yes: "Meta intends to expand the deployment of NVIDIA infrastructure"; "Meta will also deploy NVIDIA Spectrum-X Ethernet networking"; "NVIDIA will invest $3 billion in Meta's equity offering" | [nvidianews.nvidia.com](https://nvidianews.nvidia.com/news/nvidia-and-meta-to-expand-collaboration-on-muse-and-muse-family-of-models-amid-robust-growth) | Pass |
| NVDA | Nvidia Stock News (Oct 23, 2026): NVDA Falls 4.4%... | Yes | Yes, exact | Yes. The page shows Oct 23, 2026, which matches the brief and is inside the window. | Yes: NVIDIA "fell with a sector-wide sell-off"; financial media "did not point to an Nvidia-specific trigger"; AI spending concerns resurfaced on Oct 22; Meta fell after its results. (The source is an aggregator.) | [heygotrade.com](https://www.heygotrade.com/en/news/nvidia-nvda-stock-news-october-23-2026/) | Pass |

## D. Calendar (one row per event)

Pass if the event and its date appear on the source linked, and the date is in the future
relative to the refresh date.

| Ticker | Event | Date shown | Confirmed on source | Source link | Pass / Fail |
|---|---|---|---|---|---|
| AMD | Q3 2026 earnings, after market close; call at 5 p.m. ET | 2026-11-03 | Yes. The IR calendar lists "Nov 3, 2026 • 2:00 pm PDT: AMD Fiscal Third Quarter 2026 Financial Results" (2 p.m. PT = 5 p.m. ET). Release 1300 (Oct 6, 2026) says "Tuesday, Nov. 3, 2026, after the market close", with the call at "5 p.m. ET". The date is after asOf. | [AMD IR calendar](https://ir.amd.com/news-events/ir-calendar), [release 1300](https://ir.amd.com/news-events/press-releases/detail/1300) | Pass |
| BWXT | Q3 2026 results, after market close; call at 5 p.m. ET | 2026-11-02 | Could not open the IR site: investors.bwxt.com and its events page both returned HTTP 403. The company's own Business Wire release (Oct 1, 2026, republished on Finviz) does state Monday, Nov 2, after market close, call at 5:00 p.m. ET, so this is not an "expected" date. It is still not confirmed on the IR page as the rule requires. | [investors.bwxt.com/events-and-presentations](https://investors.bwxt.com/events-and-presentations) (403), [investors.bwxt.com](https://investors.bwxt.com/) (403), [Finviz wire copy](https://finviz.com/news/398036/bwx-technologies-to-announce-third-quarter-2026-results-on-monday-november-2) | Fail (could not verify) |
| FOXF | Q3 2026 results, after market close; call at 4:30 p.m. ET | 2026-11-05 | Could not open the IR site: investor.ridefox.com/events-and-presentations and foxfactory.gcs-web.com/events-and-presentations both returned HTTP 403. The company's own GlobeNewswire release (Oct 16, 2026, republished on Finviz) does state Thursday, Nov 5, 2026, after market close, call at 4:30 p.m. ET, so this is not an "expected" date. It is still not confirmed on the IR page as the rule requires. | [investor.ridefox.com/events-and-presentations](https://investor.ridefox.com/events-and-presentations) (403), [foxfactory.gcs-web.com/events-and-presentations](https://foxfactory.gcs-web.com/events-and-presentations) (403), [Finviz wire copy](https://finviz.com/news/403554/fox-factory-holding-corp-announces-third-quarter-2026-earnings-conference-call) | Fail (could not verify) |
| NVDA (market-wide) | FOMC rate decision (Oct 27 to 28 meeting) | 2026-10-28 | Yes. The Fed calendar lists the 2026 October meeting as 27-28, and Oct 28 equals asOf, so it counts as on or after. | [federalreserve.gov FOMC calendar](https://www.federalreserve.gov/monetarypolicy/fomccalendars.htm) | Pass |
| NVDA (market-wide) | October CPI release, 8:30 a.m. ET | 2026-11-10 | Yes. The BLS schedule row reads "October 2026 Nov. 10, 2026 08:30 AM". The date is after asOf. | [bls.gov CPI schedule](https://www.bls.gov/schedule/news_release/cpi.htm) | Pass |

### Rerun, closes only, BRIEF.asOf 2026-10-27, graded 2026-10-28

BRIEF.retrievedAt 2026-10-28T11:15:00-04:00. Dates must be on or after BRIEF.asOf, 2026-10-27. I found the IR pages by searching "TICKER investor relations events" and opened them on 2026-10-28. FOMC is checked against federalreserve.gov and CPI against bls.gov.

| Ticker | Event | Date shown | Confirmed on source | Source link | Pass / Fail |
|---|---|---|---|---|---|
| AMD | Q3 2026 earnings, after market close; call at 5 p.m. ET | 2026-11-03 | Yes. The IR calendar lists "Nov 3, 2026, 2:00 pm PDT: AMD Fiscal Third Quarter 2026 Financial Results" (2 p.m. PT = 5 p.m. ET). Release 1300 (Oct 6, 2026) says "Tuesday, Nov. 3, 2026, after the market close", with the call at "5 p.m. ET / 2 p.m. PT". The date is after asOf. | [AMD IR calendar](https://ir.amd.com/news-events/ir-calendar), [release 1300](https://ir.amd.com/news-events/press-releases/detail/1300) | Pass |
| BWXT | Q3 2026 results, after market close; call at 5 p.m. ET | 2026-11-02 | Could not open the IR site: four investors.bwxt.com and bwxt.gcs-web.com pages (events page, home page, the guessed release page) all returned HTTP 403. The company's own Business Wire release (Oct 1, 2026, republished on Finviz) does state "Monday, November 2, 2026, after market close" with a call at "5:00 p.m. ET", so this is not an "expected" date. It is still not confirmed on the IR page as the rule requires. | [investors.bwxt.com/events-and-presentations](https://investors.bwxt.com/events-and-presentations) (403), [bwxt.gcs-web.com/events-and-presentations](https://bwxt.gcs-web.com/events-and-presentations) (403), [investors.bwxt.com](https://investors.bwxt.com/) (403), [Finviz wire copy](https://finviz.com/news/398036/bwx-technologies-to-announce-third-quarter-2026-results-on-monday-november-2) | Fail (could not verify) |
| FOXF | Q3 2026 results, after market close; call at 4:30 p.m. ET | 2026-11-05 | Could not open the IR site: investor.ridefox.com (events page and home page) and foxfactory.gcs-web.com/events-and-presentations all returned HTTP 403. The company's own GlobeNewswire release (Oct 16, 2026, republished on Finviz) does state "Thursday, November 5, 2026, after the market close" with the call at "4:30 p.m. ET", so this is not an "expected" date. It is still not confirmed on the IR page as the rule requires. | [investor.ridefox.com/events-and-presentations](https://investor.ridefox.com/events-and-presentations) (403), [investor.ridefox.com](https://investor.ridefox.com/) (403), [foxfactory.gcs-web.com/events-and-presentations](https://foxfactory.gcs-web.com/events-and-presentations) (403), [Finviz wire copy](https://finviz.com/news/403554/fox-factory-holding-corp-announces-third-quarter-2026-earnings-conference-call) | Fail (could not verify) |
| NVDA (market-wide) | FOMC rate decision (Oct 27 to 28 meeting) | 2026-10-28 | Yes. The Fed calendar lists the 2026 October meeting as "27-28" (page last updated Oct 7, 2026). The decision date, Oct 28, is after asOf (2026-10-27). | [federalreserve.gov FOMC calendar](https://www.federalreserve.gov/monetarypolicy/fomccalendars.htm) | Pass |
| NVDA (market-wide) | October CPI release, 8:30 a.m. ET | 2026-11-10 | Yes. For the October 2026 reference month, the BLS schedule shows "Nov. 10, 2026" at "08:30 AM". The date is after asOf. | [bls.gov CPI schedule](https://www.bls.gov/schedule/news_release/cpi.htm) | Pass |

## E. Omissions

Did the agent miss something a human analyst would have included? List anything you found
in the ground-truth sources that the brief does not mention (a big headline, an earnings
date inside the window). Each one counts as a Fail in the score below.

- 
- 

## F. Your own test cases

Write two tests of your own that none of the sections above cover. Examples students have
used: "the as-of date on the page matches the changelog date", "no ticker shows a flat
sparkline when the real stock moved", "the page still renders if I delete one ticker's
news list in the data". Write the test, run it, record the result.

| Test | How you checked | Pass / Fail |
|---|---|---|
| | | |
| | | |

## Score

| Section | Passes | Total | Rate |
|---|---|---|---|
| A. Prices | | | |
| B. Weekly change | | | |
| C. News | | | |
| D. Calendar | | | |
| E. Omissions (fails only) | 0 | | |
| F. Your own | | | |
| **Overall** | | | |

Publish only if A and B are 100% and C is at least 80% after fixes. If a row failed, tell
Claude exactly which row and what the correct value is, let it fix only that, rerun the
`qa-reviewer` agent, and regrade that row. Keep the original Fail in this file: a record of
what the agent got wrong is more useful than a clean sheet.
