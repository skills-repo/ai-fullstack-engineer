# 前端深度 Playbook

> 整合自 `component-builder`、`css-master`、`web-performance`、`browser-devtools` 四份子技能。本文件是前端决策与落地的深层参考，按需读取。

## 1. 现代 Web 组件开发（component-builder）

### 原则：优先原生 Web API

Web 平台演进极快，训练数据中的模式可能已过时。**实现前先搜索最新实践**：

```bash
npx -y modern-web-guidance search "accessible modal component"
```

优先用原生能力，避免无谓的大依赖：

- **布局/弹层**：`:has()` 选择器、anchor positioning、container queries 已广泛支持。
- **滚动与动效**：View Transitions API（SPA 路由过渡）、Scroll-driven animations、content-visibility（跳过离屏渲染）。
- **表单**：原生自动填充、高级 input 类型、`requestSubmit()`。
- **系统 API**：WebUSB、WebSocket 同步、WebAssembly 按场景引入。

### 组件开发清单（React/Vue 通用）

```
[ ] 语义化标签（button/dialog/main），可键盘操作
[ ] 状态最小化，派生状态用 useMemo/computed
[ ] 组件契约清晰：props 类型 + 默认值 + 必填标注
[ ] 副作用收敛到 useEffect/生命周期，避免重复请求
[ ] 跨浏览器兼容最后验证（见第 4 节 devtools）
```

> 具体调用：`skills/component-builder`。

## 2. Tailwind / CSS 高级布局（css-master）

### 选 Grid 还是 Flexbox

| 需求 | 选 |
|------|----|
| 二维布局（行+列，如仪表盘） | CSS Grid |
| 一维流式排列（导航、工具栏） | Flexbox |
| 组件级响应式（不依赖视口） | Container Queries（`@container`） |

### 常用模式

- **圣杯布局**：`grid-template-areas` 定义 header/main/footer + 侧栏，移动端塌成单列。
- **自适应卡片网格**：`grid-cols-[repeat(auto-fit,minmax(240px,1fr))]`。
- **响应式断点**：移动优先，逐级增强；用 `aspect-ratio` 固定媒体比例避免 CLS。
- **容器查询**：组件内 `@container` 让卡片在侧栏窄、主区宽时呈现不同布局。

> 具体调用：`skills/css-master`。

## 3. Web 性能优化（web-performance）

### 优先级：LCP → bundle → 运行时 → 缓存

1. **LCP（最大内容绘制）**：关键图片用 `fetchpriority="high"`、前置预连接（`<link rel=preconnect>`）、避免阻塞渲染的 CSS/JS。
2. **INP（交互延迟）**：拆分长任务、事件处理防抖/节流、`requestAnimationFrame` 做动画、Web Worker 卸载重计算。
3. **CLS（布局偏移）**：图片/广告位预留尺寸、`font-display: swap` + 尺寸回退。
4. **Bundle 分析**：`vite build --report` / webpack-bundle-analyzer，tree-shaking、动态 `import()` 懒加载、按路由分割。
5. **缓存**：`Cache-Control` 长缓存 + 内容哈希文件名；Service Worker 做离线/预缓存。

### 工作流

```
Lighthouse 取基线(LCP/INP/CLS/TBT) → 分析 bundle + 网络瀑布 → 按优先级优化 → 复测验证改善
```

> 具体调用：`skills/web-performance`。

## 4. Chrome DevTools 自动化（browser-devtools）

用 `chrome-devtools-axi` 把调试变成可复现脚本：

```bash
npx -y chrome-devtools-axi open http://localhost:5173
# 基于 a11y 快照的 ref 交互：click @ref / fill @ref "text"
npx -y chrome-devtools-axi lighthouse http://localhost:5173   # 性能审计
```

能力：页面导航、快照、截图、元素交互、JS 执行（`eval`）、网络分析、Lighthouse 审计、设备模拟。

适用：网页自动化测试、内容提取截图、性能审计、浏览器行为调试。**不替代** Playwright/Cypress 的完整 E2E 框架（复杂流程用专业工具，配合 `software-tester`）。

> 具体调用：`skills/browser-devtools`。

## 前端决策速查

- 新组件前 → 先 `modern-web-guidance search`，优先原生 API。
- 复杂布局 → Grid（二维）/ Flexbox（一维）/ Container Queries（组件级响应式）。
- 上线前 → Lighthouse 跑 CWV，按 LCP→INP→CLS 顺序修。
- 调试 → `chrome-devtools-axi` 自动化，结果可回放。

## 与全栈流程衔接

- 前端类型来自后端契约：`scripts/gen_types_from_openapi.py`（见 `references/fullstack-workflow.md`）。
- 组件调用后端：用生成的类型安全的 `api/client.ts`，编译期拦截字段错位。
- 性能门禁接 `assets/ci-fullstack.yml`。
