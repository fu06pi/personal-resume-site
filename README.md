# Chain Personal Resume Site

靜態個人履歷網站，可直接用瀏覽器打開 `index.html`，也可部署到 GitHub Pages / Cloudflare Pages / Netlify。

## 本地預覽

```bash
cd /home/chain4655/Documents/Projects/personal-resume-site
python3 -m http.server 8088
```

然後打開：

```text
http://127.0.0.1:8088
```

## 需要替換的內容

- `index.html` 裡的 `your-email@example.com`
- Telegram / X 公開帳號
- 若要正式投遞履歷，可補上：
  - 真實姓名 / 英文名
  - 學歷
  - 工作經驗
  - 具體專案連結
  - GitHub repo links
  - 聯絡方式

## 部署 GitHub Pages

```bash
git init
git add .
git commit -m "Initial personal resume site"
gh repo create personal-resume-site --public --source=. --remote=origin --push
gh api -X POST /repos/fu06pi/personal-resume-site/pages -f source='{"branch":"main","path":"/"}'
```
