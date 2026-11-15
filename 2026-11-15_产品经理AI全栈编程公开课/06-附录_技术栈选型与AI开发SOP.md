# 06 · 附录: 标准技术栈选型与AI开发八步SOP

> [专题总览](README.md) · [学习路径总览](00-学习路径总览.md)

完成课程学习后, 实际构建内部工具与独立产品时的选型与操作守则。两套"AI原生黄金技术栈"经高校课程与行业验证, 目标是让你少走选型弯路。

## A. 两大场景标准技术栈选型表

### 场景A: 企业内部工具与AI自动化工作流(Internal Tools)

| 架构层级 | 选型 | 理由 |
|---|---|---|
| 语言与环境 | Python 3.10+, uv管理虚拟环境与pyproject.toml | Python拥有最丰富的AI与数据处理生态 |
| 前端/UI | Streamlit(数据看板/CRUD后台) 或 Gradio(多模态AI工具) | 完全免除手写前端代码负担 |
| 后端/API | 轻量逻辑直接内置于Streamlit脚本; 复杂后端用FastAPI | FastAPI内置Pydantic数据校验与自动接口文档 |
| 数据库与鉴权 | SQLite(单机轻量) 或 Supabase(PostgreSQL) | 免运维云数据库+可视化数据管理+现成用户鉴权 |
| 质量门禁 | Ruff(格式化+Linter) + mypy(类型检查) + pytest + Streamlit Agent API | 为AI提供确定性反馈闭环, 让AI自己跑测试读报错自修复 |
| 部署与监控 | Streamlit Community Cloud(share.streamlit.io) / Hugging Face Spaces / Docker | 零服务器运维, 免费上线 |

### 场景B: 独立全栈网站与跨平台App(Indie Web & Mobile Apps)

| 架构层级 | 选型 | 理由 |
|---|---|---|
| 语言与环境 | TypeScript(Node.js 20.19+) | 静态类型检查让AI在编译阶段捕获参数与接口类型错误 |
| Web前端 | Next.js 15/16 (App Router) + Tailwind CSS + shadcn/ui | 模块化文件并置架构(Colocation), 极易被AI理解与扩展 |
| App前端 | React Native (Expo) | 与Web端直接共享React与TypeScript技能 |
| 后端/API | Next.js React Server Actions与API Routes(或独立FastAPI服务) | Server Actions直接在服务端安全执行数据库变更并自动刷新前端缓存 |
| 数据库与鉴权 | Supabase 或 Prisma Postgres/Neon + NextAuth.js / OWASP鉴权规范 | 免运维云数据库、Prisma Studio可视化管理、现成鉴权方案 |
| 质量门禁 | Biome/Prettier + Vitest(单元测试) + Playwright MCP(浏览器UI视觉自检) | AI自动打开浏览器截图对照修正UI |
| 部署与监控 | Vercel(绑定GitHub自动CI/CD与PR预览URL) + Sentry + OpenTelemetry | push主分支自动重部署, PR即预览链接提前排错 |

**选型总原则**: 场景A求快(数小时内上线团队可用), 场景B求稳(商业级鉴权+CI/CD+监控)。两套栈共享Supabase——内部工具与独立产品可以复用同一套数据与账号体系。

## B. 日常驱动AI Coding Agent的八步工程守则(SOP)

来自MIT《Missing Semester 2026》与范德堡《Claude Code》课程的工程实践。开发任何内部工具或独立网站功能时, 严格遵循:

1. **初始化项目契约(CLAUDE.md / AGENTS.md)** — 新建仓库第一时间写CLAUDE.md, 写明架构边界、文件与命名约定、业务逻辑存放位置、禁止执行的操作、完成任务前必须运行的验证命令(测试、Linter与构建命令)。
2. **加载官方专属技能包与高密度文档(Skills & llms.txt)** — 用Streamlit等框架先运行 `streamlit skills` 加载匹配当前版本的官方Agent技能包; 引入外部库时优先提供标准化llms.txt紧凑文档而非原始HTML网页, 大幅节省上下文空间。
3. **先探索与规划, 后写代码(Explore → Plan → Code → Commit)** — 收到新需求切勿让AI直接改代码。先用Plan Mode让AI阅读相关文件并输出修改策略、接口变更与验收标准; 你以PM视角审查计划无误后, 再授权写代码。
4. **小步快跑与干净的Git检查点(Clean Checkpoints)** — 每次新任务前先保存干净Commit; 每次只定义一个可度量的单一任务并明确验收标准; 不把重构、修Bug和开发新功能混在同一次提交。
5. **测试先行(TDD)与MCP闭环取代人工排错** — 核心业务逻辑先让Agent写单元测试(pytest或Vitest), 你审核测试是否覆盖业务边界, 再让Agent写实现并通过测试; 前端界面调整接入Figma MCP与Playwright MCP, 让Agent自动开浏览器截图并对照设计稿修正UI。
6. **回滚与流程修复法则(Rewind & Process Repair)** — Agent陷入调试死循环或反复修不好同一问题时, 切勿继续发抱怨式追加提示词, 也不要手动修补表层症状。立即 /rewind 撤销对话步骤或 git restore 恢复代码, /clear 清空无关上下文, 反思并补充缺失的上下文说明、示例或自动化测试后重新运行。
7. **关键架构用Best-of-N并行探索** — 面对多种合理架构选型或需对比UI设计变体时, 用git worktree在独立文件夹检出多个分支, 同时启动多个Agent生成候选方案, 依预设评估量表(Rubrics)与测试结果择优合并。
8. **上线前Diff审查与安全门禁(Diff & Security Review)** — 合并入主分支触发自动上线前, 亲自审查git diff(可调只读AI Subagent协助Code Review), 重点确认三点: .env中数据库与API密钥已写入.gitignore防泄露; 关键路由已配置身份认证与授权检查(AuthN/AuthZ); 全量自动化测试100%通过。

## C. 快速排错决策卡

| 症状 | 第一动作 |
|---|---|
| AI反复修不好同一Bug | 不是提示词不够凶——回滚(/rewind或git restore), 补上下文或测试后重来(守则6) |
| 改A功能弄崩B功能 | 缺规约与测试——回滚, 先补测试锚定行为再改(守则3/5) |
| 上下文越聊越乱 | /clear清空, 从干净Git检查点重新描述任务 |
| 单文件越来越大 | 触发Compaction前兆——按模块拆分, 保持AI只在局部施工(五原则之二) |
| AI生成的代码看不懂 | 回阶段一补CS50P专题与6.1020 Reading; 验证AI代码比手写更依赖读码能力 |
| 不知道该信AI还是信测试 | 永远信测试——测试是你定义的验收标准, AI只是碰巧通过它 |
