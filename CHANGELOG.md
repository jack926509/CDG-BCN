# Changelog — CDG-BCN 歐洲 16 天行程規劃

所有版本修正歷程紀錄。格式基於 [Keep a Changelog](https://keepachangelog.com/)。

---

## [v2.3] — 2026-03-18

### 新增：交通票券專區

新增獨立的「🚇 交通票券」分頁，提供 7 個城市的完整交通指南。

#### 各城市交通資訊

| 城市 | 內容摘要 |
|------|---------|
| 巴黎 | RATP 官網、Métro + RER 路線圖連結、Navigo Easy / Navigo Découverte 週卡 / Paris Visite 日票比較、CDG 機場 RER B 線 |
| 里斯本 | Metro 路線圖、Viva Viagem + Zapping / 24h 票 / Lisboa Card 比較、辛特拉一日遊交通 |
| 波多 | Metro do Porto 路線圖、Andante / Andante Tour / Porto Card 比較 |
| 塞維亞 | Tussam 巴士 + Metro 路線圖、Tarjeta Multiviaje / 日票、舊城步行提醒 |
| 格拉納達 | 市區巴士、C30/C32 阿爾罕布拉宮接駁巴士、Granada Card |
| 馬德里 | Metro 路線圖（含觀光站標示）、Multi + 10 次票 / Abono Turístico / 機場交通、托雷多一日遊 |
| 巴塞隆納 | TMB Metro 路線圖（含觀光站標示）、T-Casual / Hola BCN! / Aerobus / Renfe R2 Nord |

#### 跨城長途交通

- Renfe（西班牙 AVE 高鐵）、CP（葡萄牙 Alfa Pendular）、ALSA（巴士）官網連結
- Skyscanner / Google Flights 廉航比價連結
- 交通省錢撇步（Uber/Bolt 價格、Google Maps 離線地圖等）

#### 技術變更

- 導覽列新增 `transport` 篩選按鈕
- JavaScript 重構：以 `panels` 物件統一管理面板顯示邏輯，取代多個 `if/else` 分支
- 新增 `hideAllPanels()` 輔助函式
- `validFilters` 陣列加入 `'transport'`

---

## [v2.2] — 2026-03-18

### 新增：Google Maps 景點連結

為行程中所有景點、餐廳、市場、觀景台等地點加上 Google Maps 搜尋連結，旅途中點擊即可導航。

#### 統計

- 共計 **77 個** Google Maps 連結
- 涵蓋全部 16 天、7 個城市

#### 各城市連結數

| 城市 | 連結數 | 代表地點 |
|------|--------|---------|
| 巴黎 | 10 | 香榭麗舍、凱旋門、羅浮宮、奧塞美術館、聖心堂、迪士尼 |
| 里斯本 | 12 | 阿爾法馬、聖喬治城堡、貝倫塔、Pastéis de Belém、佩納宮 |
| 波多 | 11 | 里貝拉、路易一世橋、萊羅書店、聖本篤車站、Café Santiago |
| 塞維亞 | 10 | 王宮、大教堂、西班牙廣場、El Rinconcillo、Casa de la Memoria |
| 格拉納達 | 11 | 阿爾罕布拉宮各區、阿爾拜辛、Bar Los Diamantes、Bodegas Castañeda |
| 馬德里 | 13 | 王宮、普拉多、蘇菲亞、麗池公園、托雷多、Mercado de Antón Martín |
| 巴塞隆納 | 10 | 聖家堂、奎爾公園、巴特婁之家、蘭布拉大道、博蓋利亞市場 |

#### 技術變更

- 連結格式：`https://www.google.com/maps/search/?api=1&query=...`，所有連結加上 `target="_blank" rel="noopener noreferrer"`
- 列印樣式更新：新增 `.ds a[href]::after, .dn2 a[href]::after { content: none; }`，避免行程描述中的地圖連結在列印時顯示冗長 URL

---

## [v2.1] — 2026-03-18

### 改善：效能、可存取性與手機體驗

兩次提交合併為一個版本，涵蓋 bug 修正與體驗優化。

#### Bug 修正

- **住宿晚數錯誤修正**：修正行程表中住宿晚數與實際行程不符的問題
- 手機版面閱讀體驗改善

#### 效能改善

- 程式碼品質提升
- 可存取性（Accessibility）改善

#### 技術變更

- commit `0afc75e`: fix: 修正住宿晚數錯誤、改善手機閱讀體驗與程式碼品質
- commit `7113d98`: enhance: 改善效能、可存取性與使用體驗

---

## [v2.0] — 2026-03-17

### 新增：實用須知分頁與在地提醒

大幅擴充行程內容，從單純景點列表升級為第一次歐洲自由行的完整指南。

#### 新增功能

- **「🧳 實用須知」分頁**：獨立分頁，涵蓋六大主題
  - 🍽 用餐時間（法國 / 葡萄牙 / 西班牙各國差異、Siesta 文化）
  - 💳 金錢與付款（歐元刷卡普及度、小費文化、ATM 提款技巧）
  - 📱 上網與通訊（eSIM 推薦、歐盟無漫遊費）
  - 🎒 打包建議（各城市溫差、鞋子、廉航行李）
  - 🛡 安全與防盜（扒手高風險區、巴黎常見騙術、緊急電話 112）
  - 🚇 交通卡省錢術（各城市交通卡與儲值方式）
- **在地提醒標籤**（💡 綠底）：每天行程加入當地人才知道的實用資訊
- **觀光客陷阱提醒**：蒙馬特幸運繩、聖米格爾市場高價、28E 電車扒手等

#### 內容更新

- 修正凡爾賽宮與迪士尼樂園二擇一說明
- 更新佛朗明哥推薦場所（Casa de la Memoria、Casa del Flamenco）
- 補充各城市具體票價與交通費用
- 新增格拉納達免費 Tapas 巡禮攻略

---

## [v1.0] — 2026-03-17

### 初版行程規劃

#### 功能

- 16 天 15 夜完整行程規劃（巴黎 → 里斯本 → 波多 → 塞維亞 → 格拉納達 → 馬德里 → 巴塞隆納）
- 互動式 HTML 單頁應用
  - 城市篩選按鈕（8 個城市）
  - 訂票清單（按緊急程度排序）
  - 響應式設計（桌面 / 手機）
  - Dark Mode 自動跟隨系統
- 每日行程含：景點描述、門票價格、注意事項
- 城市間交通段（飛機 / 高鐵 / 巴士）標示

#### 檔案

- `index.html` — 互動式行程視覺化
- `travel-planning-design-concept.md` — 設計概念文件
- `README.md` — 專案說明

---

*2026 CDG-BCN 歐洲行程規劃・最後更新 2026-03-18*
