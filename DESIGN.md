# Chain Lan Portfolio — Visual Design System

**Edition:** 2026-10-26  
**Brand context:** Finance student, securities-market research, risk-conscious thinking, transparent projects.

## Design direction

Editorial financial research, not a fintech sales landing page and not a developer terminal. Calm cream paper surfaces contrast with a deep blue-ink research hero. Restrained pale-lime highlights, technical micro-labels, generous whitespace, understated 1px borders and clear Chinese type hierarchy. Avoid decorative data dashboards that imply real performance.

## Foundation

- Ink: `#12222a`; deep hero navy: `#101d26`; secondary dark: `#1b3038`
- Cream: `#f5f5f0`; white paper: `#fffefa`; soft green panel: `#e8eddf`
- Accent: pale lime `#d5f28a` on navy; muted green `#63816d` on paper
- Rules / borders: `#d7ddd7`
- Main font: system UI sans stack with Noto Sans TC / PingFang TC fallback; micro-labels: system monospace
- Geometry: mostly square corners, sparse lines, small capsule states only
- Sections: Hero → Research focus → Featured work → Background → Method → Timeline → Contact
- Imagery: custom decorative SVG research pathway only, labeled non-market-data

## Layout, interaction and access

- Max page content width: 1180px; responsive container gutters 64px / 40px / 32px.
- Responsive breakpoints: 1050px, 800px and 600px; single-column mobile.
- Mobile nav: button with `aria-controls`, `aria-expanded`, touch-friendly target and link-triggered close.
- Projects: semantic `article` cards; `data-category` filter uses button `aria-pressed` and the native `hidden` attribute.
- Keyboard: skip link, visible focus rings; prefers-reduced-motion disables smooth scroll/transitions.
- External links use `target="_blank"` with `rel="noopener noreferrer"`.
- No external third-party font, chart dependency or tracking package.

## Editorial rules

Focus on rigorous curiosity and evidence, not seniority claims. Distinguish projects that are planned, running, historically verified, or failing. Never present diagram decoration as price charts or a model forecast. Link primary public source repos where possible. Do not embed the user's private uploaded coursework, accounts, API keys, or any live trading secrets.
