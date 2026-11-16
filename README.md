# C1 2022 research input

Public, independently sourced input for a fixed-2022 C1 economic research reproduction. This repository contains input data, not verified QuantConnect results or investment advice.

## Files and provenance

- `c1_2022_input.json`: 19,503,889 bytes of readable JSON. Contains 548 candidate security records, 19 ETF holdings snapshots, 7,124 dated financial-evidence records, benchmark document references, and a daily-session calendar.
- `SHA256SUMS`: SHA-256 checksum for the exact JSON bytes.
- This README: provenance and limitations.

Sources are SEC EDGAR public NPORT-P filings (holdings date 2021-09-30, accepted 2021-11-18 or 2021-11-24), SEC companyfacts/submissions, referenced benchmark issuer documents, and published NYSE closure calendars. Record-level source URLs, dates and hashes are retained in the JSON. No QuantConnect price history, vendor security-master export, account data, credentials or trading transactions are included.

SEC states that government-created website content and EDGAR public filing content are free to access and reuse: https://www.sec.gov/about/webmaster-frequently-asked-questions

The 2020-2022 daily-session calendar was independently rebuilt from weekdays and NYSE full closures, retaining early-close sessions:
- https://ir.theice.com/press/news-details/2019/NYSE-Group-Announces-2020-2021-and-2022-Holiday-and-Early-Closings-Calendar/default.aspx
- https://ir.theice.com/press/news-details/2021/NYSE-Group-Announces-2022-2023-and-2024-Holiday-and-Early-Closings-Calendar/default.aspx

## Validation and limitations

Local input checks preserved the 548-member universe, all 13 trailing-253-session windows, exception identifiers, and all 7,124 financial outcomes (6,261 PASS and 863 UNKNOWN). One local PDF path and redundant identifier metadata were removed. These checks do not certify full strategy correctness or a successful QuantConnect execution.

This is a frozen historical research universe, not a contemporaneously pre-registered strategy or a month-by-month latest-available universe. ETF theme selection is retrospective. Accepted timestamps and public filing status were checked; independent second-level public dissemination logs were not available. Financial evidence uses conservative availability dates. 2022 is not an out-of-sample period.

Historical security identity, ADR coverage, corporate actions, complete price coverage, and SPY/QQQ continuity still require runtime validation. Missing identity or required prices must not be silently excluded to manufacture performance results. Financial UNKNOWN exclusions are a separate explicit research rule. Any later model replay uses economic fractional-share calculations, not certified native QuantConnect fills or portfolio NAV.

Identifiers are retained for reproducible historical matching. This publication does not grant rights over third-party trademarks, identifiers or underlying source works beyond their applicable rights. It is not an official SEC, NYSE, CGS or QuantConnect dataset. No claim is made that a commercial identifier database licence has been obtained.

## Integrity

Verify `SHA256SUMS` before use. Pin a commit when retrieving this file for reproducible research. Public availability does not certify fitness for trading. QuantConnect-hosted data must remain on QuantConnect under its applicable terms; this repository is not a destination for such data.
