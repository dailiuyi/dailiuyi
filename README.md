# 戴柳逸 / dailiuyi

天津商业大学 · 软件工程 2024 级 · **Java 后端开发**

**个人站** [elma-gohan.xyz](https://elma-gohan.xyz) · **邮箱** d1753262762@gmail.com

---

## 实习经历

### 长沙市规划信息服务中心 · Java 后端开发实习生

`2026.06 - 至今` · Spring Boot 2.7 / MyBatis-Plus / PostgreSQL / Apache POI (SXSSF)

- 依据既有项目文档、数据库表结构和接口定义，完成政务通用数据导出组件的后端编码；按方案实现model/core/starter/client/web五模块Maven工程，完成6张业务表对应的数据访问、业务逻辑和21个既定REST接口编码，支持以standalone独立服务运行或通过starter嵌入业务系统。后端功能已完成，目前正在配合前端联调和测试验收。
- 数据源接入：支持API和低代码数据集两类数据源。API方式支持GET/POST/PUT请求及请求头、URL参数和请求体的配置与透传，调用前校验目标地址白名单，并按分页协议循环读取数据；支持通过dataPath定位JSON响应中的数据列表，将嵌套字段展开为可导出的Excel列。
- Excel导出：基于Apache POI SXSSF实现两种导出方式：读取已有Excel模板并按字段填充数据；根据字段配置自动生成普通或多级表头；采用分页取数和流式写入，并设置单次50万行保护上限，降低大数据量导出时的内存风险。
- 字段自动匹配：导入Excel模板时，自动将表头与系统字段对应：优先匹配完全相同的中文名，再依次尝试关键词包含、拼音首字母和近似名称匹配；同一系统字段最多匹配一个表头，无法确定的列保留给用户手动配置。
- Excel模板管理：提供模板上传、下载、预览数据读取和编辑结果保存接口；上传时校验文件类型和10MB大小限制，记录MD5摘要，并以BYTEA二进制形式保存到PostgreSQL。


### 湖南星鹏应急安全科技有限公司 · 运维实习生

`2025.06 - 2025.09`

- 参考项目文档与现有部署流程，使用Docker完成服务配置、容器部署、版本更新及运行验证，接触企业环境下的基础发布流程。
- 参与日常运维与线上问题排查，协助完成静态资源加载优化，并结合服务状态、日志和配置定位常见部署异常。


---

## 项目经历

### ELMA「家今天的饭」 · [仓库](https://github.com/dailiuyi/elma-gohan)

`2026.08 - 至今` · 个人项目 · 独立主导

Java 17 / Spring Boot 3.5 / Spring Data JPA / PostgreSQL / uni-app / Vue 3 / TypeScript

- 产品全流程落地：独立提出“只推荐一家不容易踩坑的餐厅”的决策构想，完成需求与同类产品调研、产品规划、功能开发、测试、备案和上线，打通从想法到真实用户使用的完整链路，并根据实际反馈持续迭代。
- AI协同研发：使用ChatGPT、Grok辅助产品调研和技术方案讨论，Codex完成代码实现与迭代；本人负责需求拆解、方案取舍、代码审查和问题纠正，通过JUnit 5、Vitest和实际运行验证核心功能，确保Agent产出符合需求并能够上线。
- 部署与运营：借助AI Agent完成服务器部署配置，将Spring Boot API服务和PostgreSQL运行在阿里云ECS，并完成域名ICP备案与微信小程序备案；本人负责验证域名访问、API调用、服务重启和健康状态，通过OpenClaw定时巡检线上服务，并持续进行维护与推广。


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
