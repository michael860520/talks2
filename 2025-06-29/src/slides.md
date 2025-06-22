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

</div>

<div my-10 w-min flex="~ gap-1" items-center justify-center>
  <div i-ri-github-line op50 ma text-xl/>
  <div><a href="https://github.com/michael0520" target="_blank" class="border-none! font-300">michael</a></div>
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
layout: quote
class: text-left
---

# 🙋‍♂️ Heard about the <span text-hex-8080f2 font-bold><span v-mark="0">MonoRepo</span></span>?

---
layout: quote
class: text-left
---

# 🙋‍♂️ 團隊正在使用 <span text-hex-8080f2 font-bold>MonoRepo</span>？

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
layout: fact
---

# 複雜度爆炸{.important-text-2em}

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
  <div absolute left-0 right-0 bottom-0 p20 flex>
    <div text-center text-orange bg-orange:10 rounded px4 p2 ma v-click>
    這不是線性增長，而是多維度爆炸
    </div>
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

# MultiRepo vs MonoRepo

<div grid="~ cols-2 gap-12" class="mt-8">

<div flex="~ col gap-2" v-click="3" transition duration-500 :class="$clicks < 5 ? 'translate-x-35' : ''">

<div op75>MultiRepo 痛點</div>

<div border="y main" py2>
  <div flex="~ gap-2 items-center" text-red-2>
    <div i-ph-minus-circle-duotone text-red flex-none />
    需要一整天修復
  </div>
  <div flex="~ gap-2 items-center" text-red-2>
    <div i-ph-minus-circle-duotone text-red flex-none />
    風險很高
  </div>
  <div flex="~ gap-2 items-center" text-red-2>
    <div i-ph-minus-circle-duotone text-red flex-none />
    版本同步困難
  </div>
  <div flex="~ gap-2 items-center" text-red-2>
    <div i-ph-minus-circle-duotone text-red flex-none />
    多個 CI/CD 流程
  </div>
</div>

<div v-click="4" flex="~ col gap-2" border="~ main rounded" p2 mt4 bg-red:10 relative text-sm>
  <div text-xs border="~ main rounded" bg-hex-4c1d1f text-red5 absolute top--2 left-2 px2>MultiRepo 流程</div>
  <div flex="~ col gap-1">
    <div>修復 → 發布 → 更新 → CI</div>
  </div>
</div>

<div op75 v-click="4" text-sm>
4個步驟，耗時長
</div>

</div>

<div flex="~ col gap-2" v-click="5">

<div op75>MonoRepo 優雅</div>

<div border="y main" py2>
  <div flex="~ gap-2 items-center" text-green-2>
    <div i-ph-plus-circle-duotone text-green flex-none />
    幾分鐘完成
  </div>
  <div flex="~ gap-2 items-center" text-green-2>
    <div i-ph-plus-circle-duotone text-green flex-none />
    零風險
  </div>
  <div flex="~ gap-2 items-center" text-green-2>
    <div i-ph-plus-circle-duotone text-green flex-none />
    統一版本管理
  </div>
  <div flex="~ gap-2 items-center" text-green-2>
    <div i-ph-plus-circle-duotone text-green flex-none />
    單一 CI/CD 流程
  </div>
</div>

<div v-click="6" flex="~ col gap-2" border="~ main rounded" p2 mt4 bg-green:10 relative text-sm>
  <div text-xs border="~ main rounded" bg-hex-1a4d2e text-green5 absolute top--2 left-2 px2>MonoRepo 流程</div>
  <div flex="~ gap-1">
    <div>修改 → commit → 驗證</div>
  </div>
</div>

<div op75 v-click="6" text-sm>
3個步驟，快速完成
</div>

</div>

</div>

---
layout: center
class: text-left
---

# 工具選型矩陣

<div class="mt-8 grid grid-cols-3 gap-6">

