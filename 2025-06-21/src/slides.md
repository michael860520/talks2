---
highlighter: shiki
css: unocss
colorSchema: dark
transition: fade-out
mdc: true
layout: center
lang: zh-TW
glowSeed: 4
title: MonoRepo 實戰指南：工具選型與 OXC 性能突破
---

---
layout: intro
class: pl-25
---

# Michael

<div class="opacity-80">

資深軟體工程師 / 技術 Mentor<br>
專精於前端架構與工具鏈優化<br>
開源項目貢獻者<br>

</div>

<div my-10 w-min flex="~ gap-1" items-center justify-center>
  <div i-ri-github-line op50 ma text-xl/>
  <div><a href="https://github.com/michael" target="_blank" class="border-none! font-300">michael</a></div>
  <div i-ri-twitter-x-line op50 ma text-xl ml4/>
  <div><a href="https://twitter.com/michael" target="_blank" class="border-none! font-300">@michael</a></div>
</div>

---
layout: cover
---

<h1 flex="~ col">
<div mt1 ml10 flex="~ col">
  <span flex="~ gap-2 items-center">
    MonoRepo 實戰指南
  </span>
  <span flex="~ gap-2 items-center">
    工具選型與 OXC 性能突破
  </span>
</div>
</h1>

<div abs-br mx-10 my-11 flex="~ col items-end" text-right>
  <div class="text-lg font-bold">JSDC 2025 小聚</div>
  <div text-xs opacity-75>June 21, 2025</div>
</div>

---
layout: center
class: text-center
---

# 有多少人聽過 MonoRepo？

<div class="mt-16 text-6xl">
  🙋‍♂️
</div>

---
layout: center
class: text-center
---

# 團隊正在使用 MonoRepo？

<div class="mt-16 text-6xl">
  🤔
</div>

---
layout: center
class: text-center
---

# 遇過這些痛點嗎？

<div class="mt-8 space-y-6 max-w-2xl mx-auto">
  <div v-click class="text-2xl">跑個 build 要等 5 分鐘</div>
  <div v-click class="text-2xl">Lint 一跑就去泡咖啡</div>
  <div v-click class="text-2xl">CI 告訴你還要等 30 分鐘</div>
</div>

<div v-after class="mt-12 text-xl text-amber-400">
  在 MonoRepo 中這些問題會更嚴重！
</div>

---
layout: center
---

# 複雜度爆炸

<div class="text-center">
  <div class="text-left max-w-lg mx-auto">

```typescript
// 典型大型 MonoRepo
const complexity = {
  files: 1000, // 檔案數量
  rules: 200, // ESLint 規則
  packages: 50 // package 數量
}

// 總運算量 = 1000 × 200 × 50
// = 千萬級運算！
```

  </div>

  <div class="mt-8 text-xl text-red-400">
    這不是線性增長，而是多維度爆炸
  </div>
</div>

---
layout: center
class: text-center
---

# MonoRepo 三大驅動力

<div class="mt-12 space-y-8 max-w-3xl mx-auto">

<div class="text-center">
  <h2 class="text-2xl font-bold text-indigo-400">多平台開發</h2>
  <p class="mt-4">Web + Mobile + Desktop</p>
  <p class="text-sm opacity-75">如何有效共享業務邏輯？</p>
</div>

<div class="text-center">
  <h2 class="text-2xl font-bold text-amber-400">業務複雜度</h2>
  <p class="mt-4">微服務 + 組件庫 + 工具鏈</p>
  <p class="text-sm opacity-75">版本同步會變成噩夢</p>
</div>

</div>

---
layout: center
class: text-center
---

# MonoRepo 三大驅動力

<div class="mt-12 space-y-8 max-w-3xl mx-auto">

<div class="text-center">
  <h2 class="text-2xl font-bold text-emerald-400">團隊協作</h2>
  <p class="mt-4">小團隊 → 中型團隊 → 大型企業</p>
  <p class="text-sm opacity-75">協作複雜度急劇上升</p>
</div>

<div class="text-center">
  <h2 class="text-2xl font-bold text-indigo-400">解決方案</h2>
  <p class="mt-4">統一工具鏈 + 統一規範 + 統一程式碼庫</p>
