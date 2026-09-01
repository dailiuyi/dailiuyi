# 戴柳逸 / dailiuyi

天津商业大学 · 软件工程 2024 级 · **Java 后端开发**

**个人站** [elma-gohan.xyz](https://elma-gohan.xyz) · **邮箱** d1753262762@gmail.com

---

## 实习经历

### 长沙市规划信息服务中心 · Java 后端开发实习生

`2026.06 - 至今` · Spring Boot 2.7 / MyBatis-Plus / PostgreSQL / Apache POI (SXSSF)

- 依据既有项目文档、数据库表结构和接口定义，完成政务通用数据导出组件的后端编码；按方案实现 `model/core/starter/client/web` 五模块 Maven 工程，支持 standalone 独立运行与 starter 嵌入两种接入方式。
- 完成 6 张业务表对应的数据访问、业务逻辑和 21 个 REST 接口；支持 API 与低代码数据集接入、分页取数及嵌套 JSON 字段展开。
- 基于 Apache POI SXSSF 实现模板填充与动态表头两种导出方式，支持多级合并表头、分页流式写入和单次 50 万行保护上限。
- 实现 Excel 表头与系统字段的精确、包含、拼音首字母和近似名称逐级匹配，并提供模板上传、下载、预览与编辑结果保存能力。

### 湖南星鹏应急安全科技有限公司 · 运维实习生

`2025.06 - 2025.09`

- 参考项目文档与现有部署流程，使用 Docker 完成服务配置、容器部署、版本更新及运行验证。
- 参与日常运维、线上问题排查与静态资源加载优化，结合服务状态、日志和配置定位常见部署异常。

---

## 项目经历

### ELMA「家今天的饭」 · [仓库](https://github.com/dailiuyi/elma-gohan)

`2026.08 - 至今` · 个人项目 · 独立主导

Java 17 / Spring Boot 3.5 / Spring Data JPA / PostgreSQL / uni-app / Vue 3 / TypeScript

- 提出“只推荐一家不容易踩坑的餐厅”的决策构想，独立完成调研、规划、开发、测试、备案、上线与持续迭代。
- 将风险模型与口味画像隔离后组合为 LowRegretScore；冻结会话快照并支持随机种子重放，同时提供匿名画像与一键删除关联数据。
- 使用 ChatGPT、Grok 辅助调研与方案讨论，使用 Codex 协同实现；本人负责需求拆解、方案取舍、代码审查和问题纠正，并通过 JUnit 5、Vitest 与实际运行验证结果。
- 以 `contracts/openapi.yaml` 作为接口事实源，将 API 服务与 PostgreSQL 部署至阿里云 ECS，完成 ICP 与微信小程序备案，并通过定时巡检持续维护线上服务。

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
- 回归覆盖 64 位指针截断、尾哨兵虚高 16 字节、`heap_init` 不复位空闲量等缺陷。

### 其它

- [TCG 卡牌 PDF](https://github.com/dailiuyi/tcg-card-pdf)：按真实毫米尺寸拼 A4，提供 GUI、CLI 与可下载 exe

---

## 竞赛经历

- CCPC：第十届河北省银牌、国赛铜牌；第九届河北省铜牌、国赛铜牌
- 蓝桥杯 / NOIP：第十七、十六届蓝桥杯 C/C++ 组全国二等奖、省级一等奖；初中、高中阶段多次获得 NOIP（湖南省）省级二等奖

---

## 技术栈

| 方向 | 技术 |
| --- | --- |
| 编程语言 | Java 17, SQL, C / C++ |
| 后端与数据 | Spring Boot, MyBatis-Plus, Spring Data JPA, REST, WebSocket, Apache POI (SXSSF), PostgreSQL, Flyway, Caffeine |
| 工程与测试 | Maven, Git, Git Worktree, OpenAPI, JSON Schema, JUnit 5, Vitest, Playwright |
| 前端与可视化 | Vue 3, TypeScript, uni-app, Pinia, Canvas, Three.js |
| 系统与部署 | Docker, Linux, NGINX, systemd, HTTPS, 阿里云 ECS |
| AI 协作 | ChatGPT, Grok, Codex, Claude Code, OpenClaw |