<div v-click="1" class="border border-emerald-400 rounded-lg p-4 bg-emerald:10 relative">
  <div class="absolute -top-3 left-4 bg-emerald-400 text-black px-2 py-1 rounded text-sm font-bold">推薦首選</div>
  <h3 class="text-xl font-bold text-emerald-400 mb-3">pnpm Workspaces</h3>
  <div class="space-y-2 text-sm">
    <div class="flex justify-between">
      <span class="opacity-75">適合對象</span>
      <span>想要嘗試導入</span>
    </div>
    <div class="flex justify-between">
      <span class="opacity-75">學習成本</span>
      <span class="text-green-400">極簡</span>
    </div>
    <div class="flex justify-between">
      <span class="opacity-75">推薦度</span>
      <span>⭐⭐⭐⭐⭐</span>
    </div>
  </div>
  <div class="mt-3 pt-3 border-t border-emerald-400/30">
    <div class="text-xs opacity-75">零配置，原生支援，安裝快速</div>
  </div>
</div>

<div v-click="2" class="border border-blue-400 rounded-lg p-4 bg-blue:10">
  <h3 class="text-xl font-bold text-blue-400 mb-3">Turborepo</h3>
  <div class="space-y-2 text-sm">
    <div class="flex justify-between">
      <span class="opacity-75">適合對象</span>
      <span>NextJS 為主</span>
    </div>
    <div class="flex justify-between">
      <span class="opacity-75">學習成本</span>
      <span class="text-yellow-400">簡單</span>
    </div>
    <div class="flex justify-between">
      <span class="opacity-75">推薦度</span>
      <span>⭐⭐⭐⭐</span>
    </div>
  </div>
  <div class="mt-3 pt-3 border-t border-blue-400/30">
    <div class="text-xs opacity-75">Vercel 出品，React 生態友好</div>
  </div>
</div>

<div v-click="3" class="border border-purple-400 rounded-lg p-4 bg-purple:10">
  <h3 class="text-xl font-bold text-purple-400 mb-3">Nx</h3>
  <div class="space-y-2 text-sm">
    <div class="flex justify-between">
      <span class="opacity-75">適合對象</span>
      <span>中小型團隊</span>
    </div>
    <div class="flex justify-between">
      <span class="opacity-75">學習成本</span>
      <span class="text-red-400">複雜</span>
    </div>
    <div class="flex justify-between">
      <span class="opacity-75">推薦度</span>
      <span>⭐⭐⭐</span>
    </div>
  </div>
  <div class="mt-3 pt-3 border-t border-purple-400/30">
    <div class="text-xs opacity-75">功能強大，但配置複雜</div>
  </div>
</div>

</div>

<div absolute left-0 right-0 bottom-0 p14 flex>
  <div text-center mt10 text-emerald-400 bg-orange:10 rounded px4 p2 ma v-click>
  pnpm：零配置，原生支援，安裝快速
  </div>
</div>

---

# 傳統工具鏈的致命問題

<div class="mt-8 text-left">
  <div class="mt-4 text-lg opacity-75">無論選擇哪個 MonoRepo 工具，都逃不過這個宿命</div>
</div>

<div class="mt-8 grid grid-cols-3 gap-6">

<div v-click="1" class="border border-red-400 rounded-lg p-4 bg-red:10 relative transition duration-500 transform"
     :class="$clicks < 1 ? 'translate-y-10 opacity-0' : 'translate-y-0 opacity-100'">
  <div class="absolute -top-3 left-4 bg-red-500 text-white px-2 py-1 rounded text-xs font-bold
              transition duration-300 delay-200"
       :class="$clicks < 1 ? 'scale-0' : 'scale-100'">核心問題</div>
  <h3 class="text-lg font-bold text-red-400 mb-3 transition duration-300 delay-100"
      :class="$clicks < 1 ? 'translate-x--10 opacity-0' : 'translate-x-0 opacity-100'">重複解析 AST</h3>
  <div class="space-y-2 text-sm">
    <div class="flex items-center gap-2 transition duration-300 delay-300"
         :class="$clicks < 1 ? 'translate-x--5 opacity-0' : 'translate-x-0 opacity-100'">
      <div class="w-1.5 h-1.5 bg-red-400 rounded-full"></div>
      <span>ESLint 解析</span>
    </div>
    <div class="flex items-center gap-2 transition duration-300 delay-400"
         :class="$clicks < 1 ? 'translate-x--5 opacity-0' : 'translate-x-0 opacity-100'">
      <div class="w-1.5 h-1.5 bg-red-400 rounded-full"></div>
      <span>Prettier 解析</span>
    </div>
    <div class="flex items-center gap-2 transition duration-300 delay-500"
         :class="$clicks < 1 ? 'translate-x--5 opacity-0' : 'translate-x-0 opacity-100'">
      <div class="w-1.5 h-1.5 bg-red-400 rounded-full"></div>
      <span>Babel 解析</span>
    </div>
    <div class="flex items-center gap-2 transition duration-300 delay-600"
         :class="$clicks < 1 ? 'translate-x--5 opacity-0' : 'translate-x-0 opacity-100'">
      <div class="w-1.5 h-1.5 bg-red-400 rounded-full"></div>
      <span>TypeScript 解析</span>
    </div>
  </div>
  <div class="mt-3 p-2 bg-red:20 rounded text-xs font-bold text-red-400 transition duration-300 delay-700"
       :class="$clicks < 1 ? 'translate-y-3 opacity-0' : 'translate-y-0 opacity-100'">
    同一份程式碼解析 4 次！
  </div>
