# 采集服务 (Scraper Service)

## 概述

这是 Project Navi 的内容采集服务，用于从互联网上自动抓取相关的资讯、攻略等数据。

## 功能特性

- 🌐 从多个源抓取日本相关的新闻和资讯
- 📝 自动提取和解析内容
- 🔄 定时任务调度
- 💾 直接写入 Supabase 数据库
- 🛡️ 反爬虫和错误处理机制

## 技术栈

- Python 3.11+
- requests / httpx - HTTP 客户端
- BeautifulSoup4 / lxml - HTML 解析
- APScheduler - 任务调度
- psycopg2 / asyncpg - PostgreSQL 数据库连接
- python-dotenv - 环境变量管理

## 目录结构

```
scraper/
├── scrapers/          # 各类爬虫实现
│   ├── __init__.py
│   ├── base.py       # 基础爬虫类
│   ├── news.py       # 新闻爬虫
│   ├── guide.py      # 攻略爬虫
│   └── event.py      # 活动爬虫
├── models/           # 数据模型
│   ├── __init__.py
│   └── entities.py   # 数据实体定义
├── utils/            # 工具函数
│   ├── __init__.py
│   ├── parser.py     # 内容解析工具
│   ├── db.py         # 数据库工具
│   └── logger.py     # 日志工具
├── config/           # 配置文件
│   ├── __init__.py
│   └── settings.py   # 配置管理
├── main.py           # 主程序入口
├── requirements.txt  # Python 依赖
└── .env.example      # 环境变量示例
```

## 安装

```bash
cd services/scraper
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

## 配置

复制 `.env.example` 为 `.env` 并填入相关配置：

```bash
cp .env.example .env
```

## 运行

```bash
# 运行单次采集
python main.py

# 运行定时任务
python main.py --schedule
```

## 数据流

```
互联网源 → 爬虫采集 → 内容解析 → 数据清洗 → 存入 Supabase
```
