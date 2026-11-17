# 玄樞八字｜AI 命理排盤 PWA

結合 **子平八字確定性曆法引擎（`lunar-javascript`）** 與 **Google Gemini AI** 的行動優先漸進式網頁應用程式（PWA）。

## 專案目錄結構

```text
xuanshu-bazi-pwa/
├── package.json          # 專案依賴與 Render 啟動腳本
├── server.js             # Express 後端：精準八字排盤引擎 ＋ Gemini API 安全轉發
├── .gitignore            # Git 忽略清單
├── .env.example          # 環境變數範本
├── README.md             # 部署與使用說明
└── public/
    ├── index.html        # 手機優先新中式響應式介面
    ├── manifest.json     # PWA 安裝設定檔
    ├── sw.js             # Service Worker 離線快取策略
    └── icons/            # PWA 多尺寸圖示
        ├── icon-192.png
        ├── icon-512.png
        ├── maskable-512.png
        └── apple-touch-icon.png
```

## 快速部署至 GitHub 與 Render（免費方案）

1. **上傳至 GitHub**：
   - 在 GitHub 建立新儲存庫 `xuanshu-bazi-pwa`。
   - 將本資料夾內的所有檔案（確保 `package.json` 位於儲存庫第一層）上傳並 Commit。
2. **架設至 Render**：
   - 登入 Render → **New +** → **Web Service** → 連結 `xuanshu-bazi-pwa`。
   - **Runtime**：`Node`
   - **Build Command**：`npm install`
   - **Start Command**：`npm start`
   - **Instance Type**：`Free`
   - **Environment Variables**：
     - `GEMINI_API_KEY`：填入 Google AI Studio 免費版 API Key（若未填寫，使用者亦可直接在網頁「金鑰與紀錄」分頁暫存自己的免費金鑰）。
     - `GEMINI_MODEL`：`gemini-2.5-flash`
3. **手機安裝 PWA**：
   - **iOS Safari**：開啟部署後的 `https://*.onrender.com` 網址 → 點擊底部「分享」→「加入主畫面」。
   - **Android Chrome**：開啟網址 → 點擊頂部「＋ 安裝 App」或右上角選單「安裝應用程式」。
