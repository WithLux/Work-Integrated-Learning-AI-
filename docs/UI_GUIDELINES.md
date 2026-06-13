WIL AI Assistant UI Guidelines

本文档定义 Work Integrated Learning AI Assistant 项目的用户界面设计规范。

所有页面、组件、交互、响应式布局和视觉样式都应遵循本文档，以保证整个系统具有一致、现代、专业且易于使用的用户体验。

项目主要面向正在准备实习、Placement、CV 和 Portfolio 的学生，因此界面需要同时体现：

* 专业性
* 可信度
* 友好感
* 清晰的信息层级
* 低学习成本
* 对学生用户的引导性

⸻

1. Design Goals

本项目的 UI 设计目标包括：

* 帮助学生快速完成个人资料填写
* 降低 CV 和 Portfolio 创建难度
* 清晰展示任务进度和 Placement 准备状态
* 让 AI 建议易于理解、比较和采用
* 为复杂的表单和编辑流程提供明确引导
* 保持界面简洁，避免过多视觉干扰
* 在桌面端、平板端和移动端均具有良好体验
* 为未来移动端 App 保留统一的设计语言

⸻

2. Design Style

整体设计风格：

* Modern
* Minimal
* Clean
* Professional
* Friendly
* Accessible
* Content-focused
* Student-oriented

界面应使用现代的橙白配色，通过柔和橙色表达积极、成长、机会和行动感。

整体视觉应避免过度活泼或娱乐化，确保系统仍然适合：

* 学术环境
* 职业申请
* 简历编辑
* Placement 准备
* 专业作品集展示

设计关键词：

现代
简洁
温暖
可信
专业
轻量
清晰
有引导性

⸻

3. Visual Principles

3.1 简洁优先

每个页面应具有明确的主要任务。

不要在同一个页面同时突出多个操作。

每个页面建议只设置一个主要操作按钮，例如：

* 创建 CV
* 保存资料
* 生成建议
* 导出文件
* 创建 Portfolio

次要操作使用次级按钮、文本按钮或下拉菜单。

⸻

3.2 内容优先

CV、Portfolio、学生资料和 AI 建议是页面的核心。

视觉装饰不能干扰主要内容。

避免：

* 大面积无意义渐变
* 复杂背景图案
* 过度动画
* 过多阴影
* 大量颜色混用
* 装饰性图标堆积

⸻

3.3 清晰层级

页面必须通过以下方式建立清晰的信息层级：

* 标题大小
* 字重
* 间距
* 卡片分组
* 背景色
* 边框
* 图标
* 状态标签

标题、描述、内容和辅助信息必须能够被快速区分。

⸻

3.4 渐进式引导

复杂流程应分步骤展示。

适用于：

* 用户资料创建
* CV 创建
* Portfolio 创建
* Placement Checklist
* 文档上传
* AI 优化流程

不要一次性向用户显示过多字段。

推荐使用：

* Stepper
* Progress Bar
* Section Navigation
* Accordion
* Tabs
* Checklist

⸻

3.5 用户控制

AI 只能提供建议，不应在未经确认的情况下自动覆盖用户内容。

所有 AI 修改建议应允许用户：

* 查看原文
* 查看建议
* 对比差异
* 接受建议
* 拒绝建议
* 手动修改
* 恢复原始内容

⸻

4. Color System

项目采用现代橙白配色。

整体颜色比例建议：

白色及浅色背景：70%
中性色文字和边框：20%
橙色强调色：10%

橙色主要用于：

* 主要操作
* 当前步骤
* 选中状态
* 重要提示
* 品牌标识
* 进度展示

不要在大面积背景中使用高饱和橙色。

⸻

4.1 Primary Color

主色使用现代、温暖但不过度鲜艳的橙色。

Primary 50:  #FFF7ED
Primary 100: #FFEDD5
Primary 200: #FED7AA
Primary 300: #FDBA74
Primary 400: #FB923C
Primary 500: #F97316
Primary 600: #EA580C
Primary 700: #C2410C
Primary 800: #9A3412
Primary 900: #7C2D12
Primary 950: #431407

默认品牌主色：

Primary: #F97316

主要按钮 Hover：

Primary Hover: #EA580C

主要按钮 Active：

Primary Active: #C2410C

柔和主色背景：

Primary Soft Background: #FFF7ED

主色边框：

Primary Border: #FED7AA

⸻

4.2 Secondary Color

辅助色使用深蓝灰色，增加专业感和可信度。

Secondary 50:  #F8FAFC
Secondary 100: #F1F5F9
Secondary 200: #E2E8F0
Secondary 300: #CBD5E1
Secondary 400: #94A3B8
Secondary 500: #64748B
Secondary 600: #475569
Secondary 700: #334155
Secondary 800: #1E293B
Secondary 900: #0F172A
Secondary 950: #020617

默认辅助色：

Secondary: #334155

深色标题：

Heading Color: #0F172A

正文颜色：

Body Color: #334155

辅助文字：

Muted Text: #64748B

⸻

4.3 Background Colors

主页面背景：

Page Background: #F8FAFC

卡片背景：

Card Background: #FFFFFF

次级背景：

Secondary Background: #F1F5F9

橙色提示背景：

Orange Soft Background: #FFF7ED

输入框背景：

Input Background: #FFFFFF

禁用背景：

Disabled Background: #F1F5F9

遮罩背景：

Overlay Background: rgba(15, 23, 42, 0.48)

⸻

4.4 Border Colors

默认边框：

Border: #E2E8F0

较强边框：

Border Strong: #CBD5E1

Hover 边框：

Border Hover: #FDBA74

Focus 边框：

Border Focus: #F97316

禁用边框：

Border Disabled: #E2E8F0

⸻

4.5 Semantic Colors

Success

