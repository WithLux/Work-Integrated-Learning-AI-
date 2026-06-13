WIL AI Assistant 开发规则

本文档用于规范 AI 编程助手及项目成员在 Work Integrated Learning AI Assistant 项目中的开发行为。

项目目标是为参加 Work Integrated Learning（WIL）课程的学生提供实习申请准备支持，包括：

- 用户资料管理
- CV 创建与优化
- 作品集创建
- Placement 准备指导
- AI 对话与智能建议
- 学校资料检索与问答
- CV 和作品集导出与分享

所有代码修改必须遵循本文档以及项目现有架构。

---

1. 通用开发规则

- 修改代码前，必须先阅读相关文件、依赖关系和现有实现。
- 在不了解现有逻辑的情况下，不得直接重写模块。
- 只修改当前任务相关的代码，不要修改无关文件。
- 优先复用现有模块、组件、类型、工具函数和服务。
- 优先使用简单、清晰、可维护的实现方案。
- 避免为了“未来可能使用”而进行过度设计。
- 不要引入当前任务不需要的新框架或依赖。
- 新增依赖前，先确认现有依赖无法满足需求。
- 保持代码模块化、低耦合和可复用。
- 所有关键业务逻辑必须具有明确的错误处理。
- 不得静默忽略异常。
- 不要删除现有功能，除非任务明确要求。
- 不要随意改变已有 API、数据库字段或公共组件的行为。
- 修改公共接口时，必须同步检查所有调用位置。
- 对不确定的需求，优先参考项目说明、架构文档和现有代码。

---

2. 项目架构规则

项目采用前后端分离架构。

主要技术栈：

前端

- Next.js 15
- React 19
- TypeScript
- Tailwind CSS
- Shadcn/UI
- Zustand
- TanStack Query
- React Hook Form
- Zod
- Axios

后端

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
- RAG
- ChromaDB

数据存储

- PostgreSQL
- Redis
- ChromaDB

部署

- Docker
- Docker Compose
- Nginx
- GitHub Actions

不得在没有充分理由的情况下偏离上述技术栈。

---

3. 前端目录职责

前端代码应按照以下职责划分：

    src/
    ├── app/
    ├── components/
    │   ├── ui/
    │   ├── forms/
    │   ├── layouts/
    │   └── shared/
    ├── features/
    │   ├── auth/
    │   ├── profile/
    │   ├── resume/
    │   ├── portfolio/
    │   ├── placement/
    │   └── assistant/
    ├── services/
    ├── hooks/
    ├── stores/
    ├── schemas/
    ├── types/
    ├── lib/
    └── utils/

app/

负责：

- 页面路由
- 页面入口
- 页面布局
- 服务端组件
- 页面级数据组织
- Loading、Error 和 Not Found 页面

禁止：

- 编写复杂业务逻辑
- 直接访问数据库
- 在页面中重复实现 API 请求逻辑
- 在页面文件中堆积大量 UI 代码

components/

负责：

- 通用 UI 组件
- 布局组件
- 表单组件
- 跨业务模块复用的展示组件

通用组件不得依赖具体业务数据结构，除非该组件明确属于某个业务模块。

features/

负责：

- 具体业务模块
- 业务组件
- 业务 Hooks
- 业务状态
- 业务数据转换

每个功能模块应尽可能独立。

例如：

    features/resume/
    ├── components/
    ├── hooks/
    ├── schemas/
    ├── types/
    └── utils/

services/

负责：

- 调用后端 API
- 封装 Axios 请求
- 请求参数转换
- 响应数据转换
- API 错误标准化

禁止：

- 页面渲染
- UI 状态管理
- Toast 展示
- React 组件逻辑

stores/

仅用于真正需要跨页面共享的客户端状态，例如：

- 当前用户基本信息
- 登录状态
- 系统设置
- 主题设置
- 未完成的多步骤编辑状态

不得将所有 API 数据放入 Zustand。

服务端数据应优先使用 TanStack Query 管理。

---

4. TypeScript 规则

- 不要使用 any。
- 不要通过 as any 绕过类型检查。
- 不要无意义地使用类型断言。
- TypeScript 必须保持严格类型安全。
- 函数参数和返回值应具有明确类型。
- API 请求和响应必须定义类型。
- 公共类型应放入合适的 types 文件。
- 表单数据结构应与 Zod Schema 保持一致。
- 优先使用 z.infer 从 Zod Schema 推断类型。
- 不要同时手动维护两套完全相同的类型定义。
- 使用联合类型表示有限状态。
- 使用泛型时必须保证其实际提高复用性。
- 不要定义过度复杂且难以理解的泛型。
- 对可能为空的数据使用明确的 null 或 undefined 类型。
- 不要使用非空断言 ! 隐藏潜在问题。
- 枚举值较少时，优先使用字符串联合类型。
- 导出的类型和接口名称使用 PascalCase。

