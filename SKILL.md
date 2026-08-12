---
name: ai-fullstack-engineer
description: >-
  AI 全栈应用工程师技能库：覆盖从 API 设计、数据库、后端架构、FastAPI 开发，到前端组件、CSS
  布局、Web 性能、浏览器调试的全链路能力，并内置 AI-native 全栈工作流（契约优先、前后端并行、类型安全、AI
  辅助调试与一键脚手架）。触发词："全栈"、"搭一个应用"、"前后端一起"、"设计 API"、"数据库
  Schema"、"FastAPI"、"React/Vue 组件"、"CSS 布局"、"性能优化"、"Lighthouse"、"浏览器调试"、"脚手架"、"Next.js"、"App Router"、"Tailwind 审计"。
agent_created: true
metadata:
  version: 1.0.0
  category: 全栈开发
  difficulty: 专家
  architecture: superpower
---

# AI 全栈应用工程师 (AI Full-Stack Application Engineer)

> 把 AI 编程助手变成一名能独立扛下整条应用交付链路的全栈搭档：从后端 API、数据库、架构，到前端组件、样式、性能与调试，并用 AI-native 工作流把前后端打通成一条流水线。

本技能由 `backend-developer` 与 `frontend-engineer` 整合而来，采用 **superpower 架构**：`SKILL.md` 只做路由，深层 playbook 放在 `references/` 中**按需加载**，细粒度能力放在 `skills/` 子技能，确定性任务交给 `scripts/`，可复用模板放在 `assets/`。

## 何时使用

在以下任一情况触发本技能：

- 需要从零**搭建一个完整应用**（前端 + 后端 + 数据库）
- 需要**设计 API**（REST/GraphQL）、定义接口契约、做版本管理
- 需要**设计数据库 Schema**、选型 ORM、优化慢查询与索引
- 需要用 **FastAPI / Node.js** 实现后端服务、依赖注入、异步 API
- 需要开发 **React / Vue 组件**、用 Tailwind/CSS Grid 做响应式布局
- 需要**用 Next.js（App Router）**搭建前端：布局/页面、服务端/客户端组件、路由处理器、数据缓存
- 需要**优化 Web 性能**（Core Web Vitals、bundle、缓存、运行时）
- 需要**用 Chrome DevTools 自动化**调试、截图、性能审计
- 需要**审计 Tailwind CSS**（未用类/purge、v3→v4 迁移、配置漂移、冲突类名）
- 需要把复杂任务拆成**多个专职 Agent 协作**（多智能体编排 / orchestrator / 子 Agent 流水线）
- 需要**一键生成全栈脚手架**、从 OpenAPI 生成类型安全的 TS 客户端
- 需要一条** AI-native 全栈工作流**把前后端并联交付

## 能力索引（超级技能路由）

本技能采用渐进式加载（progressive disclosure）。`SKILL.md` 仅作路由，**按需**读取下列 `references/` 中的完整 playbook，避免一次性占满上下文。