Success: #16A34A
Success Background: #F0FDF4
Success Border: #BBF7D0
Success Text: #166534

用于：

* 保存成功
* 导出完成
* Checklist 已完成
* 验证通过
* AI 任务完成

Warning

Warning: #D97706
Warning Background: #FFFBEB
Warning Border: #FDE68A
Warning Text: #92400E

用于：

* 内容尚未完成
* AI 内容需要确认
* 文档可能过期
* 表单存在提醒

Error

Error: #DC2626
Error Background: #FEF2F2
Error Border: #FECACA
Error Text: #991B1B

用于：

* 表单错误
* 上传失败
* 导出失败
* 权限错误
* 网络错误

Information

Info: #2563EB
Info Background: #EFF6FF
Info Border: #BFDBFE
Info Text: #1E40AF

用于：

* 普通说明
* 系统提示
* 帮助内容
* 非紧急通知

⸻

4.6 Color Usage Rules

* 主色只用于关键操作和重要状态。
* 同一页面最多使用一个主要强调色。
* 不要使用橙色作为长段正文颜色。
* 禁止使用纯黑色作为主要文字颜色。
* 禁止使用低对比度浅灰色展示重要信息。
* 错误信息只能使用 Error 色系。
* 成功状态只能使用 Success 色系。
* Warning 不应与 Primary 使用完全相同的视觉样式。
* 不得仅依靠颜色表达状态，必须搭配文字或图标。
* 所有文字和背景组合必须满足基本可访问性对比度要求。

⸻

5. Typography

5.1 Font Family

英文和数字推荐使用：

Inter

中文推荐使用系统字体：

"PingFang SC"
"Noto Sans SC"
"Microsoft YaHei"

完整字体栈：

font-family:
  Inter,
  "PingFang SC",
  "Noto Sans SC",
  "Microsoft YaHei",
  system-ui,
  -apple-system,
  BlinkMacSystemFont,
  "Segoe UI",
  sans-serif;

Next.js 项目优先通过 next/font 加载 Inter。

不要为普通正文使用衬线字体。

CV 模板预览可以根据模板类型使用额外字体，但应用系统界面必须保持统一。

⸻

5.2 Heading Typography

Display

适用于登录欢迎页或 Landing Page 主标题。

Font Size: 48px
Line Height: 56px
Font Weight: 700
Letter Spacing: -0.02em

Heading 1

页面主标题。

Font Size: 32px
Line Height: 40px
Font Weight: 700
Letter Spacing: -0.02em

Heading 2

页面区块标题。

Font Size: 24px
Line Height: 32px
Font Weight: 600
Letter Spacing: -0.01em

Heading 3

卡片或功能模块标题。

Font Size: 20px
Line Height: 28px
Font Weight: 600

Heading 4

表单分组或小节标题。

Font Size: 16px
Line Height: 24px
Font Weight: 600

⸻

5.3 Body Typography

Large Body

Font Size: 18px
Line Height: 28px
Font Weight: 400

Default Body

Font Size: 16px
Line Height: 24px
Font Weight: 400

Small Body

Font Size: 14px
Line Height: 20px
Font Weight: 400

Caption

Font Size: 12px
Line Height: 16px
Font Weight: 400

⸻

5.4 Typography Rules

* 页面只能有一个主要 h1。
* 标题必须按语义层级排列。
* 不要仅为了视觉效果跳过标题级别。
* 正文默认使用 16px。
* 表单辅助文字可以使用 14px。
* 不建议使用小于 12px 的文字。
* 长段正文行宽建议控制在 60–75 个字符。
* 标题应简短明确。
* 按钮文字应使用动作词。
* 不要使用全大写英文作为长文本。
* 数字、百分比和状态值应保持易读。
* 文本链接必须与普通文字有清晰区别。

⸻

6. Spacing System

项目使用基于 8px 的间距系统。

基础单位：

4px
8px
12px
16px
24px
32px
40px
48px
64px
80px

推荐 Tailwind 映射：

1  = 4px
2  = 8px
3  = 12px
4  = 16px
6  = 24px
8  = 32px
10 = 40px
12 = 48px
16 = 64px
20 = 80px

⸻

6.1 Page Spacing

桌面端页面左右间距：

32px–48px

平板端页面左右间距：

24px

移动端页面左右间距：

16px

页面顶部和底部建议：

Desktop: 32px–48px
Mobile: 24px

⸻

6.2 Component Spacing

卡片内部间距：

Desktop: 24px
Mobile: 16px

表单字段之间：

16px–24px

标题与描述之间：

8px

区块之间：

32px–48px

按钮组间距：

8px–12px

图标和文字之间：

8px

⸻

6.3 Spacing Rules

* 不要随意使用非标准间距值。
* 同类组件必须使用一致间距。
* 信息层级越高，区块间距应越大。
* 不要完全依赖 Divider 分隔内容，应优先使用留白。
* 表单布局需要保持稳定节奏。
* 移动端应适当缩小外部间距，但不能压缩点击区域。
* 空白区域是设计的一部分，不要过度填满页面。

⸻

7. Border Radius

整体使用中等圆角，体现现代感但避免过度柔和。

Small: 6px
Default: 8px
Medium: 12px
Large: 16px
Extra Large: 24px
Full: 9999px

使用建议：

* Input：8px
* Button：8px
* Card：12px
* Dialog：16px
* Dropdown：12px
* Badge：9999px
* Avatar：9999px
* Toast：12px
* File Upload Area：12px

规则：

* 同类型组件必须保持相同圆角。
* 普通按钮不要使用完全胶囊形，除非是标签或筛选按钮。
* 主内容卡片不要使用过大圆角。
* CV 预览纸张建议使用 4px–8px 小圆角。

⸻

8. Shadows