</div>

</div>

---
layout: center
---

# MultiRepo vs MonoRepo

<div grid="~ cols-2 gap-12" class="mt-8">

<div>
  <h2 class="text-xl font-bold text-red-400 mb-6">MultiRepo 痛點</h2>

  <div class="space-y-4 text-sm">
    <div>修復一個共享組件 bug：</div>
    <div class="ml-4 space-y-2 opacity-75">
      <div>1. 修復 shared-components</div>
      <div>2. 發布新版本到 npm</div>
      <div>3. 更新 4 個專案依賴</div>
      <div>4. 各自跑 CI/CD</div>
      <div>5. 祈禱沒有 breaking changes</div>
    </div>
    <div class="text-red-400 mt-4">需要一整天，風險很高</div>
  </div>
</div>

<div>
  <h2 class="text-xl font-bold text-emerald-400 mb-6">MonoRepo 優雅</h2>

  <div class="space-y-4 text-sm">
    <div>同樣的修復：</div>
    <div class="ml-4 space-y-2 opacity-75">
      <div>1. 修改 packages/components/Button.tsx</div>
      <div>2. 一次 commit 驗證所有使用方</div>
    </div>
    <div class="text-emerald-400 mt-4">幾分鐘完成，零風險</div>
  </div>
</div>

</div>

---
layout: center
class: text-center
---

# Lerna 已死，pnpm 當立

<div class="mt-12 space-y-8">

<div v-click>
  <h2 class="text-2xl font-bold text-red-400">Lerna 的衰落</h2>
  <div class="mt-4 grid grid-cols-3 gap-8 max-w-2xl mx-auto">
    <div>
      <div class="text-red-400 font-bold">使用率</div>
      <div>25% → 22%</div>
    </div>
    <div>
      <div class="text-red-400 font-bold">滿意度</div>
      <div>60% → 48%</div>
    </div>
    <div>
      <div class="text-red-400 font-bold">維護</div>
      <div>不再積極</div>
    </div>
  </div>
</div>

<div v-click>
  <h2 class="text-2xl font-bold text-emerald-400">pnpm 的崛起</h2>
  <div class="mt-4 grid grid-cols-3 gap-8 max-w-2xl mx-auto">
    <div>
      <div class="text-emerald-400 font-bold">使用率</div>
      <div>13% → 21%</div>
    </div>
    <div>
      <div class="text-emerald-400 font-bold">滿意度</div>
      <div>90%+</div>
    </div>
    <div>
      <div class="text-emerald-400 font-bold">性能</div>
      <div>50%+ 更快</div>
    </div>
  </div>
</div>

</div>

---
layout: center
class: text-center
---

# 工具選型矩陣

<div class="mt-8">

| 工具 | 適合團隊 | 學習成本 | 推薦度 |
|------|----------|----------|--------|
| **pnpm Workspaces** | 小型團隊 (5-15人) | 極簡 | ⭐⭐⭐⭐⭐ |
| **Turborepo** | 中型團隊 (10-30人) | 簡單 | ⭐⭐⭐⭐ |
| **Nx** | 大型企業 (20+人) | 複雜 | ⭐⭐⭐ |

</div>

<div class="mt-8 text-xl text-emerald-400">
  pnpm：零配置，原生支援，極速安裝
</div>

---
layout: center
class: text-center
---

# 所有工具的共同死穴

<div class="mt-12 text-3xl font-bold text-red-400">
  性能瓶頸
</div>

<div class="mt-8 space-y-4">
  <div class="text-xl">重複解析 AST</div>
  <div class="text-sm opacity-75">ESLint、Prettier、Babel、TypeScript 各自解析</div>
</div>

<div class="mt-8 space-y-4">
  <div class="text-xl">CI/CD 時間爆炸</div>
  <div class="text-sm opacity-75">Pipeline 動輒 30 分鐘以上</div>
</div>

---
layout: center
---

# 傳統工具鏈問題

<div class="text-center">
  <div class="text-left max-w-lg mx-auto">