</div>

<div v-click="2" class="border border-orange-400 rounded-lg p-4 bg-orange:10 relative transition duration-500 transform"
     :class="$clicks < 2 ? 'translate-y-10 opacity-0' : 'translate-y-0 opacity-100'">
  <div class="absolute -top-3 left-4 bg-orange-500 text-white px-2 py-1 rounded text-xs font-bold
              transition duration-300 delay-200"
       :class="$clicks < 2 ? 'scale-0' : 'scale-100'">時間消耗</div>
  <h3 class="text-lg font-bold text-orange-400 mb-3 transition duration-300 delay-100"
      :class="$clicks < 2 ? 'translate-x--10 opacity-0' : 'translate-x-0 opacity-100'">開發流程耗時</h3>

  <div class="text-left text-xs font-mono bg-black:20 p-2 rounded mb-3 transition duration-300 delay-300"
       :class="$clicks < 2 ? 'translate-x-5 opacity-0' : 'translate-x-0 opacity-100'">
    <div>$ npm run lint</div>
    <div class="text-orange-400">3分鐘</div>
    <div>$ npm run format</div>
    <div class="text-orange-400">1分鐘</div>
    <div>$ npm run build</div>
    <div class="text-red-400">8分鐘</div>
  </div>

  <div class="p-2 bg-orange:20 rounded text-xs font-bold text-orange-400 transition duration-300 delay-500"
       :class="$clicks < 2 ? 'translate-y-3 opacity-0' : 'translate-y-0 opacity-100'">
    總耗時：12分鐘
  </div>
</div>

<div v-click="3" class="border border-purple-400 rounded-lg p-4 bg-purple:10 relative transition duration-500 transform"
     :class="$clicks < 3 ? 'translate-y-10 opacity-0' : 'translate-y-0 opacity-100'">
  <div class="absolute -top-3 left-4 bg-purple-500 text-white px-2 py-1 rounded text-xs font-bold
              transition duration-300 delay-200"
       :class="$clicks < 3 ? 'scale-0' : 'scale-100'">影響範圍</div>
  <h3 class="text-lg font-bold text-purple-400 mb-3 transition duration-300 delay-100"
      :class="$clicks < 3 ? 'translate-x--10 opacity-0' : 'translate-x-0 opacity-100'">規模化災難</h3>
  <div class="space-y-2 text-sm">
    <div class="flex justify-between transition duration-300 delay-300"
         :class="$clicks < 3 ? 'translate-x-5 opacity-0' : 'translate-x-0 opacity-100'">
      <span>小型 (1K 檔案)</span>
      <span class="text-orange-400">5分鐘</span>
    </div>
    <div class="flex justify-between transition duration-300 delay-400"
         :class="$clicks < 3 ? 'translate-x-5 opacity-0' : 'translate-x-0 opacity-100'">
      <span>中型 (10K 檔案)</span>
      <span class="text-red-400">25分鐘</span>
    </div>
    <div class="flex justify-between transition duration-300 delay-500"
         :class="$clicks < 3 ? 'translate-x-5 opacity-0' : 'translate-x-0 opacity-100'">
      <span>大型 (50K+ 檔案)</span>
      <span class="text-red-500 font-bold">90分鐘</span>
    </div>
  </div>
  <div class="mt-3 p-2 bg-purple:20 rounded text-xs font-bold text-purple-400 transition duration-300 delay-600"
       :class="$clicks < 3 ? 'translate-y-3 opacity-0' : 'translate-y-0 opacity-100'">
    CI/CD 流程明顯拖慢開發節奏
  </div>