示例：

    export type ResumeStatus = "draft" | "completed" | "archived";
    
    export interface Resume {
      id: string;
      title: string;
      status: ResumeStatus;
      updatedAt: string;
    }

不允许：

    const handleData = (data: any) => {
      return data.value;
    };

---

5. React 与 Next.js 规则

- 默认优先使用 Server Component。
- 只有需要浏览器 API、交互状态或 React Hooks 时才使用 "use client"。
- 不要为了方便将整个页面设置为 Client Component。
- 服务端组件和客户端组件的边界必须清晰。
- 页面组件只负责组织布局和功能模块。
- 将复杂交互拆分为独立组件或 Hook。
- 避免超大型组件。
- 单个组件应只承担一个清晰职责。
- 不要在渲染过程中执行副作用。
- 不要在 useEffect 中实现本可直接计算的派生状态。
- 不要滥用 useEffect。
- 使用稳定且有意义的列表 key。
- 不要使用数组下标作为动态列表的 key。
- 表单优先使用 React Hook Form 和 Zod。
- 服务端数据优先使用 TanStack Query。
- 页面级错误使用 Next.js Error Boundary 处理。
- 加载状态应提供明确的 Skeleton、Spinner 或提示信息。
- 所有异步交互必须处理 Loading、Success 和 Error 状态。

---

6. 组件开发规则

- 优先复用现有组件。
- 优先使用 Shadcn/UI 中已有的基础组件。
- 避免创建功能重复的 Button、Input、Dialog、Card 等组件。
- 保持组件小而聚焦。
- 展示组件与业务逻辑尽可能分离。
- 重复出现两次以上的复杂 UI 应考虑抽取。
- 不要为了复用一小段简单 JSX 而过度拆分。
- 组件 Props 必须定义清晰类型。
- Boolean Props 使用具有明确含义的名称，例如：

    isLoading
    isEditable
    showActions

- 回调函数使用清晰命名，例如：

    onSubmit
    onCancel
    onDelete
    onTemplateChange

- 不要使用含义模糊的名称，例如：

    handleIt
    doAction
    dataInfo
    tempValue

---

7. 样式与响应式规则

- 使用 Tailwind CSS。
- 避免行内样式。
- 除非处理动态计算值，否则不要使用 style={{}}。
- 优先使用现有 Design Token 和 Shadcn/UI 样式。
- 不要随意添加新的颜色值。
- 避免在多个文件中重复相同的 Tailwind 类组合。
- 响应式设计必须采用移动端优先原则。
- 页面至少需要检查以下宽度：

    Mobile: 375px
    Tablet: 768px
    Desktop: 1280px
    Large Desktop: 1440px

- 不允许出现非预期横向滚动。
- 表单、表格、导航栏和编辑器必须适配小屏幕。
- 按钮和可点击区域应满足基本可访问性要求。
- 不得仅通过颜色传递状态信息。
- 文本颜色必须具有足够对比度。
- 所有交互元素必须具有可见的 Focus 状态。
- 图标按钮必须提供 aria-label。
- 图片必须提供有意义的 alt，装饰图片使用空 alt。

---

8. API 调用规则

禁止在 UI 组件中直接调用 API。

禁止：

    fetch("/api/v1/resumes");

直接出现在页面组件或通用 UI 组件中。

必须遵循：

    Page
    ↓
    Feature
    ↓
    Hook / Query
    ↓
    Service
    ↓
    Backend API

推荐结构：

    features/resume/hooks/use-resumes.ts
            ↓
    services/resume-service.ts
            ↓
    /api/v1/resumes

Service 示例：

    export const resumeService = {
      getAll: async (): Promise<Resume[]> => {
        const response = await apiClient.get<ApiResponse<Resume[]>>(
          "/api/v1/resumes"
        );
    
        return response.data.data;
      },
    };

API 请求必须：

- 使用统一的 Axios 实例
- 使用统一的 Base URL
- 统一处理 Token
- 统一处理超时
- 统一处理未授权响应
- 定义请求参数类型
- 定义响应数据类型
- 对错误进行标准化

不要在多个 Service 中重复实现相同的请求配置。

---

9. API 设计规范

后端 API 采用 RESTful 风格。

统一版本前缀：

    /api/v1

