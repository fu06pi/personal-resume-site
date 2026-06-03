# Chain Personal Resume Site

靜態個人履歷 / 作品集網站，用來公開整理 AI 輔助量化研究、MT5 自動交易、回測流程與研究系統工程成果。

- **Live site:** https://fu06pi.github.io/personal-resume-site/
- **Repository:** https://github.com/fu06pi/personal-resume-site
- **目前內容版本:** 2026-06-03
- **技術棧:** HTML, CSS, vanilla JavaScript, GitHub Pages

## 專案定位

這個網站是公開版履歷與專案敘事頁，重點不是展示單一策略績效，而是說明如何把交易想法轉成可驗證、可迭代、可自動化的研究與執行系統。

目前內容聚焦於：

- AI-assisted trading research
- MT5 / Python 策略開發
- XAUUSD 策略營運與風控流程
- TradingView Pine 策略轉譯
- 社群 / 市場情報研究管線
- 可公開的 GitHub 技術成果；不公開 runtime secrets 或私人帳號細節

## 網站結構

主檔案：`index.html`

主要區塊：

- `#top` — hero statement 與角色摘要
- `#about` — 目前研究方向與操作哲學
- `#projects` — MT5、策略情報、OKX、歷史資料研究等代表專案
- `#quant-progress` — 最新量化系統進度，更新至 2026-06-03
- `#mt5-architecture` — MT5 策略 / 程式碼架構與開發時間線
- `#weekly-log` — 週度研究與營運紀錄
- `#skills` — 技術技能標籤
- `#contact` — 公開聯絡方式

輔助檔案：

- `assets/styles.css` — 視覺系統與 responsive layout
- `DESIGN.md` — dark developer-focused 設計語言參考
- `.nojekyll` — 避免 GitHub Pages 套用 Jekyll 處理

## 目前公開敘事重點

### Quant Progress

最新版網站文案彙整近期 MT5 / XAUUSD 工作：

- FTMO demo 監控與防守型風控狀態
- 趨勢 sleeve 在回撤後暫停
- 低風險 SELL-only false-breakout complement sleeve 觀測
- Momentum Surfer V2 週級回測清理
- 策略組合偏好 parallel independent sleeves，而不是 simple overlay
- 部署原則維持 backtest-first / paper-first

### MT5 Architecture

網站已把交易系統架構整理成四層：

1. **Runtime Core** — live strategy、supervisor、active plan、MT5 bridge
2. **State / Logs** — account snapshots、strategy status、drawdown、runtime telemetry
3. **Research Layer** — backtests、spikes、parameter sweeps、portfolio experiments
4. **Quality Gates** — compile checks、unit tests、secret hygiene、rollback discipline

### 開發時間線

公開時間線說明系統從早期 MQL5 EA 實驗，逐步轉成 Python-led MT5 research / live-ops framework：

- 2026-04 — 早期 MT5 / MQL5 策略實驗
- 2026-05 — Python framework、supervisor、prop-challenge 進展
- 2026-06 — 低風險 live-ops、complement sleeve 研究、公開文件整理

## 本地預覽

```bash
cd /home/chain4655/Documents/Projects/personal-resume-site
python3 -m http.server 8088
```

打開：

```text
http://127.0.0.1:8088
```

## 驗證方式

基本 HTML parse check：

```bash
python3 - <<'PY'
from html.parser import HTMLParser
from pathlib import Path

class Parser(HTMLParser):
    pass

Parser().feed(Path('index.html').read_text(encoding='utf-8'))
print('HTML parse OK')
PY
```

確認重要公開文案存在：

```bash
python3 - <<'PY'
from pathlib import Path
html = Path('index.html').read_text(encoding='utf-8')
required = [
    'Quant Progress · Updated 2026-06-03',
    'MT5 Strategy & Code Architecture',
    'prop_portfolio_complement_fb_sell_only',
    'Parallel independent sleeves',
]
missing = [item for item in required if item not in html]
if missing:
    raise SystemExit(f'Missing expected copy: {missing}')
print('Content check OK')
PY
```

## 部署

目前 GitHub Pages 從 `main` branch root 部署。

```bash
git status --short
git add index.html assets/styles.css README.md DESIGN.md .nojekyll
git commit -m "docs: update resume site content"
git push origin main
```

查 GitHub Pages 狀態：

```bash
gh api repos/fu06pi/personal-resume-site/pages --jq '{status:.status,url:.html_url,source:.source}'
```

查線上頁面是否已更新：

```bash
curl -L https://fu06pi.github.io/personal-resume-site/ | grep -E "Quant Progress|MT5 Strategy"
```

## 公開安全注意事項

這是 public repository。不要提交：

- MT5 帳號、broker login 或 server 私密資訊
- API keys、tokens、passwords、`.env`
- runtime logs、state snapshots、order records、account exports
- 含敏感 equity / account identifier 的私人報告
- 會暴露帳號 ID、餘額、server name 或私人對話的截圖

公開文案應聚焦在系統架構、研究流程與工程成果；避免放入 live account identifier 或操作憑證。

## 內容更新 Checklist

推送前確認：

- [ ] `index.html` 已反映最新公開敘事
- [ ] 私人帳號 ID 與 credentials 已移除或 redacted
- [ ] 已執行 HTML parse check
- [ ] 已用 `git diff` 檢查沒有 accidental secret / runtime state exposure
- [ ] commit message 使用 documentation-focused wording
- [ ] push 到 `origin/main`
- [ ] GitHub Pages 已重建，live site 含新版文案
