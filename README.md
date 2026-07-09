# 家庭庫存與價格管理系統

單一 `index.html` 的純前端網站，零外部相依、免建置、免伺服器。
資料目前存在**瀏覽器本機 (localStorage)**：同一台裝置同一個瀏覽器才看得到，不會跨裝置同步。

---

## 佈署方式（擇一，都是免費、幾分鐘完成）

### 方式 A：Netlify Drop（最快，免帳號拖曳）
1. 開 https://app.netlify.com/drop
2. 把整個 `inventory-app` 資料夾拖進去
3. 幾秒後就給你一個 `https://xxxx.netlify.app` 網址，完成

### 方式 B：Cloudflare Pages
1. 登入 Cloudflare → Pages → Create → Upload assets
2. 上傳 `index.html`（或整個資料夾）
3. 取得 `https://xxxx.pages.dev` 網址

### 方式 C：Vercel
1. 登入 Vercel → Add New → Project
2. 拖曳資料夾或連 GitHub repo
3. 無需任何設定（Framework 選 Other），直接 Deploy

### 方式 D：GitHub Pages
1. 建一個 repo，把 `index.html` 放進去
2. Settings → Pages → Source 選 `main` 分支根目錄
3. 網址為 `https://<帳號>.github.io/<repo>/`

> 任一方式都不需要修改程式碼，因為整站就是一個 `index.html`。

---

## 重要限制：資料不會跨裝置同步

因為資料存瀏覽器本機：
- 手機新增的商品，電腦不會出現（反之亦然）
- 清除瀏覽器資料 / 換瀏覽器 = 資料不見
- 適合「只用一台裝置」的情境

### 要真正多裝置同步 → 需要接後端（Supabase）
程式的資料層已集中在 `DB` / `load()` / `save()`，之後改成讀寫 Supabase 即可，
畫面不用重做。屆時可加上：Email／Google 登入、雲端儲存、多裝置即時同步、家庭共用。

---

## 手機使用小技巧
佈署後在手機瀏覽器打開網址 →「加入主畫面」，即可像 App 一樣從桌面開啟。

## 本機開發／預覽
直接用瀏覽器打開 `index.html` 即可，或用任意靜態伺服器：
```
npx serve .
```