示例：

    /api/v1/auth
    /api/v1/users
    /api/v1/profiles
    /api/v1/resumes
    /api/v1/portfolios
    /api/v1/placements
    /api/v1/assistant
    /api/v1/documents

资源路径应使用复数名词。

推荐：

    GET    /api/v1/resumes
    POST   /api/v1/resumes
    GET    /api/v1/resumes/{resume_id}
    PATCH  /api/v1/resumes/{resume_id}
    DELETE /api/v1/resumes/{resume_id}

避免：

    /createResume
    /getResumeList
    /deleteResumeById

成功响应格式：

    {
      "success": true,
      "message": "操作成功",
      "data": {}
    }

失败响应格式：

    {
      "success": false,
      "message": "错误信息",
      "error_code": "RESUME_NOT_FOUND"
    }

规则：

- 使用正确的 HTTP 状态码。
- 不要对所有结果都返回 200。
- 创建资源使用 201。
- 无返回内容的删除操作可使用 204。
- 参数错误使用 400 或 422。
- 未认证使用 401。
- 无权限使用 403。
- 资源不存在使用 404。
- 冲突使用 409。
- 服务端异常使用 500。
- 不要在响应中暴露堆栈、数据库结构或内部异常信息。

---

10. FastAPI 规则

后端代码按照职责分层：

    backend/
    ├── app/
    │   ├── api/
    │   ├── core/
    │   ├── models/
    │   ├── schemas/
    │   ├── database/
    │   ├── services/
    │   ├── ai/
    │   ├── tasks/
    │   └── utils/
    ├── migrations/
    └── tests/

推荐调用流程：

    Router
    ↓
    Service
    ↓
    Repository
    ↓
    Database

Router 层

负责：

- 接收 HTTP 请求
- 参数验证
- 身份认证和权限依赖
- 调用 Service
- 返回标准响应

禁止：

- 编写复杂业务逻辑
- 直接执行 SQL
- 直接调用大型 AI 工作流
- 在路由中完成复杂数据转换

Service 层

负责：

- 业务逻辑
- 权限判断
- 事务协调
- 调用 Repository
- 调用 AI Service
- 业务异常处理

database 层

负责：

- 数据库查询
- 数据新增、修改和删除
- 封装 SQLAlchemy 操作

禁止：

- HTTP 响应处理
- AI Prompt 拼接
- 页面展示逻辑

Schema 层

负责：

- 请求验证
- 响应序列化
- 数据边界定义

必须使用 Pydantic 模型。

不要直接将 SQLAlchemy Model 作为 API 请求模型。

---

11. Python 规则

- 使用 Python 3.12+ 支持的语法。
- 所有公共函数必须包含类型提示。
- 不要使用无意义的 dict、list 作为宽泛类型。
- 优先使用明确的数据模型。
- 使用 async def 时，不得在其中直接执行阻塞操作。
- 阻塞型文件处理或第三方调用应放入线程池或任务队列。
- 不要使用可变对象作为默认参数。
- 不要使用裸 except。
- 捕获具体异常类型。
- 自定义业务异常应统一管理。
- 日志不得包含密码、Token、完整简历内容或其他敏感信息。
- 不要使用 print() 作为生产日志。
- 使用统一 Logger。
- 函数和变量使用 snake_case。
- 类名使用 PascalCase。
- 常量使用 UPPER_SNAKE_CASE。
- 模块名使用小写 snake_case。

不允许：

    def create_resume(data={}):
        ...

推荐：

    def create_resume(data: ResumeCreate) -> Resume:
        ...

---

12. 数据库规则

PostgreSQL

用于存储结构化业务数据，包括：

- 用户账户
- 用户资料
- 教育经历
- 工作经历
- 技能
- 项目经历
- CV 数据
- 作品集数据
- 模板信息
- 导出记录
- 分享链接
- AI 任务状态
- 操作日志

规则：

- 所有表必须具有主键。
- 业务表应包含创建时间和更新时间。
- 使用外键维护必要的关系完整性。
- 常用查询字段应根据实际查询添加索引。
- 不要为所有字段盲目添加索引。
- 不要在代码中拼接原始 SQL。
- 避免 N+1 查询。
- 删除行为必须明确使用软删除还是硬删除。
- 涉及多个写操作时使用事务。
- 用户只能访问属于自己的数据。
- 所有查询必须考虑用户数据隔离。

Redis

用于：

- 缓存
- Session
- 限流
- 临时任务状态
- 短期生成结果
- 异步任务状态

规则：