</div>

</div>

<div v-click="4" class="mt-6 text-center transition duration-500 transform"
     :class="$clicks < 4 ? 'translate-y-10 opacity-0 scale-95' : 'translate-y-0 opacity-100 scale-100'">
  <div class="inline-block bg-orange:10 border border-orange-400 text-orange-400 px-6 py-3 rounded-lg
              transition duration-300 hover:scale-105 hover:bg-orange:20">
    <div class="text-lg font-bold">開發體驗明顯受損</div>
    <div class="text-sm mt-1">等待時間過長，開發節奏被打斷</div>
  </div>
</div>

---

<h1 text-center flex="~ col gap-1 items-center" py5>
<div flex="~ gap-2 items-center" font-bold><div i-logos-rust text-3xl /> OXC 革命性解決方案</div>
<div text-lg op75 mt2>Oxidation Compiler Collection - Rust 驅動的 JavaScript 工具鏈</div>
</h1>
<div grid="~ cols-[1fr_max-content_1fr] gap-8" px-10 mt4>

<div flex="~ col gap-6" py2 transition duration-500 :class="$clicks < 6 ? 'translate-x-55' : 'translate-x-20'">
  <div
    v-click
    op50 font-bold uppercase text-sm tracking-0.2em text-left
    transition duration-500 :class="$clicks < 6 ? 'translate-x--0' : ''"
  >核心優勢</div>

  <div v-click flex="~ col gap-1">
    <div flex="~ gap-2">
      <div text-2xl i-ph-lightning-duotone text-emerald />
      <div>50-100倍 速度提升</div>
    </div>
    <div text-sm op60>Rust 原生性能，告別等待時間</div>
  </div>
  <div v-click flex="~ col gap-1">
    <div flex="~ gap-2">
      <div text-2xl i-ph-database-duotone text-blue />
      <div>80% 記憶體減少</div>
    </div>
    <div text-sm op60>Zero-copy 記憶體共享技術</div>
  </div>
  <div v-click flex="~ col gap-1">
    <div flex="~ gap-2">
      <div text-2xl i-ph-target-duotone text-purple />
      <div>一次 AST 解析</div>
    </div>
    <div text-sm op60>統一 AST 架構，消除重複解析</div>
  </div>
  <div v-click flex="~ col gap-1">
    <div flex="~ gap-2">
      <div text-2xl i-ph-rocket-launch-duotone text-orange />
      <div>原生並行處理</div>
    </div>
    <div text-sm op60>多核 CPU 充分利用，極致並行</div>
  </div>
</div>

<div w-1px h-full border="l main" translate-x-25 v-click />

<div flex="~ col gap-6" py2 translate-x-25>
  <div op50 font-bold uppercase text-sm tracking-0.2em v-after>企業級驗證</div>

  <div flex="~ col" mt4 v-click>
    <div font-semibold text-emerald>Shopify</div>
    <div flex="~ gap-1 items-center" text-sm op75 ml3>
      <div i-ph-code-duotone />
      500萬行程式碼
    </div>
    <div flex="~ gap-1 items-center" text-emerald ml3>
      <div i-ph-check-duotone />
      75分鐘 → 8秒 (450× 提升)
    </div>
  </div>

  <div flex="~ col" v-click>
    <div font-semibold text-indigo>Vue.js 3</div>
    <div flex="~ gap-1 items-center" text-sm op75 ml3>
      <div i-ph-code-duotone />
      核心框架
    </div>
    <div flex="~ gap-1 items-center" text-indigo ml3>
      <div i-ph-check-duotone />
      構建時間減少 90%
    </div>
  </div>

  <div flex="~ col" v-click>
    <div font-semibold text-amber>平均表現</div>
    <div flex="~ gap-1 items-center" text-amber ml3>
      <div i-ph-chart-line-up-duotone />
      50-100倍性能提升
    </div>
  </div>