阴影应轻量，主要用于建立层级。

Small Shadow

box-shadow: 0 1px 2px rgba(15, 23, 42, 0.05);

用于：

* Input Hover
* 小型卡片
* 下拉按钮

Default Shadow

box-shadow:
  0 1px 3px rgba(15, 23, 42, 0.08),
  0 1px 2px rgba(15, 23, 42, 0.04);

用于：

* 普通卡片
* 导航栏
* CV 模板卡片

Medium Shadow

box-shadow:
  0 10px 25px rgba(15, 23, 42, 0.10);

用于：

* Dialog
* Dropdown
* Popover
* Preview Floating Panel

规则：

* 不要给所有元素添加阴影。
* 普通卡片优先使用浅边框。
* 悬浮元素才能使用明显阴影。
* 禁止使用强烈黑色阴影。
* 同一个区域避免叠加多层明显阴影。

⸻

9. Layout System

9.1 Application Layout

登录后的主界面推荐使用：

Desktop:
Sidebar + Header + Main Content
Tablet:
Collapsible Sidebar + Header + Main Content
Mobile:
Top Header + Drawer Navigation + Main Content

桌面端结构：

┌──────────────┬─────────────────────────────────┐
│              │ Header                          │
│   Sidebar    ├─────────────────────────────────┤
│              │                                 │
│              │ Main Content                    │
│              │                                 │
└──────────────┴─────────────────────────────────┘

⸻

9.2 Content Width

普通内容页面最大宽度：

1280px

表单页面推荐最大宽度：

720px–880px

设置页面推荐最大宽度：

800px

CV 编辑页面可以使用更宽布局：

1440px

AI 对话页面推荐最大内容宽度：

960px

⸻

9.3 Grid

桌面端使用 12 列 Grid。

推荐：

Column Count: 12
Gutter: 24px

平板端：

Column Count: 8
Gutter: 16px

移动端：

Column Count: 4
Gutter: 16px

⸻

10. Navigation

10.1 Sidebar

Sidebar 推荐包含：

* Dashboard
* My Profile
* CV Builder
* Portfolio
* Placement Preparation
* AI Assistant
* Documents
* Settings

底部可包含：

* Help
* User Menu
* Logout

Sidebar 宽度：

Expanded: 256px
Collapsed: 72px

规则：

* 当前页面必须具有明显选中状态。
* 选中项使用浅橙背景和深橙文字。
* 图标和文字保持 8px–12px 间距。
* 不要在 Sidebar 中放置过多二级菜单。
* 菜单名称应简短。
* 移动端 Sidebar 使用 Drawer。
* Drawer 打开后必须阻止背景滚动。

当前菜单样式：

Background: #FFF7ED
Text: #C2410C
Icon: #EA580C

⸻

10.2 Header

Header 可包含：

* 页面标题
* Breadcrumb
* 通知入口
* 帮助入口
* 用户头像
* 用户菜单

高度建议：

Desktop: 64px
Mobile: 56px

Header 应保持简洁。

不要同时放置过多主要操作。

页面主要操作应优先放在页面标题区域，而不是全局 Header。

⸻

10.3 Breadcrumb

适用于三级及以上页面结构。

示例：

CV Builder / My CV / Edit

规则：

* 当前页面不可点击。
* 上级页面可以点击。
* 移动端可只展示上一级页面。
* Breadcrumb 不得替代页面标题。

⸻

11. Buttons

11.1 Primary Button

用于页面最主要的操作。

示例：

* 创建 CV
* 保存并继续
* 生成建议
* 导出 PDF
* 发布 Portfolio

视觉：

Background: #F97316
Text: #FFFFFF
Border: Transparent
Hover: #EA580C
Active: #C2410C
Focus Ring: #FDBA74

⸻

11.2 Secondary Button

用于次要操作。

示例：

* 预览
* 保存草稿
* 返回
* 稍后完成

视觉：

Background: #FFFFFF
Text: #334155
Border: #CBD5E1
Hover Background: #F8FAFC
Hover Border: #94A3B8

⸻

11.3 Ghost Button

用于低强调操作。

示例：

* 取消
* 更多
* 查看详情
* 编辑

视觉：

Background: Transparent
Text: #475569
Hover Background: #F1F5F9

⸻

11.4 Destructive Button

用于删除或撤销等危险操作。

视觉：

Background: #DC2626
Text: #FFFFFF
Hover: #B91C1C

危险操作必须提供确认。

⸻

11.5 Button Sizes

Small

Height: 32px
Padding: 12px
Font Size: 14px

Default

Height: 40px
Padding: 16px
Font Size: 14px

Large

Height: 48px
Padding: 20px
Font Size: 16px

⸻

11.6 Button Rules

* 按钮文字应使用动词。
* 同一区域只能有一个 Primary Button。
* 不要使用“确定”作为所有按钮的通用文字。
* 应使用明确名称，例如“保存 CV”“删除项目”。
* 图标按钮必须提供 Tooltip 和 aria-label。
* Loading 时应显示 Spinner。
* Loading 时应禁止重复提交。
* Disabled 状态必须明显。
* 移动端主要按钮可占满宽度。
* 点击区域高度不得小于 40px。
* 不要将文本链接设计成主要按钮。
* 删除操作不得使用 Primary Orange。

⸻

12. Cards

卡片用于组织独立信息模块。

适用于：

* CV 列表
* Portfolio 项目
* Placement Checklist
* AI 建议
* 模板选择
* Dashboard 数据
* 最近活动

默认 Card：

Background: #FFFFFF
Border: 1px solid #E2E8F0
Border Radius: 12px
Padding: 24px
Shadow: Small or None

Hover Card：

Border: #FDBA74
Shadow: Default
Transform: translateY(-1px)

规则：