- 所有 Key 必须使用统一命名空间。
- 所有临时数据必须设置过期时间。
- 不要将 Redis 作为永久数据库使用。
- 不要在 Redis 中长期保存完整 CV 或作品集内容。
- 缓存失效策略必须明确。

Key 示例：

    wil:session:{user_id}
    wil:rate_limit:{user_id}
    wil:resume_generation:{task_id}
    wil:rag_cache:{content_hash}

ChromaDB

用于：

- 存储大学手册向量
- 存储课程说明向量
- 存储 WIL 指南向量
- 存储工作场所安全资料向量
- 存储 Placement 相关知识向量

规则：

- 向量数据必须包含来源信息。
- Metadata 至少包含文档名称、章节、页码或来源标识。
- 不要将用户密码、Token 等敏感数据写入向量数据库。
- 用户私有文档必须与公共知识库隔离。
- 删除原始资料时，必须同步考虑向量数据清理。
- Embedding 模型发生变化时，不得混用不兼容向量。

---

13. SQLAlchemy 与 Alembic 规则

- SQLAlchemy Model 只描述数据库结构和关系。
- 不要将复杂业务逻辑写入 ORM Model。
- 所有数据库结构修改必须创建 Alembic Migration。
- 不得只修改 Model 而不创建 Migration。
- 不要手动修改已在共享环境执行过的 Migration。
- 新修改应创建新的 Migration。
- Migration 必须同时实现 upgrade 和 downgrade。
- Migration 提交前必须检查生成内容。
- 不要直接依赖 Alembic 自动生成的结果而不审查。
- 数据迁移和结构迁移应谨慎区分。
- 删除字段前必须考虑已有数据和回滚策略。

---

14. 身份认证与权限规则

- 身份认证使用安全的 JWT 或服务端 Session 方案。
- 密码必须使用可靠算法进行哈希。
- 不得明文保存密码。
- 不得在日志中打印密码、Access Token 或 Refresh Token。
- Access Token 应具有较短有效期。
- Refresh Token 必须支持撤销或失效。
- 敏感 Cookie 必须设置：

    HttpOnly
    Secure
    SameSite

- 每个用户资源接口都必须进行所有权检查。
- 前端隐藏按钮不能代替后端权限验证。
- 用户 ID 不得仅依赖客户端提交。
- 密码重置链接必须具有有效期且只能使用一次。
- 登录、注册和密码重置接口应实施限流。
- 不要向攻击者暴露账户是否存在的过多信息。

---

15. CV 功能规则

CV 模块应支持：

- 根据用户资料生成 CV
- 多种专业模板
- 针对不同行业选择模板
- 编辑各个 CV Section
- 调整内容顺序
- 保存草稿
- 预览
- 导出 PDF
- 导出 Word
- 分享

规则：

- 用户原始资料与生成后的 CV 内容应分开存储。
- AI 优化不得直接覆盖用户原文。
- 必须允许用户比较并接受或拒绝 AI 建议。
- AI 不得编造用户不存在的经历、技能、成绩或证书。
- 生成内容必须明确来自用户输入或标记为建议。
- CV 模板与 CV 数据应分离。
- 不要将版式信息硬编码进业务数据。
- 导出结果必须与预览内容保持一致。
- 导出失败必须返回明确错误。
- 文件名必须经过清理，避免非法路径字符。

---

16. Portfolio 功能规则

作品集模块应支持：

- 项目展示
- 成就展示
- Reflection
- 图片和视觉材料
- 模板布局
- 编辑和预览
- 导出
- 公开分享链接

规则：

- 用户上传内容必须验证文件类型和大小。
- 不得仅根据文件扩展名判断文件类型。
- 文件名必须重新生成或进行安全清理。
- 上传文件不得直接执行。
- 分享链接必须使用不可预测的 Token。
- 分享链接应支持撤销。
- 私有作品集不得通过公开 URL 访问。
- 用户删除项目时，应处理关联图片和文件。
- 图片应进行尺寸限制和必要压缩。
- 所有公开内容必须提供隐私设置。

---

17. Placement Preparation 功能规则

Placement 模块可以包含：

- Placement Readiness Checklist
- 申请材料检查
- CV 写作建议
- 专业展示建议
- 面试准备建议
- 申请流程指导
- WIL 要求说明

规则：

- 系统提供的是辅助指导，不得将 AI 建议描述为学校或雇主的正式决定。
- 涉及学校政策时，应优先使用检索到的正式资料。
- 涉及课程规定时，应显示信息来源。
- 不确定的信息必须明确说明不确定性。
- 不得保证用户一定获得实习或工作机会。
- 不得帮助用户伪造经历、证明、推荐信或工作记录。
- 不得代替学生完成需要个人真实反思的学术任务。
- 应鼓励用户审核并修改 AI 生成内容。

