---
name: hk-share-daily-market-html
description: Maintain and use the Hong Kong stock daily market statistics / HK stock technical screener HTML entry. Use when Codex is asked about 港股每日行情统计、港股技术筛选、港股行情HTML、Hong Kong stock technical screener、HK share technical screener, or to update/view/open/check this HTML page at the fixed GitHub Pages link.
---

# 港股每日行情统计 HTML

## Fixed Entry

Default to the published GitHub Pages entry first:

https://simondongxiao.github.io/hk-share-technical-screener/

When the user asks to view, open, check, or share the 港股每日行情统计 / 港股技术筛选 HTML, provide or open this URL unless they explicitly ask for a local file, source inspection, update, or deployment.

## Market Scope

Use all Hong Kong-listed equities as the screening universe, covering HKEX Main Board and GEM ordinary shares. Exclude ETFs, REITs, warrants, CBBCs, debt securities, suspended/non-tradable instruments, and duplicate share classes unless the user explicitly asks to include them.

## Source Policy

韭研公社 and 雪球 are not reliable primary sources for the Hong Kong market workflow. Prefer local data under `D:\codex` first, then use external sources when local material is missing.

Prioritize these source layers:

1. Local generated snapshots, scripts, and research archives under `D:\codex`.
2. HKEX / HKEX Data Marketplace for official security universe, Main Board/GEM listing status, instrument attributes, trading calendar, and licensed historical market data.
3. HKEXnews for issuer announcements, filings, repurchases, dividends, board-meeting notices, trading arrangements, suspensions, and regulatory publications.
4. Yahoo Finance, Stooq, Financial Modeling Prep, Finnhub, Alpha Vantage, Polygon, Tiingo, IEX Cloud, or another available market-data provider for prices, volume, sector tags, market cap, and technical history. Record provider name, query date, and any key/API limitation in the output.
5. Company IR websites, filings, broker notes already saved locally, and credible financial media for event explanations. Keep source-vs-derived attribution explicit.

## Guardrails

- Do not update, regenerate, or deploy the HTML unless the user explicitly asks to update or deploy it.
- Do not fetch market data or run daily update jobs for a view/share/check request.
- Do not invent HKEX coverage from A股-only sources. If a field cannot be sourced for 港股, mark the gap and keep the page usable.
- Do not treat this skill as a one-off run log. Keep durable instructions here; keep dated execution notes out of the skill.
- Preserve the fixed public URL above as the canonical entry unless the user explicitly changes the hosting target.

## Update Workflow

Use this workflow only after an explicit user request such as "更新这个HTML", "重新生成港股技术筛选页面", or "部署HK share technical screener".

1. Search local history and source under `D:\codex` before changing anything.
   Prioritize these terms:
   - `hk_share_technical_screener.py`
   - `hk-share-technical-screener`
   - `hong kong technical screener`
   - `港股每日行情统计`
   - `港股技术筛选`

2. Inspect the matching scripts, generated HTML, deployment files, and any README-like local notes. Prefer the existing local workflow over inventing a new generator.

3. If no HK-specific generator exists, adapt the A股 workflow conservatively:
   - Keep the same HTML structure, statistics, ranking logic, backup rules, and reporting requirements.
   - Replace only the universe loader and market-data adapters so the universe becomes all eligible Hong Kong equities.
   - Keep market-specific caveats visible for missing HK-only fields.

4. Before editing or regenerating any existing HTML/source/deployment artifact, create a timestamped backup beside the old file or in a clearly named local backup directory. Do not overwrite prior backups.

5. Make the smallest change that satisfies the request, following the discovered local project conventions.

6. After an update, verify all of the following before reporting completion:
   - The HTML opens successfully.
   - Links still point to the intended public entry: `https://simondongxiao.github.io/hk-share-technical-screener/`.
   - The displayed date or data date matches the user-requested update date, or today's date when that is what the user requested.
   - The screened universe is all eligible Hong Kong equities, not only watchlists or A/H samples.
   - Any deployment step was explicitly requested by the user and the final public URL is reachable.

## Reporting

When no update was requested, answer with the fixed GitHub Pages link and any requested local context. When an update was requested and completed, report the files changed, backup location, source coverage, data gaps, verification result, and the final URL.
