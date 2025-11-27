# Git Repository 遷移指南

## 📋 目標
將本地專案與現有 GitHub repo 斷開，並建立一個全新的 repo。

---

## 🔧 步驟 1：移除現有的 Remote 連接

已執行以下命令：
```bash
git remote remove origin
```

---

## 📝 步驟 2：建立新的 GitHub Repository

### 方法 A：透過 GitHub 網頁介面

1. 登入 GitHub (https://github.com)
2. 點擊右上角的 **+** 按鈕，選擇 **New repository**
3. 填寫以下資訊：
   - **Repository name**: 輸入新的 repo 名稱（例如：`flypig-ai-ecommerce-growth`）
   - **Description**: 可選，填寫專案描述
   - **Visibility**: 選擇 Public 或 Private
   - **不要**勾選 "Initialize this repository with a README"（因為本地已有專案）
4. 點擊 **Create repository**

### 方法 B：透過 GitHub CLI（如果已安裝）

```bash
gh repo create <新repo名稱> --public --source=. --remote=origin --push
```

---

## 🔗 步驟 3：連接新的 Remote Repository

建立新 repo 後，GitHub 會顯示連接指令。執行以下命令：

```bash
# 添加新的 remote origin
git remote add origin https://github.com/<你的使用者名稱>/<新repo名稱>.git

# 或者使用 SSH（如果已設定 SSH key）
git remote add origin git@github.com:<你的使用者名稱>/<新repo名稱>.git

# 驗證 remote 設定
git remote -v
```

---

## 📤 步驟 4：提交並推送現有變更

在推送之前，建議先提交目前的變更：

```bash
# 查看變更狀態
git status

# 添加所有變更（或選擇性添加）
git add .

# 提交變更
git commit -m "feat: 移除 Gamma API，改用 Context 管理 API Key，新增整合提示詞文件"

# 推送到新的 repo
git push -u origin main
```

**注意：** 如果新 repo 使用不同的預設分支名稱（例如 `master`），請相應調整：
```bash
git push -u origin main:main
# 或
git push -u origin main:master
```

---

## 🧹 步驟 5：清理不需要的檔案（可選）

如果不想將某些檔案推送到新 repo，可以：

1. **更新 .gitignore**
   ```bash
   # 編輯 .gitignore，添加不需要的檔案或目錄
   ```

2. **移除已追蹤的檔案**
   ```bash
   git rm --cached <檔案或目錄>
   ```

3. **常見的 .gitignore 項目**
   ```
   node_modules/
   dist/
   .env
   .env.local
   .firebase/
   *.log
   .DS_Store
   ```

---

## ✅ 驗證步驟

完成後，執行以下命令確認：

```bash
# 檢查 remote 設定
git remote -v

# 檢查分支狀態
git branch -a

# 檢查提交歷史
git log --oneline -5
```

---

## 🔄 如果遇到問題

### 問題 1：推送被拒絕
如果遇到 `rejected` 錯誤，可能是因為新 repo 有初始 commit：
```bash
git pull origin main --allow-unrelated-histories
git push -u origin main
```

### 問題 2：想要完全清除 Git 歷史
如果希望從頭開始（不保留歷史）：
```bash
# 移除現有的 .git 目錄
rm -rf .git

# 重新初始化
git init
git add .
git commit -m "Initial commit"

# 連接新的 remote
git remote add origin <新repo-url>
git push -u origin main
```

### 問題 3：想要保留歷史但更改分支名稱
```bash
# 重新命名分支
git branch -m main master  # 或 master main

# 推送新分支
git push -u origin main
```

---

## 📚 相關資源

- [GitHub 建立新 Repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository)
- [Git Remote 文件](https://git-scm.com/docs/git-remote)
- [Git Push 文件](https://git-scm.com/docs/git-push)

---

**完成後，您的本地專案就會連接到新的 GitHub repository！**