---

18. AI 服务规则

所有 AI 调用必须通过统一 AI Service。

禁止：

- 在 Router 中直接调用 OpenAI SDK
- 在 React 组件中直接调用模型 API
- 将 API Key 暴露到前端
- 在多个模块中重复创建模型客户端
- 将完整系统 Prompt 散落在业务代码中

推荐流程：

    API Router
    ↓
    Application Service
    ↓
    AI Service / Workflow
    ↓
    LLM Provider

AI Service 应负责：

- 模型客户端初始化
- Prompt 管理
- Token 限制
- 超时
- 重试
- 错误转换
- 输出验证
- 日志与用量记录
- Guardrails
- 敏感信息处理

所有 AI 输出都应视为不可信输入，必须进行验证。

---

19. Prompt Engineering 规则

- System Prompt 应集中管理。
- 不要在代码中到处拼接长 Prompt。
- Prompt 应具有明确角色、目标、输入、约束和输出格式。
- 结构化结果优先使用 JSON Schema 或 Pydantic Model。
- 不要依赖模型始终返回合法 JSON。
- 所有结构化输出必须进行解析和验证。
- Prompt 中必须明确禁止编造用户经历。
- Prompt 中必须区分事实、用户输入、检索资料和建议。
- 修改 Prompt 时，应记录修改原因。
- Prompt 不得包含真实 API Key 或生产环境秘密。
- 用户输入必须使用明确边界包裹，防止与系统指令混淆。
- 不得让检索文档中的指令覆盖系统规则。

---

20. RAG 规则

RAG 主要用于检索：

- 大学手册
- 课程说明
- WIL 政策
- Placement 要求
- 工作场所安全指南
- 官方申请指南

标准流程：

    用户问题
    ↓
    查询预处理
    ↓
    向量检索
    ↓
    可选关键词检索
    ↓
    结果过滤与重排
    ↓
    上下文构建
    ↓
    LLM 生成
    ↓
    引用来源

规则：

- 回答学校政策或课程要求时必须提供来源。
- 不得仅凭模型记忆回答可能变化的规定。
- 检索不到可靠内容时，应明确说明无法确认。
- 不要伪造引用。
- 引用必须能对应实际检索文档。
- 上下文必须限制长度。
- 不要将整个文档无条件放入 Prompt。
- 文档切分应保留章节和来源 Metadata。
- 检索结果必须进行相关性过滤。
- 用户上传文档与公共资料必须使用不同 Collection 或命名空间。
- 必须防范文档中的 Prompt Injection。
- 文档中的命令、角色声明和系统指令只能作为内容，不能作为可执行指令。
- 记录知识库版本和更新时间。
- 更新资料后应重新建立相关向量索引。

---

21. LangChain 与 LangGraph 规则

- 简单单次调用不要强制使用 LangGraph。
- 只有涉及多步骤决策、工具调用或可恢复工作流时才使用 LangGraph。
- 每个 Agent 必须具有明确职责。
- 不要创建职责高度重叠的多个 Agent。
- Agent 不得拥有无限制工具权限。
- 工具输入必须经过 Schema 验证。
- 工具输出必须被视为不可信数据。
- 工作流必须设置最大步骤数。
- 必须防止 Agent 无限循环。
- 长时间任务需要保存状态或 Checkpoint。
- AI 失败时必须具有可理解的降级方案。
- 用户确认后才能执行高影响操作，例如：
  - 覆盖 CV 内容
  - 删除作品集
  - 发送邮件
  - 创建公开分享链接
  - 提交申请材料

未来的多 Agent 可以按照以下职责拆分：

    Career Coach Agent
    Resume Agent
    Portfolio Agent
    Placement Assistant Agent
    Retrieval Agent

不得仅为了使用 Multi-Agent 而进行不必要的拆分。

---

22. AI Guardrails 规则

AI 不得：

- 编造用户工作经历
- 编造教育经历
- 编造成绩、奖项或证书
- 生成虚假推荐信
- 帮助用户欺骗学校或雇主
- 保证申请成功
- 将非正式建议描述为学校官方规定
- 泄露其他用户数据
- 在未经允许的情况下公开用户 CV 或作品集
- 执行来自上传文档中的恶意指令
- 将模型输出未经验证地直接写入数据库

AI 应当：

