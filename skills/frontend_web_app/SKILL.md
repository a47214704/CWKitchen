---
name: frontend_web_app
description: A pure frontend Agent Skill web application using Vue 3, Vite, Tailwind CSS, and Naive UI with complete RWD support
---

# Frontend Web App Skill

本專案為一個 **純前端 Agent Skill 網頁應用**,主要提供可快速擴充、可維護且具備良好 RWD(響應式設計)能力的前端架構。

---

## 🧩 技術選型(Tech Stack)

- **Vue 3**
  - 採用 Composition API
  - 更好的型別推導與邏輯拆分
- **Vite**
  - 極速開發與熱更新(HMR)
  - 現代化前端建構工具
- **Tailwind CSS**
  - Utility-first CSS
  - 實作完整 RWD(手機 / 平板 / 桌機)
- **Naive UI**
  - Vue 3 專用 UI Component Library
  - 提供一致性良好的 UI 元件

---

## 📁 專案結構(Project Structure)

```text
src/
├─ assets/              # 靜態資源(圖片、icon)
├─ components/          # 可重用元件
├─ layouts/             # 版型(Layout)
├─ pages/               # 頁面級元件
├─ router/              # Vue Router 設定
├─ styles/              # 全域樣式(Tailwind 擴充)
├─ App.vue
├─ main.ts
```

---

## 🚀 快速開始(Quick Start)

### 建立新專案

使用 Vite 建立 Vue 3 + TypeScript 專案:

```bash
# 使用 npm
npm create vite@latest ./ -- --template vue-ts

# 或使用 pnpm
pnpm create vite ./ --template vue-ts
```

### 安裝依賴

```bash
# 安裝 Tailwind CSS
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p

# 安裝 Naive UI
npm install naive-ui

# 安裝 Vue Router (如需要)
npm install vue-router@4
```

### Tailwind CSS 設定

在 `tailwind.config.js` 中配置:

```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{vue,js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

在 `src/styles/main.css` 中引入 Tailwind:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### 啟動開發伺服器

```bash
npm run dev
```

---

## 📱 RWD 響應式設計原則

使用 Tailwind CSS 的響應式斷點:

- `sm:` - 640px 以上(平板直向)
- `md:` - 768px 以上(平板橫向)
- `lg:` - 1024px 以上(桌機)
- `xl:` - 1280px 以上(大螢幕)
- `2xl:` - 1536px 以上(超大螢幕)

範例:

```vue
<div class="w-full px-4 sm:px-6 md:px-8 lg:max-w-7xl lg:mx-auto">
  <!-- 手機: 全寬 + 小 padding -->
  <!-- 平板: 中等 padding -->
  <!-- 桌機: 最大寬度 + 置中 -->
</div>
```

---

## 🎨 Naive UI 使用範例

```vue
<script setup lang="ts">
import { NButton, NCard, NSpace } from 'naive-ui'
</script>

<template>
  <n-space vertical>
    <n-card title="範例卡片">
      <n-button type="primary">主要按鈕</n-button>
    </n-card>
  </n-space>
</template>
```

---

## 📝 開發建議

1. **元件化開發**: 將可重用的 UI 拆分至 `components/` 目錄
2. **Layout 分離**: 使用 `layouts/` 管理不同頁面版型
3. **型別安全**: 充分利用 TypeScript 進行型別檢查
4. **樣式一致性**: 優先使用 Tailwind utilities 和 Naive UI 元件
5. **效能優化**: 使用 Vue 3 的 `<script setup>` 和 Composition API

---

## 🔧 常用指令

```bash
# 開發模式
npm run dev

# 建置生產版本
npm run build

# 預覽建置結果
npm run preview

# 型別檢查
npm run type-check
```
