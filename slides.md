---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: Welcome to Slidev
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# open graph
# seoMeta:
#  ogImage: https://cover.sli.dev
---

# POEditor 簡介

講者：Valtina  
日期：2025/07/14

<div @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  Press Space for next page <carbon:arrow-right />
</div>

---
transition: fade-out
---

# 為什麼需要 POEditor？

- 🌍 多語系版本管理困難  
- 🔁 翻譯內容反覆變更，容易出錯  
  - 能建立字串管理的 SSOT，清楚指認位置，後續交接和長期管理較有彈性(FE、Product)
    1. 可設立標籤管理字串
    2. 可透過截圖知道字串所在頁面和位置
- 🎨 設計稿、翻譯、開發進度不同步  
- 🧑‍🤝‍🧑 缺乏協作平台，依賴手動溝通
    - 能統一 VS 的產品字串管理，若後續要指派業務同仁 local 翻譯也較方便(Ruby)
<br>
<br>
- ❓ 風險或疑慮
    - 產品已開發，具有轉移時間成本，須由大家一起評估
    - 需要購買方案而非開新的 seats，會提升部門開發成本

---
transition: slide-up
---

# POEditor 是什麼？

一款協助產品開發團隊管理翻譯的線上平台

- 🌐 支援多種語系格式：JSON、iOS Strings、Android XML 等
- 👥 多人協作、權限控管
- 🔄 自動匯入／匯出、API 整合
  - 目前 PG Team 也只是拿來當成協作平台，沒有更進階的使用與操作
- 🕘 支援歷史版本與變更紀錄

<div class="mt-0 ml-12 fit-content" transition="slide-up">
  <a href="https://poeditor.com/account/logs" target="_blank"
     class="text-blue-600 hover:underline hover:text-blue-800 transition">
    🔗 前往範例 Dashboard
  </a>
</div>

---
layout: image-right-custom
image: https://cover.sli.dev
---

# PG team 會議簡報 - 背景

- 🗓️ PG 已使用至少 5 年以上，管理超過 10+ 語言，以產品區分字串平台上的 project
- 💳 方案的負責人和購買窗口是 3S PM director Frank Chu (Owner)，會定期檢閱字串量確認何時要 upgrade 方案
- ✍️ reference 語言是英文(Figma 稿件也是)，中文字串翻譯由 PM 負責，英文和其他語系由 growth team 的 copywriter Roderick Ordonez 負責(copywriter 在平台中也是 Admin 身分)

---
layout: image-right-custom
image: https://cover.sli.dev
---

# PG team 會議簡報 - 字串管理流程

- 🎨 Designer 產出英文 Figma 稿件，不須做任何翻譯相關工作
- ⌨️ FE 根據 Figma 設計稿在字串平台上設 Key(term)+上傳介面截圖
- 🗣️ PM 翻譯中文後，通知 copywriter 壓時間請他協助英文和其他所有語言字串確認 (請 contractor 翻譯)
- 🚀 在 rc 當天早上前確認所有字串已更新在平台上，FE 透過 API 直接更新字串上版
- 💡 其他使用建議：
  - 平台上更新字串時，建議複製一個 term 把中英翻完，刪除舊有 term 再給 copywriter 以免上檔到其他語言的舊字串
  - PG 基於 poeditor 匯出 key value json 格式自行開發一個 AI 翻譯工具分享給我們：AI Translation Service

---
transition: slide-up
---

# 購買方案初估

- 🧮 費用計算以所有 project 的 key(term) 數量*(term 數+國家數)計算，[方案一覽](https://poeditor.com/pricing/)
- 🗂️ project 應照現在 Excel 的方式區分，Client/Hub/Participant/QG 分開
- 🔢 詞條計算方式：terms 數量也算一個字串，總數應為 terms 數量 * (1 + 語言數量)
  - 建議購買 plus (10000)，每月 $39*12=468/y (一年約台幣14,040)
  - 所有現有 [i18n Excel 檔案](https://viewsonic0-my.sharepoint.com/personal/cindy_chen_viewsonic_com/_layouts/15/onedrive.aspx?id=%2Fpersonal%2Fcindy%5Fchen%5Fviewsonic%5Fcom%2FDocuments%2FUVS%20Department%2FSwift%20UIUX%20Design%2FInternationalization&ct=1752223038984&or=Teams%2DHL&ga=1&LOF=1)
    1. Client-Windows/567
    2. Participant(In Class)/149
    3. Learning Platform(After Class)/91
    4. Hub/742
    5. Product page/669
    6. App launcher/13
    7. Quiz generator/135
    8. Client-Mac/233
    9. Client-IFP/216