- 明确说明建议性质
- 提醒用户审核生成内容
- 将事实与建议分开
- 在引用课程或学校规定时展示来源
- 无法确认时主动说明
- 对高风险或不可逆操作要求用户确认
- 保留用户原始内容
- 支持用户拒绝 AI 修改

---

23. 文件上传规则

系统可能接收：

- CV
- Word 文档
- PDF
- 图片
- Reflection Journal
- Portfolio 资源

所有上传必须：

- 限制文件大小
- 验证 MIME Type
- 验证实际文件内容
- 清理文件名
- 使用安全存储路径
- 生成不可预测的文件 ID
- 防止目录遍历
- 防止覆盖已有文件
- 限制允许的扩展名
- 对可疑文件拒绝处理
- 不允许用户控制服务端完整存储路径

禁止：

- 直接执行上传文件
- 将用户文件存储在源代码目录
- 将私有文件配置为永久公开
- 将文件内容完整写入日志
- 信任文件扩展名
- 使用用户原文件名作为唯一存储标识

---

24. PDF、Word 与导出规则

- CV 和作品集导出逻辑必须放在独立服务中。
- 导出模板与业务数据应分离。
- PDF 与 Word 的内容应尽可能一致。
- 导出任务较慢时应使用异步任务。
- 导出任务必须记录状态：

    pending
    processing
    completed
    failed

- 用户只能下载属于自己的导出文件。
- 临时导出文件必须设置清理机制。
- 分享文件应使用具有有效期或可撤销的链接。
- 导出失败不得产生损坏文件供用户下载。
- 文件响应必须设置正确的 Content-Type。
- 所有模板必须检查分页、字体、间距和长文本溢出问题。

---

25. 后台任务规则

以下任务可考虑使用后台任务或 Worker：

- PDF 生成
- Word 生成
- 大型文件解析
- Embedding 生成
- 文档索引
- 批量 AI 分析
- 邮件发送
- 图片处理

规则：

- API 不应长时间阻塞等待任务完成。
- 每个任务必须具有唯一 Task ID。
- 任务必须记录状态和失败原因。
- 任务应尽可能支持重试。
- 重试次数必须有限制。
- 任务应尽可能具有幂等性。
- 不得因重复提交生成重复资源。
- 用户只能查看自己的任务状态。
- 失败任务不得永久停留在 Processing 状态。

---

26. 安全规则

- 所有密钥必须通过环境变量管理。
- 不要将 .env 提交到 Git。
- 提供 .env.example 时不得包含真实密钥。
- 前端只允许使用明确可公开的环境变量。
- OpenAI API Key 只能存在于后端。
- 所有用户输入必须进行验证。
- 所有用户输出必须根据上下文安全转义。
- 防范 SQL Injection。
- 防范 XSS。
- 防范 CSRF。
- 防范 SSRF。
- 防范路径遍历。
- 防范恶意文件上传。
- 防范 Prompt Injection。
- 防范越权访问。
- 对认证接口和 AI 接口实施限流。
- CORS 不得在生产环境无条件允许所有来源。
- Swagger/OpenAPI 在生产环境应根据需求限制访问或关闭。
- 安全响应头应由 Nginx 或后端统一配置。
- 不要在错误响应中暴露内部路径、SQL 或堆栈信息。
- 敏感操作必须写入审计日志。
- 日志中的个人信息应最小化。

---

27. 隐私与用户数据规则

本项目涉及用户个人信息、教育经历和就业申请资料。

必须遵循：

- 只收集完成功能所需的数据。
- 明确区分必要字段和可选字段。
- 用户应能够查看和修改自己的数据。
- 用户应能够删除自己的 CV 和作品集。
- 对账户删除后的数据保留策略必须明确。
- 不得将用户数据用于未说明的用途。
- 不得将不同用户的数据混入同一个 AI 上下文。
- 不得将用户完整 CV 写入普通应用日志。
- AI Provider 请求中只发送完成任务所需的信息。
- 非必要情况下，应移除姓名、邮箱、电话等直接标识符。
- 公开分享前必须获得用户明确操作。
- 开发和测试环境不得直接使用真实用户敏感数据。

---

28. 错误处理规则

前后端必须提供统一错误处理。

后端应区分：

- 参数验证错误
- 认证错误
- 权限错误
- 资源不存在
- 数据冲突
- 外部 AI 服务错误
- 文件处理错误
- 数据库错误
- 内部服务器错误

前端应：

- 显示用户可理解的信息
- 不显示后端堆栈
- 不直接显示敏感内部错误
- 提供必要的重试操作
- 保留用户尚未提交的表单内容
- 对网络错误和服务端错误进行区分
- 对 AI 生成失败提供重新生成或恢复选项

