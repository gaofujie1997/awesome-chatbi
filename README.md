# Awesome ChatBI

> 🌟 A curated list of ChatBI / AI-powered conversational business intelligence (AI 问数 / Text2SQL / NL2SQL) — open-source platforms, commercial products, frameworks, papers, tutorials and real-world cases.

> 🌟 收录 ChatBI / 智能问数 / Text2SQL / NL2SQL 相关的开源平台、商业产品、技术框架、论文、教程与真实案例的精选导航。

**[简体中文](./README.zh-CN.md)**

ChatBI (Conversational Business Intelligence) lets users query data by asking questions in plain language and get answers (tables, charts, insights) powered by LLMs. This repo maps the whole ecosystem — from open-source platforms you can self-host to commercial products, the underlying frameworks, research, and hands-on tutorials.

Topics covered: **NL2SQL · Text2SQL · Semantic Layer · Data Agent · Conversational BI · AI Analytics**.

---

## Contents

- [Open-source Platforms](#open-source-platforms)
- [Frameworks & Libraries](#frameworks--libraries)
- [Commercial Products](#commercial-products)
- [Research & Datasets](#research--datasets)
- [Tutorials & Articles](#tutorials--articles)
- [Related Awesome Lists](#related-awesome-lists)
- [Contributing](#contributing)
- [License](#license)

<!-- Badge: mark each entry with its data-source support, e.g. "Doris ✓ MySQL ✓ PostgreSQL ✓" where verified. -->

---

## Open-source Platforms

> Self-hostable ChatBI / AI 问数 platforms. Marked with data-source support where verified.

| Project | Stars | Language | Highlights |
| --- | --- | --- | --- |
| [DB-GPT](https://github.com/eosphoros-ai/DB-GPT) | ★20.1k | Python | Open-source AI-native data application framework; Text2SQL, agent, RAG. Supports Doris & many DBs |
| [WrenAI](https://github.com/Canner/WrenAI) | ★17.9k | Python | Semantic-layer-driven NL2SQL for enterprise self-serve analytics |
| [DataEase SQLBot](https://github.com/dataease/SQLBot) | ★6.9k | JavaScript | Open-source ChatBI from Fit2Cloud; officially supports Apache Doris datasource |
| [sqlchat](https://github.com/sqlchat/sqlchat) | ★5.8k | — | Chat with your database in natural language, web UI |
| [jimureport](https://github.com/jeecgboot/jimureport) (积木报表) | ★8.5k | Java | Report + ChatBI, supports Doris & more |
| [Aix-DB](https://github.com/apconw/Aix-DB) | ★2.2k | — | AI-assisted data query, supports Doris |
| [ChatBI (ambition119)](https://github.com/ambition119/chatBI) | ★181 | — | Lightweight ChatBI demo |
| [Langchain-ChatBI](https://github.com/dynamiclu/Langchain-ChatBI) | ★154 | Python | ChatBI built on LangChain |
| [vanna-chatbi](https://github.com/owenliang/vanna-chatbi) | ★30 | — | ChatBI powered by Vanna |

## Frameworks & Libraries

> Underlying building blocks: Text2SQL / NL2SQL / semantic layers / agent frameworks.

| Project | Stars | Description |
| --- | --- | --- |
| [Vanna](https://github.com/vanna-ai/vanna) | ★13k | Open-source Text2SQL framework (Python): train on your schema, chat to query |
| [DB-GPT](https://github.com/eosphoros-ai/DB-GPT) | ★20.1k | (also listed above) framework + tools |
| [WrenAI](https://github.com/Canner/WrenAI) | ★17.9k | semantic layer engine |
| [Superset](https://github.com/apache/superset) | ★local | BI + AI assistant integrations |
| [MindsDB](https://github.com/mindsdb/mindsdb) | — | AI using SQL interfaces |
| [db-ally](https://github.com/zama-ai/db-ally) | — | SQL-free LLM data access via natural language views |

## Commercial Products

> Proprietary ChatBI / conversational analytics products (many integrate mainstream data warehouses incl. Doris via MySQL-compatible protocol).

### China / 国内
- **帆软 Dora** — AI 智能问数助手 from FanRuan (FineReport/FineBI family). Ask questions, get charts & analysis. Integrates mainstream DWs.
- **帆软 FineBI** — BI platform with AI 问数 capabilities; officially in the Apache Doris ecosystem.
- **亿信 ABI** — intelligent BI + AI 问数.
- **永洪** — Yunhong BI with AI assistant.
- **观远数据** — Guandian Consumer BI with AI features.
- **Smartbi** (思迈特) — BI + AI 对话式分析.
- **网易有数**. **Kyligence** — semantic layer + AI.
- **SelectDB** — Doris commercial vendor with AI features.

### Global / 国际
- **Microsoft Power BI Copilot** — conversational analytics inside Power BI.
- **ThoughtSpot Spotter** — NL search + AI analytics.
- **Tableau** (Salesforce AI) — AI-assisted analytics.
- **Qlik Sense** — AI/ML augmented analytics.
- **Sigma** — spreadsheets + AI.
- **DBeaver AI**, **Looker**, **Hex**, **MotherDuck** — AI-flavored analytics tooling.

> Note: commercial product support for specific DWs (e.g. Doris) should be verified on each vendor's official docs.

## Research & Datasets

> NL2SQL / Text2SQL research, benchmarks and data agents.

| Resource | Stars | Description |
| --- | --- | --- |
| [Awesome-Text2SQL](https://github.com/eosphoros-ai/Awesome-Text2SQL) | ★3.7k | Comprehensive Text2SQL paper/tool/dataset list |
| [awesome-data-agents](https://github.com/hkustdial/awesome-data-agents) | ★777 | Continuously updated paper list on Data Agents |
| [DB-GPT-Hub](https://github.com/eosphoros-ai/DB-GPT-Hub) | ★2k | Text2SQL fine-tuning & benchmark hub |
| [NL2SQL_Handbook](https://github.com/HKUSTDial/NL2SQL_Handbook) | ★1.6k | NL2SQL handbook from HKU-CSE |
| [NL2SQL](https://github.com/yechens/NL2SQL) | ★1.6k | Datasets & models for NL2SQL |
| [Spider / BIRD] (datasets) | — | Standard NL2SQL benchmarks |

## Tutorials & Articles

- **Overview**: [ChatBI 核心技术：生成式 BI 解锁智能商业决策](https://book.qq.com/book-read/56843108/10)
- **开源解析**: [chatbi 探索 & 多款开源 AI chatbi 产品解析](https://damodev.csdn.net/68633aaeb93e2f417961c872)
- **NL2SQL 项目盘点**: [Github 9 个惊艳的开源 NL2SQL 项目](https://juejin.cn/post/7538719894222733353)
- **架构**: [SQLBot: 基于大模型与 RAG 的智能问数系统架构](https://blog.csdn.net/weixin_35770067/article/details/153335005)
- **Doris + ChatBI**: [3 步！用 Doris + DeepSeek 搭建 ChatBI 系统](https://segmentfault.com/a/1190000046198598)

## Related Awesome Lists

- [eosphoros-ai/Awesome-Text2SQL](https://github.com/eosphoros-ai/Awesome-Text2SQL)
- [HKUSTDial/awesome-data-agents](https://github.com/hkustdial/awesome-data-agents)
- [awesome-doris-ai](https://github.com/gaofujie1997/awesome-doris-ai) — our companion list for Doris × AI

---

## Contributing

Open a PR! Guidelines:
- Mark each entry with its **data-source support** (e.g. Doris / MySQL / PostgreSQL) where verified.
- Tag each entry as **open-source**, **commercial**, **framework**, or **research**.
- Follow the [awesome list guidelines](https://github.com/sindresorhus/awesome).

## License

[MIT](./LICENSE)