</div>

</div>

---
layout: two-cols
class: px-8
---

# 傳統工具鏈的問題

<div class="space-y-6">

<div class="relative">

  <!-- 工具鏈問題展示 -->
  <div class="space-y-3">
    <!-- ESLint -->
    <div class="relative">
      <div v-click="2" class="flex items-center justify-between p-3 bg-red:20 border border-red/20 rounded">
        <span class="font-semibold">ESLint</span>
        <span>→ 解析 AST₁</span>
      </div>
      <div v-click="6" class="absolute inset-0 flex items-center justify-center pointer-events-none">
        <div class="text-6xl text-red font-bold transform rotate-12">✗</div>
      </div>
    </div>
    <!-- Prettier -->
    <div class="relative">
      <div v-click="3" class="flex items-center justify-between p-3 bg-red:20 border border-red/20 rounded">
        <span class="font-semibold">Prettier</span>
        <span>→ 解析 AST₂</span>
      </div>
      <div v-click="7" class="absolute inset-0 flex items-center justify-center pointer-events-none">
        <div class="text-6xl text-red font-bold transform rotate-12">✗</div>
      </div>
    </div>
    <!-- Babel -->
    <div class="relative">
      <div v-click="4" class="flex items-center justify-between p-3 bg-red:20 border border-red/20 rounded">
        <span class="font-semibold">Babel</span>
        <span>→ 解析 AST₃</span>
      </div>
      <div v-click="8" class="absolute inset-0 flex items-center justify-center pointer-events-none">
        <div class="text-6xl text-red font-bold transform rotate-12">✗</div>
      </div>
    </div>
    <!-- TypeScript -->
    <div class="relative">
      <div v-click="5" class="flex items-center justify-between p-3 bg-red:20 border border-red/20 rounded">
        <span class="font-semibold">TypeScript</span>
        <span>→ 解析 AST₄</span>
      </div>
      <div v-click="9" class="absolute inset-0 flex items-center justify-center pointer-events-none">
        <div class="text-6xl text-red font-bold transform rotate-12">✗</div>
      </div>
    </div>
  </div>

  <!-- 問題總結 -->
  <div v-click="10" class="mt-6 p-4 bg-red:20 border border-red/20 rounded text-center">
    <div class="text-red font-bold text-lg">❌ 重複解析浪費資源</div>
    <div class="text-sm mt-2 op75">每個工具都要重新解析同一份程式碼</div>
  </div>
</div>
</div>

::right::

<div class="space-y-6" v-show="$clicks >= 11">

## OXC 革命性解決方案

<!-- OXC Parser -->
<div v-click="12" class="p-4 bg-green:20 border border-green/20 rounded text-center mb-6">
  <div class="flex items-center justify-center gap-3">
    <div>
      <div class="font-bold text-lg">OXC Parser</div>
      <div class="text-sm op75">一次解析，統一 AST</div>
    </div>
  </div>
</div>

<!-- 共享 AST -->
<div v-click="13" class="space-y-3">
  <div class="flex items-center gap-3 p-3 bg-green:20 border border-green/20 rounded">
    <span class="text-green text-xl">✓</span>
    <span class="font-semibold">oxc_linter</span>
    <span class="text-sm op75 ml-auto">共享 AST</span>
  </div>
  <div class="flex items-center gap-3 p-3 bg-green:20 border border-green/20 rounded">
    <span class="text-green text-xl">✓</span>
    <span class="font-semibold">oxc_formatter</span>
    <span class="text-sm op75 ml-auto">共享 AST</span>
  </div>
  <div class="flex items-center gap-3 p-3 bg-green:20 border border-green/20 rounded">
    <span class="text-green text-xl">✓</span>
    <span class="font-semibold">oxc_transformer</span>
    <span class="text-sm op75 ml-auto">共享 AST</span>
  </div>
  <div class="flex items-center gap-3 p-3 bg-green:20 border border-green/20 rounded">
    <span class="text-green text-xl">✓</span>
    <span class="font-semibold">oxc_resolver</span>
    <span class="text-sm op75 ml-auto">共享 AST</span>
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
layout: center
class: 'text-center pb-5'
---

# Thank you!
Slides can be found on [..](..)