* 只有可点击 Card 才使用 Hover 位移。
* Card 必须具有清晰标题。
* Card 内操作按钮数量应受到限制。
* 多个次要操作使用 Dropdown Menu。
* 同一列表中的 Card 高度应尽可能一致。
* 不要在 Card 中嵌套过多 Card。
* 移动端 Padding 可降为 16px。

⸻

13. Forms

表单是本项目最重要的 UI 类型之一。

13.1 Form Structure

每个字段建议包含：

Label
Input
Helper Text
Error Message

示例：

Job Title
[ Software Engineer Intern                 ]
填写你希望申请的职位名称。

⸻

13.2 Input Style

默认：

Height: 40px
Background: #FFFFFF
Border: #CBD5E1
Border Radius: 8px
Text: #0F172A
Placeholder: #94A3B8

Focus：

Border: #F97316
Ring: rgba(249, 115, 22, 0.18)

Error：

Border: #DC2626
Ring: rgba(220, 38, 38, 0.12)

Disabled：

Background: #F1F5F9
Text: #94A3B8
Cursor: not-allowed

⸻

13.3 Label

Font Size: 14px
Font Weight: 500
Color: #334155
Margin Bottom: 6px–8px

必填字段使用：

*

但必须同时提供可访问性属性。

⸻

13.4 Helper Text

Font Size: 13px–14px
Color: #64748B
Margin Top: 6px

辅助文字应解释用户应该填写什么，而不是重复 Label。

⸻

13.5 Error Message

Font Size: 13px–14px
Color: #DC2626
Margin Top: 6px

错误信息必须明确。

不推荐：

输入错误

推荐：

结束日期不能早于开始日期。

⸻

13.6 Form Layout

移动端：

Single Column

桌面端可以使用双列，但只适用于关联且较短字段，例如：

First Name | Last Name
Start Date | End Date
City       | Country

以下字段应占满整行：

* Description
* Personal Summary
* Project Details
* Reflection
* AI Instructions
* Address
* Skills Selection

⸻

13.7 Form Rules

* 表单必须保存用户已输入内容。
* 长表单应支持自动保存或保存草稿。
* 不要在用户输入过程中频繁弹出 Toast。
* 校验错误应显示在字段附近。
* 提交失败时不要清空表单。
* 第一个错误字段应自动获得焦点。
* 日期选择器必须允许键盘操作。
* 表单必须显示保存状态。
* 离开未保存页面时应提醒用户。
* 不要使用 Placeholder 代替 Label。
* 可选字段应明确标记为“可选”。
* 多步骤表单必须显示当前步骤和总步骤。

⸻

14. Select, Checkbox and Radio

Select

适用于选项数量较多的单选场景。

例如：

* 行业
* 学位类型
* 国家
* CV 模板
* Portfolio 可见性

选项超过 10 个时应支持搜索。

⸻

Checkbox

适用于多个独立选择或 Checklist。

例如：

* Placement 准备清单
* 技能选择
* 导出内容选择

Checkbox Label 必须可以点击。

⸻

Radio Group

适用于选项较少且互斥的选择。

例如：

* Portfolio 可见性
* 导出格式
* CV 风格
* 工作类型

选项数量建议不超过 5 个。

⸻

15. Textarea and Rich Text Editor

Textarea 用于：

* Personal Summary
* Job Description
* Project Description
* Reflection
* Achievement
* AI 补充要求

默认最小高度：

120px

较长内容：

200px–320px

富文本编辑器工具栏应保持精简，仅提供必要功能：

* Heading
* Bold
* Italic
* Bullet List
* Numbered List
* Link
* Undo
* Redo

不要提供过多字体、颜色或排版选项，以避免导出样式不一致。

编辑器应显示：

* 字数
* 保存状态
* AI 优化入口
* Preview 入口

⸻

16. Modal and Dialog

Dialog 用于：

* 确认删除
* 导出设置
* 分享设置
* 模板预览
* 简短编辑
* AI 建议确认

Dialog 不应承载超长复杂表单。

宽度建议：

Small: 400px
Default: 520px
Large: 720px

规则：

* Dialog 必须有明确标题。
* 说明文字应简短。
* 右上角提供关闭按钮。
* Esc 可以关闭非高风险 Dialog。
* 删除确认必须说明具体对象。
* 主要操作放在右侧。
* 移动端 Dialog 可使用 Bottom Sheet 或全屏页面。
* 打开 Dialog 时焦点必须进入 Dialog。
* 关闭后焦点应返回原触发元素。

⸻

17. Toast and Notifications

Toast 用于短暂反馈：

* 保存成功
* 复制成功
* 导出任务已开始
* 分享链接已创建
* 网络操作失败

Toast 不适合展示：

* 长段错误信息
* 表单字段错误
* 必须长期保留的重要通知
* 复杂 AI 结果

位置建议：

Desktop: Top Right
Mobile: Top Center

Toast 自动关闭时间：

Success: 3–4 seconds
Information: 4–5 seconds
Error: 6 seconds or manual close

错误 Toast 应提供必要操作，例如：

* 重试
* 查看详情
* 重新登录

⸻

18. Badges and Status

Badge 用于显示：

* Draft
* Completed
* Processing
* Failed
* Public
* Private
* AI Generated
* Needs Review

状态颜色：

Draft: Gray
Completed: Green
Processing: Blue
Needs Review: Orange
Failed: Red
Public: Green
Private: Gray

规则：

* Badge 文字保持简短。
* 不要只使用颜色表达状态。
* 不要将 Badge 设计得像按钮。
* 可点击筛选标签与状态 Badge 应有不同交互表现。

⸻

19. Tables and Lists

表格适用于：

* 文件列表
* 导出记录
* 版本历史
* 管理页面
* 任务记录

表格不适合：

