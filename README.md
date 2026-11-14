<div align="center">

# 張人文 Zhang RenWen

**Front-end Engineer｜前端工程師**

[GLRR](https://zhang-renwen.github.io/glrr-demo/) · [CN–TW Terms Converter](https://zhang-renwen.github.io/cn-tw-terms/) · [Modern WEB Dev Notes](https://zhang-renwen.github.io/modern-web-dev-notes/) · [CS & Network Roadmap](https://zhang-renwen.github.io/cs-network-roadmap/)

</div>

---

### About me｜關於我

I studied business administration and moved into software engineering after graduating. I have worked as a front-end engineer since 2018, most recently on life-insurance systems (policyholder services, claims, new business and KYC). My personal projects extend that into full-stack work: data pipelines, APIs, authentication and deployment. I like turning complex information into interfaces that are clear and easy to use.

商管背景出身，畢業後轉職成為軟體工程師。2018 年起擔任前端工程師，最近幾年參與壽險系統開發（保戶服務、理賠、新契約、KYC）。個人專案則從前端延伸到全端：資料管線、API、身分驗證與部署。喜歡把複雜的資訊整理成清楚好用的介面。

---

### Featured projects｜精選專案

#### [Global Liquidity Risk Radar (GLRR)｜全球資金水位與風險雷達系統](https://github.com/Zhang-RenWen/glrr-demo)

A full-stack system that monitors global liquidity, credit stress and Taiwan equities.

- A Python ETL gathers about 140 indicators from nine sources, including FRED, BIS, World Bank, CFTC and EIA, and keeps point-in-time history so backtests only use data that was available at the time
- A Spring Boot API on PostgreSQL, with Keycloak OIDC (Authorization Code + PKCE, TOTP) and RBAC, serves a React member app and a Vue admin console in three languages
- Measured partitioning on 364k rows and moved back to a plain table (107 ms → 11 ms); merged the indicator overview from 73 requests into 1
- Deployed to AWS (ECS Fargate, CloudFront, RDS) with CloudFormation under its own domain, then moved off AWS after a cost review (USD 60–75 → about USD 5 a month) to a one-command local Docker setup
- This repo hosts a read-only demo (data as of 2026-11-02); licensed series and trading signals are masked
- Built with AI assistance; I owned the requirements, architecture trade-offs, acceptance and incident handling

追蹤全球資金流動性、信用市場與台股的風險監控系統。

- Python ETL 從 FRED、BIS、World Bank、CFTC、EIA 等 9 個來源整合約 140 支指標，保留 point-in-time 歷史版本，讓回測只用當時可取得的資料
- Spring Boot API 搭配 PostgreSQL，以 Keycloak OIDC（Authorization Code＋PKCE、TOTP）與 RBAC 控管權限，提供繁中、英、日三語系的 React 會員前台與 Vue 後台
- 36 萬筆資料實測後把 Partition 改回一般資料表（107 ms → 11 ms）；指標總覽從 73 個請求合併為 1 個
- 以 CloudFormation 部署至 AWS（ECS Fargate、CloudFront、RDS）並以正式網域上線，評估成本後下雲（月費 USD 60～75 → 約 USD 5），改為本機 Docker 一鍵啟動
- 此 repo 是唯讀 Demo（資料截至 2026-11-02），授權受限資料與交易訊號已遮罩
- AI 協作開發；我負責需求、架構取捨、驗收與事故判斷

[Live demo 線上 Demo](https://zhang-renwen.github.io/glrr-demo/) · [Source 原始碼](https://github.com/Zhang-RenWen/glrr-demo)

#### [CN–TW Terms Converter｜兩岸用語對照・簡繁轉換器](https://github.com/Zhang-RenWen/cn-tw-terms)

Converts Simplified to Traditional Chinese and flags Mainland Chinese terms with their Taiwan equivalents.

- Character conversion uses OpenCC (opencc-js) and runs entirely in the browser, so no text is uploaded; plain HTML, CSS and JavaScript, with no framework or backend
- An 867-term glossary in 17 categories: everyday terms are replaced (充電寶 → 行動電源), evaluative terms are flagged with a note (顏值, 內卷, 社畜), and false friends are flagged only (窩心, 愛人, 研究所)
- Every term gets a static SEO page at deploy time, with a sitemap and JSON-LD structured data
- The glossary is open JSON; GitHub Actions validates every pull request and deploys merged changes to GitHub Pages

簡體轉繁體，同時把中國用語標示或轉成台灣用語。

- 字形轉換使用 OpenCC（opencc-js），全部在瀏覽器內完成、不上傳文字；純 HTML、CSS、JavaScript，沒有框架或後端
- 17 類、867 詞的詞彙庫：一般用語直接替換（充電寶 → 行動電源）、評價意涵只標示並附說明（顏值、內卷、社畜）、同字異義只標示提醒（窩心、愛人、研究所）
- 部署時替每個詞產生靜態 SEO 頁，加上 sitemap 與 JSON-LD 結構化資料
- 詞彙庫以 JSON 開放擴充，PR 由 GitHub Actions 自動檢查，合併後自動部署到 GitHub Pages

[Try it 線上使用](https://zhang-renwen.github.io/cn-tw-terms/) · [Source 原始碼](https://github.com/Zhang-RenWen/cn-tw-terms) · [Contribute terms 貢獻詞彙](https://github.com/Zhang-RenWen/cn-tw-terms/blob/main/CONTRIBUTING.md)

#### [CS & Network Roadmap｜計算機科學、網路世界 Road Map](https://github.com/Zhang-RenWen/cs-network-roadmap)

An interactive guide (in Traditional Chinese) that follows one HTTPS request from the browser to the database, layer by layer.

- 183 topics laid out along the request path, from DNS, CDN and TLS through load balancing and runtimes to the database
- The Packet Journey animates two scenarios, an API request (Cloudflare → ALB → ECS Fargate → RDS) and an OIDC + PKCE login; each step shows how the five packet layers change, where TLS terminates, and what error you would see if that step broke
- React + TypeScript, driven by type-checked data files; 443 Vitest tests keep the site in sync with my notes
- GLRR is what I built; this is the knowledge map I distilled from building it. Built with AI pair programming; I own the content, requirements and acceptance

互動式教學網頁：跟著一個 HTTPS 請求從瀏覽器走到資料庫，看每一層的知識點。

- 183 個知識點依請求路徑排列，從 DNS、CDN、TLS、負載平衡、執行環境到資料庫
- 封包旅程以動畫走兩個情境：API 請求（Cloudflare → ALB → ECS Fargate → RDS）與 OIDC + PKCE 登入；每一站顯示封包五層的變化、TLS 終止點，以及這一站壞掉會看到什麼錯誤
- React + TypeScript，由型別檢查過的資料檔驅動；443 個 Vitest 測試讓網站和筆記保持同步
- GLRR 是實作，Road Map 是我把實作過程整理成的知識地圖。AI 協作開發，我負責內容、需求與驗收

[Explore 線上瀏覽](https://zhang-renwen.github.io/cs-network-roadmap/) · [Source 原始碼](https://github.com/Zhang-RenWen/cs-network-roadmap)

#### [Modern WEB Dev Notes｜前端開發知識庫](https://github.com/Zhang-RenWen/modern-web-dev-notes)

My front-end engineering notes (in Traditional Chinese), with concepts verified by running code.

- 182 notes on HTML, CSS, JavaScript, TypeScript, browser internals, performance, frameworks, tooling and security, plus ES6–ES2026 features and 138 mock-interview questions
- 15 step-by-step animations for mechanisms such as the event loop, the prototype chain and HTTP caching
- Migrated from 182 hand-written HTML pages to VitePress with a conversion script that kept URLs and anchors; GitHub Actions deploys to GitHub Pages, and a broken internal link fails the build

我的前端工程筆記，讀到的觀念盡量寫程式驗證。

- 182 篇筆記，涵蓋 HTML、CSS、JavaScript、TypeScript、瀏覽器原理、效能、框架、工程化與資安，以及 ES6～ES2026 新語法和 138 題模擬面試
- 15 個逐步動畫，說明事件循環、原型鏈、HTTP 快取等原理
- 從 182 個手寫 HTML 遷移到 VitePress，以腳本轉換並保留網址與錨點；GitHub Actions 部署到 GitHub Pages，站內連結失效時建置失敗

[Read 線上閱讀](https://zhang-renwen.github.io/modern-web-dev-notes/) · [Source 原始碼](https://github.com/Zhang-RenWen/modern-web-dev-notes)

---

### Tech｜技術

| Area 領域 | Technologies 使用過的技術 |
| --- | --- |
| **Front-end 前端** | JavaScript, TypeScript, Vue 2/3, Nuxt, React, Vite, VitePress, Tailwind CSS, Vuetify, D3.js |
| **Back-end 後端** | Java Spring Boot (RESTful API, transactions, RBAC), Flyway, C# ASP.NET, Python ETL, Keycloak, OIDC (PKCE, TOTP), JWT |
| **Database 資料庫** | PostgreSQL |
| **Testing & quality 測試與品質** | Vitest, Vue Test Utils, Testing Library, JUnit + Testcontainers (integration tests on a real PostgreSQL), pytest, TypeScript type checking, ESLint, oxlint, Prettier, Ruff; CI triggered by changed paths |
| **Cloud & tooling 雲端與工程化** | AWS (ECS Fargate, ECR, RDS, S3, CloudFront, EventBridge Scheduler, CloudFormation), Docker, GitHub Actions CI/CD, GitHub Pages, Cloudflare DNS, monorepo |
| **Finance domain 金融領域** | Life insurance: policyholder services, claims, new business and KYC; financial system design: idempotent transactions, batch reconciliation, change auditing; macro liquidity and credit-risk indicators<br />壽險實務：保戶服務、理賠、新契約、KYC；金融系統設計：交易冪等、批次對帳、異動稽核；總經流動性與信用風險指標 |
