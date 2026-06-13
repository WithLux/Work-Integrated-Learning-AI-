系统架构文档（Architecture Document）

1. 技术栈

前端（Frontend）

- Next.js 15
- React 19
- TypeScript
- Tailwind CSS
- Shadcn/UI
- Zustand
- React Hook Form
- Zod
- Axios

后端（Backend）

- FastAPI
- Python 3.12+
- SQLAlchemy
- Alembic
- Pydantic

AI 服务

- OpenAI GPT
- OpenAI Embedding
- LangChain
- LangGraph

数据库

PostgreSQL

用于存储：

- 用户信息
- 简历数据
- 职业经历
- 教育经历
- 技能信息

Redis

用于：

- 缓存
- 会话管理
- 限流
- 异步任务

ChromaDb

用于:

- 存储向量数据信息

部署

- Docker
- Docker Compose
- Nginx
- GitHub Actions

---

2. 组件设计规范（Component Rules）

页面层（Pages）

职责：

- 页面布局
- 页面路由
- 页面状态管理

禁止：

- 直接访问数据库
- 直接调用 API
- 编写复杂业务逻辑

---

Components

职责：

- UI 展示
- 通用组件封装
- 表单组件

示例：

    components/
    ├── ui/
    ├── forms/
    ├── layouts/
    └── shared/

---

Features

职责：

- 业务逻辑实现
- 页面功能模块

示例：

    features/
    ├── auth/
    ├── profile/
    └── resume/

---

Services

职责：

- 调用后端接口
- 请求封装
- 数据转换

禁止：

- UI 逻辑
- 页面渲染逻辑

---

3. 状态管理方案（State Management）

本地状态

使用：

    useState
    useReducer

适用于：

- 表单状态
- Modal 状态
- Loading 状态

---

全局状态

使用：

    Zustand

管理：

- 用户登录状态
- 用户信息
- 系统设置
- 主题设置

---

服务端状态

推荐：

    TanStack Query

用于：

- API 缓存
- 自动刷新
- 请求状态管理

---

4. API 设计规范（API Design）

设计原则

采用：

    RESTful API

---

接口路径

    /api/v1/auth
    /api/v1/users
    /api/v1/resumes

---

返回格式

成功：

    {
      "success": true,
      "message": "操作成功",
      "data": {}
    }

失败：

    {
      "success": false,
      "message": "错误信息"
    }

---

API 调用规则

禁止：

    fetch()

直接出现在页面中

必须遵循：

    Page
    ↓
    Feature
    ↓
    Service
    ↓
    API

---

5. 数据流设计（Data Flow）

标准业务流程

    用户界面
    
    ↓
    
    Feature
    
    ↓
    
    Service
    
    ↓
    
    API
    
    ↓
    
    业务逻辑
    
    ↓
    
    数据库

---

登录流程

    登录页面
    
    ↓
    
    Auth API
    
    ↓
    
    JWT Token
    
    ↓
    
    Redis Session
    
    ↓
    
    Dashboard

---

6. 部署方案（Deployment）**

开发环境

    Frontend
    localhost:3000
    
    Backend
    localhost:8000
    
    PostgreSQL
    localhost:5432
    
    Redis
    localhost:6379

---

Docker 容器

    frontend
    
    backend
    
    postgres
    
    redis

---

生产环境架构

    Internet
    
    ↓
    
    Nginx
    
    ↓
    
    Next.js
    
    ↓
    
    FastAPI
    
    ↓
    
    PostgreSQL
    
    ↓
    
    Redis

---

CI/CD

使用：

- GitHub Actions

自动执行：

- Lint
- Test
- Build
- Docker Build

---

7. 未来架构规划（Future Architecture）

第二阶段

新增：

- AI 简历优化
- AI 简历评分
- AI 作品集优化

---

第三阶段

新增：

- Placement Assistant
- Career Coach
- Interview Assistant

采用：

    LangGraph Multi-Agent

架构。

---

长期规划

支持：

- 移动端 App
- 多语言系统
- 微服务架构
- 云部署
- 高并发扩展

未来拆分：

    auth-service
    
    resume-service
    
    user-service
    
    ai-service

通过 API Gateway 统一管理。
