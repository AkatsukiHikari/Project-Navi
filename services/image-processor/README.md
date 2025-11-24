# 图像处理服务 (Image Processor)

## 概述

提供图像处理功能的微服务，支持图像压缩、裁剪、格式转换、水印添加等操作。

## 功能特性

- 🖼️ 图像压缩和优化
- ✂️ 图像裁剪和缩放
- 🔄 格式转换（JPG, PNG, WebP等）
- 🎨 图像滤镜和效果
- 💧 水印添加
- 📊 图像信息提取

## 技术栈

- FastAPI - Web 框架
- Pillow - 图像处理
- OpenCV - 高级图像处理
- Uvicorn - ASGI 服务器

## 安装

```bash
cd services/image-processor
poetry install
```

## 运行

```bash
poetry run uvicorn src.image_processor.main:app --reload
```

## API 文档

启动服务后访问: http://localhost:8000/docs
