Work Integrated Learning AI Assistant

1. 项目概述（Project Overview）

Work Integrated Learning AI Assistant（WIL AI 助手）是一款面向大学生的智能职业发展辅助平台，旨在帮助学生更高效地完成实习（Placement）、Industry Project 和 Graduate Program 的申请准备工作。

系统通过整合人工智能（AI）、简历生成、作品集构建、知识库检索（RAG）以及职业指导功能，为学生提供一站式职业发展支持，提高申请材料质量和求职竞争力。

核心功能包括：

- AI 简历生成（AI Resume Builder）
- AI 作品集生成（AI Portfolio Builder）
- Placement 准备指导
- AI 职业顾问聊天助手
- PDF 导出与分享
- 用户资料管理

---

2. 项目目标（Goals）

业务目标

- 帮助学生快速创建专业简历
- 帮助学生构建个人作品集
- 提供 Placement 申请指导
- 提升学生就业准备度
- 减少简历和作品集制作时间
- 提高学生申请成功率

技术目标

- 构建可扩展的 AI 助手系统
- 支持基于 RAG 的知识问答
- 支持多种简历模板
- 支持多种作品集模板
- 支持 PDF 导出
- 支持未来移动端扩展

---

3. 目标用户（Target Users）

主要用户

- WIL 课程学生
- 实习申请者
- Graduate Program 申请者
- 应届毕业生
- 计算机及工程类学生

次要用户

- Career Advisor（职业导师）
- Academic Supervisor（学术导师）
- Placement Coordinator（实习协调员）

---

4. MVP 范围（Minimum Viable Product）

MVP 包含内容

用户系统

- 用户注册
- 用户登录
- JWT 身份认证
- 用户资料管理

简历生成模块

- 个人信息填写
- 教育经历填写
- 项目经历填写
- 技能填写
- 简历模板选择
- PDF 导出

---

MVP 不包含内容

以下功能不属于第一阶段开发：

作品集模块

- 项目展示
- 技能展示
- 成果展示
- 作品集模板
- PDF 导出

Placement 准备模块

- Placement Checklist
- 简历检查建议
- 面试准备建议
- 求职指导

AI 助手

- 聊天界面
- 简历优化建议
- 作品集优化建议
- Placement 问答

RAG 知识库

- WIL Handbook
- Placement Guidelines
- Resume Writing Guide
- Interview Guide

其他

- LinkedIn 同步
- 视频面试分析
- 工作推荐系统
- 管理员后台
- 多语言支持
- 实时协作编辑

---

5. 页面设计（Pages / Routes）

公共页面

/

首页（Landing Page）

功能：

- 产品介绍
- 功能展示
- 注册入口
- 登录入口

---

/login

登录页面

功能：

- 用户登录
- 忘记密码

---

/register

注册页面

功能：

- 用户注册
- 邮箱验证（未来扩展）

---

受保护页面

/dashboard

用户仪表盘

功能：

- 用户信息概览
- 简历完成度
- 作品集完成度
- Placement 准备进度

---

/profile

个人资料管理

功能：

- 基本信息
- 教育背景
- 技能管理
- 工作经历管理

---

/resume

简历编辑器

功能：

- 编辑简历
- AI 内容生成
- AI 内容优化
- 模板切换

---

/resume/preview

简历预览页

功能：

- 实时预览
- PDF 导出

---

/portfolio

作品集编辑器

功能：

- 项目管理
- 技能展示
- 成果展示
- 模板切换

---

/portfolio/preview

作品集预览页

功能：

- 在线预览
- PDF 导出

---

/assistant

AI 职业助手

功能：

- AI 对话
- 简历问答
- Placement 问答
- 职业发展建议

---

/resources

资源中心

功能：

- WIL Handbook
- Resume Guide
- Interview Guide
- Career Resources

---

6. 功能需求（Features）

用户管理模块

用户认证

- JWT 登录认证
- Refresh Token
- 密码加密存储
- 会话管理

用户资料管理

支持保存：

- 个人信息
- 教育经历
- 技能信息
- 工作经历
- 获奖经历
- 证书信息

---

简历生成模块

AI Resume Builder

用户填写：

- 教育背景
- 技能信息
- 项目经历
- 工作经历

系统自动生成：

- 专业简历内容
- 职业描述
- 项目描述

简历模板

支持：

- Software Engineer
- Data Analyst
- IT Graduate
- General Placement

导出功能

支持：

- PDF

---

作品集模块

Portfolio Builder

支持：

- 项目展示
- 技能展示
- 成果展示
- Reflection 展示

Portfolio Templates

支持：

- Modern
- Academic
- Professional

导出与分享

支持：

- PDF 导出
- 在线分享链接

---

AI 助手模块

AI Chat Assistant

支持：

- 简历优化建议
- 项目描述优化
- Placement 问答
- 面试准备指导

---

RAG 知识库模块

知识来源：

- WIL Handbook
- Course Outline
- Placement Policy
- Career Resources

工作流程：

用户提问

↓

Embedding 向量化

↓

Vector Database 检索

↓

返回相关文档片段

↓

LLM 生成答案

---

Placement Preparation 模块

Placement Checklist

例如：

- Resume 完成
- Portfolio 完成
- LinkedIn 更新
- Interview 准备完成

求职资源

包括：

- Resume Writing Tips
- Interview Guide
- Professional Presentation Guide

---

7. 未来扩展计划（Future Plans）

Phase 2

AI Resume Review

自动检测：

- 拼写错误
- 语法错误
- ATS 兼容性

AI Portfolio Review

自动分析：

- 项目质量
- 技能覆盖度
- 展示效果

LinkedIn Integration

支持：

- LinkedIn 信息导入
- 自动生成简历

Job Recommendation

根据：

- 技能
- 兴趣
- 课程背景

推荐：

- Internship
- Placement
- Graduate Program

---

Phase 3

AI Mock Interview

支持：

- 模拟面试
- 自动评分
- 面试反馈

---

9. 验收标准（Acceptance Criteria）

功能验收

用户系统

- 用户可正常注册
- 用户可正常登录
- JWT 身份认证正常工作
- 用户资料可保存

简历模块

- 用户可创建简历
- 可切换模板
- 可导出 PDF

作品集模块

- 用户可创建作品集
- 可展示项目内容
- 可导出 PDF

AI 助手

- 可正常聊天
- 可回答 Placement 相关问题
- 可基于知识库回答问题

---

技术验收

Frontend

- Next.js 项目构建成功
- TypeScript 无错误
- 支持移动端响应式布局

Backend

- FastAPI 正常运行
- RESTful API 正常工作
- JWT 鉴权正常工作

Database

- PostgreSQL 正常运行
- 数据持久化正常

AI

- OpenAI API 正常调用
- RAG 检索正常运行

Deployment

- Docker Compose 启动成功
- 前后端容器正常通信
- 数据库连接正常
- 项目可一键部署
- 无阻塞性 Bug
- 所有核心功能可正常使用


