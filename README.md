# 戴柳逸 / dailiuyi

天津商业大学 · 软件工程 2024 级 · **Java 后端开发实习**

我是戴柳逸，主要寻找 Java 后端开发实习机会。我从 12 岁开始参加算法竞赛，已有 8 年算法训练；做过 Java 后端与运维实习，也把 AI Agent 协作、契约先行和代码审查用于真实项目交付。

**个人站** [elma-gohan.xyz](https://elma-gohan.xyz) · **邮箱** dailiuyi@tjcu.edu.cn

---

## 实习经历

### 长沙市规划信息服务中心 · Java 后端开发实习生

`2026.06 - 至今` · Spring Boot 2.7 / MyBatis-Plus / PostgreSQL / Apache POI (SXSSF)

- 参与通用数据导出组件后端开发，搭建 `model/core/starter/client/web` 五模块 Maven 工程，支持独立部署与 starter 依赖嵌入两种接入模式。
- 完成 6 张业务表建模、21 个 REST 接口及后端功能开发；支持 API 白名单校验、低代码数据集接入、分页取数与 JSON 字段展开。
- 基于 Apache POI SXSSF 实现 template/dynamic 双模式导出，支持多级合并表头、50 万行上限保护与空数据校验。
- 实现中文名精确匹配、包含关系、拼音首字母和 Levenshtein 编辑距离逐级匹配；支持 Excel 模板校验、存储、预览与在线编辑。

### 湖南星鹏应急安全科技有限公司 · 运维实习生

`2025.06 - 2025.09`

- 使用 Docker 完成服务与容器部署、版本更新和运行验证。
- 参与日常巡检与线上问题排查，结合服务状态、日志和配置定位常见部署异常。

---

## 竞赛经历

- 第十届 CCPC 河北省银牌、国赛铜牌
- 第九届 CCPC 河北省铜牌、国赛铜牌
- 第十七届蓝桥杯 C/C++ 组全国二等奖、省级一等奖
- 第十六届蓝桥杯 C/C++ 组全国二等奖、省级一等奖
- 初中、高中阶段多次获得 NOIP（湖南省）省级二等奖

---

## 项目

### Three Body Lab · [在线演示](https://threebody.elma-gohan.xyz/) · [仓库](https://github.com/dailiuyi/ThreeBodySimulation)

实时 N 体引力实验室。Java 17 + Spring Boot + REST / WebSocket + Vue 3。

- 将 RK4、N 体两两引力与 Plummer 软化封装为纯 Java 物理核，并建立能量漂移、角动量、近距离事件等数值健康诊断。
- 以 OpenAPI 和 WebSocket JSON Schema 固化 REST / WS 通信协议，按契约协同前后端与 Agent 开发。
- 针对浏览器消费速度低于实时状态更新速度的问题，按数据用途拆分处理，避免慢客户端拖垮计算。
- 设计实验 Job System：独立任务、单 worker 队列调度、暂停/恢复/单步/取消、启动恢复、结果归档与独立回放。
- 完成 Vue 3 / Pinia 二维、三维可视化，支持实时观察、历史回放、数值诊断与报告导出；并写有[公网部署复盘](https://github.com/dailiuyi/ThreeBodySimulation/blob/main/docs/PUBLIC_DEPLOYMENT_POSTMORTEM.md)。

<img src="https://raw.githubusercontent.com/dailiuyi/ThreeBodySimulation/main/screenshots/2026-08-14/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202026-08-14%20144744.png" alt="Three Body Lab" width="100%" />

### [ELMA 家今天的饭](https://github.com/dailiuyi/elma-gohan)

只推荐一家不容易踩坑的餐厅。Java 17 + Spring Boot + PostgreSQL + 微信小程序。

- 将风险模型与口味画像隔离后组合为 LowRegretScore，服务端每次只返回一家候选餐厅。
- 冻结会话快照并支持随机种子重放；提供匿名画像与一键删除全部关联数据。
- 使用 `contracts/openapi.yaml` 作为接口事实源。

### [MiniMalloc](https://github.com/dailiuyi/minialloc)

在 8KB 静态堆上自实现 malloc/free 风格接口，不依赖系统堆。

- 采用 first-fit、块切割、地址有序空闲链表与前后相邻合并，缓解外部碎片。
- 使用 `uintptr_t` / `size_t` 统一地址计算，并实现 8 字节对齐、惰性初始化与双向块头转换。
- 回归覆盖 64 位指针截断、尾哨兵虚高 16 字节、`heap_init` 不复位空闲量等缺陷。

### 其它

- [TCG 卡牌 PDF](https://github.com/dailiuyi/tcg-card-pdf)：按真实毫米尺寸拼 A4，提供 GUI、CLI 与可下载 exe
- 个人站：[elma-gohan.xyz](https://elma-gohan.xyz)

---

## 技术栈

| 方向 | 技术 |
| --- | --- |
| 后端 | Java 17, Spring Boot, MyBatis-Plus, Apache POI (SXSSF), REST, WebSocket |
| 数据与中间件 | PostgreSQL, MySQL, Nacos |
| 工程化 | Maven, Git, JUnit 5, OpenAPI + JSON Schema, AI Agent 协同开发 |
| 前端与可视化 | Vue 3, TypeScript, Pinia, Canvas 2D, Three.js |
| 系统与部署 | Docker, Linux, NGINX, systemd, HTTPS |
| 语言与底层 | Java, C / C++, 内存池, 指针操作 |

---