不得使用空的错误处理：

    try {
      await saveResume();
    } catch {
      // 什么都不做
    }

---

29. 日志规则

日志应包含：

- 请求追踪 ID
- 操作类型
- 任务状态
- 错误类型
- 必要的性能信息

日志不得包含：

- 密码
- Access Token
- Refresh Token
- API Key
- 完整 Cookie
- 完整 CV 内容
- 完整作品集内容
- 未脱敏个人信息
- 上传文件完整内容

错误日志应保留足够排查信息，但不得暴露用户隐私。

---

30. 测试规则

新增功能必须根据风险添加相应测试。

前端测试重点

- 表单验证
- 关键组件交互
- Loading 和 Error 状态
- CV 编辑流程
- Portfolio 编辑流程
- 响应式布局
- 权限相关 UI
- API 错误处理

后端测试重点

- Service 业务逻辑
- API 状态码
- 身份认证
- 资源所有权
- 数据验证
- 数据库操作
- 文件上传
- 导出权限
- RAG 检索
- AI 输出验证

AI 测试重点

- 不编造用户经历
- 不生成虚假资格
- 引用来源正确
- 无资料时能够拒绝猜测
- Prompt Injection 防护
- 结构化输出验证
- 超时与失败降级
- Token 长度限制

修复 Bug 时，应尽可能添加能够复现该 Bug 的测试。

---

31. 文件与命名规则

- 不要创建不必要的文件。
- 遵循现有文件夹结构。
- 不要随意新增顶层目录。
- 保持命名风格一致。
- 文件名应准确反映其职责。
- 不要使用 temp、test2、newFile、finalVersion 等模糊命名。
- 不要保留无用的注释代码。
- 不要提交调试文件。
- 不要提交生成产物、缓存或本地环境文件。
- 空目录确实需要保留时，可使用 .gitkeep。
- 新增文件前，先确认现有文件是否可以合理扩展。
- 不要创建职责完全重复的 Service、Hook 或 Utility。

前端文件名推荐使用 kebab-case：

    resume-editor.tsx
    use-resume-query.ts
    resume-service.ts

Python 文件名使用 snake_case：

    resume_service.py
    portfolio_repository.py

---

32. Git 规则

- 每次提交只包含一个清晰目的。
- 不要将无关格式化修改与功能修改混在一起。
- 提交前检查 git diff。
- 不要提交 .env。
- 不要提交数据库 Volume。
- 不要提交 node_modules。
- 不要提交 Python 虚拟环境。
- 不要提交 IDE 私有配置。
- 不要强制推送共享分支，除非团队明确同意。
- 处理冲突时必须理解双方代码，不得直接选择全部一方。
- Commit Message 应清晰描述修改。

示例：

    feat(resume): add editable education section
    fix(auth): handle expired refresh token
    refactor(ai): extract prompt validation service
    test(portfolio): add share permission tests
    docs: update local development instructions

---

33. Docker 规则

- 开发和生产配置应明确区分。
- 不要在镜像中写入密钥。
- 生产镜像应尽可能使用多阶段构建。
- 容器内服务通过 Docker Service Name 通信。
- 浏览器访问后端时使用公开 URL，而不是 Docker Service Name。
- 数据库必须使用持久化 Volume。
- 不要将数据库数据目录提交到 Git。
- 服务必须配置健康检查。
- depends_on 不等于服务已经可用。
- 后端应实现数据库连接重试或等待机制。
- Dockerfile 应固定主要运行环境版本。
- 不要在生产容器中安装不必要的开发依赖。
- 容器应尽可能使用非 Root 用户运行。
- 日志应输出到标准输出和标准错误。

开发环境示例：

    Browser → localhost:3000
    Browser → localhost:8000
    Frontend Container → backend:8000
    Backend Container → postgres:5432
    Backend Container → redis:6379
    Backend Container → chromadb:8000

---

34. CI/CD 规则

GitHub Actions 至少应执行：

前端

- 安装依赖
- Lint
- TypeScript 检查
- Test
- Build

后端

- 安装依赖
- Lint
- 类型检查
- Test
- Alembic Migration 检查

容器

- Docker Build
- 必要的镜像安全检查
- 验证 Docker Compose 配置

CI 失败时不得合并到受保护分支。

不得通过删除测试、禁用规则或使用宽泛忽略配置来绕过 CI。

---

35. 文档规则

新增或修改以下内容时应同步更新文档：