* CV 卡片
* Portfolio 项目展示
* 移动端主要内容

表格规则：

* 表头必须清晰。
* 行高度建议至少 48px。
* Hover 行使用浅灰背景。
* 操作放在最后一列。
* 多个操作使用 More Menu。
* 空值使用 —。
* 日期格式保持统一。
* 移动端应转换为 Card List 或允许合理横向滚动。
* 表格上方提供搜索、筛选和排序。
* 批量操作只有在确实需要时使用。

⸻

20. Empty States

以下情况必须提供 Empty State：

* 尚未创建 CV
* 尚未创建 Portfolio
* 没有上传文档
* 没有 AI 对话
* 没有导出记录
* 搜索无结果
* Checklist 尚未开始

Empty State 应包含：

* 简单图标或插图
* 明确标题
* 一段说明
* 一个主要操作

示例：

你还没有创建 CV
添加你的教育经历、技能和项目，
快速生成一份专业 CV。
[创建第一份 CV]

不要只显示：

No data

⸻

21. Loading States

根据等待时间选择不同 Loading 表现。

短时间操作

使用：

* Button Spinner
* Inline Spinner

适用于：

* 保存
* 删除
* 简单 API 请求

页面加载

使用：

* Skeleton

适用于：

* Dashboard
* CV 列表
* Portfolio 列表
* Profile 页面

AI 长任务

使用：

* Progress Indicator
* 当前步骤
* 取消按钮
* 状态说明

示例：

正在分析你的 CV……
1. 读取 CV 内容
2. 检查结构
3. 生成改进建议

规则：

* 不要长时间只显示无限旋转 Spinner。
* AI 处理必须告诉用户当前正在进行什么。
* 不要使用虚假的精确百分比。
* 用户可以继续使用其他页面时，应允许后台运行。
* 防止用户重复提交同一任务。

⸻

22. Error States

错误页面应包含：

* 清晰标题
* 简短解释
* 可执行操作
* 必要的错误编号

常用错误：

404

页面不存在
你访问的页面可能已被删除或移动。
[返回 Dashboard]

403

你没有权限访问此内容。
[返回上一页]

500

系统暂时无法完成请求。
请稍后重试。如果问题持续发生，请联系支持人员。
[重新加载]

错误信息不得暴露：

* 后端堆栈
* 数据库信息
* 文件路径
* API Key
* 内部服务名称

⸻

23. Dashboard

Dashboard 应帮助学生快速理解当前进度。

建议包含：

Welcome Section

显示：

* 用户姓名
* 简短欢迎语
* 当前最重要的下一步操作

示例：

下午好，Yiming
你的个人资料已经完成 70%。
完善技能和项目经历后即可生成第一份 CV。

⸻

Progress Overview

显示：

* Profile Completion
* CV Completion
* Portfolio Completion
* Placement Readiness

进度展示应搭配具体说明。

不要只显示百分比。

⸻

Quick Actions

建议包含：

* Create CV
* Add Project
* Upload Document
* Ask AI Assistant

最多展示 4 个主要快捷操作。

⸻

Recent Activity

显示：

* 最近编辑的 CV
* 最近生成的建议
* 最近导出的文件
* 最近更新的 Portfolio

⸻

Next Steps

根据用户状态提供建议，例如：

* 补充技能
* 添加一个项目
* 完成 Placement Checklist
* 审核 AI 建议
* 导出最新 CV

⸻

24. User Profile UI

Profile 页面建议按以下 Section 组织：

* Personal Information
* Contact Information
* Education
* Work Experience
* Skills
* Projects
* Achievements
* Certifications
* Preferences

长页面可以使用：

* 左侧 Section Navigation
* Accordion
* Tabs
* Stepper

每个 Section 应：

* 独立保存
* 显示完成状态
* 支持添加多个条目
* 支持排序
* 支持删除
* 支持编辑

完成状态：

Not Started
In Progress
Completed

不要要求用户一次填写全部资料。

⸻

25. CV Builder UI

CV Builder 是项目核心界面。

桌面端推荐三栏或双栏布局：

左侧：Section Navigation
中间：Content Editor
右侧：Live Preview

较小桌面端可使用：

Editor + Preview Tabs

移动端使用：

Edit Tab
Preview Tab

⸻

25.1 CV Section Navigation

包含：

* Personal Details
* Professional Summary
* Education
* Experience
* Projects
* Skills
* Certifications
* Achievements
* References

每个 Section 显示：

* Section Name
* Completion Status
* Drag Handle
* Visibility Toggle

⸻

25.2 Live Preview

Preview 应：

* 接近最终 PDF 效果
* 保持纸张比例
* 支持缩放
* 支持分页
* 实时反映修改
* 明确显示页面数量

纸张样式：

Background: White
Aspect Ratio: A4
Subtle Shadow
Small Border Radius

不要让 Preview 中的编辑功能过多。

主要编辑操作应在 Editor 中完成。

⸻

25.3 Template Selection

模板列表应显示：

* 模板缩略图
* 模板名称
* 推荐行业
* 风格标签
* Preview
* Select

风格标签示例：

* Modern
* Professional
* Creative
* Technical
* Academic

当前模板使用橙色边框和 Check 图标标记。

⸻

25.4 AI Resume Suggestions

AI 建议使用独立卡片展示。

每条建议应包含：

* 建议类型
* 原始内容
* 推荐内容
* 修改原因
* 接受按钮
* 拒绝按钮
* 手动编辑入口

建议类型示例：

* Clarity
* Grammar
* Impact
* Structure
* Missing Information
* Keyword Match

AI 建议不能直接覆盖用户原文。

⸻

26. Portfolio Builder UI

Portfolio 页面应更强调视觉展示。

支持：

