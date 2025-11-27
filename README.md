# AI EC SEO Booster v1.0

**AI 智能電商SEO加速器**

一個由 AI 驅動的智能電商市場分析與 SEO 內容策略生成工具，透過 Google Gemini API 提供專業的市場洞察、競爭分析、買家人物誌描繪，並自動生成 SEO 優化的內容策略與前導頁提示詞。

---

## 📋 目錄

- [功能特色](#功能特色)
- [核心工作流程](#核心工作流程)
- [技術架構](#技術架構)
- [快速開始](#快速開始)
- [使用指南](#使用指南)
- [專案結構](#專案結構)
- [API 設定](#api-設定)
- [部署說明](#部署說明)
- [開發指南](#開發指南)
- [授權資訊](#授權資訊)

---

## ✨ 功能特色

### 🎯 三階段智能分析流程

**第一階段：深度市場分析**
- 📊 **產品核心價值提煉**：自動分析產品特色、核心優勢與解決的痛點
- 🌍 **目標市場定位**：深入剖析文化洞察、消費習慣、語言特性與搜尋趨勢
- 🏢 **競爭對手分析**：智能識別 3 個主要競爭對手，分析行銷策略與優劣勢
- 👥 **買家人物誌描繪**：建立 3 個詳細的潛在客戶畫像，包含興趣、痛點與搜尋關鍵字

**第二階段：內容與 SEO 策略**
- 📝 **內容主題建議**：生成 3 個吸引目標客群的非銷售性質內容主題
- 🔍 **專業 SEO 指導**：針對每個主題提供關鍵字密度、語意關鍵字與連結策略
- 🎨 **互動元素建議**：提出可增加使用者參與度的互動元素點子
- 📢 **行動呼籲文案**：提供多個自然且具說服力的 CTA 文案範例

**第三階段：AI Studio 提示詞生成**
- 🤖 **一鍵生成提示詞**：為 Google AI Studio 生成詳細的 React + Tailwind CSS 前導頁提示詞
- 💻 **完整程式碼規格**：包含頁面結構、設計規範、SEO 要求與內容指引

### 🔐 安全與便利性

- ✅ **API Key 本地管理**：使用 React Context API 管理，儲存在瀏覽器 localStorage
- 🔒 **安全性保證**：API Key 僅儲存在本地，不會上傳至伺服器
- 📥 **報告下載**：支援一鍵下載市場分析與內容策略報告（Markdown 格式）
- 🖼️ **圖片分析**：支援產品圖片上傳，使用 Gemini Vision API 進行視覺分析

---

## 🔄 核心工作流程

```
輸入產品資訊
    ↓
[第一階段] 市場分析
    ├─ 產品核心價值分析
    ├─ 目標市場定位
    ├─ 競爭對手分析
    └─ 買家人物誌描繪
    ↓
[第二階段] 內容策略生成
    ├─ 內容主題建議（3個）
    ├─ SEO 指導方針
    ├─ 互動元素建議
    └─ CTA 文案建議
    ↓
[第三階段] 提示詞生成
    └─ AI Studio 前導頁提示詞
    ↓
下載報告 / 複製提示詞
```

---

## 🛠️ 技術架構

### 前端技術棧

| 技術 | 版本 | 用途 |
|------|------|------|
| **React** | ^19.1.1 | UI 框架 |
| **TypeScript** | ~5.8.2 | 型別安全 |
| **Tailwind CSS** | CDN | 樣式框架 |
| **Vite** | ^6.2.0 | 建置工具 |
| **@google/genai** | ^1.19.0 | Gemini API 客戶端 |

### 核心架構設計

```
src/
├── contexts/
│   └── ApiKeyContext.tsx      # API Key 狀態管理
├── components/
│   └── ApiKeyModal.tsx        # API Key 設定彈窗
├── services/
│   └── geminiService.ts       # Gemini API 服務層
├── types.ts                   # TypeScript 型別定義
├── App.tsx                    # 主應用元件
└── index.tsx                  # 應用入口
```

### 設計模式

- **Context API**：全域狀態管理（API Key）
- **服務層模式**：API 呼叫封裝
- **元件化設計**：可重用的 UI 元件
- **型別安全**：完整的 TypeScript 型別定義

---

## 🚀 快速開始

### 前置需求

- Node.js 18+ 
- npm 或 yarn
- Google Gemini API Key（[免費申請](https://aistudio.google.com/app/apikey)）

### 安裝步驟

1. **複製專案**
   ```bash
   git clone https://github.com/mkhsu2002/AI-EC-SEO-Booster.git
   cd AI-EC-SEO-Booster
   ```

2. **安裝依賴**
   ```bash
   npm install
   ```

3. **啟動開發伺服器**
   ```bash
   npm run dev
   ```

4. **開啟瀏覽器**
   - 訪問 `http://localhost:3000`
   - 首次使用會提示設定 Gemini API Key
   - 輸入您的 API Key 即可開始使用

### 建置生產版本

```bash
npm run build
```

建置產出位於 `dist/` 目錄。

---

## 📖 使用指南

### 第一步：設定 API Key

1. 點擊右上角「API Key 設定」按鈕
2. 輸入您的 Google Gemini API Key
3. API Key 會自動儲存在瀏覽器中
4. 點擊「開始使用」完成設定

> 💡 **提示**：如果還沒有 API Key，可以點擊「還沒有 Key? 點此免費獲取」連結前往申請。

### 第二步：輸入產品資訊

在表單中填寫以下資訊：

- **產品名稱**（必填）：例如「人體工學辦公椅」
- **產品描述**（必填）：詳細的產品資訊、規格與主要賣點
- **目標市場**（必填）：例如「台灣」、「美國加州」或「日本東京」
- **產品連結網址**（選填）：產品頁面 URL
- **產品圖片**（選填）：上傳產品圖片，支援拖曳上傳

### 第三步：生成市場分析

1. 點擊「生成市場分析報告」按鈕
2. 等待 AI 分析（約 30-60 秒）
3. 查看完整的市場分析報告
4. 可點擊「下載報告」保存為 Markdown 檔案

### 第四步：生成內容策略

1. 在分析報告下方點擊「第二步：生成內容策略」
2. 等待策略生成（約 20-40 秒）
3. 查看內容主題、SEO 指導與互動元素建議
4. 可點擊「下載策略」保存報告

### 第五步：生成前導頁提示詞

1. 從三個內容主題中選擇一個
2. 點擊「生成 AI Studio 提示詞」
3. 在彈窗中查看完整的提示詞
4. 點擊「複製提示詞」複製到剪貼簿
5. 將提示詞貼到 Google AI Studio 或其他 AI 程式碼助理中使用

---

## 📁 專案結構

```
AI-EC-SEO-Booster/
├── src/
│   ├── contexts/
│   │   └── ApiKeyContext.tsx          # API Key Context 管理
│   ├── components/
│   │   └── ApiKeyModal.tsx            # API Key 設定 Modal
│   ├── services/
│   │   ├── geminiService.ts           # Gemini API 服務
│   │   └── gammaService.ts            # Gamma API 服務（已移除）
│   ├── types.ts                       # TypeScript 型別定義
│   ├── App.tsx                        # 主應用元件
│   └── index.tsx                      # 應用入口
├── public/
│   ├── _headers                       # Cloudflare Pages headers
│   └── _redirects                     # SPA 路由重定向
├── dist/                              # 建置輸出目錄
├── index.html                         # HTML 入口檔案
├── vite.config.ts                     # Vite 配置
├── tsconfig.json                      # TypeScript 配置
├── package.json                       # 專案依賴
└── README.md                          # 本文件
```

---

## 🔑 API 設定

### Google Gemini API

本專案使用 Google Gemini API 進行 AI 分析。API Key 管理方式：

- **儲存位置**：瀏覽器 localStorage
- **安全性**：API Key 僅儲存在本地，不會上傳至任何伺服器
- **設定方式**：透過 UI 介面設定，首次使用會自動提示

### 取得 API Key

1. 前往 [Google AI Studio](https://aistudio.google.com/app/apikey)
2. 登入您的 Google 帳號
3. 點擊「Create API Key」
4. 複製生成的 API Key
5. 在應用程式中貼上並儲存

### API 使用限制

- 免費方案有使用限制，請參考 [Google Gemini API 定價](https://ai.google.dev/pricing)
- 建議監控 API 使用量以避免超額費用

---

## 🚢 部署指南

### 本地部署

#### 前置需求

- Node.js 18+ 
- npm 或 yarn

#### 部署步驟

1. **複製專案**
   ```bash
   git clone https://github.com/mkhsu2002/AI-EC-SEO-Booster.git
   cd AI-EC-SEO-Booster
   ```

2. **安裝依賴**
   ```bash
   npm install
   ```

3. **建置專案**
   ```bash
   npm run build
   ```

4. **預覽建置結果**
   ```bash
   npm run preview
   ```

5. **部署到本地伺服器**
   - 建置產出位於 `dist/` 目錄
   - 可使用任何靜態檔案伺服器部署
   - 例如：使用 `npx serve dist` 或 `python -m http.server` 在 dist 目錄

---

### GitHub Pages 部署

#### 步驟 1: 設定 GitHub Actions

1. 在專案根目錄建立 `.github/workflows/` 資料夾
2. 建立 `deploy.yml` 檔案，內容如下：

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Set up Node
        uses: actions/setup-node@v4
        with:
          node-version: 20
      - name: Install dependencies
        run: npm install
      - name: Build
        env:
          GITHUB_PAGES: 'true'
        run: npm run build
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: ./dist

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    needs: build
    runs-on: ubuntu-latest
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

#### 步驟 2: 開啟 GitHub Pages

1. 進入 GitHub 儲存庫的 **Settings** > **Pages**
2. 在 **Build and deployment** > **Source** 中選擇 **GitHub Actions**
3. 推送程式碼後，GitHub Actions 會自動建置並部署
4. 部署完成後，網站會顯示在 `https://<username>.github.io/AI-EC-SEO-Booster/`

#### 步驟 3: 設定 Base Path（如需要）

如果部署在子路徑下，需要在 `vite.config.ts` 中設定：

```typescript
export default defineConfig({
  base: '/AI-EC-SEO-Booster/', // 替換為您的儲存庫名稱
  // ... 其他設定
})
```

---

### Cloudflare Pages 部署

#### 步驟 1: 連接 GitHub Repository

1. 登入 [Cloudflare Dashboard](https://dash.cloudflare.com/)
2. 前往 **Workers & Pages** > **Create application** > **Pages** > **Connect to Git**
3. 選擇您的 GitHub 帳號並授權
4. 選擇 `AI-EC-SEO-Booster` 儲存庫

#### 步驟 2: 設定建置配置

**⚠️ 重要：** 請確認建置命令設定正確！

在 Cloudflare Pages 設定中配置：

- **Project name**: `AI-EC-SEO-Booster`（或自訂名稱）
- **Production branch**: `main`
- **Build command**: `npm run build` ⚠️ **請確認是 `build` 而不是 `dev`**
- **Build output directory**: `dist`
- **Root directory**: `/`（預設）
- **Node.js version**: 20（建議）

**常見錯誤：**
- ❌ 錯誤：`npm run dev`（這會啟動開發伺服器，導致部署卡住）
- ✅ 正確：`npm run build`（這會建置生產版本）

#### 步驟 3: 環境變數（可選）

本專案使用 Context API 管理 API Key，無需設定環境變數。如需設定其他環境變數：

1. 進入專案設定 > **Environment variables**
2. 新增所需的環境變數
3. 例如：`NODE_VERSION: 20`

#### 步驟 4: 部署

1. 點擊 **Save and Deploy**
2. Cloudflare 會自動開始建置和部署
3. 部署完成後，您會獲得一個 `*.pages.dev` 的網址
4. 可在 **Custom domains** 中設定自訂網域

#### 步驟 5: 自動部署

之後每次推送到 `main` 分支，Cloudflare Pages 會自動重新建置和部署。

#### 注意事項

- 確保 `wrangler.toml` 配置正確（如使用 Cloudflare Workers）
- 檢查 `public/_headers` 和 `public/_redirects` 檔案是否正確複製到 `dist/`
- 詳細說明請參考 `CLOUDFLARE_PAGES.md`

---

## 📊 功能詳細說明

### 市場分析功能

**產品核心價值分析**
- 自動提取產品的主要特色
- 識別核心競爭優勢
- 分析產品解決的用戶痛點

**目標市場定位**
- 文化洞察分析
- 消費習慣研究
- 語言特性識別
- 搜尋趨勢分析

**競爭對手分析**
- 自動識別主要競爭對手（3個）
- 分析行銷策略
- 評估優勢與劣勢

**買家人物誌**
- 建立 3 個詳細的買家畫像
- 包含基本資料、興趣、痛點
- 提供搜尋關鍵字建議

### 內容策略功能

**內容主題生成**
- 3 個非銷售性質內容主題
- 每個主題包含標題、描述
- 主要關鍵字與長尾關鍵字
- 完整的 SEO 指導方針

**SEO 指導**
- 關鍵字密度建議
- 語意關鍵字列表
- 內部連結策略
- 外部連結策略

**互動元素建議**
- 2-3 個互動元素點子
- 詳細的實作描述

**CTA 文案**
- 3 個自然且具說服力的行動呼籲文案

### AI Studio 提示詞生成

生成的提示詞包含：

- **產品資訊**：名稱、描述、目標市場
- **目標受眾**：買家人物誌詳細資訊
- **關鍵訊息**：產品特色、優勢、痛點解決方案
- **SEO 要求**：關鍵字、長尾關鍵字、語意關鍵字
- **頁面結構**：Header、Hero、痛點、解決方案、見證、CTA
- **設計規範**：色彩、字體、動畫效果
- **技術規格**：React、Tailwind CSS、響應式設計

---

## 🐛 常見問題

### Q: API Key 安全嗎？

A: 是的，API Key 僅儲存在您的瀏覽器 localStorage 中，不會上傳至任何伺服器。您可以隨時清除或更換 API Key。

### Q: 支援哪些圖片格式？

A: 支援常見的圖片格式：PNG、JPG、JPEG、GIF、WebP。

### Q: 分析報告可以匯出嗎？

A: 可以，市場分析報告和內容策略都可以下載為 Markdown 格式檔案。

### Q: 生成的提示詞可以在哪些平台使用？

A: 生成的 AI Studio 提示詞適用於 Google AI Studio、Claude、ChatGPT 等支援程式碼生成的 AI 工具。

### Q: 需要網路連線嗎？

A: 是的，本應用程式需要網路連線以呼叫 Google Gemini API。

---

## 📝 更新日誌

### v1.0.0 (2025-01)

- ✨ 初始版本發布
- 🎯 三階段智能分析流程
- 🔐 API Key Context 管理機制
- 📊 完整的市場分析功能
- 📝 內容策略生成功能
- 🤖 AI Studio 提示詞生成
- 📥 Markdown 報告下載功能
- 🖼️ 產品圖片分析支援

---


## 📄 授權資訊

本專案採用 MIT 授權條款。

---

## 🔗 相關連結

- [Google Gemini API 文件](https://ai.google.dev/docs)
- [React 官方文件](https://react.dev/)
- [Tailwind CSS 文件](https://tailwindcss.com/docs)
- [Vite 文件](https://vitejs.dev/)

---

## 👏 致謝

- [Google Gemini](https://ai.google.dev/) - 提供強大的 AI 分析能力
- [React](https://react.dev/) - 優秀的 UI 框架
- [Tailwind CSS](https://tailwindcss.com/) - 實用的 CSS 框架
- [Vite](https://vitejs.dev/) - 快速的建置工具

---

## 💬 技術支援與討論

如有任何問題、建議或需要技術支援，歡迎[加入 FlyPig 專屬 LINE 群組](https://line.me/R/ti/g/@icareuec)。

我們會在這裡提供：

- 技術支援與問題解答
- 功能更新與使用教學
- 社群討論與經驗分享
- 最新功能預覽與測試

---

## 🔗 推薦同步參考

如果您對 AI 電商行銷工具感興趣，歡迎同步參考以下相關專案：

- **[AI-PM-Designer-Pro](https://github.com/mkhsu2002/AI-PM-Designer-Pro)** - AI 電商商品圖文生成工具，從產品圖自動生成完整行銷素材包
- **[AI_Digital_Portrait_Studio](https://github.com/mkhsu2002/AI_Digital_Portrait_Studio)** - 專為電商設計 AI 人像圖片生成工具

---

## ☕ 請我喝杯咖啡

如果這個專案對您有幫助，歡迎[請我喝杯咖啡](https://buymeacoffee.com/mkhsu2002w)，您的支持是我持續開發的動力！

---

## 👉 商業部署及客製需求

若需協助委外部署或客製化選項開發（例如新增場景、人物姿態），歡迎聯絡 FlyPig AI：

- **Email**: flypig@icareu.tw
- **LINE ID**: icareuec

---

## 📄 License

**MIT License**

Open sourced by [FlyPig AI](https://flypigai.icareu.tw/)

Copyright (c) 2025 AI EC SEO Booster

---

<div align="center">

**⭐ 如果這個專案對您有幫助，請給我們一個 Star！**

Made with ❤️ by FlyPig AI

</div>

