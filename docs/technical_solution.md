# 通海南洋 (TongHai Nanyang) 项目技术方案

## 1. 项目概述
本项目“通海南洋数字化平台”旨在为企业家提供跨境商业与资产规划服务。当前代码库实现了该平台的前端展示部分，支持多语言（简/繁/英）切换，展示核心团队、服务板块及行业解决方案。

> **注意**：项目当前实际代码基于 **Vue 3** 技术栈实现，与 *Master PRD (docs/new.md)* 中规划的 Next.js 架构不同。本方案基于**当前实际代码库**编写。

## 2. 技术栈架构 (Technology Stack)

| 模块 | 技术选型 | 说明 |
| :--- | :--- | :--- |
| **核心框架** | **Vue 3.4** | 采用 Composition API 风格开发 |
| **构建工具** | **Vite 5.0** | 高性能前端构建与开发服务器 |
| **开发语言** | **TypeScript 5.3** | 强类型支持，提高代码健壮性 |
| **UI 组件库** | **Element Plus 2.5** | 企业级 UI 组件库 |
| **状态管理** | **Pinia 2.1** | 轻量级 Vue 状态管理库 |
| **路由管理** | **Vue Router 4.2** | 页面路由管理 |
| **国际化** | **Vue I18n 11.2** | 支持 中(简/繁)/英 多语言切换 |

## 3. 项目结构 (Project Structure)

```text
src/
├── assets/          # 静态资源 (图片, 字体等)
├── components/      # 公共 UI 组件
├── i18n/            # 国际化语言包配置
├── layouts/         # 页面布局组件
├── router/          # 路由配置
├── stores/          # Pinia 状态管理
├── views/           # 页面视图
│   ├── Home.vue        # 首页
│   ├── About.vue       # 关于我们
│   ├── Team.vue        # 团队介绍
│   ├── Services.vue    # 服务体系
│   ├── Industries.vue  # 行业方案
│   └── Contact.vue     # 联系我们
├── App.vue          # 根组件
└── main.ts          # 入口文件
```

## 4. 核心功能模块 (Core Modules)

### 4.1 多语言支持 (I18n Strategy)
项目内置了完善的国际化支持，配置文件位于 `src/i18n`。
- **支持语言**: 简体中文 (CN), 繁体中文 (TW), 英语 (EN)。
- **实现方式**: 使用 `vue-i18n` 进行文本替换和动态切换。

### 4.2 业务页面 (Business Views)
- **门户官网**: 展示品牌形象、核心价值。
- **服务体系**: 详细介绍出海、身份规划、财富架构等六大业务板块。
- **专家团队**: 展示创始人及顾问团队信息（对应 PRD 中的核心团队介绍）。

## 5. 开发与部署 (Development & Deployment)

### 开发环境
- 依赖管理: `npm` 或 `yarn`
- 启动命令: `npm run dev` (通过 Vite 启动本地服务)

### 构建部署
- 构建命令: `npm run build`
- 输出目录: `dist/`
- 部署方式: 静态站点托管 (Static Hosting) 或 Nginx 反向代理。

## 6. 后续建议
- **架构对齐**: 鉴于 `docs/new.md` 提及 Next.js + Strapi 架构，建议确认是否需要迁移至 Next.js 以获得更好的 SEO 支持和服务端渲染能力，或者继续基于 Vue 3 完善 SPA 应用。
- **CMS 集成**: 当前内容主要硬编码或前端管理，建议后续按 PRD 规划接入 Headless CMS (如 Strapi) 以管理团队和内容数据。
