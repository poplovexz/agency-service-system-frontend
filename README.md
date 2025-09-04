# 代理服务系统 - 前端

这是一个基于 Next.js 的现代化代理服务管理系统前端应用。

## 🚀 功能特性

- 🏢 **企业管理**: 完整的企业信息管理系统
- 👥 **用户权限**: 基于角色的权限管理系统
- 📋 **业务流程**: 可配置的业务流程管理
- 💰 **财务管理**: 佣金、费用、报价管理
- 📊 **数据分析**: 实时数据统计和报表
- 📱 **响应式设计**: 支持桌面和移动设备
- 🔔 **实时通知**: WebSocket实时消息推送
- 🔐 **安全认证**: JWT令牌认证和权限控制

## 🛠️ 技术栈

- **框架**: Next.js 13.5.6 (App Router)
- **语言**: TypeScript
- **样式**: Tailwind CSS
- **UI组件**: Radix UI + shadcn/ui
- **状态管理**: React Hooks + Context
- **表单处理**: React Hook Form + Zod
- **HTTP客户端**: Axios
- **实时通信**: WebSocket
- **图标**: Lucide React

## 📦 快速开始

### 环境要求

- Node.js 18.x 或更高版本
- npm 或 yarn
- 后端API服务 (运行在端口3001)

### 安装依赖

```bash
npm install
```

### 环境配置

复制环境变量文件：

``bbash
cp .env.example .env.local
```

编辑 `.env.local` 文件：

```env
# API服务器地址
NEXT_PUBLIC_API_URL=http://localhost:3001

# WebSocket服务器地址  
NEXT_PUBLIC_WS_URL=ws://localhost:3001

# 应用配置
NEXT_PUBLIC_APP_NAME=代理服务系统
NEXT_PUBLIC_APP_VERSION=1.0.0
```

### 开发模式

```bash
npm run dev
```

应用将在 [http://localhost:3000](http://localhost:3000) 启动。

### 生产构建

```bash
# 云端构建（推荐）
# 推送到GitHub后自动触发构建

# 本地构建
npm run build
npm start
```

## 📁 项目结构

```
agency-service-system/
├── app/                    # Next.js 13 App Router
│   ├── admin/             # 管理员页面
│   ├── dashboard/         # 仪表板
│   ├── login/             # 登录页面
│   ├── business-management/ # 业务管理
│   └── ...
├── components/            # 可复用组件
│   ├── admin/             # 管理员组件
│   ├── common/            # 通用组件
│   ├── forms/             # 表单组件
│   └── ui/                # UI基础组件
├── lib/                   # 工具库
│   ├── api/               # API客户端
│   ├── auth/              # 认证相关
│   └── utils/             # 工具函数
├── hooks/                 # 自定义Hooks
├── types/                 # TypeScript类型定义
└── public/                # 静态资源
```

## 🔧 核心功能模块

### 1. 认证与权限系统
- JWT令牌认证
- 基于角色的权限控制 (RBAC)
- 细粒度权限管理
- 会话管理

### 2. 企业管理
- 企业信息维护
- 部门层级管理
- 人员角色分配
- 组织架构图

### 3. 业务流程管理
- 可视化流程设计
- 任务自动分配
- 进度实时跟踪
- 审批工作流

### 4. 客户关系管理
- 客户信息管理
- 线索跟进
- 商机管理
- 客户服务记录

### 5. 财务管理
- 智能报价系统
- 合同生命周期管理
- 佣金自动计算
- 财务报表分析

## 🚀 部署方案

### 云端构建 (推荐)

本项目支持GitHub Actions云端构建，避免本地内存不足问题：

1. 推送代码到GitHub
2. GitHub Actions自动构建
3. 自动部署到服务器

### 本地部署

``bbash
# 使用PM2部署
npm run build
pm2 start ecosystem.config.js
```

## 🐛 故障排除

### 构廹问题

1. **内存不足导致构建失败**
   - 使用云端构建（推荐）
   - 或增加本地内存限制: `export NODE_OPTIONS="--max-old-space-size=4096"`

2. **依赖冲突**
   ``bbash
   rm -rf node_modules package-lock.json
   npm install
   ```

### 运行时问题

1. **API连接失败**
   - 检查后端服务状态
   - 确认环境变量配置
   - 检查网络连接

2. **权限错误**
   - 清除浏览器缓存
   - 重新登录获取新令牌

## 🤝 贡献指南

1. Fork 项目
2. 创建功能分支 (`git checkout -b feature/amazing-feature`)
3. 提交更改 (`git commit -m 'Add amazing feature'`)
4. 推送到分支 (`git push origin feature/amazing-feature`)
5. 创建 Pull Request

## 📄 许可证

本项目采用 MIT 许可证。

## 📞 支持与联系

- **技术支持**: system@agency.com
- **问题反馈**: GitHub Issues
- **文档**: 项目文档目录

---

**注意**: 本项目支持云端构建，推荐使用GitHub Actions进行构建和部署，避免本地资源限制问题。
