# Chain Lan — Finance & Market Research Portfolio

**Live site:** https://fu06pi.github.io/personal-resume-site/  
**Source:** https://github.com/fu06pi/personal-resume-site  
**Public content edition:** 2026-10-26  
**Deployment:** GitHub Pages, `main` branch root  
**Stack:** HTML5, CSS3, vanilla JavaScript (no build step, no external font or tracking requirement)

## Positioning

A finance-first public portfolio for 藍振虔 (Chain Lan), a student in the Department of Finance at Shih Chien University, Taiwan. The site highlights securities-market research, falsifiable hypotheses, risk awareness and transparent progress. It is **not** a software-engineering CV or a claim of consistent trading profit. AI-assisted technical implementation is explicitly described as supporting work, not a core personal technical advantage.

## Featured work and evidence boundaries

| Work | Website status | Evidence / limitations |
| --- | --- | --- |
| TAIEX / TX OHLC forecasting & pre-market review | Research / development | Public repo: [tw-market-scenario-engine](https://github.com/fu06pi/tw-market-scenario-engine). As of documented October research plan, TEJ authorization, training, model comparisons and acceptance gates must be verified; do not claim TimesFM or ARIMA has achieved a target. |
| MT5 / XAUUSD strategy validation | Historical research record | Public repo: [mt5-auto-trading-system](https://github.com/fu06pi/mt5-auto-trading-system). Historical June 2026 ICT/SMC baseline: 176 trades, -13.08% return, PF 0.55; failed live gate. Explicitly *not* live performance. |
| Trump policy and Taiwanese electronics-equity prices | Academic research topic | Project topic based on the owner's October 2026 materials. Full school report is not publicly posted by this site. |
| NQ / GC opening-range & market-structure research | Ongoing research | Process and research topics only (OR, VWAP, MAE/MFE). No claim of positive expectancy without supporting tested artifacts. |

## Site layout

- `#top` — finance-first hero and illustrative **non-performance** research diagram
- `#work` — four featured projects with working category filters
- `#about` — education, prior engineering study, completed general finance-ethics exam and career goals
- `#approach` — hypothesis, validation and review framework
- `#timeline` — evidence-aware research notes through October 2026
- `#contact` — owner-controlled public contact points

### Content rules

1. Do not label intended internship applications as completed employment or internships.
2. Do not present pending securities/futures/banking certifications as passed.
3. Do not claim automated trading profit, production readiness or model accuracy from plans, backtests or simulations.
4. Keep user-provided academic documents private unless separately approved for publication.
5. Do not publish credentials, keys, financial account identifiers, trading logs, account balances or local machine details.
6. Link to public source repositories and disclose AI-assisted development without overstating proficiency.
7. Date historical metrics, distinguish strategy backtests from actual accounts, and retain failed trials where relevant.

## Local preview

Open `index.html` in a browser or serve the repository root:

```bash
python3 -m http.server 8088
```

Visit http://localhost:8088/personal-resume-site/ only if the folder is mounted below the server root; when serving from the repo root directly, visit http://localhost:8088/.

## Validation checklist

- [ ] HTML parses and all internal `href="#..."` anchors exist
- [ ] CSS loads from `assets/styles.css`
- [ ] Project category filters work and update `aria-pressed`
- [ ] Mobile navigation toggles `aria-expanded`, closes after selection
- [ ] Responsive layouts at approximately 1050, 800 and 600px
- [ ] Keyboard focus visible, reduced motion respected
- [ ] No secrets, accounts, fabricated profit/accuracy, unsupported certification claims
- [ ] GitHub Pages reflects the most recent `main` revision

## Deployment and edits

GitHub Pages serves from `main` root (no bundler). Update `index.html`, `assets/styles.css`, `README.md`, and `DESIGN.md`, commit, push, and verify published HTML and CSS.

The hero plot is an **illustrative research-path SVG** rather than an OHLC market series. No live price feeds, backtest results or third-party API connections are embedded in this static site.
