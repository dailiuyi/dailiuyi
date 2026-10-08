# 戴柳逸 / dailiuyi

天津商业大学 · 软件工程 2024 级 · **Java 后端开发**

**个人站** [elma-gohan.xyz](https://elma-gohan.xyz)（含[博客](https://elma-gohan.xyz)） · **邮箱** d1753262762@gmail.com · **GitHub** [github.com/dailiuyi](https://github.com/dailiuyi)

---

## 实习经历

### 长沙市规划信息服务中心 · Java 后端开发实习生

`2026.06 - 至今` · Spring Boot 2.7 / MyBatis-Plus / PostgreSQL / Apache POI (SXSSF)

- 依据既有项目文档、数据库表结构和接口定义，完成政务通用数据导出组件的后端编码；按方案实现 model/core/starter/client/web 五模块 Maven 工程，完成 6 张业务表对应的数据访问、业务逻辑和 21 个既定 REST 接口编码，支持以 standalone 独立服务运行或通过 starter 嵌入业务系统。后端功能已完成，目前正在配合前端联调和测试验收。
- 数据源接入：支持 API 和低代码数据集两类数据源。API 方式支持 GET/POST/PUT 请求及请求头、URL 参数和请求体的配置与透传，调用前校验目标地址白名单，并按分页协议循环读取数据；支持通过 dataPath 定位 JSON 响应中的数据列表，将嵌套字段展开为可导出的 Excel 列。
- Excel 导出：基于 Apache POI SXSSF 实现两种导出方式：读取已有 Excel 模板并按字段填充数据；根据字段配置自动生成普通或多级表头；采用分页取数和流式写入，并设置单次 50 万行保护上限，降低大数据量导出时的内存风险。
- 字段自动匹配：导入 Excel 模板时，自动将表头与系统字段对应：优先匹配完全相同的中文名，再依次尝试关键词包含、拼音首字母和近似名称匹配；同一系统字段最多匹配一个表头，无法确定的列保留给用户手动配置。
- Excel 模板管理：提供模板上传、下载、预览数据读取和编辑结果保存接口；上传时校验文件类型和 10MB 大小限制，记录 MD5 摘要，并以 BYTEA 二进制形式保存到 PostgreSQL。

### 湖南星鹏应急安全科技有限公司 · 运维实习生

`2025.06 - 2025.09`

- 参考项目文档与现有部署流程，使用 Docker 完成服务配置、容器部署、版本更新及运行验证，接触企业环境下的基础发布流程。
- 参与日常运维与线上问题排查，协助完成静态资源加载优化，并结合服务状态、日志和配置定位常见部署异常。

---

## 项目经历

### 团队研发工具链：AI 自主编码与研发效能

`2026.08 - 至今` · Elixir/OTP、Python、Spring Boot 3、Unity C# · 担任角色：代码开发

围绕「AI Agent 自主完成研发任务」建设的一套工具链，覆盖任务编排、过程可观测、落地业务平台与协议工程四个层次：

**1. innovation-symphony — 多仓库自主编码编排框架** · [仓库](https://github.com/dailiuyi/innovation-symphony)

- 基于 Elixir/OTP 实现（lib 约 2.2 万行，51 个 ExUnit 测试文件）：Bot 监听 GitLab/GitHub 上带 `ready` 标签的 Issue，自动认领任务、执行编码，经独立评审门禁与检查项验证后以 Draft PR 交付，支持 0-5 次返工预算与失败自动恢复，另设独立看门狗进程兜底。
- 支持按仓库/按 Issue 通过评论指定模型；编码自检（tests/lint）在 Linux 任务隔离环境中执行；检查结果经结构化解析后再判定通过，避免“看一眼就算过”。
- 工程纪律：20+ 篇文档（决策日志 DECISIONS.md、需求、Issue 协议、自动恢复、评审返工规则等），增量实现均有编号与验收记录；已真实跑通「Issue #3 → 自动诊断 → 评审 → Draft PR #4」完整链路。

**2. innovation-view — Symphony 只读可观测看板** · [仓库](https://github.com/dailiuyi/innovation-view)

- 为 Symphony 运行时提供 Linear 风格只读看板：任务四态看板（待关注/进行中/待评审/已交付）、Agent 会话列表与角色过滤、按 Agent 的上下文查看器（提示词、近期输出、转录搜索，分页有界）。
- Python 3.11 标准库实现采集/存储/API/页面生成，支持 WSL 环境数据拉取；单测覆盖上下文 API 与状态映射，Playwright 浏览器冒烟检查；明示安全边界（无鉴权、仅限内网使用）。

**3. innovation-ar-resource-platform — AR 资源管理平台** · [仓库](https://github.com/dailiuyi/innovation-ar-resource-platform)

- RuoYi + Spring Boot 3 多模块（287 个 Java 文件）+ Vue 3（101 个 .vue 文件）+ PostgreSQL + Docker Compose。管理员上传/预览/发布 AR 场景资源，用户扫码下载运行。
- 完整资源接入闭环：场景 → 版本草稿 → 多文件上传（校验/注册/重试/启动对账）→ 每场景仅一个“当前发布版本”且发布文件冻结。
- 契约优先：OpenAPI v0.3.0 接口契约 + 运行时清单 JSON Schema；42 篇编号规格文档，数据库/契约/浏览器/密钥扫描/接入各环节留存 JSON 验证证据。

**4. innovation-MR — Unity MR 局域网联机 UPM 包** · [仓库](https://github.com/dailiuyi/innovation-MR)

- Unity 6 + Netcode for GameObjects 2.12 的可复用包（`com.innovationmr.ngo-lan`，经 Git URL 安装）：UDP 广播“发现主机并加入”，约 700 行 C#。
- 协议正确性优先：连接 IP 一律取自 UDP 源地址而非广播 JSON（不可信字段）、magic + 格式版本校验、端口钳制到 1..65535、会话缓存/队列/信令包均有资源上限；以 ConnectionApprover 委托作为安全扩展点。
- 附 EditMode 协议与注册表测试、CHANGELOG、第三方声明与示例（基础局域网大厅）。

### ELMA「家今天的饭」 · [仓库](https://github.com/dailiuyi/elma-gohan)

`2026.08 - 至今` · 个人项目 · 独立主导

Java 17 / Spring Boot 3.5 / Spring Data JPA / PostgreSQL / uni-app / Vue 3 / TypeScript

- 产品全流程落地：独立提出“只推荐一家不容易踩坑的餐厅”的决策构想，完成需求与同类产品调研、产品规划、功能开发、测试、备案和上线，打通从想法到真实用户使用的完整链路，并根据实际反馈持续迭代。
- AI 协同研发：使用 ChatGPT、Grok 辅助产品调研和技术方案讨论，Codex 完成代码实现与迭代；本人负责需求拆解、方案取舍、代码审查和问题纠正，通过 JUnit 5（后端 51 个测试文件）、Vitest 和实际运行验证核心功能，确保 Agent 产出符合需求并能够上线。
- 部署与运营：借助 AI Agent 完成服务器部署配置，将 Spring Boot API 服务和 PostgreSQL 运行在阿里云 ECS，并完成域名 ICP 备案与微信小程序备案；本人负责验证域名访问、API 调用、服务重启和健康状态，通过 OpenClaw 定时巡检线上服务，并持续进行维护与推广。

### Three Body Lab（三体参数实验室） · [在线演示](https://threebody.elma-gohan.xyz/) · [仓库](https://github.com/dailiuyi/ThreeBodySimulation)

`2026.02 - 至今` · 个人项目 · 独立主导

Java 17 / Spring Boot / REST / WebSocket / Vue 3 / TypeScript / Three.js

- 将 RK4、N 体两两引力与 Plummer 软化封装为不依赖 Spring 的纯 Java 计算模块，并记录能量、角动量、最近距离等数值健康指标。
- 将画面快照、轨迹和指标设计为“仅保留最新值”，任务状态和错误按顺序发送；把网络发送与轨迹保存移至后台线程，避免慢客户端阻塞模拟计算或造成消息堆积。
- 将每次模拟封装为独立任务，由单 worker 队列顺序执行，支持暂停、恢复、单步、取消、重启恢复、结果归档与独立回放。
- 以 OpenAPI 和 WebSocket JSON Schema 固化通信协议，完成二维、三维可视化、历史回放与报告导出，并写有[公网部署复盘](https://github.com/dailiuyi/ThreeBodySimulation/blob/main/docs/PUBLIC_DEPLOYMENT_POSTMORTEM.md)。

<img src="https://raw.githubusercontent.com/dailiuyi/ThreeBodySimulation/main/screenshots/2026-08-14/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202026-08-14%20144744.png" alt="Three Body Lab" width="100%" />

### [MiniMalloc](https://github.com/dailiuyi/minialloc)

在 8KB 静态堆上自实现 malloc/free 风格接口，不依赖系统堆。

- 采用 first-fit、块切割、地址有序空闲链表与前后相邻合并，缓解外部碎片。
- 使用 `uintptr_t` / `size_t` 统一地址计算，并实现 8 字节对齐、惰性初始化与双向块头转换。
- 回归覆盖 64 位指针截断、尾哨兵虚高 16 字节、`heap_init` 不复位空闲量等缺陷（12 个场景 / 47 项检查）。

### 其它

- [TCG 卡牌 PDF](https://github.com/dailiuyi/tcg-card-pdf)：按真实毫米尺寸拼 A4，提供 GUI、CLI 与可下载 exe
- [tjcu8](https://github.com/dailiuyi/tjcu8)：五页静态站渐进重构练习（纯 HTML → CSS 分层 → JS 模块化 → Vite → Vue 3 共享页壳），全过程留有文档
- [Utopia-UI-design](https://github.com/dailiuyi/Utopia-UI-design)：Unity 6 MR 游戏的 UI 设计 Kit，以 Agent Skill（设计 token + 规范文档）形式发布，供 AI Agent 直接套用
- 个人博客：[elma-gohan.xyz](https://elma-gohan.xyz)，基于 Astro 自建（自研 rehype/remark 插件、字体子集化、Go 统计服务）

---

## 竞赛经历

- CCPC：第十届河北省银牌、国赛铜牌；第九届河北省铜牌、国赛铜牌
- 蓝桥杯 / NOIP：第十七、十六届蓝桥杯 C/C++ 组全国二等奖、省级一等奖；初中、高中阶段多次获得 NOIP（湖南省）省级二等奖

---

## 技术栈

| 方向 | 技术 |
| --- | --- |
| 编程语言 | Java 17, SQL, C / C++, Python, Elixir, C# |
| 后端与数据 | Spring Boot 2.7 / 3.x, MyBatis-Plus, Spring Data JPA, REST, WebSocket, Apache POI (SXSSF), PostgreSQL, Flyway, Caffeine |
| 工程与测试 | Maven, Git, Git Worktree, OpenAPI, JSON Schema, JUnit 5, ExUnit, Vitest, Playwright, unittest |
| 前端与可视化 | Vue 3, TypeScript, uni-app, Pinia, Canvas, Three.js |
| 系统与部署 | Docker, Linux, NGINX, systemd, HTTPS, 阿里云 ECS |
| 其它平台 | Unity 6 (Netcode for GameObjects), Astro |
| AI 协作 | ChatGPT, Grok, Codex, Claude Code, OpenClaw（AI Agent 自主研发流程设计与验收） |
