# Awesome ChatBI

> 🌟 收录 ChatBI / 智能问数 / AI 数据分析相关的开源平台、商业产品、技术框架、论文、教程与真实案例的精选导航。

> 🌟 A curated list of ChatBI / AI-powered conversational business intelligence (AI 问数 / Text2SQL / NL2SQL) — open-source platforms, commercial products, frameworks, papers, tutorials and real-world cases.

**[English](./README.md)**

ChatBI（对话式商业智能）让用户用自然语言提问即可获得数据答案（表格、图表、洞察），由大模型（LLM）驱动。本仓库梳理整个生态——从可自托管的开源平台到商业产品、底层框架、科研论文，再到动手教程。

覆盖主题：**NL2SQL · Text2SQL · 语义层 · Data Agent · 对话式 BI · AI 数据分析**。

---

## 目录

- [开源平台](#开源平台)
- [框架与库](#框架与库)
- [商业产品](#商业产品)
- [科研论文与数据集](#科研论文与数据集)
- [教程与文章](#教程与文章)
- [相关精选清单](#相关精选清单)
- [贡献](#贡献)
- [许可](#许可)

<!-- 说明：每条目用标记注明数据源支持情况，例如 "Doris ✓ MySQL ✓ PostgreSQL ✓"（已核实处） -->

---

## 开源平台

> 可自托管的 ChatBI / AI 问数平台。已核实的注明数据源支持。

| 项目 | Stars | 语言 | 亮点 |
| --- | --- | --- | --- |
| [DB-GPT](https://github.com/eosphoros-ai/DB-GPT) | ★20.1k | Python | 开源 AI 原生数据应用框架；Text2SQL、Agent、RAG。支持 Doris 及众多数据库 |
| [WrenAI](https://github.com/Canner/WrenAI) | ★17.9k | Python | 语义层驱动的 NL2SQL，面向企业自助分析 |
| [DataEase SQLBot](https://github.com/dataease/SQLBot) | ★6.9k | JavaScript | 飞致云开源 ChatBI；官方文档支持 Apache Doris 数据源 |
| [sqlchat](https://github.com/sqlchat/sqlchat) | ★5.8k | — | 用自然语言与数据库对话，Web UI |
| [jimureport](https://github.com/jeecgboot/jimureport)（积木报表） | ★8.5k | Java | 报表 + 问数，支持 Doris 等 |
| [Aix-DB](https://github.com/apconw/Aix-DB) | ★2.2k | — | AI 辅助数据查询，支持 Doris |
| [ChatBI (ambition119)](https://github.com/ambition119/chatBI) | ★181 | — | 轻量 ChatBI 示例 |
| [Langchain-ChatBI](https://github.com/dynamiclu/Langchain-ChatBI) | ★154 | Python | 基于 LangChain 构建的 ChatBI |
| [vanna-chatbi](https://github.com/owenliang/vanna-chatbi) | ★30 | — | 基于 Vanna 的 ChatBI |

## 框架与库

> 底层构建模块：Text2SQL / NL2SQL / 语义层 / Agent 框架。

| 项目 | Stars | 说明 |
| --- | --- | --- |
| [Vanna](https://github.com/vanna-ai/vanna) | ★13k | 开源 Text2SQL 框架（Python）：在数据集上训练，自然语言查询 |
| [DB-GPT](https://github.com/eosphoros-ai/DB-GPT) | ★20.1k | （同上列出）框架 + 工具 |
| [WrenAI](https://github.com/Canner/WrenAI) | ★17.9k | 语义层引擎 |
| [Apache Superset](https://github.com/apache/superset) | — | BI + AI 助手集成 |
| [MindsDB](https://github.com/mindsdb/mindsdb) | — | 用 SQL 接口使用 AI |
| [db-ally](https://github.com/zama-ai/db-ally) | — | 免 SQL，通过自然语言视图访问 LLM 数据 |

## 商业产品

> 闭源 ChatBI / 对话式分析产品（多数通过 MySQL 兼容协议对接 Doris 等主流数仓）。

### 国内
- **帆软 Dora**：帆软（FineReport/FineBI 产品线）AI 智能问数助手。提问即可得到图表与分析，对接主流数仓。
- **帆软 FineBI**：BI 平台，含 AI 问数能力；是 Apache Doris 官方生态收录的 BI 工具之一。
- **亿信 ABI**：智能 BI + AI 问数。
- **永洪**：永洪 BI，带 AI 助手。
- **观远数据**：消费级 BI，含 AI 能力。
- **Smartbi**（思迈特）：BI + AI 对话式分析。
- **网易有数**、**Kyligence**（语义层 + AI）。
- **SelectDB**：Doris 商业厂商，含 AI 能力。

### 国际
- **Microsoft Power BI Copilot**：Power BI 内的对话式分析。
- **ThoughtSpot Spotter**：NL 搜索 + AI 分析。
- **Tableau**（Salesforce AI）：AI 辅助分析。
- **Qlik Sense**：AI/ML 增强分析。
- **Sigma**：电子表格 + AI。
- **DBeaver AI**、**Looker**、**Hex**、**MotherDuck**：AI 化分析工具。

> 提示：商业产品对特定数仓（如 Doris）的支持请以各厂商官方文档为准。

## 科研论文与数据集

> NL2SQL / Text2SQL 研究、基准与数据代理。

| 资源 | Stars | 说明 |
| --- | --- | --- |
| [Awesome-Text2SQL](https://github.com/eosphoros-ai/Awesome-Text2SQL) | ★3.7k | 全面的 Text2SQL 论文/工具/数据集清单 |
| [awesome-data-agents](https://github.com/hkustdial/awesome-data-agents) | ★777 | 持续更新的 Data Agents 论文列表 |
| [DB-GPT-Hub](https://github.com/eosphoros-ai/DB-GPT-Hub) | ★2k | Text2SQL 微调与基准中心 |
| [NL2SQL_Handbook](https://github.com/HKUSTDial/NL2SQL_Handbook) | ★1.6k | 港大-CSE 的 NL2SQL 手册 |
| [NL2SQL](https://github.com/yechens/NL2SQL) | ★1.6k | NL2SQL 数据集与模型 |
| Spider / BIRD（数据集） | — | 标准 NL2SQL 基准 |

## 教程与文章

- **综述**：[ChatBI 核心技术：生成式 BI 解锁智能商业决策](https://book.qq.com/book-read/56843108/10)
- **开源解析**：[chatbi 探索 & 多款开源 AI chatbi 产品解析](https://damodev.csdn.net/68633aaeb93e2f417961c872)
- **NL2SQL 项目盘点**：[Github 9 个惊艳的开源 NL2SQL 项目](https://juejin.cn/post/7538719894222733353)
- **架构**：[SQLBot: 基于大模型与 RAG 的智能问数系统架构](https://blog.csdn.net/weixin_35770067/article/details/153335005)
- **Doris + ChatBI**：[3 步！用 Doris + DeepSeek 搭建 ChatBI 系统](https://segmentfault.com/a/1190000046198598)

## 相关精选清单

- [eosphoros-ai/Awesome-Text2SQL](https://github.com/eosphoros-ai/Awesome-Text2SQL)
- [HKUSTDial/awesome-data-agents](https://github.com/hkustdial/awesome-data-agents)
- [awesome-doris-ai](https://github.com/gaofujie1997/awesome-doris-ai) — 姊妹清单，聚焦 Doris × AI

---

## 贡献

欢迎提交 PR！规范如下：

- 每条目标注其**数据源支持**（如 Doris / MySQL / PostgreSQL，已核实处）
- 将每条目标记为**开源**、**商业产品**、**框架**或**科研**
- 遵循 [awesome 列表规范](https://github.com/sindresorhus/awesome)

## 许可

[MIT](./LICENSE)