* Project Cards
* Image Gallery
* Project Details
* Skills Used
* Achievements
* Reflections
* External Links

Portfolio Builder 桌面端推荐：

Editor + Live Preview

项目卡片应显示：

* 封面图
* 项目名称
* 简短描述
* 技能标签
* 可见性
* 编辑操作

图片上传区域应支持：

* 点击上传
* 拖拽上传
* 上传进度
* 文件类型说明
* 大小限制说明
* 删除和替换

公开分享前必须显示：

* 当前可见性
* 将公开的内容
* 分享链接状态
* 撤销分享入口

⸻

27. Placement Preparation UI

Placement 页面建议使用：

* Checklist
* Progress Overview
* Guidance Cards
* Resource Links
* AI Support Entry

Checklist 示例：

☑ 完成个人资料
☑ 添加教育经历
☐ 创建 CV
☐ 创建 Portfolio
☐ 检查联系方式
☐ 阅读 Placement 要求

每个 Checklist Item 可以包含：

* 状态
* 简短说明
* 相关页面链接
* 完成时间

官方要求和 AI 建议必须有明确视觉区别。

官方资料建议使用：

蓝色 Information Card
Source Label
Last Updated
External Link

AI 建议建议使用：

橙色 AI Suggestion Card
AI Label
Review Reminder

⸻

28. AI Assistant UI

AI Assistant 页面应采用现代对话布局。

推荐结构：

Conversation Sidebar
Chat Header
Message Area
Composer
Context / Source Panel

⸻

28.1 User Message

Alignment: Right
Background: #F97316
Text: #FFFFFF
Border Radius: 16px 16px 4px 16px

⸻

28.2 Assistant Message

Alignment: Left
Background: #FFFFFF
Border: #E2E8F0
Text: #334155
Border Radius: 16px 16px 16px 4px

Assistant Message 应支持：

* Markdown
* List
* Heading
* Code Block
* Source Citation
* Copy
* Feedback
* Retry

⸻

28.3 Suggested Prompts

空对话页面可以显示：

* 帮我检查 CV
* 如何准备 Placement 申请？
* 帮我优化项目描述
* 我的 Portfolio 还缺少什么？
* 解释 WIL 课程要求

Suggested Prompt 使用轻量 Card，不应设计成 Primary Button。

⸻

28.4 Source Citation

涉及学校要求、课程材料和政策时，回答下方必须显示来源。

来源卡片包含：

* 文档名称
* 章节
* 页码
* 更新时间
* 查看来源

来源与 AI 回答应在视觉上明确区分。

不得显示不存在的来源。

⸻

28.5 AI Disclaimer

在适当位置显示：

AI 生成的内容可能不完全准确。提交申请材料前，请确认所有经历、成绩和个人信息真实无误。

不需要在每一条消息中重复，但在以下页面必须可见：

* AI Assistant 首次使用
* AI CV 建议
* AI Portfolio 建议
* 最终导出前

⸻

29. File Upload UI

上传组件必须清晰展示：

* 支持的格式
* 最大文件大小
* 当前上传状态
* 失败原因
* 删除或重新上传操作

默认上传区域：

Background: #F8FAFC
Border: 1px dashed #CBD5E1
Border Radius: 12px
Min Height: 160px

Hover：

Background: #FFF7ED
Border: #FB923C

Dragging：

Background: #FFEDD5
Border: #F97316

文件上传完成后显示：

* 文件图标
* 文件名称
* 文件大小
* 上传状态
* 删除按钮

⸻

30. Export UI

导出流程应允许用户选择：

* PDF
* Word
* 是否包含特定 Section
* 模板
* 文件名称

导出过程中显示：

正在生成文件

导出完成后显示：

* 文件名
* 格式
* 生成时间
* 下载按钮
* 分享按钮

不要在文件尚未生成完成时展示无效下载按钮。

⸻

31. Search and Filtering

搜索框建议包含：

* Search Icon
* Placeholder
* Clear Button
* Keyboard Focus State

示例：

搜索 CV、Portfolio 或文件

筛选建议使用：

* Select
* Filter Popover
* Filter Chips

已应用筛选必须清晰显示，并提供：

清除全部

搜索无结果必须显示 Empty State，而不是空白区域。

⸻

32. Icons

推荐使用：

Lucide Icons

规则：

* 同一项目只使用一套主要图标库。
* 图标线宽保持一致。
* 默认图标尺寸为 16px、20px 或 24px。
* 图标应辅助文字，不应替代关键文字。
* 独立图标按钮必须提供 Tooltip。
* 不使用含义模糊的图标。
* 删除使用 Trash 图标。
* 编辑使用 Pencil 图标。
* 添加使用 Plus 图标。
* 导出使用 Download 图标。
* 分享使用 Share 图标。
* AI 功能可以使用 Sparkles 图标。

⸻

33. Illustrations and Images

插图应保持：

* 简洁
* 现代
* 柔和
* 与橙色品牌一致
* 不过度卡通化

适用于：

* Landing Page
* Empty State
* Onboarding
* Success Page

用户上传图片必须：

* 保持比例
* 避免拉伸
* 提供加载占位
* 处理加载失败
* 支持响应式显示

头像推荐使用正方形裁剪和圆形展示。

⸻

34. Motion and Animation

动画应服务于理解和反馈。

推荐动画时间：

Fast: 150ms
Default: 200ms
Slow: 300ms

推荐缓动：

cubic-bezier(0.2, 0, 0, 1)

适用场景：

* Button Hover
* Dropdown Open
* Dialog Enter
* Sidebar Collapse
* Tab Change
* Card Hover
* Progress Update

规则：

* 不要使用超过 500ms 的普通交互动画。
* 不要为所有元素添加动画。
* 不要使用影响阅读的持续动画。
* 支持 prefers-reduced-motion。
* 页面切换动画应轻量。
* AI 内容出现时可使用轻微 Fade，不使用过度打字动画。
* 不应通过动画拖延实际操作。

