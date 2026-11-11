<div align="center">

# 張人文 Zhang RenWen

**軟體工程師**

[GLRR 風險雷達](#global-liquidity--risk-radar-glrr) · [簡繁轉換器](#簡繁轉換器與兩岸用語詞彙庫) · [前端筆記](#modern-web-dev-notes)

</div>

---

### 關於我

商管背景出身，畢業後轉職成為軟體工程師。喜歡把複雜的資訊整理成清楚好用的介面。

### 精選專案

#### [Global Liquidity & Risk Radar (GLRR)](https://github.com/Zhang-RenWen/glrr-demo)

全球資金水位與風險雷達，一套監控全球資金與市場風險的系統。

- 將主專案的資料與畫面發佈成唯讀靜態 Demo，不連後端、不需登入
- 依資料授權範圍處理顯示內容，受限資料以遮罩呈現，並在頁尾標示來源
- 透過 GitHub Actions 自動發佈到 GitHub Pages

[線上 Demo](https://zhang-renwen.github.io/glrr-demo/) · [原始碼](https://github.com/Zhang-RenWen/glrr-demo)

#### [簡繁轉換器與兩岸用語詞彙庫](https://github.com/Zhang-RenWen/cn-tw-terms)

不只轉換字形，也標示兩岸用語差異的開源工具。

- 以純 HTML 與 JavaScript 實作，使用 OpenCC 在瀏覽器內完成轉換，不需後端或資料庫
- 區分一般用語、評價意涵、同字異義三種類型，分別替換或提醒
- 詞彙以 JSON 管理，任何人都能發 Pull Request 擴充，並由 GitHub Actions 自動檢查

[線上使用](https://zhang-renwen.github.io/cn-tw-terms/) · [原始碼](https://github.com/Zhang-RenWen/cn-tw-terms) · [貢獻詞彙](https://github.com/Zhang-RenWen/cn-tw-terms/blob/main/CONTRIBUTING.md)

#### [Modern WEB Dev Notes](https://github.com/Zhang-RenWen/modern-web-dev-notes)

我的前端知識庫，涵蓋前端工程通用知識，以及 ES6 到 ES2026 的新語法，並盡量附上實際驗證過的範例。

- 以 VitePress 建置，支援本地全文搜尋與數學式
- 透過 GitHub Actions 自動部署

[線上閱讀](https://zhang-renwen.github.io/modern-web-dev-notes/) · [原始碼](https://github.com/Zhang-RenWen/modern-web-dev-notes)

### 技術

| 領域 | 使用過的技術 |
| --- | --- |
| **前端** | JavaScript、TypeScript、Vue 2/3、Nuxt、React、Vite、Tailwind CSS、Vuetify、D3.js |
| **後端** | Java Spring Boot（RESTful API、Transaction、RBAC）/ Flyway Migration / C# ASP.NET / Keycloak / OIDC / JWT |
| **資料庫** | PostgreSQL |
| **測試與品質** |Vitest / Vue Test Utils / JUnit + Testcontainers（真實 PostgreSQL 整合測試）/ pytest / TypeScript 型別檢查 / ESLint / Prettier / Ruff；CI 依 app 路徑自動觸發（GLRR：Vitest 227、JUnit 228、pytest 292 個測試） |
| **雲端與工程化** | AWS（ECS Fargate、ECR、RDS、S3、CloudFront、EventBridge）/ Docker / GitHub Actions CI/CD / Cloudflare DNS / Monorepo  |
| **金融領域** | 保戶服務、理賠、新契約、KYC 流程實務；交易冪等、批次對帳、異動稽核等金融系統設計觀念；總經流動性 與信用風險指標|
