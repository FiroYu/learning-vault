# 05 · 阶段五: 跨平台移动App(iOS & Android)独立开发与上线(第11–12周)

> [专题总览](README.md) · [学习路径总览](00-学习路径总览.md) · 上一阶段 [阶段四](04-阶段四_全栈网站开发.md) · 附录 [技术栈与SOP](06-附录_技术栈选型与AI开发SOP.md)

**阶段目标**: 将阶段四掌握的TypeScript、React组件思维与Supabase后端无缝迁移至移动端, 掌握使用React Native开发跨平台iOS与Android独立App的完整能力。

## 学习顺序

1. [CS147L主课](#1-cs147l-cross-platform-mobile-app-development-autumn-2026) — React Native + Supabase
2. 按需拓展: [FSO Part 10](#2-full-stack-open-part-10-react-native) 或 [CS193p](#3-cs193p-developing-apps-for-ios-using-swiftui-spring-2025)
3. 交付里程碑5

## 课程详情

### 1. CS147L: Cross-Platform Mobile App Development (Autumn 2026)

| 项 | 内容 |
|---|---|
| 机构 | Stanford University |
| 形式与费用 | 课程网站公开完整教学大纲、讲义Slides与作业规约(Spec) |
| 技术栈 | JavaScript/TypeScript, React Native, CSS/StyleSheets, AsyncStorage, Supabase |
| 链接 | <https://cs147l.stanford.edu/> · 历史公开课件 <https://hci.stanford.edu/courses/cs147l/2024/au/> |

**核心内容**: 一套代码同时构建iOS与Android跨平台原生应用(Facebook、Instagram、UberEats、Discord同款核心技术)。覆盖组件状态、样式表布局、异步编程(Async/await)、React Hooks(useEffect)、页面导航(Navigation)与Supabase云端存储。作业直接拆解主流App核心体验:
- **A2** — Hinge(卡片交互)
- **A3** — Spotify(列表与API调用)
- **A4** — Buzz/Fizz(社交应用)
- 毕业设计 — 独立App

**PM定制学习策略**: **独立App开发首选课程!** 相比分别学两套原生开发语言, React Native让你直接复用Next.js中学到的TypeScript与React组件技能; 且该课2026秋大纲明确允许并指导学生在开发与高阶项目中使用Claude Code或Cursor等AI工具辅助。

### 2. Full Stack Open Part 10 (React Native)

| 项 | 内容 |
|---|---|
| 机构 | University of Helsinki |
| 形式与费用 | 官网免费 |
| 链接 | <https://fullstackopen.com/en/part10> |

**使用策略**: 按需查阅React Native进阶文档, 不必整章刷完。

### 3. CS193p: Developing Apps for iOS using SwiftUI (Spring 2025)

| 项 | 内容 |
|---|---|
| 机构 | Stanford University |
| 形式与费用 | cs193p.stanford.edu免费公开全套视频与配套材料 |
| 技术栈 | Swift, SwiftUI, Model与UI分离架构 |
| 链接 | <https://cs193p.stanford.edu/> |

**核心内容**: 斯坦福经典iOS开发课——Swift类型系统、声明式SwiftUI视图构建、列表与导航(ForEach/Identifiable); 核心强调将Model(数据与业务逻辑)与UI(界面视图)彻底分离的工程架构。

**PM定制学习策略**: 选修, 仅限纯苹果生态深度开发者。若目标是快速上线iOS与Android双端App, 优先学CS147L (React Native); 若专门开发纯iOS/Mac原生应用, 再学CS193p。

### 备选: Vibe Coding for Beginners: From Zero to App

| 项 | 内容 |
|---|---|
| 机构 | Google Cloud (Coursera) |
| 形式与费用 | 需付费或申请助学金, 不支持免费Audit |
| 学时 | 6个模块共7小时 |
| 链接 | <https://www.coursera.org/learn/vibe-coding-for-beginners-from-zero-to-app> |

**内容**: 零基础学习者在Google Cloud中配置开发工具、用Gemini与Coding Agent编写功能代码、测试调试并迭代出可用Web应用。

**PM定制学习策略**: 选修补充。不支持免费旁听且偏重Google Cloud与Gemini生态入门; 在学完MIT Missing Semester与Anthropic免费课后, 仅作备选参考。

## 里程碑5: 跨平台App交付

**任务**: 基于React Native (Expo) + TypeScript + Supabase, 将阶段四独立网站的核心功能(或全新的移动端产品创意)构建为跨平台移动App。

**架构要点**: 与Web端共享同一个Supabase PostgreSQL数据库与用户鉴权体系——一套后端, 双端复用。

**验收清单**:
- [ ] Expo项目本地跑通, iOS/Android模拟器均可运行
- [ ] 实现至少3个页面(导航Navigation配置)
- [ ] 数据读写走Supabase(与Web端同库)
- [ ] 真机调试通过(Expo Go扫码)
- [ ] 完成发布准备(Expo EAS Build或商店素材清单)

## 阶段完成清单

- [ ] CS147L核心主题学完(状态/样式/异步/Hooks/导航/存储)
- [ ] 在Claude Code或Cursor辅助下完成至少1个课程项目(A2–A4任选)
- [ ] 里程碑5交付, 真机可演示

## 结业之后

五阶段走完, 你已具备"PM视角的AI全栈交付能力"。后续深化方向:
- **工程深度**: 回头系统补CS50W完整项目、MIT 6.1020并发单元、UW–Madison Unit 2(RAG/监控)
- **产品深化**: 用[场景A技术栈](06-附录_技术栈选型与AI开发SOP.md)持续交付团队内部工具; 用场景B栈迭代独立产品
- **方法论迭代**: 关注 Missing Semester 与 Anthropic Academy 的课程更新, AI工程实践演化极快
