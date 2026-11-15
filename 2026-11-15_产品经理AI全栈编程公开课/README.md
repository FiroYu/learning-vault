> 📦 本文收录于开源学习库 **[FiroYu/learning-vault](https://github.com/FiroYu/learning-vault)**
> 由 FiroYu 的 Agent 整理 · 2026-11 · 素材来源: 《产品经理AI全栈编程公开课调研》(2026-11, 含70条参考文献)

# 产品经理AI全栈编程公开课 · 系统学习路径

面向**零代码基础、但已具备用代码完成简单工具经验**的产品经理(PM), 用 15 周系统学习, 完成从"会用AI写简单脚本的PM"到"能独立交付生产级产品的AI全栈构建者"的跃迁。三大核心目标:

1. 系统掌握软件开发方法与原则
2. 借助AI独立完成网站与App开发
3. 制作并上线内部工具

## 核心范式: 从手写语法到规约驱动的AI架构师

传统路线让初学者花数百小时背语法、手写算法; 在AI编程Agent高度成熟的2026年, 软件开发的瓶颈已从"代码生成速度"转移到**架构边界定义、上下文控制与正确性验证**。

MIT《Missing Semester 2026》给出的最佳心智模型是"**经理与实习生(Manager and Intern)**": 实习生(Agent)负责执行繁琐的代码编写与工具调用, 经理(你)必须提供清晰的架构方向、安全护栏与验收反馈。

你的PM优势可以直接迁移为工程能力:

| 产品经理技能 | 软件工程对应物 |
|---|---|
| 需求拆解 | 问题拆解与模块化架构(Decomposition) |
| PRD撰写 | 系统规约(Specifications) |
| 验收标准定义 | 自动化测试断言(Test Assertions) |
| 边界条件思考 | 前置/后置条件契约(Pre/Postconditions) |
| 项目级流程规范 | 上下文配置(CLAUDE.md / AGENTS.md) |

## 学习总原则: 螺旋式上升, 以战代练

最忌讳"把所有基础课囤起来看完再动手"——连续看两个月语法视频没有真实产出, 极易陷入"看课听得懂、自己写一行也写不出"的困境。正确姿势: **每学完一个阶段的方法论, 立即在AI辅助下交付一个真实可用的软件产物**:

本地自动化工具 → 内部数据/AI工具上线 → AI应用毕业项目 → 全栈独立网站上线 → 跨平台移动App交付

## 两大路径

| 路径 | 总学时 | 周期 | 学习深度 | 适合谁 |
|---|---|---|---|---|
| **极速实战路径(Fast-Track)** | ≈48小时(不含阶段四) / ≈60–65小时(含阶段四概念级) | 4–6周(可跳过阶段四) | 只学每门课"PM定制策略"指定的核心模块与关键章节 | 急于交付第一个内部工具/网站 |
| **系统进阶路径(Systematic)** | ≈210–240小时(含阶段四全量45–60h) | 15周(约3–4个月) | 深入完成高校经典工程课作业 | 想建立扎实工程底座 |

> 两条路径使用同一套课程清单, 区别只在学习深度。逐课对照见 [00-学习路径总览](00-学习路径总览.md)。

## 六阶段路线图

| 阶段 | 周次 | 主题 | 核心课程 | 实战交付物(里程碑) |
|---|---|---|---|---|
| [一](01-阶段一_编程思维与软件构造.md) | 第1–2周 | 编程思维破冰与软件构造基本原则 | AI Python for Beginners · CS50P挑读 · CS106A挑读 · MIT 6.1020精读 | 模块化Python自动化工具(含规约注释+单元测试) |
| [二](02-阶段二_工程工具链与Agent工程化.md) | 第3–4周 | 现代工程工具链与AI Agent架构师方法论 | MIT Missing Semester 2026 · Claude Code 101 · DLAI Claude Code · 范德堡Claude Code · UW–Madison资源库 | "AI工程标准脚手架"仓库(CLAUDE.md+CI) |
| [三](03-阶段三_内部工具与数据库.md) | 第5–6周 | 内部工具、关系型数据库与自动化后端上线 | SQLBolt · CS50 SQL精选 · Streamlit · Gradio · FastAPI+Supabase | 企业级内部工具上线交付同事使用 |
| [四](04-阶段四_AI原理.md) | 第7–9周 | AI原理与 fundamentals* | CS50 AI (Intro to AI with Python) | AI应用毕业项目(系统路径可获免费证书) |
| [五](05-阶段五_全栈网站开发.md) | 第10–13周 | 独立全栈网站开发、鉴权与生产部署 | Full Stack Open Part 0 · Next.js官方课程 · CS50W选修 | 带注册登录+数据库CRUD的全栈网站上线 |
| [六](06-阶段六_跨平台App开发.md) | 第14–15周 | 跨平台移动App(iOS & Android)独立开发 | 斯坦福CS147L · FSO Part 10/CS193p按需 | React Native跨平台App真机交付 |

> \*阶段四为整理时新增的延伸阶段(原调研为四大模块五阶段), 理由与CS50家族逐门取舍见 [08-课程资源链接总表](08-课程资源链接总表.md)。

## 学习中必须内化的五大工程原则

来自 MIT 6.1020 / 斯坦福CS106A / MIT Missing Semester 2026 / 范德堡Claude Code课的教学大纲核心, 贯穿全部六阶段:

1. **规约先行与契约式设计** — 在写任何函数实现之前先写规约(Write the spec before the body, every time)。规约精确定义输入前置条件、输出后置条件与隐含边界约定。AI时代直接体现为CLAUDE.md与功能规约文档。
2. **问题拆解与Token感知的模块化架构** — 人类难以阅读的代码库, AI Agent同样难以驾驭。把复杂产品拆成高内聚小模块, 定义显式接口, 保持数据模型与视图分离, 让AI每次只在局部受控范围内施工。
3. **测试先行与自动化验证闭环** — "代码不会做你期望它做的事, 只会做你指令它做的事"。先写测试并审计其是否捕捉产品需求, 再让Agent写实现; 配置Linter/类型检查器, 把报错直接接入Agent反馈闭环。
4. **底层Git版本控制与并行分支隔离** — 从Blob/Tree/DAG/引用的底层数据模型理解Git; 掌握 /clear、/rewind 上下文回滚, 以及 git worktree 多Agent并行开发(Best-of-N)。
5. **环境隔离与可复现交付** — 虚拟环境(uv + pyproject.toml)、环境变量安全(.env + .gitignore)、容器化(Docker)、CI/CD(GitHub Actions / Vercel / Streamlit Cloud), 实现代码推送即自动上线。

## 文件索引

| 文件 | 内容 |
|---|---|
| [00-学习路径总览](00-学习路径总览.md) | 双路径逐课对照、周计划、里程碑验收标准、进度总清单 |
| [01-阶段一_编程思维与软件构造](01-阶段一_编程思维与软件构造.md) | 4门课详情: AI Python / CS50P / CS106A / MIT 6.1020 |
| [02-阶段二_工程工具链与Agent工程化](02-阶段二_工程工具链与Agent工程化.md) | 5门课详情: Missing Semester / 三门Claude Code课 / UW–Madison |
| [03-阶段三_内部工具与数据库](03-阶段三_内部工具与数据库.md) | 4门课详情: SQL / Streamlit / Gradio / FastAPI+Supabase |
| [04-阶段四_AI原理](04-阶段四_AI原理.md) | 1门课详情: CS50 AI (新增延伸阶段) |
| [05-阶段五_全栈网站开发](05-阶段五_全栈网站开发.md) | 3门课详情: Full Stack Open / Next.js官方课程 / CS50W |
| [06-阶段六_跨平台App开发](06-阶段六_跨平台App开发.md) | 3门课详情: CS147L / FSO Part 10 / CS193p + Vibe Coding备选 |
| [07-附录_技术栈选型与AI开发SOP](07-附录_技术栈选型与AI开发SOP.md) | 场景A/B标准技术栈表 + AI Coding Agent八步工程守则 |
| [08-课程资源链接总表](08-课程资源链接总表.md) | 全部20门课程/资源官方链接 + CS50家族取舍 + 扩展资源 + 来源说明 |

## 课程全景: 四大能力模块

**模块一 编程基础、计算思维与软件工程核心原则**(消除语法陌生感, 建立"读懂代码、理解执行流、掌握拆解与规约设计"的基本功)

| 课程 | 机构 | 学时 | 深度要求 |
|---|---|---|---|
| AI Python for Beginners | DeepLearning.AI (Andrew Ng) | 17h | 必学·完整 |
| CS50P | Harvard (David Malan) | 60h(全量) | 挑读4个专题 |
| CS106A | Stanford (Chris Piech等) | 23讲(全量) | 挑读3份讲义 |
| 6.1020 Software Construction | MIT | 19+ Reading(全量) | 精读4个Reading |

**模块二 现代工程工具链、Git与AI Agent工程化开发**(连接"懂一点语法"与"能指挥AI开发复杂工程"的最关键桥梁)

| 课程 | 机构 | 学时 | 深度要求 |
|---|---|---|---|
| Missing Semester 2026新版 | MIT CSAIL | 9讲(9–20h) | 必刷·核心7讲 |
| Claude Code 101 & in Action | Anthropic | ≈3h | 必修·一晚学完 |
| Claude Code: A Highly Agentic Coding Assistant | DeepLearning.AI & Anthropic | 2h | 必修·三个实战项目 |
| Claude Code: Software Engineering with Generative AI Agents | Vanderbilt (Dr. Jules White) | 5–6h | 必修·AI委派工程学 |
| CS: AI-Assisted Software Development | UW–Madison | 10周资源库 | 当字典按需查 |

**模块三 内部工具制作、数据库建模与快速上线**(PM性价比最高的切入点: 对前端动效要求低, 对数据查询准确性、表单效率、上线速度要求高)

| 课程 | 机构/技术栈 | 学时 | 深度要求 |
|---|---|---|---|
| SQLBolt + CS50 SQL | SQLBolt / Harvard | 3–4h + 精选单元 | 必学 |
| Streamlit官方教程 + Coding Agent指南 | Streamlit | 4–6h | 必学·内部工具首选 |
| Building Generative AI Applications with Gradio | DeepLearning.AI & HF | 59min | 必学·PoC利器 |
| FastAPI官方教程 + Supabase实战 | FastAPI / Supabase | 4–6h | 必学·生产级后端 |

**模块四 独立全栈网站与跨平台App开发及上线**(面向外部用户的商业级产品全链路)

| 课程 | 机构 | 学时 | 深度要求 |
|---|---|---|---|
| Full Stack Open (Part 0 + 精选) | 赫尔辛基大学 | Part 0约2h | 必读Part 0 |
| React Foundations + Learn Next.js | Vercel官方 | 12–15h(16章) | 强烈必学·网站主线 |
| CS50W | Harvard | 96h(全量) | 选修4个专题周 |
| CS147L跨平台App开发 | Stanford | 一学期 | App开发首选 |
| CS193p SwiftUI | Stanford | 一学期 | 选修·纯苹果生态 |
| Vibe Coding for Beginners | Google Cloud | 7h | 备选参考 |

**延伸模块 AI原理**(整理时新增, 排为阶段四, 见上文路线图表)

| 课程 | 机构 | 学时 | 深度要求 |
|---|---|---|---|
| CS50's Intro to AI with Python | Harvard (Brian Yu) | 45–60h(全量, 整理者估算) | 系统: 全量+免费证书 / 极速: 概念级15–20h或跳过 |

> 链接均经2026-11-15可用性抽查(20条中19条HTTP 200; fastapi.tiangolo.com为本机代理出口无法访问, 域名为官方权威域名)。课程链接与内容可能随时间变化, 以各官网为准。
