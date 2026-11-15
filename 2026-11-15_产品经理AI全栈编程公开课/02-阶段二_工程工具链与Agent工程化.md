# 02 · 阶段二: 现代工程工具链与AI Agent架构师方法论(第3–4周)

> [专题总览](README.md) · [学习路径总览](00-学习路径总览.md) · 上一阶段 [阶段一](01-阶段一_编程思维与软件构造.md) · 下一阶段 [阶段三](03-阶段三_内部工具与数据库.md)

**阶段目标**: 彻底告别"在网页聊天框里复制粘贴代码"的低效模式。搭建专业级本地开发环境, 掌握命令行、Git版本控制底层逻辑、自动化质量门禁(Linter/CI), 以及Claude Code等Agent工具的工程化编排。

这是连接"懂一点语法"与"能指挥AI开发复杂工程"的最关键桥梁。**绝大多数非科班人员在AI开发时卡壳, 不是因为不会写自然语言提示词, 而是不懂终端命令行、环境变量、包管理器、Git分支回滚和AI上下文架构。**

## 学习顺序

1. [The Missing Semester of Your CS Education (2026新版)](#1-the-missing-semester-of-your-cs-education-2026新版) — MIT出品, 核心7讲, 全栈PM必刷
2. [Anthropic Claude Code 101](#2-claude-code-101--claude-code-in-action) — 一晚上学完的官方工具课
3. [Claude Code: A Highly Agentic Coding Assistant](#3-claude-code-a-highly-agentic-coding-assistant) — DeepLearning.AI出品, 三个实战项目演练
4. [Claude Code: Software Engineering with Generative AI Agents](#4-claude-code-software-engineering-with-generative-ai-agents) — 范德堡出品, AI委派工程学
5. ([CS: AI-Assisted Software Development 资源库](#5-cs-ai-assisted-software-development-fall-2026-资源库) — UW–Madison, 随时当字典查)
6. 交付里程碑2

## 课程详情

### 1. The Missing Semester of Your CS Education (2026新版)

| 项 | 内容 |
|---|---|
| 机构/讲师 | MIT CSAIL · Anish Athalye, Jon Gjengset, Jose Javier Gonzalez Ortiz |
| 形式与费用 | 官网、GitHub与YouTube完全免费开源(CC BY-NC-SA 4.0) |
| 学时 | 9讲(每讲1小时视频+课后练习, 总计约9–20小时) |
| 链接 | <https://missing.csail.mit.edu/2026/> · GitHub <https://github.com/missing-semester/missing-semester> |

**核心内容**(2026年1月重大改版, 新增5门全新讲座): Shell与命令行环境; 开发环境与工具(VS Code/Cursor、LSP语言服务器、AI补全); 调试与性能分析; Git底层数据模型与版本控制; 代码打包与发布(uv、pyproject.toml); Agentic Coding(经理与实习生模型、TDD、MCP、AGENTS.md、Skills、Subagents、git worktrees); Beyond the Code(技术沟通、README与Commit规范、Code Review); Code Quality(格式化、Linter、单元测试、Pre-commit、GitHub Actions CI/CD)。

**PM定制学习策略**: **全栈PM必刷核心课!** 完整阅读9讲笔记与视频。核心7讲及要点:
- **1/12 与 1/13 Shell与命令行环境** — 路径导航、流与管道`|`、环境变量`$PATH`与`.env`
- **1/14 开发环境与工具** — 配置VS Code或Cursor及LSP语言服务器代码跳转
- **1/16 Version Control and Git(重中之重)** — 从底层快照与DAG有向无环图理解 commit/branch/merge/stash/restore 与.gitignore, 完成分支冲突解决练习
- **1/20 Packaging and Shipping Code** — 依赖冲突、uv虚拟环境(`uv venv`)与pyproject.toml
- **1/21 Agentic Coding** — 上下文窗口管理、AGENTS.md/CLAUDE.md配置、Skills、Subagents与git worktrees并行Agent
- **1/22 与 1/23 Beyond the Code & Code Quality** — 说明设计原因"Why"的Commit/README规范; 配置格式化、ruff、pre-commit钩子与GitHub Actions自动CI

**可跳过**: 第4讲(调试)中的Linux底层C/C++工具(gdb/bpftrace/valgrind)。

### 2. Claude Code 101 & Claude Code in Action

| 项 | 内容 |
|---|---|
| 机构/讲师 | Anthropic Academy / Coursera · Anthropic官方团队 |
| 形式与费用 | Coursera及Anthropic Academy完全免费(实操需自备付费订阅或API Key) |
| 学时 | 101为4模块约1.5–2小时; in Action约1小时 |
| 链接 | <https://www.coursera.org/learn/claude-code-101> · <https://anthropic.skilljar.com/claude-code-101> |

**核心内容**: Agent循环机制、权限与安全控制、Explore → Plan → Code → Commit日常工作流、Plan Mode(先规划策略再改代码)、CLAUDE.md持久化项目记忆、自定义Skills、Subagents(子Agent上下文隔离)、Hooks(确定性自动化控制)与MCP连接外部工具。

**PM定制学习策略**: AI工具实操必修, 花一个晚上学完。重点掌握:
- **Plan Mode** — 防止AI盲目改动代码
- **CLAUDE.md + Hooks** 的工程化配置

若不想折腾终端, 初期也可先用Claude桌面端Code标签页或网页版上手。

### 3. Claude Code: A Highly Agentic Coding Assistant

| 项 | 内容 |
|---|---|
| 机构/讲师 | DeepLearning.AI & Anthropic · Elie Schoppik (Anthropic) |
| 形式与费用 | DeepLearning.AI免费开放(2026年8月更新) |
| 学时 | 10节视频课共2小时 |
| 链接 | <https://www.deeplearning.ai/courses/claude-code-a-highly-agentic-coding-assistant> |

**核心内容**: 通过三个实战项目演练AI工程最佳实践:
1. 探索并开发RAG聊天机器人代码库
2. 重构电商数据Jupyter Notebook并转化为交互式仪表盘
3. 连接Figma MCP导入设计稿生成Web应用, 用Playwright MCP自动打开浏览器截图、引导AI优化UI设计

**PM定制学习策略**: **高度契合PM工作流!** 尤其第3个项目(Figma设计稿 → MCP → 生成Web界面 → Playwright浏览器自动截图调优), 直接打通产品经理从设计稿到前端验证的闭环。

### 4. Claude Code: Software Engineering with Generative AI Agents

| 项 | 内容 |
|---|---|
| 机构/讲师 | Vanderbilt University (Coursera) · Dr. Jules White |
| 形式与费用 | Coursera免费旁听(Audit Free; 实操需Claude Code付费订阅) |
| 学时 | 6个模块约5–6小时 |
| 链接 | <https://www.coursera.org/learn/claude-code> |

**核心内容**: 专为"像Tech Lead一样委派任务"设计——Best-of-N多方案探索模式、生成前定义代码质量评估标准(Rubrics)与验收条件、Token感知的模块化代码库架构、基于git worktree的多Agent并行开发、多模态提示词; 核心原则: "当AI反复出错时, 优先改进提示词、上下文与验证闭环, 而非手动修补症状"。

**PM定制学习策略**: 建立AI架构师思维的核心课, 官方对比指南明确推荐技术负责人与管理者学习。内化每次迭代Checklist:

**保存Git检查点 → 定义可度量任务 → 写验收标准 → 跑全量验证 → 审查Diff**

### 5. CS: AI-Assisted Software Development (Fall 2026 资源库)

| 项 | 内容 |
|---|---|
| 机构/讲师 | UW–Madison (威斯康星大学麦迪逊分校) CS教学团队 |
| 形式与费用 | 课程资源指南与阅读清单全网公开免费 |
| 学时 | 10周大学课程配套资源(Unit 1 + Unit 2) |
| 链接 | <https://aicoding.cs.wisc.edu/fa26/resources.html> · 主页 <https://aicoding.cs.wisc.edu/> |

**核心内容**: Unit 1(第1–5周)Claude Code工作流、TypeScript基础、Vitest单元测试、GitLab CI/CD、Docker容器、FastAPI后端、SQL与OWASP安全鉴权; Unit 2(第6–10周)云端LLM API、MCP开发、RAG架构与Sentry生产监控。

**PM定制学习策略**: **作为全栈工程百科导航字典使用**——遇到单元测试(Vitest)、接口设计(FastAPI)、安全鉴权(JWT/OWASP)或错误监控(Sentry)盲区时, 直接按其resources.html精选的免费必读指南查阅。不需要从头刷。

## 里程碑2: AI工程标准脚手架仓库

**任务**: 在GitHub上搭建一个属于自己的"AI工程标准脚手架仓库", 之后所有项目从它起步。

**必须内置**:
- 结构化CLAUDE.md — 明确模块边界、测试与Linter命令、禁止操作清单
- .gitignore — 至少忽略.env与虚拟环境目录
- 单元测试框架(pytest或Vitest)
- GitHub Actions自动检查工作流(Linter+测试)

**验收清单**:
- [ ] CLAUDE.md包含架构边界/命名约定/验证命令/禁止操作四要素
- [ ] .gitignore忽略密钥文件
- [ ] 故意提交一个错误, CI能拦截
- [ ] push后Actions全绿

## 阶段完成清单

- [ ] Missing Semester核心7讲笔记读完(系统路径: 全部9讲+练习)
- [ ] Claude Code 101 + in Action学完
- [ ] DeepLearning.AI Claude Code课三个项目跑通(至少复刻Figma→Playwright闭环)
- [ ] 范德堡课学完, 迭代Checklist内化
- [ ] 里程碑2交付