| 任务 | 读取 / 调用 | 关键词（grep 线索） |
|------|------------|---------------------|
| AI-native 全栈工作流（脚手架→契约→并行→联调→部署） | `references/fullstack-workflow.md` | 全栈, workflow, 脚手架, 联调, 类型安全, 并行, AI 工作流 |
| 后端深度 playbook（API + 架构模式 + 数据 + FastAPI） | `references/backend-playbook.md` | 后端, api, 架构, orm, 索引, fastapi, 异步, repository |
| 前端深度 playbook（组件 + CSS + 调试 + 性能） | `references/frontend-playbook.md` | 前端, 组件, css, grid, 性能, cwv, devtools, 响应式 |
| 多智能体编排 playbook（决策树 + 框架选型 + 通信 + 踩坑清单） | `references/multi-agent-orchestration-playbook.md` | 多智能体, 编排, 决策树, crewai, langgraph, autogen, swarm, 通信, 聚合, 踩坑 |
| API 与接口设计（细粒度调用） | `skills/api-design/SKILL.md` | rest, graphql, 版本, 错误码, openapi, 契约 |
| 后端架构模式（细粒度调用） | `skills/backend-patterns/SKILL.md` | 分层, express, 中间件, 安全, 限流, circuit breaker |
| 数据库设计（细粒度调用） | `skills/database-design/SKILL.md` | schema, 索引, 范式, 迁移, 主键, 软删除 |
| FastAPI Python 开发（细粒度调用） | `skills/fastapi-python/SKILL.md` | fastapi, pydantic, async, 依赖注入, 中间件 |
| 现代 Web 组件开发（细粒度调用） | `skills/component-builder/SKILL.md` | 组件, react, vue, modal, 表单, view transitions |
| Tailwind/CSS 高级布局（细粒度调用） | `skills/css-master/SKILL.md` | tailwind, grid, flexbox, 圣杯布局, 容器查询, 响应式 |
| Web 性能优化（细粒度调用） | `skills/web-performance/SKILL.md` | lcp, inp, cls, bundle, 缓存, lighthouse, 代码分割 |
| Chrome DevTools 自动化（细粒度调用） | `skills/browser-devtools/SKILL.md` | devtools, 截图, 快照, 审计, 自动化, lighthouse |
| Next.js App Router 范式（细粒度调用） | `skills/nextjs-app-router/SKILL.md` | next.js, app router, 服务端组件, 客户端组件, 路由处理器, server action, 缓存, rsc |
| Tailwind CSS 审计（细粒度调用） | `skills/tailwind-audit/SKILL.md` | tailwind, 审计, purge, 未用类, v3迁移, 配置漂移, 冲突类名, @apply |
| 多智能体编排（细粒度调用） | `skills/multi-agent-orchestration/SKILL.md` | 多智能体, multi-agent, 编排, orchestrator, 子agent, 协作, crewai, langgraph, 共识, 并行 |

> 路由规则：先判断任务属于「后端 / 前端 / 全栈流程」哪一类；先做方法论决策就读 `references/`，要落地某个具体技能就直接调 `skills/` 对应子技能。

## 内置脚本（确定性、可重复执行）

放在 `scripts/`，优先用脚本处理重复/确定性任务，而非每次重写代码：

- `scripts/scaffold_fullstack.py --name <项目> --be fastapi|express --fe react|vue` — 生成可直接运行的全栈骨架（后端 + 前端 + 数据库占位 + README）
- `scripts/gen_types_from_openapi.py --spec openapi.json --out src/api/types.ts` — 从 OpenAPI 规范生成 TS 接口，保证前后端类型安全

运行示例：

```bash
python3 scripts/scaffold_fullstack.py --name my-saas --be fastapi --fe react
python3 scripts/gen_types_from_openapi.py --spec openapi.json --out src/api/types.ts
```

## 模板资源

`assets/` 提供可直接套用的配置与模板：

- `assets/openapi-spec-template.yaml` — 起步版 OpenAPI 3.0 契约模板（契约优先工作流入口）
- `assets/docker-compose.fullstack.yaml` — 前端 + 后端 + 数据库一体编排模板
- `assets/ci-fullstack.yml` — GitHub Actions 前后端联合构建/测试 CI 模板

## 核心原则（始终遵循）

1. **契约优先**：先定 API 契约（OpenAPI），前后端并行，用类型安全消除联调摩擦。
2. **前后端一视同仁**：UI 不只是"能显示"，API 不只是"能跑"——两端都要稳定、可维护、可观测。
3. **渐进式加载**：先读路由表与对应 `references/`，再动手；不凭记忆猜框架命令与最新 Web API。
4. **脚本确定性**：脚手架、类型生成这类重复活交给 `scripts/`，产物可复现、可评审。
5. **安全与性能内建**：输入验证、限流、索引、Core Web Vitals 是基本功，不是事后补丁。
6. **明确边界**：生产环境调优、微服务治理、CDN 选型等专项，结果以报告呈现，不做拍板替代。

## 与其他技能协作

- 需要**测试**（单测 / E2E / 覆盖率）→ 调用 `software-tester`
- 需要**安全审计**（密钥、依赖、OWASP）→ 调用 `security-guardian`
- 需要**运维部署**（CI/CD、容器、IaC）→ 调用 `devops-engineer`
- 需要**文档**（README、API 文档、架构图）→ 调用 `docs-writer`
