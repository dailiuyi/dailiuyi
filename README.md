# dailiuyi

天津商业大学 · **后端 / 全栈实习**

**站点** [elma-gohan.xyz](https://elma-gohan.xyz) · **邮箱** dailiuyi@tjcu.edu.cn

---

### [Three Body Lab](https://threebody.elma-gohan.xyz/) ·

实时 N 体引力实验室。Java 17 + Spring Boot + Vue 3 + WebSocket。

- 物理核：牛顿引力 + Plummer 软化 + 定步长 RK4，SI 单位
- 工程：OpenAPI / WebSocket JSON Schema 作为前后端事实源
- 交互：Canvas 2D + Three.js 3D、历史时间轴、数值健康诊断、报告导出
- 上线：NGINX + systemd，Java 只听回环；写过[部署复盘](https://github.com/dailiuyi/ThreeBodySimulation/blob/main/docs/PUBLIC_DEPLOYMENT_POSTMORTEM.md)

[仓库](https://github.com/dailiuyi/ThreeBodySimulation)

<img src="https://raw.githubusercontent.com/dailiuyi/ThreeBodySimulation/main/screenshots/2026-08-14/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202026-08-14%20144744.png" alt="Three Body Lab" width="100%" />

### [ELMA 家今天的饭](https://github.com/dailiuyi/elma-gohan)

只推荐一家不容易踩坑的餐厅。Java 17 + Spring Boot + PostgreSQL + 微信小程序。

- 风险模型与口味画像隔离，组合成 LowRegretScore
- 服务端只返回一家；会话快照冻结，随机种子可重放
- 匿名画像 + 一键删除全部关联数据
- 接口事实源：`contracts/openapi.yaml`

### [MiniMalloc](https://github.com/dailiuyi/minialloc)

在 8KB 静态堆上自实现 malloc/free（FreeRTOS `heap_4` 简化）。

first-fit、块切割、地址有序空闲链表、相邻合并。测试覆盖过 64 位指针截断、尾哨兵虚高 16 字节、`heap_init` 不复位空闲量。

### 其它

- [TCG 卡牌 PDF](https://github.com/dailiuyi/tcg-card-pdf)：按真实毫米尺寸拼 A4，GUI + CLI + 可下载 exe
- 个人站：[elma-gohan.xyz](https://elma-gohan.xyz)

---

## 技术栈

| 层 | 仓库里能看到 |
| --- | --- |
| 后端 | Java 17, Spring Boot, OpenAPI, WebSocket, PostgreSQL |
| 前端 | Vue 3, TypeScript, Canvas / Three.js, uni-app |
| 系统 | C 分配器, NGINX, systemd, Docker, HTTPS |
| 工作方式 | 契约先行、可复现实验、公网部署、写复盘 |

---