```bash
# 典型開發流程時間消耗
$ npm run lint
⏳ ESLint 解析中... 8分鐘

$ npm run format
⏳ Prettier 格式化中... 3分鐘

$ npm run build
⏳ TypeScript 編譯中... 12分鐘

# 總耗時：23分鐘！
```

  </div>

  <div class="mt-8 text-xl text-red-400">
    開發體驗嚴重受影響
  </div>
</div>

---
layout: center
class: text-center
---

# OXC 革命性解決方案

<div class="mt-8 text-xl">
  Oxidation Compiler Collection
</div>

<div class="mt-8 text-sm opacity-75">
  Rust 驅動的 JavaScript 工具鏈
</div>

<div class="mt-12 grid grid-cols-2 gap-12 max-w-3xl mx-auto">
  <div>
    <h3 class="text-lg font-bold text-emerald-400 mb-4">核心優勢</h3>
    <div class="space-y-3 text-sm">
      <div>50-100倍 速度提升</div>
      <div>80% 記憶體減少</div>
      <div>一次 AST 解析</div>
      <div>原生並行處理</div>
    </div>
  </div>

  <div>
    <h3 class="text-lg font-bold text-indigo-400 mb-4">關鍵技術</h3>
    <div class="space-y-3 text-sm">
      <div>統一 AST 革命</div>
      <div>Zero-copy 記憶體共享</div>
      <div>Rust 原生性能</div>
      <div>多核 CPU 充分利用</div>
    </div>
  </div>
</div>

---
layout: center
class: text-center
---

# 統一 AST 架構

<div grid="~ cols-2 gap-12" class="mt-8">

<div>
  <h2 class="text-lg font-bold text-red-400 mb-6">傳統：N×AST 解析</h2>
  <div class="space-y-2 text-sm">
    <div>ESLint → AST₁</div>
    <div>Prettier → AST₂</div>
    <div>Babel → AST₃</div>
    <div>TypeScript → AST₄</div>
  </div>
  <div class="mt-4 text-red-400">
    重複解析：O(4n) 複雜度
  </div>
</div>

<div>
  <h2 class="text-lg font-bold text-emerald-400 mb-6">OXC：統一 AST</h2>
  <div class="space-y-2 text-sm">
    <div>OXC → Unified AST</div>
    <div>├─ oxc_linter</div>
    <div>├─ oxc_formatter</div>
    <div>├─ oxc_transformer</div>
    <div>└─ oxc_resolver</div>
  </div>
  <div class="mt-4 text-emerald-400">
    零拷貝共享：O(n) 複雜度
  </div>
</div>

</div>

---
layout: center
class: text-center
---

# 性能表現對比

<div class="mt-12 grid grid-cols-3 gap-8">

<div class="text-center">
  <div class="text-4xl font-bold text-emerald-400">60×</div>
  <h3 class="font-semibold mt-2">小型專案</h3>
  <div class="text-sm opacity-75 mt-2">1K 檔案</div>
  <div class="text-sm mt-2">
    <div class="text-red-400">傳統：30秒</div>
    <div class="text-emerald-400">OXC：0.5秒</div>
  </div>
</div>

<div class="text-center">
  <div class="text-4xl font-bold text-indigo-400">96×</div>
  <h3 class="font-semibold mt-2">中型專案</h3>
  <div class="text-sm opacity-75 mt-2">10K 檔案</div>
  <div class="text-sm mt-2">
    <div class="text-red-400">傳統：8分鐘</div>
    <div class="text-indigo-400">OXC：5秒</div>
  </div>
</div>

<div class="text-center">
  <div class="text-4xl font-bold text-amber-400">90×</div>
  <h3 class="font-semibold mt-2">大型專案</h3>
  <div class="text-sm opacity-75 mt-2">50K 檔案</div>
  <div class="text-sm mt-2">
    <div class="text-red-400">傳統：45分鐘</div>
    <div class="text-amber-400">OXC：30秒</div>
  </div>
</div>

</div>

---
layout: center
class: text-center
---

# 企業級驗證

<div class="mt-12 space-y-8">

