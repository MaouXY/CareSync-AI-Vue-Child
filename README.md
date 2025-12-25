# CareSync-AI-Vue-Child

基于 Vue 3 + TypeScript + Vite 的 AI 数字人陪伴系统，专为儿童用户设计。

## 项目概述

CareSync-AI-Vue-Child 是一个集成了智能对话、实时视频交互和情感陪伴功能的现代化前端应用。通过 WebRTC 技术实现与 AI 数字人的实时交互，为儿童提供安全、有趣的 AI 互动体验。

## 核心功能

### AI 数字人陪伴
- 实时视频对话：集成 WebRTC 技术，实现与 AI 数字人的实时视频交互
- 智能语音交互：支持语音输入和 AI 语音回复
- 情感识别：AI 能够根据用户输入识别情感状态并做出相应回应
- 连接状态监控：实时显示与 AI 数字人的连接状态

### 智能聊天系统
- 多轮对话：支持上下文记忆的连续对话
- Markdown 渲染：支持富文本消息显示
- 思考过程展示：可展开查看 AI 的思考过程
- 消息历史：本地存储聊天记录，支持历史消息查看
- 快捷回复：提供智能快捷回复建议

### 用户界面
- 响应式设计：适配多种屏幕尺寸
- 直观操作：简洁友好的用户界面
- 实时状态：显示发送状态、打字指示器等
- 主题定制：针对儿童用户的界面设计

## 技术栈

### 前端框架
- **Vue 3**：使用 Composition API 构建现代化前端应用
- **TypeScript**：提供类型安全和更好的开发体验
- **Vite**：快速的构建工具和开发服务器
- **Pinia**：Vue 状态管理库
- **Vue Router**：客户端路由管理

### UI 和样式
- **Tailwind CSS**：实用优先的 CSS 框架
- **Arco Design**：企业级 UI 组件库
- **Three.js**：3D 图形渲染支持

### 核心依赖
```json
{
  "vue": "^3.5.17",
  "pinia": "^3.0.4",
  "vue-router": "^4.6.3",
  "axios": "^1.13.2",
  "marked": "^16.3.0",
  "three": "^0.180.0"
}
```

## 项目结构

```
src/
├── api/              # API 接口层
│   ├── auth.ts       # 认证相关 API
│   ├── chat.ts       # 聊天相关 API
│   ├── http.ts       # HTTP 请求封装
│   └── index.ts      # API 统一导出
├── components/       # 可复用组件
│   ├── ChatRoom.vue  # 聊天房间组件
│   ├── HelloWorld.vue
│   └── HomePage.vue
├── layout/           # 布局组件
│   └── BaseLayout.vue
├── router/           # 路由配置
│   └── index.js
├── services/         # 业务逻辑层
│   └── ChatService.ts
├── store/            # 状态管理
│   ├── auth.ts       # 认证状态
│   └── index.ts
├── types/            # 类型定义
│   └── auth.ts
├── views/            # 页面视图
│   ├── BookSearchView.vue
│   ├── ChatView.vue  # 聊天页面
│   ├── LitHealView.vue
│   ├── LiveView.vue  # 直播页面
│   └── LoginView.vue # 登录页面
├── App.vue           # 根组件
└── main.ts           # 应用入口
```

## 快速开始

### 安装依赖
```bash
npm install
```

### 开发模式
```bash
npm run dev
```

### 构建生产版本
```bash
npm run build
```

### 预览构建结果
```bash
npm run preview
```

## 主要功能模块

### 1. 登录系统 (LoginView)
- 用户身份验证
- 儿童用户信息管理
- 安全登录机制

### 2. 聊天界面 (ChatView)
- 文本消息交互
- 消息历史管理
- 快捷回复功能
- Markdown 消息渲染

### 3. 数字人陪伴 (LiveView)
- WebRTC 视频连接
- AI 数字人实时对话
- 语音交互支持
- 连接状态管理
- 消息气泡显示

## 特色功能

### 思考过程展示
AI 回复时会显示思考过程，帮助用户理解 AI 的推理逻辑：
```typescript
interface Message {
  id: string;
  content: string;
  sender: 'user' | 'ai';
  timestamp: Date;
  thinking?: string; // AI 思考过程
}
```

### 本地存储
- 聊天记录自动保存到 localStorage
- 页面刷新后历史消息不丢失
- 支持清空历史对话

### WebRTC 集成
- 实时音视频通信
- 自动重连机制
- 媒体流管理

## 项目目标

1. **CSS 规范化**：使样式更加规范化，便于项目引入和维护
2. **完善历史功能**：优化聊天历史管理和显示功能
3. **多模态支持**：扩展对多模态大模型的支持，包括图像、语音等

## 技术亮点

- 现代化前端架构：采用 Vue 3 Composition API
- TypeScript 全覆盖：完整的类型定义和检查
- 组件化设计：高度模块化的组件结构
- 状态管理：使用 Pinia 进行集中式状态管理
- 实时通信：WebRTC 实现的实时音视频交互
- 用户体验：针对儿童用户优化的交互设计

## 配置说明

### 环境变量
项目使用 `.env` 文件进行配置管理，包含 API 基础 URL 等配置。

### API 接口
- 聊天 API：`/ark/bot/chat`
- 支持 POST 请求
- 包含 prompt 和 history 参数

## 部署说明

项目基于 Vite 构建，支持多种部署方式：
- 静态文件部署
- Docker 容器化部署
- 云平台部署（支持 SPA 路由）

## License

MIT
