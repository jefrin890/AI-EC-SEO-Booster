# Cloudflare Pages 部署配置

## ⚠️ 重要：必須設置構建命令

從部署日誌可以看到 `No build command specified. Skipping build step.`，這表示 Cloudflare Pages **沒有執行構建**，因此部署的是源文件而不是構建後的文件。

## 構建設置步驟

**必須在 Cloudflare Dashboard 中手動設置：**

1. 登入 Cloudflare Dashboard
2. 進入您的 Pages 專案
3. 點擊 **Settings** → **Builds & deployments**
4. 在 **Build configuration** 中設置：
   - **Build command**: `npm run build`
   - **Build output directory**: `dist`
   - **Root directory**: (留空或設置為 `/`)
   - **Node.js version**: 18 或更高

## 構建設置詳情

- **構建命令**: `npm run build`
- **構建輸出目錄**: `dist`
- **Node.js 版本**: 18 或更高

## 重要文件

- `public/_headers` - 設置正確的 MIME types（已自動複製到 `dist/_headers`）
- `public/_redirects` - SPA 路由重定向（已自動複製到 `dist/_redirects`）

## 驗證部署

部署後，請確認：

1. `dist/_headers` 文件存在於構建輸出中
2. `dist/index.html` 引用的是 `/assets/main-*.js` 而不是 `/index.tsx`
3. 所有 JavaScript 文件都有正確的 `Content-Type: application/javascript` header

## 故障排除

如果仍然遇到 MIME type 錯誤：

1. 確認 Cloudflare Pages 使用的是構建後的 `dist` 目錄，而不是源文件
2. 檢查 `dist/_headers` 文件是否正確包含所有規則
3. 在 Cloudflare Dashboard 中檢查 Transform Rules 設置