⸻

35. Responsive Design

项目必须采用 Mobile-first。

建议断点：

sm: 640px
md: 768px
lg: 1024px
xl: 1280px
2xl: 1536px

⸻

35.1 Mobile

目标宽度：

320px–767px

规则：

* 页面左右 Padding 使用 16px。
* 使用单列布局。
* Sidebar 转为 Drawer。
* 表单按钮可占满宽度。
* Modal 可转为 Bottom Sheet 或全屏页面。
* CV Editor 和 Preview 使用 Tabs。
* 表格转为 Card List。
* 不依赖 Hover。
* 所有点击区域至少 44×44px。
* 主要操作放在容易触达的位置。
* 固定底部操作栏不得遮挡内容。

⸻

35.2 Tablet

目标宽度：

768px–1023px

规则：

* 页面 Padding 使用 24px。
* Sidebar 默认可以折叠。
* 简单页面可以使用双列布局。
* CV 编辑器优先使用 Editor/Preview Tabs。
* Dashboard 卡片使用两列。
* Dialog 最大宽度不能超过屏幕。

⸻

35.3 Desktop

目标宽度：

1024px+

规则：

* 显示完整 Sidebar。
* Dashboard 可使用 3–4 列布局。
* CV Builder 可以使用 Editor + Preview。
* 页面内容居中并设置最大宽度。
* 复杂筛选可以横向排列。
* 充分利用空间，但不能让正文行宽过长。

⸻

35.4 Responsive Testing

至少测试：

375 × 812
768 × 1024
1024 × 768
1280 × 800
1440 × 900

必须检查：

* 是否出现横向滚动
* 按钮是否被截断
* 表单是否溢出
* Dialog 是否超出屏幕
* 导航是否可操作
* Preview 是否可查看
* 表格是否合理转换
* 键盘是否遮挡输入框
* 固定元素是否遮挡内容

⸻

36. Accessibility

项目至少遵循 WCAG 2.1 AA 的基本原则。

必须：

* 使用语义化 HTML。
* 所有 Input 都有 Label。
* 所有图片都有 Alt。
* 所有图标按钮都有 aria-label。
* 所有功能可以通过键盘操作。
* Focus 状态始终可见。
* Dialog 正确管理焦点。
* 错误信息能够被屏幕阅读器识别。
* 状态变化使用适当的 Live Region。
* 颜色对比度满足要求。
* 不仅依赖颜色传递信息。
* 支持浏览器缩放到 200%。
* 支持 prefers-reduced-motion。

Focus Ring 推荐：

2px solid #F97316
2px offset

不要通过：

outline: none;

直接移除所有 Focus 样式。

⸻

37. Dark Mode

第一阶段可以不实现 Dark Mode，但所有颜色应尽可能通过 Design Token 定义，为未来扩展保留空间。

不要在组件中大量硬编码颜色。

推荐通过 CSS Variables 管理：

:root {
  --background: #f8fafc;
  --foreground: #0f172a;
  --card: #ffffff;
  --primary: #f97316;
  --primary-foreground: #ffffff;
  --secondary: #334155;
  --muted: #f1f5f9;
  --muted-foreground: #64748b;
  --border: #e2e8f0;
  --destructive: #dc2626;
}

未来 Dark Mode 可以覆盖对应变量。

⸻

38. Design Tokens

建议在 Tailwind 和全局 CSS 中统一定义以下 Token：

Colors
Typography
Spacing
Border Radius
Shadow
Animation Duration
Z-index
Container Width
Breakpoints

示例：

:root {
  --color-primary: #f97316;
  --color-primary-hover: #ea580c;
  --color-primary-soft: #fff7ed;
  --color-background: #f8fafc;
  --color-surface: #ffffff;
  --color-text-primary: #0f172a;
  --color-text-secondary: #334155;
  --color-text-muted: #64748b;
  --color-border: #e2e8f0;
  --color-border-strong: #cbd5e1;
  --radius-sm: 6px;
  --radius-md: 8px;
  --radius-lg: 12px;
  --radius-xl: 16px;
  --shadow-sm: 0 1px 2px rgba(15, 23, 42, 0.05);
  --shadow-md:
    0 1px 3px rgba(15, 23, 42, 0.08),
    0 1px 2px rgba(15, 23, 42, 0.04);
}

规则：

* 组件优先使用 Token。
* 不要在多个组件中重复硬编码相同颜色。
* 修改品牌颜色时，应只需要修改 Token。
* Token 名称应描述用途，而不是描述具体颜色。

推荐：

primary
background
foreground
muted
border
destructive

避免：

orangeButton
lightGrayText

⸻

39. Shadcn/UI Usage

项目优先复用 Shadcn/UI 组件，包括：

* Button
* Input
* Textarea
* Select
* Checkbox
* Radio Group
* Dialog
* Sheet
* Dropdown Menu
* Tabs
* Card
* Badge
* Toast
* Tooltip
* Progress
* Skeleton
* Accordion
* Alert
* Avatar
* Command
* Popover

规则：

* 不要重复创建已有基础组件。
* Shadcn/UI 组件应根据本设计规范统一调整。
* 不要在不同页面为同一组件设置完全不同的风格。
* 业务组件应建立在基础 UI 组件之上。
* 修改基础组件时必须检查所有使用位置。
* 不要在页面中大量复制 Shadcn 示例代码而不进行结构整理。

⸻

40. Component States

所有交互组件必须考虑以下状态：

Default
Hover
Focus
Active
Disabled
Loading
Error
Success
Selected

例如按钮不能只实现 Default 和 Hover。

输入框不能只实现 Default 和 Error。

