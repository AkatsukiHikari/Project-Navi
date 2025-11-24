# 内容审核服务 (Content Moderator)

## 概述

基于 AI 的内容审核服务，用于检测和过滤不当内容、垃圾信息和违规内容。

## 功能特性

- 🛡️ 评论内容审核
- 🚫 敏感词过滤
- 🤖 垃圾信息检测
- ⚠️ 违规内容识别
- 📊 内容风险评分
- 🔍 多语言支持（日语、英语、中文）

## 技术栈

- Anthropic Claude API - AI 内容分析
- FastAPI - Web 框架
- Better Profanity - 敏感词过滤
- AsyncPG - 数据库连接

## 安装

```bash
cd services/content-moderator
poetry install
```

## 配置

创建 `.env` 文件：

```env
ANTHROPIC_API_KEY=your_api_key_here
DATABASE_URL=postgresql://user:password@host:port/database
```

## 运行

```bash
poetry run uvicorn src.content_moderator.main:app --reload --port 8002
```

## API 文档

启动服务后访问: http://localhost:8002/docs

## 审核规则

- 暴力和仇恨言论
- 色情和不雅内容
- 个人信息泄露
- 垃圾广告
- 虚假信息
