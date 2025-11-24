# Project Navi

**Project Navi** 是一款综合性的移动和Web应用程序，旨在为在日本的外国居民和游客提供服务。无论您是游客、学生还是职场人士，这个应用都将是您在日本生活的终极指南。

## 项目愿景

我们的目标是为在日本的国际社群创建一个一站式平台，提供必要信息，促进社区互动，让日常生活更加便捷和愉快。

## 核心功能

- **新闻与热点：** 及时了解与外国人相关的最新新闻和热门事件
- **活动平台：** 发现、创建和加入各种活动，与社区建立联系
- **精选攻略：** 探索详尽的攻略，涵盖从必吃餐厅、娱乐场所到基本旅行技巧的方方面面
- **省钱中心：** 查找省钱技巧、优惠信息和独家优惠券

## 应用架构

包含两个主要的应用：

- **`apps/expo` (移动端App):** 面向用户的主要应用程序，支持 iOS 和 Android。用户将通过此应用访问所有核心功能
- **`apps/nextjs` (Web/管理后台):** 基于Web的应用程序，将作为管理平台内容的后台，用于管理内容、用户和活动

## 技术栈

### 前端应用

- **Monorepo:** [Turborepo](https://turbo.build/repo)
- **包管理器:** [pnpm](https://pnpm.io/)
- **移动端:** [React Native](https://reactnative.dev/) 与 [Expo](https://expo.dev/)
- **Web端:** [Next.js](https://nextjs.org/) 15
- **API:** [tRPC](https://trpc.io/)
- **数据库:** [Drizzle ORM](https://orm.drizzle.team/) (后端为 Supabase)
- **认证:** [better-auth](https://github.com/Better-Stack/better-auth)
- **UI:** [Shadcn UI](https://ui.shadcn.com/) 和 [Tailwind CSS](https://tailwindcss.com/)

### 后端服务

- **语言:** Python 3.11+
- **依赖管理:** [Poetry](https://python-poetry.org/)
- **Web框架:** [FastAPI](https://fastapi.tiangolo.com/)
- **AI:** [Anthropic Claude API](https://www.anthropic.com/)
- **图像处理:** Pillow, OpenCV
- **爬虫:** requests, BeautifulSoup4

## 目录结构

```
project-navi/
├── apps/                          # 应用程序
│   ├── expo/                      # 📱 移动端 App (React Native + Expo)
│   │   ├── src/
│   │   │   ├── app/               # Expo Router 页面
│   │   │   ├── components/        # UI 组件
│   │   │   ├── screens/           # 功能页面
│   │   │   │   ├── home/          # 首页
│   │   │   │   ├── news/          # 新闻列表
│   │   │   │   ├── events/        # 活动列表
│   │   │   │   ├── guides/        # 攻略列表
│   │   │   │   ├── coupons/       # 优惠券中心
│   │   │   │   ├── profile/       # 个人中心
│   │   │   │   └── auth/          # 登录注册
│   │   │   ├── navigation/        # 导航配置
│   │   │   ├── hooks/             # 自定义 Hooks
│   │   │   ├── services/          # API 服务
│   │   │   ├── types/             # TypeScript 类型定义
│   │   │   ├── constants/         # 常量配置
│   │   │   ├── styles/            # 样式文件
│   │   │   └── utils/             # 工具函数
│   │   └── assets/                # 静态资源
│   │
│   └── nextjs/                    # 🖥️ Web 管理后台 (Next.js 15)
│       ├── src/
│       │   ├── app/
│       │   │   ├── (admin)/       # 管理后台路由组
│       │   │   │   ├── dashboard/ # 仪表盘
│       │   │   │   ├── news/      # 新闻管理
│       │   │   │   ├── events/    # 活动管理
│       │   │   │   ├── guides/    # 攻略管理
│       │   │   │   ├── coupons/   # 优惠券管理
│       │   │   │   ├── categories/# 分类管理
│       │   │   │   ├── users/     # 用户管理
│       │   │   │   └── settings/  # 系统设置
│       │   │   ├── api/           # API 路由
│       │   │   └── _components/   # 页面组件
│       │   ├── components/        # 共享组件
│       │   ├── hooks/             # 自定义 Hooks
│       │   ├── lib/               # 工具库
│       │   ├── types/             # TypeScript 类型
│       │   ├── auth/              # 认证相关
│       │   └── trpc/              # tRPC 客户端
│       └── public/                # 静态文件
│
├── packages/                      # 共享包 (Monorepo)
│   ├── api/                       # 📦 tRPC API
│   │   └── src/
│   │       └── router/            # API 路由定义
│   │
│   ├── db/                        # 🗄️ 数据库 (Drizzle ORM + Supabase)
│   │   └── src/
│   │       └── schema/            # 数据库表结构
│   │
│   ├── auth/                      # 🔐 认证 (better-auth)
│   │   └── src/
│   │
│   ├── ui/                        # 🎨 共享 UI 组件
│   │   └── src/
│   │
│   └── validators/                # ✅ 数据验证 (Zod)
│       └── src/
│
├── services/                      # 🐍 Python 微服务
│   ├── scraper/                   # 内容采集服务
│   │   ├── src/scraper/
│   │   │   ├── scrapers/          # 爬虫实现
│   │   │   ├── models/            # 数据模型
│   │   │   ├── utils/             # 工具函数
│   │   │   └── config/            # 配置管理
│   │   ├── logs/                  # 日志文件
│   │   ├── pyproject.toml         # Poetry 配置
│   │   └── .env.example           # 环境变量示例
│   │
│   ├── image-processor/           # 图像处理服务 (FastAPI)
│   │   ├── src/image_processor/
│   │   │   ├── api/               # FastAPI 路由
│   │   │   ├── services/          # 处理服务
│   │   │   └── utils/             # 工具函数
│   │   └── pyproject.toml
│   │
│   ├── ai-analyzer/               # AI 分析服务 (Claude API)
│   │   ├── src/ai_analyzer/
│   │   │   ├── api/               # FastAPI 路由
│   │   │   ├── services/          # AI 服务
│   │   │   ├── models/            # 数据模型
│   │   │   └── utils/             # 工具函数
│   │   └── pyproject.toml
│   │
│   ├── content-moderator/         # 内容审核服务
│   │   ├── src/content_moderator/
│   │   │   ├── api/               # FastAPI 路由
│   │   │   ├── services/          # 审核服务
│   │   │   ├── models/            # 数据模型
│   │   │   └── utils/             # 工具函数
│   │   └── pyproject.toml
│   │
│   └── README.md                  # 服务说明文档
│
├── docs/                          # 📚 项目文档
│   ├── api/                       # API 文档
│   ├── architecture/              # 架构设计文档
│   └── deployment/                # 部署文档
│
├── tooling/                       # 🛠️ 开发工具配置
│   ├── eslint/                    # ESLint 配置
│   ├── prettier/                  # Prettier 配置
│   ├── typescript/                # TypeScript 配置
│   └── tailwind/                  # Tailwind CSS 配置
│
├── turbo.json                     # Turborepo 配置
├── package.json                   # 根项目配置
├── pnpm-workspace.yaml            # pnpm 工作区配置
└── README.md                      # 项目说明文档
```

## 数据流架构

### 数据写入流程

```
1. 自动采集: 互联网 → Python Scraper → Supabase 数据库
2. 手动录入: Web 管理后台 → tRPC API → Supabase 数据库
3. 内容处理: 用户内容 → AI Analyzer/Image Processor → Supabase
4. 内容审核: 用户评论 → Content Moderator → Supabase
```

### 数据读取流程

```
Supabase 数据库 → tRPC API → 移动端 App / Web 管理后台
```

### 服务通信

```
┌─────────────┐      ┌──────────────┐      ┌─────────────┐
│   移动端    │◄────►│   tRPC API   │◄────►│   Supabase  │
│   (Expo)    │      │  (@acme/api) │      │  (Database) │
└─────────────┘      └──────────────┘      └─────────────┘
                            ▲                      ▲
                            │                      │
┌─────────────┐            │                      │
│  Web 管理   │────────────┘                      │
│  (Next.js)  │                                   │
└─────────────┘                                   │
                                                  │
┌─────────────────────────────────────────────────┘
│
│  Python 微服务
├─ Scraper (采集)
├─ Image Processor (图像处理)
├─ AI Analyzer (AI 分析)
└─ Content Moderator (内容审核)
```

## 快速上手

### 前置要求

- Node.js v22.21.0+
- pnpm v10.19.0+
- Python 3.11+
- Poetry 1.7+

### 安装依赖

#### 1. 安装 Node.js 依赖

```bash
pnpm install
```

#### 2. 安装 Python 服务依赖

```bash
# 安装 Poetry
curl -sSL https://install.python-poetry.org | python3 -

# 安装各服务依赖
cd services/scraper && poetry install
cd ../image-processor && poetry install
cd ../ai-analyzer && poetry install
cd ../content-moderator && poetry install
```

### 环境配置

#### 1. 前端应用环境变量

将 `.env.example` 文件复制为新的 `.env` 文件，并填入您的 Supabase 数据库和认证提供商所需的环境变量。

```bash
cp .env.example .env
```

#### 2. Python 服务环境变量

每个 Python 服务都需要配置各自的 `.env` 文件：

```bash
cp services/scraper/.env.example services/scraper/.env
cp services/ai-analyzer/.env.example services/ai-analyzer/.env
cp services/content-moderator/.env.example services/content-moderator/.env
cp services/image-processor/.env.example services/image-processor/.env
```

### 数据库设置

推送 Drizzle schema 到您的 Supabase 数据库：

```bash
pnpm db:push
```

查看数据库（可选）：

```bash
pnpm db:studio
```

### 运行开发服务器

#### 前端应用

```bash
# 同时启动所有前端应用
pnpm dev

# 或单独启动
pnpm dev:next    # 只启动 Next.js
```

#### Python 服务

```bash
# 采集服务（定时任务）
cd services/scraper
poetry run python src/scraper/main.py

# 图像处理服务
cd services/image-processor
poetry run uvicorn src.image_processor.main:app --reload

# AI 分析服务
cd services/ai-analyzer
poetry run uvicorn src.ai_analyzer.main:app --reload --port 8001

# 内容审核服务
cd services/content-moderator
poetry run uvicorn src.content_moderator.main:app --reload --port 8002
```

## 开发命令

### 前端应用

```bash
pnpm build          # 构建所有应用
pnpm typecheck      # 类型检查
pnpm lint           # 代码检查
pnpm lint:fix       # 自动修复代码问题
pnpm format         # 格式化代码检查
pnpm format:fix     # 格式化并修复代码
pnpm clean          # 清理 node_modules
pnpm clean:workspaces  # 清理所有工作区
```

### Python 服务

在各服务目录下：

```bash
poetry run black .           # 格式化代码
poetry run ruff check .      # 代码检查
poetry run mypy .            # 类型检查
poetry run pytest            # 运行测试
```

## 部署

详细的部署文档请参考 `docs/deployment/` 目录。

### 推荐的部署方案

- **前端应用:** Vercel / Railway
- **Python 服务:** Docker + Railway / Google Cloud Run
- **数据库:** Supabase (已包含)


## 相关文档

- [Services 服务说明](./services/README.md)
- [API 文档](./docs/api/)
- [架构设计](./docs/architecture/)
- [部署文档](./docs/deployment/)