<div>
  <h2 class="text-2xl font-bold text-emerald-400">Shopify</h2>
  <p class="mt-2">500萬行程式碼</p>
  <p class="text-lg">75分鐘 → 8秒</p>
  <p class="text-emerald-400 font-bold">450× 提升</p>
</div>

<div>
  <h2 class="text-2xl font-bold text-indigo-400">Discord</h2>
  <p class="mt-2">15萬+ 檔案</p>
  <p class="text-lg">完整檢查只需 3秒</p>
</div>

</div>

---
layout: center
---

# 實戰整合：立即可用

<div class="text-center">
  <div class="text-left max-w-lg mx-auto">

```json
// package.json
{
  "scripts": {
    "lint": "oxlint && eslint .",
    "lint:fix": "oxlint && eslint . --fix"
  },
  "devDependencies": {
    "oxlint": "^0.15.0"
  }
}
```

  </div>

  <div v-click class="mt-8 text-xl text-emerald-400">
    零破壞性更新，立即見效
  </div>
</div>

---
layout: center
class: text-center
---

# 漸進式導入策略

<div class="mt-12 space-y-8">

<div>
  <h2 class="text-xl font-bold text-indigo-400">第一週：並行驗證</h2>
  <p class="mt-2">保持現有配置，並行執行 OXC</p>
</div>

<div v-click>
  <h2 class="text-xl font-bold text-emerald-400">第二週：部分替換</h2>
  <p class="mt-2">pre-commit 使用 OXC，CI 保留 ESLint</p>
</div>

<div v-click>
  <h2 class="text-xl font-bold text-amber-400">第三週：完全遷移</h2>
  <p class="mt-2">享受 10-50倍速度提升</p>
</div>

</div>

---
layout: center
class: text-center
---

# Void0 計劃

<div class="mt-8 text-lg">
  Evan You 領導的雄心計劃
</div>

<div class="mt-8 grid grid-cols-2 gap-8 max-w-2xl mx-auto">
  <div class="text-center">
    <div class="text-indigo-400 font-bold">已完成</div>
    <div class="mt-2">Oxlint</div>
  </div>
  <div class="text-center">
    <div class="text-emerald-400 font-bold">開發中</div>
    <div class="mt-2">Rolldown</div>
  </div>
  <div class="text-center">
    <div class="text-amber-400 font-bold">規劃中</div>
    <div class="mt-2">Formatter</div>
  </div>
  <div class="text-center">
    <div class="text-purple-400 font-bold">願景</div>
    <div class="mt-2">JS Engine</div>
  </div>
</div>

<div v-click class="mt-8 text-xl text-amber-400">
  Oxlint 只是八個工具之一！
</div>

---
layout: center
class: text-center
---

# 總結

<div class="mt-12 space-y-8">

<div class="text-2xl font-bold text-indigo-400">
  MonoRepo 是趨勢
</div>

<div class="text-2xl font-bold text-emerald-400">
  pnpm 已勝出
</div>

<div class="text-2xl font-bold text-amber-400">
  OXC 是未來
</div>

</div>

---
layout: center
class: text-center
---

# 立即行動

<div class="mt-12 space-y-8 max-w-2xl mx-auto">

<div>
  <h2 class="text-xl font-bold text-emerald-400">今天就開始</h2>
  <p class="mt-2">npm install -D oxlint</p>
  <p class="text-sm opacity-75">修改一行配置，立即提升</p>
</div>

<div v-click>
  <h2 class="text-xl font-bold text-indigo-400">持續關注</h2>
  <p class="mt-2">Nx 2025 路線圖</p>
  <p class="text-sm opacity-75">準備無縫升級</p>
</div>

</div>

<div v-click class="mt-12 text-xl font-bold text-emerald-400">
  效率革命從選對工具開始！
</div>

---
layout: end
class: text-center
---

# 謝謝大家！

<div class="mt-8">
  <div class="text-xl font-semibold">Q&A 討論時間</div>
  <div class="text-gray-400 mt-2">一起推動前端開發效率革命</div>
</div>

<div class="mt-10 text-sm opacity-50">
  JSDC 2025 小聚 • MonoRepo 實戰指南
</div>
