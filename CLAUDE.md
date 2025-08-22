# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 语言

用中文交互

## Project Overview

This is a Texas Hold'em multiplayer online poker game project ("德州扑克 多人联网游戏") with a Python FastAPI backend and TypeScript/Next.js/Phaser 3 frontend.

**Current Status:** Early development stage - basic project structure exists but core functionality is not yet implemented.

## Development Commands

### Backend (Python FastAPI)
使用 uv 管理项目

开发环境设置：
- `uv sync` - 安装依赖
- `uv add <package>` - 添加新依赖
- `uv add --dev <package>` - 添加开发依赖

运行项目：
- `uv run main.py` - 启动开发服务器
- `uv run uvicorn main:app --reload` - 启动 FastAPI 开发服务器（热重载）
- `uv run uvicorn main:app --host 0.0.0.0 --port 8000` - 生产环境启动

代码质量检查：
- `uv run ruff check` - 代码检查
- `uv run ruff format` - 代码格式化
- `uv run mypy .` - 类型检查

### Frontend (TypeScript/Next.js/Phaser 3)

使用 pnpm 管理项目

开发环境设置：
- `pnpm install` - 安装依赖
- `pnpm add <package>` - 添加依赖
- `pnpm add -D <package>` - 添加开发依赖

运行项目：
- `pnpm dev` - 启动开发服务器（http://localhost:3000）
- `pnpm build` - 构建生产版本
- `pnpm start` - 启动生产服务器
- `pnpm preview` - 预览构建结果

代码质量检查：
- `pnpm lint` - ESLint 检查
- `pnpm lint:fix` - 自动修复 lint 问题
- `pnpm type-check` - TypeScript 类型检查
- `pnpm format` - Prettier 格式化


## Architecture

### Planned Architecture
- **Backend:** Python FastAPI providing REST API and WebSocket endpoints for real-time multiplayer functionality
- **Frontend:** Next.js (React) application with TypeScript for type safety and Phaser 3 for game rendering
- **Communication:** WebSocket connections for real-time game state synchronization between players
- **Game Logic:** Server-authoritative Texas Hold'em poker implementation

### Project Structure
```
/
├── main.py              # Backend entry point (currently basic script)
├── pyproject.toml       # Python project configuration
├── .python-version      # Python 3.12
├── frontend/            # Next.js frontend application
└── readme.md           # Project description (Chinese)
```

### Key Development Areas
1. **Backend Implementation:** FastAPI application with poker game logic, user management, and WebSocket support
2. **Frontend Game UI:** React components for poker table, cards, betting interface
3. **Game Rendering:** Phaser 3 integration for smooth card animations and table visualization
4. **Real-time Communication:** WebSocket implementation for multiplayer synchronization
5. **Game State Management:** Server-side game state with client-side prediction for responsive gameplay

## Configuration Notes

- Python version: 3.12 (specified in .python-version)
- Frontend uses TypeScript with Next.js App Router
- Project name: "poker-link"
- No database configuration yet - will need to be added for user and game persistence