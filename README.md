# 專案設置與團隊規範

> 我們的目標：快速上軌，任務、責任、進度一目了然。

### **1) 團隊與聯絡人**

* **團隊類別**：

  * **開發、維護組**：負責工程規範、修復、升級、CI/CD、監控。

  * **角色軸**：前端 (Next.js + Tailwind)、後端 (Supabase)、Agent (Google ADK)。

* **聯絡窗口**：

  * **泰銘**：需求確認、專案建立

  * **敦傑**：技術規範、Code Review

> **若需加入或新起專案，請先聯繫泰銘或敦傑。**

### **2) 專案流程：加入與建立**

**A. 加入現有專案**

1. 進入專案 repo 的 **Projects**，找到對應的 Board。

2. 建立或選擇一個 Issue，**指派給自己**，並將其**加入 Project**。

3. 為 Issue 加上**標籤**。

4. 在 Issue 內填寫《任務撰寫規則》中的必填欄位。

5. 將 Issue 卡片移至 `Ready` 或 `In Progress`，即可開始。

**B. 建立新專案**

1. **聯繫泰銘**：確認是否需要新專案，並提供簡短的名稱與範圍說明。

2. **建立同名 Board**：選擇 `Board` 視圖，並建立以下欄位：

   * `Inbox`：新需求

   * `Ready`：已敲定、可執行

   * `In Progress`：進行中

   * `Review`：PR 待審

   * `Done`：已完成

   * `Blocked`：卡關、需協助

   * `Icebox`：暫緩

3. **建立標籤**：

   * **類型**：`type:feat`, `type:fix`, `type:chore`, `type:docs`, `type:agent`, `type:ui`

   * **範圍**：`area:frontend`, `area:backend`, `area:agent`, `area:infra`

   * **優先**：`P0`, `P1`, `P2`, `P3`

### **3) 任務撰寫規則**

**Issue 必填欄位**：

* **背景/脈絡**：為什麼要做？來源是誰？

* **目標/輸出**：一句話說清楚要達成什麼。

* **完成定義 (DoD)**：可測試、可驗收的勾選清單。

* **子任務**：將任務拆解為多個步驟。

* **風險/依賴**：會卡住你的原因或對象。

* **參考/設計**：相關連結或截圖。

### **4) 分支與 PR 規範**

* **分支命名**：`feature/<短描述>`、`fix/<短描述>`

* **主分支**：`main`

* **PR 要求**：

  * 必須**連結 Issue** (`Closes #123`)。

  * 標籤必須**齊全**（類型、範圍、優先）。

  * 至少有 **1 位 Reviewer**。

  * **CI 必須通過**。

### **5) 專案看板運作規矩**

* **新需求**：一律先放 `Inbox`。

* **開始工作**：將卡片**指派給自己**，並移到 `In Progress`。

* **卡關**：若卡住超過 1 天，請移到 `Blocked`，並在 Issue 中標註需要協助的人。

* **待審核**：PR 發出後，將卡片移到 `Review`。

* **每週整理**：由開發維護組定期清理 `Inbox` 和 `Icebox`。

### **6) 範例任務**

**標題**：`[Task] 建置 /auth/login 頁與 Supabase OAuth 串接`
**標籤**：`type:feat`, `area:frontend`, `P1`
**內容**：

* **目標**：提供 Google OAuth 登入，成功後取得 session，並導向 `/dashboard`。

* **DoD**：

  * 支援 Google OAuth 並驗收。

  * 登入失敗時顯示錯誤提示。

  * README 已更新。

  * 至少有 1 例單元或端對端測試。

* **子任務**：

  * 新增 `/auth/login` 頁面與按鈕。

  * 串接 Supabase Auth。

  * 成功後寫入使用者資料。

  * 新增頁面保護 (middleware)。

* **風險**：需要 Supabase 專案金鑰；UI 需設計稿。

### **7) 快速訊息模板**

* **建立專案**：

  ```
  泰銘您好，我要建立新專案：
  名稱：<repo 同名>
  範圍：<一句話描述>
  請幫我確認權限與 Project Board，謝謝！
  
  ```

* **卡關協助**：

  ```
  敦傑您好，我在任務 <#issue_link> 卡住（欄位已移到 Blocked）。
  症狀：<描述>
  嘗試：<描述>
  需要：<審查/決策/資源>
  
  ```

### **8) 檔案結構建議**

```
.
├─ .github/
│  └─ ISSUE_TEMPLATE/
│     └─ task.yml
├─ docs/
│  └─ PROJECT_GUIDE.md
├─ frontend/
├─ agents/
└─ infra/

```

### **9) 每週驗收清單**

* \[ \] Project 與 Board 同名。

* \[ \] 看板上沒有超過 7 天未更新的 `In Progress` 卡片。

* \[ \] 所有進行中的 Issue 都有指派人、標籤和 DoD。

* \[ \] `Blocked` 事項已標註負責人且未超過 48 小時。

* \[ \] 所有 PR 都已連結 Issue 並通過 CI。
