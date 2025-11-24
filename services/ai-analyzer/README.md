# AI 分析服务 (AI Analyzer)

## 概述

基于 Claude API 的 AI 分析服务，提供内容分析、摘要生成、标签提取等功能。

## 功能特性

- 📝 内容摘要生成
- 🏷️ 自动标签提取
- 🌐 内容翻译
- 📊 情感分析
- 🔍 关键词提取
- 📋 内容分类

## 技术栈

- Anthropic Claude API - AI 模型
- FastAPI - Web 框架
- LangChain - AI 应用框架
- Pydantic - 数据验证

## 安装

```bash
cd services/ai-analyzer
poetry install
```

## 配置

创建 `.env` 文件：

```env
ANTHROPIC_API_KEY=your_api_key_here
OPENAI_API_KEY=your_openai_key_here  # 可选
```

## 运行

```bash
poetry run uvicorn src.ai_analyzer.main:app --reload --port 8001
```

## API 文档

启动服务后访问: http://localhost:8001/docs