可选择卡片必须具有明确的 Selected 状态。

AI 建议必须具有：

Pending Review
Accepted
Rejected
Edited

⸻

41. Content and Microcopy

文案应：

* 简洁
* 明确
* 友好
* 专业
* 面向行动
* 避免技术术语

推荐：

保存并继续
创建第一份 CV
添加项目经历
查看 AI 建议
重新生成
下载 PDF

避免：

Submit
Confirm
Execute
Process Data
Operation Successful

除非界面整体使用英文，否则不要中英文混用。

错误文案必须说明：

* 发生了什么
* 用户可以做什么

例如：

文件上传失败。请确认文件小于 10MB，并使用 PDF 或 Word 格式。

⸻

42. AI Content Visual Rules

AI 生成内容必须在视觉上与用户原始内容区分。

建议使用：

Sparkles Icon
AI Generated Badge
Soft Orange Background
Review Reminder

AI 建议卡片：

Background: #FFF7ED
Border: #FED7AA
Icon: #EA580C

必须显示：

AI 建议

或：

AI Generated

不得让用户误以为 AI 生成内容是学校官方信息。

涉及官方资料时应显示：

Official Source

AI 内容和官方资料必须使用不同视觉标识。

⸻

43. Data Privacy UI

涉及以下操作时必须提供清晰提示：

* 上传 CV
* 上传 Portfolio 文件
* 创建公开链接
* 向 AI 发送个人资料
* 删除账户
* 删除 CV
* 删除 Portfolio

公开分享 Dialog 应明确说明：

* 哪些内容将被公开
* 谁可以访问
* 链接是否可以撤销
* 是否允许搜索引擎索引

删除账户应使用高风险确认流程，不得只使用普通确认按钮。

⸻

44. Onboarding

首次使用建议提供 3–4 步 Onboarding：

1. 完善个人资料
2. 创建专业 CV
3. 建立 Portfolio
4. 完成 Placement 准备

Onboarding 应：

* 可以跳过
* 可以稍后重新查看
* 不超过 4 个步骤
* 使用简短文字
* 提供明确的下一步操作

完成 Onboarding 后进入 Dashboard，并展示个性化下一步建议。

⸻

45. Page Templates

Standard List Page

Page Header
Description
Primary Action
Search / Filters
Content List
Pagination or Load More

Standard Form Page

Breadcrumb
Page Header
Form Sections
Save Status
Primary and Secondary Actions

Standard Detail Page

Breadcrumb
Title and Status
Primary Actions
Summary
Detail Sections
Activity or History

Standard Builder Page

Builder Header
Section Navigation
Editor
Preview
Save / Export Actions

Standard AI Page

Context Header
Conversation
Sources
Prompt Suggestions
Message Composer

⸻

46. Z-index System

推荐统一设置：

Base Content: 0
Sticky Element: 10
Header: 20
Sidebar: 30
Dropdown: 40
Overlay: 50
Dialog: 60
Toast: 70
Tooltip: 80

不要在组件中随意使用：

z-index: 9999

除非基础组件系统统一定义。

⸻

47. UI Development Rules

开发 UI 时必须：

* 优先复用现有组件。
* 遵循 Tailwind CSS 规范。
* 遵循 Shadcn/UI 组件结构。
* 不使用行内样式。
* 不随意硬编码颜色。
* 不创建重复组件。
* 使用 TypeScript 严格类型。
* 处理所有组件状态。
* 实现响应式布局。
* 实现键盘操作。
* 提供 Loading、Empty 和 Error 状态。
* 对 AI 内容添加明确标识。
* 对危险操作添加确认。
* 对长任务提供状态反馈。
* 保持页面视觉层级清晰。

⸻

48. UI Completion Checklist

完成一个页面或组件后必须检查以下内容。

Visual

* 是否符合橙白品牌配色
* 标题层级是否清晰
* 间距是否使用统一规则
* 圆角是否一致
* 边框和阴影是否合理
* 是否存在过多强调色
* 页面是否过度拥挤
* 文本是否容易阅读

Interaction

* Hover 是否正常
* Focus 是否可见
* Loading 是否正常
* Disabled 是否明显
* Error 是否清晰
* Success 是否有反馈
* 是否防止重复提交
* 危险操作是否需要确认

Responsive

* Mobile 是否正常
* Tablet 是否正常
* Desktop 是否正常
* 是否存在横向滚动
* 按钮是否被截断
* 表单是否溢出
* Dialog 是否超出屏幕
* 导航是否可以正常打开

Accessibility

* Input 是否具有 Label
* 图片是否具有 Alt
* 图标按钮是否具有 aria-label
* 是否支持键盘操作
* Focus 顺序是否正确
* 颜色对比度是否足够
* 是否只使用颜色表达状态
* Dialog 是否正确管理焦点

Project-specific

* AI 内容是否具有明确标识
* AI 修改是否需要用户确认
* 官方来源是否清晰显示
* 用户原始内容是否保留
* CV Preview 是否接近导出效果
* Portfolio 图片是否正确裁剪
* Placement 进度是否清晰
* 上传限制是否明确显示
* 导出状态是否清晰
* 隐私和分享状态是否明确

⸻

49. Core UI Principles

所有 UI 设计和实现必须遵循以下核心原则：

清晰优先于装饰
一致性优先于个性化样式
用户控制优先于自动执行
内容优先于复杂视觉效果
可访问性优先于纯视觉表现
移动端体验优先于桌面端补丁
真实来源优先于 AI 推测
专业可信优先于过度娱乐化

最终界面应让学生感受到：

我知道下一步应该做什么。
我能够控制自己的内容。
AI 建议是清晰且可以审核的。
我的资料和申请材料看起来专业可信。
这个系统能够帮助我完成 Placement 准备。