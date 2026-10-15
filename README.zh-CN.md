# Awesome ChatBI

> 🌟 收录 **ChatBI / 智能问数** 相关的开源平台、商业产品、语义层、技术框架、基准与论文、教程与真实案例的精选导航。

> 🌟 A curated list of **ChatBI** (AI-powered conversational business intelligence) — open-source platforms, commercial products, semantic layers, frameworks, benchmarks, papers, tutorials and real-world cases.

**[English](./README.md)**

**ChatBI**（对话式商业智能，也叫 **GenBI / AI 问数 / 对话式 BI**）让用户用自然语言提问，由大模型（LLM）在数据仓库之上生成答案——表格、图表与洞察。它处在 **NL2SQL / Text2SQL**、**语义层**、**数据 Agent** 与传统 **BI** 的交叉点上。

本仓库梳理整个生态：现在就能自托管什么、该买什么、可以在什么之上构建、该读什么，以及如何选型。

**覆盖主题：** ChatBI · AI 问数 · NL2SQL · Text2SQL · 语义层 · Data Agent · 对话式 BI · GenBI

> ⭐ 星数为大致快照，会随时间变化。

---

## 目录

- [生态地图](#生态地图)
- [核心概念](#核心概念)
- [开源平台](#开源平台)
- [框架与库](#框架与库)
- [语义层与指标](#语义层与指标)
- [具备 AI / 对话能力的 BI 平台](#具备-ai--对话能力的-bi-平台)
- [商业产品](#商业产品)
- [综述与论文](#综述与论文)
- [基准与数据集](#基准与数据集)
- [教程、课程与文章](#教程课程与文章)
- [如何选型](#如何选型)
- [数据源兼容性](#数据源兼容性)
- [相关精选清单](#相关精选清单)
- [贡献](#贡献)
- [许可](#许可)

---

## 生态地图

```
        ┌──────────────────────────────────────────────────────┐
        │  用户用自然语言提出问题                                │
        └───────────────────────┬──────────────────────────────┘
                                ▼
        ┌──────────────────────────────────────────────────────┐
        │  ChatBI 应用层                                        │
        │  对话界面 · 多轮会话 · 图表渲染 ·                     │
        │  仪表盘 · 结果解释                                    │
        └───────────────────────┬──────────────────────────────┘
                                ▼
        ┌──────────────────────────────────────────────────────┐
        │  Agent / 编排层                                       │
        │  意图解析 · Schema 链接 · 工具调用 ·                  │
        │  SQL 生成 · 自我纠错 · 执行                           │
        └───────────────────────┬──────────────────────────────┘
                                ▼
        ┌──────────────────────────────────────────────────────┐
        │  语义层与上下文                                       │
        │  指标 · 维度 · 业务术语表 ·                           │
        │  基于文档与示例查询的 RAG（few-shot）                 │
        └───────────────────────┬──────────────────────────────┘
                                ▼
        ┌──────────────────────────────────────────────────────┐
        │  大模型层                                             │
        │  通用 LLM 提示词 · 微调 SQL 模型 ·                    │
        │  Embedding · 重排序模型                               │
        └───────────────────────┬──────────────────────────────┘
                                ▼
        ┌──────────────────────────────────────────────────────┐
        │  数据层                                               │
        │  Apache Doris · StarRocks · ClickHouse · MySQL ·     │
        │  PostgreSQL · Snowflake · BigQuery · Databricks ...  │
        └──────────────────────────────────────────────────────┘
```

## 核心概念

| 术语 | 含义 |
| --- | --- |
| **NL2SQL / Text2SQL** | 把自然语言问题转换为可执行 SQL。ChatBI 的技术内核。 |
| **ChatBI / GenBI** | 位于 NL2SQL 之上的对话式产品：对话界面、多轮上下文、图表与追问。 |
| **语义层（Semantic Layer）** | 对指标/维度（如"营收"）的受治理抽象，让 LLM 按业务定义生成正确的 SQL。 |
| **Schema 链接（Schema Linking）** | 把问题中的词映射到真实表/列；通常是准确率最大的瓶颈。 |
| **ChatBI 中的 RAG** | 检索 DDL、文档、指标定义与历史 Q→SQL 对作为上下文（few-shot），提升准确率。 |
| **执行准确率（EX）** | 基准指标：生成的 SQL 是否返回正确结果集（而非仅字符串匹配）。 |
| **精确匹配（EM）** | 基准指标：生成的 SQL 文本是否与标准 SQL 完全一致。更严格，参考意义较低。 |
| **数据 Agent（Data Agent）** | 不仅写 SQL，还能规划多步分析、调用工具并汇报结论的智能体。 |

---

## 开源平台

> 可自托管的 ChatBI / AI 问数平台——对话界面 + NL2SQL + 执行，开箱可部署。

| 项目 | Stars | 语言 | 说明 |
| --- | --- | --- | --- |
| [Chat2DB](https://github.com/OtterMind/Chat2DB) | ★28.3k | Java | 免费、跨平台、本地优先的数据库客户端与 SQL 工作台，带 AI/NL2SQL。原 `CodePhiliaX/Chat2DB` |
| [pandas-ai](https://github.com/sinaptik-ai/pandas-ai) | ★23.9k | Python | 用自然语言与数据库或数据湖（SQL、CSV、parquet）对话 |
| [DB-GPT](https://github.com/eosphoros-ai/DB-GPT) | ★20.1k | Python | 智能体式 AI 数据助手：Text2SQL + RAG + Agent + AWEL 工作流。支持 Doris 等多种数据库 |
| [WrenAI](https://github.com/Canner/WrenAI) | ★17.9k | Python | 面向 AI Agent 的 GenBI；基于语义层（MDL）的受治理 text-to-SQL |
| [JimuReport](https://github.com/jeecgboot/jimureport)（积木报表） | ★8.5k | Java | 免费报表设计器（类 JasperReports），内置 ChatBI / AI 问数 |
| [SQLBot](https://github.com/dataease/SQLBot) | ★6.9k | JS | 飞致云出品的 LLM + RAG 智能问数；**官方文档支持 Apache Doris 数据源** |
| [sqlchat](https://github.com/sqlchat/sqlchat) | ★5.8k | TypeScript | 面向下一个十年的对话式 SQL 客户端与编辑器 |
| [SuperSonic](https://github.com/tencentmusic/supersonic) | ★5.1k | Java | 腾讯音乐的 AI+BI 平台，统一 **Chat BI** 与 **Headless BI**（语义层） |
| [WhoDB](https://github.com/clidey/whodb) | ★5.0k | Go | 轻量、AI 驱动的数据浏览与 SQL 客户端 |
| [Dataherald](https://github.com/Dataherald/dataherald) | ★3.6k | Python | 面向企业数据的 NL2SQL 引擎，自带评测工具 |
| [Aix-DB](https://github.com/apconw/Aix-DB) | ★2.3k | — | AI 辅助数据查询平台；支持 Doris |
| [Dash](https://github.com/agno-agi/dash) | ★2.3k | Python | 自学习数据 Agent（Agno），能从历史查询中持续改进 |
| [nao](https://github.com/getnao/nao) | ★1.9k | TypeScript | 面向数据团队的开源分析 Agent（感知 dbt） |
| [QueryWeaver](https://github.com/FalkorDB/QueryWeaver) | ★1.1k | Python | 开源 Text2SQL 工具，基于图结构 Schema 把自然语言转为 SQL |
| [openhare](https://github.com/sjjian/openhare) | ★815 | Dart | AI 驱动的跨平台桌面 SQL 客户端 |
| [langchain_data_agent](https://github.com/eosho/langchain_data_agent) | ★236 | Python | 极简 NL2SQL Agent：英文自然语言 → SQL |
| [ChatBI (ambition119)](https://github.com/ambition119/chatBI) | ★181 | — | 轻量 ChatBI 示例 |
| [Langchain-ChatBI](https://github.com/dynamiclu/Langchain-ChatBI) | ★154 | Python | 基于 LangChain 构建的 ChatBI |
| [vanna-chatbi](https://github.com/owenliang/vanna-chatbi) | ★30 | — | 基于 Vanna 的 ChatBI |

## 框架与库

> 用于组装你自己的 ChatBI 的构建模块。

### Text2SQL / NL2SQL 框架

| 项目 | Stars | 语言 | 说明 |
| --- | --- | --- | --- |
| [Vanna](https://github.com/vanna-ai/vanna) | ★23.8k | Python | 基于 RAG 的 Text-to-SQL 框架：用 DDL/文档/Q→SQL 对训练，然后对话查询 |
| [DB-GPT](https://github.com/eosphoros-ai/DB-GPT) | ★20.1k | Python | 面向 AI 原生数据应用的框架 + 平台 |
| [WrenAI](https://github.com/Canner/WrenAI) | ★17.9k | Python | 语义层驱动的 NL2SQL 引擎 |
| [sqlglot](https://github.com/tobymao/sqlglot) | ★9.7k | Python | SQL 解析、转译与优化——事实上的方言转换层 |
| [SQLFlow](https://github.com/sql-machine-learning/sqlflow) | ★5.2k | Go | "让 SQL 与 AI 结合"：扩展 SQL 语法以支持模型训练/预测 |
| [SqlCoder](https://github.com/defog-ai/sqlcoder) | ★4.0k | Jupyter | 领先的开源自然语言 → SQL 大模型 |
| [DB-GPT-Hub](https://github.com/eosphoros-ai/DB-GPT-Hub) | ★2.0k | Python | Text2SQL 模型、数据集与微调技术 |
| [agents-flex](https://github.com/agents-flex/agents-flex) | ★1.0k | Java | 轻量 Java AI Agent 框架（LLM + 工具 + NL2SQL） |
| [PremSQL](https://github.com/premAI-io/premsql) | ★462 | Python | 端到端、本地优先的 Text-to-SQL 流水线 |
| [Text2Sql.Net](https://github.com/shuyu-labs/Text2Sql.Net) | ★138 | C# | 用 .NET + Semantic Kernel 开发的 Text2SQL 工具 |
| [DSPy-Text2SQL](https://github.com/jjovalle99/DSPy-Text2SQL) | ★107 | Jupyter | 用 DSPy 程序优化做 Text-to-SQL |
| [db-ally](https://github.com/zama-ai/db-ally) | — | Python | 免 SQL，通过自然语言"视图"访问数据 |

### 用于构建 ChatBI 的通用 Agent / LLM 框架

| 项目 | Stars | 语言 | 说明 |
| --- | --- | --- | --- |
| [LangChain](https://github.com/langchain-ai/langchain) | ★147.8k | Python | 默认工具箱；含 SQLDatabaseToolkit / SQL Agent |
| [RAGFlow](https://github.com/infiniflow/ragflow) | ★92.2k | Go | RAG 引擎，常与 ChatBI 搭配做"文档 + 数据"问答 |
| [AutoGen](https://github.com/microsoft/autogen) | ★61.4k | Python | 多 Agent 对话框架，适合"分析 Agent"模式 |
| [CrewAI](https://github.com/crewAIInc/crewAI) | ★59.7k | Python | 基于角色的多 Agent 编排 |
| [LlamaIndex](https://github.com/run-llama/llama_index) | ★52.5k | Python | 提供 NLSQLTableQueryEngine / text-to-SQL 组件 |
| [Agno](https://github.com/agno-agi/agno) | ★42.7k | Python | 高性能多 Agent 框架（Dash 即基于它） |
| [FastGPT](https://github.com/labring/FastGPT) | ★29.8k | TypeScript | 知识库问答平台，含工作流编排 |
| [MaxKB](https://github.com/1Panel-dev/MaxKB) | ★23.0k | Python | 企业级问答/Agent 平台 |
| [BISHENG](https://github.com/dataelement/bisheng) | ★12.0k | Python | 面向企业 AI 应用的开源大模型 DevOps 平台 |

## 语义层与指标

> 决定 ChatBI 准确率的关键层：指标定义一次，让 LLM 去查询。

| 项目 | Stars | 语言 | 说明 |
| --- | --- | --- | --- |
| [Cube](https://github.com/cube-js/cube) | ★21.0k | Rust | 面向 AI、BI 与嵌入式分析的开源语义层；有 AI/MCP 方向的支持 |
| [dbt](https://github.com/dbt-labs/dbt) | ★14.0k | Rust | 数据转换 + 语义层；dbt 指标可供给下游 BI/LLM |
| [Malloy](https://github.com/malloydata/malloy) | ★2.6k | TypeScript | 描述数据关系与转换的现代开源语言 |
| [MetricFlow](https://github.com/dbt-labs/metricflow) | ★1.8k | Python | 用代码定义、构建与维护指标 |

## 具备 AI / 对话能力的 BI 平台

> 加入了 AI/对话能力的传统 BI 工具——通常是最务实的第一步。

| 项目 | Stars | 语言 | 说明 |
| --- | --- | --- | --- |
| [Apache Superset](https://github.com/apache/superset) | ★75.1k | Python | 最流行的开源 BI；可接入 AI 助手 |
| [Metabase](https://github.com/metabase/metabase) | ★49.7k | Clojure | 易用的开源 BI 与嵌入式分析；AI 能力逐步推出 |
| [Redash](https://github.com/getredash/redash) | ★28.8k | Python | 查询与可视化，可连接任意数据源 |
| [DataEase](https://github.com/dataease/DataEase) | ★24.6k | Java | 人人可用的开源 BI 工具；与 SQLBot 同厂，搭配使用效果好 |

## 商业产品

> 闭源 ChatBI / 对话式分析产品。多数通过 MySQL/PostgreSQL 兼容协议对接主流数仓（Doris、StarRocks、ClickHouse、Snowflake 等）。

### 国内

- **帆软 Dora** —— 帆软的 AI 智能问数助手（FineReport / FineBI 产品线）；提问即可获得图表与叙事化分析。
- **帆软 FineBI** —— 具备 AI 问数能力的 BI 平台；已被 Apache Doris 官方生态文档收录。
- **阿里云 Quick BI（智能小 Q）** —— 阿里云上的自然语言查询与洞察生成。
- **百度 Sugar BI（智能问数）** —— 百度的对话式查询 BI。
- **腾讯云 BI / 数据洞察** —— 带 AI 对话分析的腾讯云 BI。
- **火山引擎 DataWind / 智能数据洞察** —— 字节跳动的 AI BI 产品。
- **网易有数** —— BI + AI 助手。
- **亿信 ABI** —— 智能 BI + AI 问数。
- **永洪 BI（Yonghong）** —— 带 AI 助手的 BI。
- **观远数据（Guandian）** —— 面向消费/零售的 BI，含 AI 能力。
- **Smartbi（思迈特）** —— BI + 对话式分析。
- **Kyligence Zen / Kyligence AI** —— 指标平台 + 语义层 + AI。
- **衡石科技 HENGSHI SENSE** —— 嵌入式分析，支持自然语言查询。
- **数势科技 SwiftAgent** —— 面向企业的 LLM 数据分析 Agent。
- **袋鼠云数栈 / 滴普科技 / 明略科技** —— 数据平台厂商，陆续加入问数能力。
- **SelectDB** —— Apache Doris 背后的商业厂商，具备 AI 方向能力。

### 国际

- **Microsoft Power BI Copilot** —— Power BI 内的对话式分析。
- **ThoughtSpot**（Spotter / Sage）—— 自然语言搜索与 AI 生成洞察。
- **Tableau Pulse / Tableau Agent**（Salesforce）—— AI 辅助分析与指标摘要。
- **Qlik Sense**（Insight Advisor）—— 增强分析。
- **Google Looker + Gemini** —— Looker 中的对话式 BI。
- **Amazon QuickSight Q** —— 用 ML 回答自然语言业务问题。
- **Snowflake Cortex Analyst / Snowflake Intelligence** —— 在 Snowflake 数据上做 text-to-SQL。
- **Databricks Genie / Assistant** —— 湖仓中的对话式分析。
- **MicroStrategy Auto** —— 自然语言机器人 / 自动生成仪表盘。
- **Oracle Analytics AI**、**SAP Joule / Datasphere**、**Domo AI**、**GoodData AI**。
- **Sigma Computing**、**Zenlytic**、**Fabi.ai**、**Hex Magic**、**Julius AI**、**DataChat**、**Tellius**、**AnswerRocket**、**Obviously AI**。

> 提示：某厂商是否支持特定数仓（如 Apache Doris）请以其官方文档为准——这方面变化很快。

## 综述与论文

| 资源 | Stars | 说明 |
| --- | --- | --- |
| [Awesome-Text2SQL](https://github.com/eosphoros-ai/Awesome-Text2SQL) | ★3.8k | LLM + Text2SQL 的教程与资源精选 |
| [NL2SQL_Handbook](https://github.com/HKUSTDial/NL2SQL_Handbook) | ★1.6k | 持续更新的 NL2SQL 进展手册 |
| [NL2SQL](https://github.com/yechens/NL2SQL) | ★1.6k | Text2SQL 语义解析数据集、解决方案与 paper 资源整合 |
| [DAMO-ConvAI](https://github.com/AlibabaResearch/DAMO-ConvAI) | ★1.6k | 阿里达摩院对话式 AI——包含 **DIN-SQL** |
| [Awesome-LLM-based-Text2SQL](https://github.com/DEEP-PolyU/Awesome-LLM-based-Text2SQL) | ★1.4k | TKDE 2025 综述：《Next-Generation Database Interfaces》 |
| [awesome-data-agents](https://github.com/HKUSTDial/awesome-data-agents) | ★777 | Data Agents 论文列表 |
| [Agentar-Scale-SQL](https://github.com/antgroup/Agentar-Scale-SQL) | ★478 | 蚂蚁集团的可扩展 NL2SQL 框架 |
| [RAT-SQL](https://github.com/microsoft/rat-sql) | ★451 | 微软的关系感知 Schema 编码（经典基线） |
| [AgentBench](https://github.com/THUDM/AgentBench) | ★3.8k | 评估 LLM 作为 Agent 的基准（含数据库任务） |
| [tianchi_nl2sql](https://github.com/beader/tianchi_nl2sql) | ★556 | 天池中文 NL2SQL 挑战赛第 3 名方案 |

## 基准与数据集

**广泛使用的 NL2SQL 基准**

| 数据集 | 说明 |
| --- | --- |
| **Spider** | 经典的跨域 text-to-SQL 基准（耶鲁）。 |
| **Spider 2.0** | 企业级真实 SQL 工作流——难度大幅提升。 |
| **BIRD** | 大规模基准，聚焦**执行准确率**与脏数据。 |
| **WikiSQL** | 早期大规模单表数据集（已基本饱和）。 |
| **SParC / CoSQL** | 多轮对话式 text-to-SQL。 |
| **Dr.Spider** | 面向鲁棒性的诊断型基准。 |
| **Archer** | 中英双语 NL2SQL 基准。 |
| **CSpider / DuSQL** | 中文 text-to-SQL 数据集。 |
| **TableBench** | 表格问答/推理基准。 |

**工具与辅助数据集**

| 项目 | Stars | 说明 |
| --- | --- | --- |
| [text2sql-data](https://github.com/jkkummerfeld/text2sql-data) | ★588 | 整合的 text-to-SQL 数据集（ATIS、GeoQuery、WikiSQL…） |
| [shopkeeper-agent](https://github.com/didilili/shopkeeper-agent) | ★460 | 电商数据分析 Agent 示例 |
| [tableQA](https://github.com/abhijithneilabraham/tableQA) | ★320 | 表格问答工具 |
| [distil-text2sql](https://github.com/distil-labs/distil-text2sql) | ★290 | 蒸馏一个小型 text2sql 模型 |
| [jev4pg](https://github.com/Sheltercosmo/jev4pg) | ★276 | 面向 PostgreSQL 的 Text2SQL |
| [dat](https://github.com/hexinfo/dat) | ★258 | 数据库智能分析与问答工具 |
| [Open_Data_QnA](https://github.com/GoogleCloudPlatform/Open_Data_QnA) | ★231 | Google Cloud 数据问答参考实现 |
| [text2sql-framework](https://github.com/Text2SqlAgent/text2sql-framework) | ★160 | Text-to-SQL Agent 框架 |
| [text2sql-lgesql](https://github.com/X-LANCE/text2sql-lgesql) | ★155 | LGESQL：线图增强的 text-to-SQL |
| [gap-text2sql](https://github.com/awslabs/gap-text2sql) | ★109 | AWS：从自然语言生成 SQL |

## 教程、课程与文章

**实战类**

- [Data-Agent：从 0 到 1 构建 Text2SQL 智能体实战教程](https://github.com/qifan777/data-agent-tutorial) ★110 —— StateGraph 编排、双层 NL2SQL、工程化实践。
- [3 步！用 Doris + DeepSeek 搭建 ChatBI 系统（保姆级教程）](https://segmentfault.com/a/1190000046198598)
- [零基础上手！用 Dify + DeepSeek + Doris MCP Server，实现秒级 SQL 调用](https://cloud.tencent.com.cn/developer/article/2558425)

**架构与解析类**

- [SQLBot: 基于大模型与 RAG 的智能问数系统架构](https://blog.csdn.net/weixin_35770067/article/details/153335005)
- [chatbi 探索 & 多款开源 AI chatbi 产品解析](https://damodev.csdn.net/68633aaeb93e2f417961c872)
- [Github 9 个惊艳的开源 NL2SQL 项目](https://juejin.cn/post/7538719894222733353)
- [ChatBI 核心技术：生成式 BI 解锁智能商业决策](https://book.qq.com/book-read/56843108/10)

**官方文档**

- [DB-GPT 文档](http://docs.dbgpt.cn/) —— 含 [Apache Doris 集成](http://docs.dbgpt.cn/zh-CN/docs/v0.8.0/installation/integrations/doris_install/)
- [SQLBot：配置 Apache Doris 数据源](https://dataease.cn/sqlbot/v1/user_manual/datasource_apachedoris/)

## 如何选型

| 你的诉求 | 建议从哪开始 |
| --- | --- |
| 开箱即用的开源问数系统 | **SQLBot**、**SuperSonic**、**DB-GPT** |
| 把 NL2SQL 嵌入自有应用 | **Vanna**、**WrenAI**、**sqlglot** + 你的 LLM |
| 业务指标口径要准确 | **语义层**（**Cube**、**dbt/MetricFlow**）+ LLM |
| 分析师用的桌面工具 | **Chat2DB**、**WhoDB**、**openhare** |
| 给现有 BI 加对话能力 | **Superset / Metabase / DataEase** + AI 助手，或商业 BI |
| 需要企业级支持的产品 | **帆软 Dora**、**Quick BI**、**ThoughtSpot**、**Power BI Copilot** |
| 微调自己的 SQL 模型 | **DB-GPT-Hub**、**SqlCoder**、**PremSQL** |

**实用评估维度**

1. **数据源覆盖** —— 是否支持你数仓的方言（Doris/StarRocks/ClickHouse…）？
2. **准确率机制** —— 是否对 DDL+文档做 RAG？有无 few-shot 示例？有无语义层？有无自我纠错回路？
3. **治理能力** —— 行/列级权限、审计日志、数据是否出域？
4. **部署形态** —— SaaS、私有化自托管，还是离线/内网隔离？
5. **多轮与追问** —— 跨问题是否保持上下文？
6. **成本** —— 每次提问的 token 消耗、缓存策略，小模型是否够用。
7. **可评测性** —— 能否用你自己的"问题→标准 SQL"测试集衡量执行准确率？

## 数据源兼容性

ChatBI 工具通常通过标准驱动/协议连接数据库。常被问到的几个：

| 数据库 | 典型连接方式 | 说明 |
| --- | --- | --- |
| **Apache Doris** | MySQL 协议（端口 9030） | SQLBot（官方文档）、DB-GPT、积木报表、Aix-DB 及多数 MySQL 兼容客户端均支持 |
| **StarRocks** | MySQL 协议 | 与 Doris 同一生态 |
| **ClickHouse** | HTTP / native | 支持广泛 |
| **MySQL / PostgreSQL** | 原生 | 普遍支持 |
| **Snowflake / BigQuery / Databricks** | 原生 SDK / 数仓 API | 商业产品中常见 |

> 若某工具"支持 MySQL"，通常也能连 Doris/StarRocks——但方言相关的 SQL 生成质量仍需实测。

## 相关精选清单

- [eosphoros-ai/Awesome-Text2SQL](https://github.com/eosphoros-ai/Awesome-Text2SQL) —— Text2SQL 论文、工具、数据集
- [HKUSTDial/awesome-data-agents](https://github.com/hkustdial/awesome-data-agents) —— Data Agents 研究
- [awesome-doris-ai](https://github.com/gaofujie1997/awesome-doris-ai) —— 姊妹清单，聚焦 Apache Doris × AI

---

## 贡献

欢迎提交 PR！请遵循以下规范：

- **先验证再收录** —— 附上仓库链接，并尽可能注明支持的数据源。
- **给每条打标签** —— *开源*、*商业产品*、*框架*、*语义层*、*科研* 或 *教程*。
- **星数保持约数**（如 `★12.3k`），并及时更新过期数据。
- **一句话说明理由** —— 讲清*为什么*值得收录，而不只是它是什么。
- 遵循 [Awesome 列表规范](https://github.com/sindresorhus/awesome)。

欢迎的贡献方向：真实落地案例、非英文资源、Spider/BIRD 上的评测结果、基准横向对比、部署指南。

## 许可

[MIT](./LICENSE)