- 环境变量
- API
- 数据库结构
- 启动命令
- Docker 配置
- AI 模型
- RAG 数据源
- 文件上传限制
- 导出流程
- 权限规则
- 部署方式

README 至少应说明：

- 项目用途
- 技术栈
- 环境要求
- 环境变量
- 本地启动方式
- Docker 启动方式
- 数据库迁移
- 测试命令
- 常见问题

在单次开发结束后请更新DEVElOP.md，注意不要写成流水账，只是记录完成事项、关键决策、当前问题和下一步。

---

36. 禁止行为

AI 编程助手不得：

- 未阅读相关代码就大规模修改。
- 修改与任务无关的文件。
- 无理由重构整个项目。
- 使用 any 绕过 TypeScript。
- 在 UI 组件中直接调用 API。
- 在 Router 中编写复杂业务逻辑。
- 在代码中硬编码密码、Token 或 API Key。
- 将 OpenAI Key 暴露给浏览器。
- 未创建 Migration 就修改数据库结构。
- 将 AI 输出直接作为可信数据写入数据库。
- 自动覆盖用户原始 CV 内容。
- 生成虚假经历、技能、证书或成绩。
- 伪造大学政策或引用。
- 忽略权限检查。
- 通过禁用 Lint 或测试掩盖问题。
- 创建大量没有实际用途的文件。
- 删除现有测试来使构建通过。
- 使用空 catch 隐藏错误。
- 在生产环境开放任意 CORS。
- 将用户敏感信息记录到日志。
- 在未确认的情况下执行不可逆操作。

---

37. 完成任务前检查

每次完成修改后，必须根据修改范围执行以下检查。

通用检查

- 是否只修改了相关文件
- 是否复用了现有代码
- 是否引入重复逻辑
- 命名是否清晰
- 是否存在无用代码
- 是否存在调试输出
- 是否更新了必要文档
- 是否意外暴露敏感数据

前端检查

必须执行：

    npm run lint
    npm run type-check
    npm run test
    npm run build

如果项目使用其他包管理器，应使用项目已有命令。

同时检查：

- TypeScript 是否无错误
- 页面是否可以正常渲染
- Loading 状态是否正常
- Error 状态是否正常
- 表单验证是否正常
- Mobile 布局是否正常
- Tablet 布局是否正常
- Desktop 布局是否正常
- 是否存在横向滚动
- 键盘操作是否可用

后端检查

必须执行项目已有的对应命令，例如：

    ruff check .
    mypy .
    pytest
    alembic check

同时检查：

- FastAPI 是否可以启动
- OpenAPI Schema 是否可以生成
- API 状态码是否正确
- Pydantic 验证是否正常
- 数据库操作是否正确
- Migration 是否完整
- 权限检查是否生效
- 异常是否被正确转换
- 日志是否泄露敏感信息

Docker 检查

涉及容器修改时执行：

    docker compose config
    docker compose build
    docker compose up

确认：

- 所有容器可以启动
- 健康检查通过
- 服务之间可以通信
- 数据库数据可以持久化
- 前端可以访问后端
- 后端可以访问数据库、Redis 和 ChromaDB

AI 与 RAG 检查

涉及 AI 功能时确认：

- 模型失败时有错误处理
- 输出经过 Schema 验证
- 不会编造用户经历
- 不会泄露其他用户数据
- 检索结果包含真实来源
- 无结果时不会伪造答案
- 文档 Prompt Injection 不会覆盖系统规则
- Token 和上下文长度受到限制
- 高影响操作需要用户确认

---

38. AI 助手完成任务后的回复格式

完成代码任务后，应简洁说明：

1. 修改了什么
2. 修改了哪些主要文件
3. 为什么这样修改
4. 执行了哪些检查
5. 哪些检查通过
6. 是否存在尚未解决的问题

不要声称执行了未实际运行的命令。

如果无法执行某项检查，必须明确说明原因。

示例：

    已完成 CV 教育经历编辑功能。
    
    主要修改：
    - 新增教育经历表单组件
    - 新增 Resume Service 更新接口
    - 添加 Zod 表单验证
    - 添加后端教育经历更新逻辑
    
    已执行：
    - npm run lint：通过
    - npm run type-check：通过
    - npm run build：通过
    - pytest：通过
    
    未执行：
    - Docker 完整启动测试，因为当前环境未运行 Docker。

---

39. 核心原则

在所有实现中始终遵循：

    安全性优先于便利性
    用户真实性优先于 AI 生成效果
    可维护性优先于过度复杂设计
    现有架构优先于随意引入新模式
    真实来源优先于模型猜测
    用户确认优先于自动执行高影响操作
