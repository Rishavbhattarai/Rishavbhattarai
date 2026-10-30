<div align="center">

# Hi, I'm Rishav Bhattarai 👋

**Salesforce Developer @ UNLV Office of Information Technology · Java/Spring Boot Engineer · MS in MIS (2026)**

[![Portfolio](https://img.shields.io/badge/Portfolio-rishavbhattarai.com.np-3b82f6?style=for-the-badge)](https://rishavbhattarai.com.np/portfolio.html)
[![Email](https://img.shields.io/badge/Email-bhattarai.rishav%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:bhattarai.rishav@gmail.com)

</div>

---

### About Me

- 🔧 Currently building **Sales & Service Cloud** solutions and automating **CI/CD pipelines** (87% faster deployments, ~150 eng. hours saved/month) at UNLV
- 💼 6 years as a **Senior Java/Spring Boot Developer** before that (2018–2024), building fintech payment microservices that handled 4,000+ daily transactions
- 🎓 **MS in Management Information Systems**, UNLV (May 2026), with a conference paper on CISO budget defense modeling
- 🧠 Building and measuring: a crash-safe job queue, a usage-billing pipeline that reconciles to Salesforce, a cell-injury screen for drug discovery, and RAG evaluations that report where each method loses
- 🧩 Wrote two Claude Code plugins that reject bad code before it reaches disk: Salesforce deploy breakers, and Supabase RLS holes plus code that won't run on Cloudflare Workers
- 🔀 11 pull requests merged upstream: two Apache SeaTunnel source connectors (Intercom, Typeform), a test moved off a deprecated API in Apache Beam, a tagged-PDF fix in OpenDataLoader PDF, a zip filename field in Docling, an MCP server fix in Prisma's Claude Code plugin, and five TheAlgorithms/Java bug fixes found with a fuzz harness I wrote.
- 🌱 Background in Nepal building production fintech (**PayMe & AwiPay**, 100K+ users) before moving into Salesforce + AI engineering

---

### 🚀 Featured Projects

| Project | Result | Stack |
|---|---|---|
| [**CytoGuard**](https://github.com/Rishavbhattarai/cytoguard-cell-painting) | Flags injured wells in Cell Painting drug screens and names the injury mechanism. On compounds the model never saw, macro-F1 is **0.462 vs 0.146** for the published baseline, and injured-vs-healthy AUROC is **0.947**. A label-shuffled control scores chance (0.053). | `Python` `LightGBM` `Cellpose-SAM` |
| [**jobq**](https://github.com/Rishavbhattarai/distributed-job-queue) | Job queue that never loses a job or runs one twice by mistake. In a 10,000-job run with a worker killed every 10 seconds (13 kills), all 10,000 succeeded and none ran to success twice. 63 tests, CI runs a chaos test. | `Python` `FastAPI` `Redis` `PostgreSQL` `Prometheus` |
| [**Usage Metering & Billing**](https://github.com/Rishavbhattarai/usage-metering-billing) | Turns raw usage events into invoices and syncs them to Salesforce. Ingests 1M events (10% duplicates) at **38,568 events/s**, stores exactly the unique ones, and rebuilds all 200 invoices from the event log with identical SHA-256 hashes. Ledger and Salesforce match to the cent, zero drift. | `Python` `FastAPI` `PostgreSQL` `Salesforce Bulk API 2.0` |
| [**FlowGuard for Salesforce DX**](https://github.com/Rishavbhattarai/salesforce-flowguard) | Claude Code plugin that blocks hardcoded RecordType and Profile IDs, SOQL and DML inside loops, and Flows with no fault path, before Claude writes or commits them. 12 rules, 55 unit tests. On the hardcoded-ID eval it scores **1.00 with the plugin and 0.00 without**. | `Python` `Apex` `Salesforce Flow` `Claude Code hooks` |
| [**RLS & Edge Guard**](https://github.com/Rishavbhattarai/rls-edge-guard) | Claude Code plugin that rejects an edit if it adds a Supabase RLS hole, puts a service-role key in the browser, or uses Node code that won't run on Cloudflare Workers. Across 9 eval cases it lifted Sonnet from **0.78 to 0.98** and Haiku from **0.76 to 0.93**. Without it, every model shipped a table with RLS off when asked for "just the table". Static findings are checked against real Postgres with pgTAP. | `Python` `Supabase` `PostgreSQL` `Cloudflare Workers` |
| [**Tanks Arena**](https://github.com/Rishavbhattarai/multiplayer-arena) | Authoritative-server multiplayer netcode. Holds **1,680 players** on one Node process within the 33 ms tick (p99 26.4 ms). Delta snapshots cut per-player bandwidth by **73%**. A cheating client is rejected and corrected. | `TypeScript` `WebSockets` `Prometheus` |
| [**GraphRAG vs Vector RAG**](https://github.com/Rishavbhattarai/multihop-rag-showdown-) | Side-by-side evaluation on 50 MuSiQue multi-hop questions, fully local on Ollama. Pure GraphRAG lost (18% vs 28%); a hybrid of both scored best (34%). With 50 questions the gaps are not statistically significant, and the README says so. | `Python` `Ollama` `ChromaDB` |
| [**CAFE-RAG**](https://github.com/Rishavbhattarai/CAFE-RAG) | Plain-language search over 818 climate-health datasets on Harvard Dataverse. recall@5 **0.705**, MRR **0.635** on a 44-query gold set. | `Python` `SQLite FTS5` `ChromaDB` `Ollama` |

**Open-source pull requests (merged)**

| PR | What it does |
|---|---|
| [apache/seatunnel #12831](https://github.com/apache/seatunnel/pull/12831) | Adds an Intercom source connector to SeaTunnel (design in [#12823](https://github.com/apache/seatunnel/issues/12823)). Fixed all four review items; the integration test passes on Java 11 and 17. |
| [apache/seatunnel #12844](https://github.com/apache/seatunnel/pull/12844) | Adds a Typeform source connector (fixes [#12822](https://github.com/apache/seatunnel/issues/12822)). Pages with Typeform's `before` cursor and waits 500 ms between requests to stay under its 2 requests/s limit. 20 unit tests. |
| [apache/beam #40865](https://github.com/apache/beam/pull/40865) | Moves `SplittableParDoProcessFnTest` off the deprecated `DoFnTester`. The tests advance processing time and fire timers by hand, which `TestPipeline` can't do, so the test helper now runs `ProcessFn` through `DoFnRunners.simpleRunner`, the same runner the DirectRunner uses. All 15 tests pass with their bodies unchanged. |
| [opendataloader-pdf #776](https://github.com/opendataloader-project/opendataloader-pdf/pull/776) | Shares one marked-content ID across adjacent text operators. PDFs from Google Docs and Chrome print had one tag per letter in the structure tree. |
| [docling-project/docling #4996](https://github.com/docling-project/docling/pull/4996) | Adds an optional `filename` to `ZipArchiveResult`, so a converted zip can carry a real download name instead of `converted_docs.zip`. Older results still validate. Step 1 of a three-repo change for [docling-serve #732](https://github.com/docling-project/docling-serve/pull/732). |
| [prisma/claude-plugin #3](https://github.com/prisma/claude-plugin/pull/3) | Pins the local Prisma MCP server to `prisma@7.10.1`. Unpinned, `npx` pulled the 8.0 release candidate, which has no `mcp` command, so the server failed to start in Claude Code. |
| TheAlgorithms/Java [#7660](https://github.com/TheAlgorithms/Java/pull/7660), [#7661](https://github.com/TheAlgorithms/Java/pull/7661), [#7662](https://github.com/TheAlgorithms/Java/pull/7662), [#7663](https://github.com/TheAlgorithms/Java/pull/7663), [#7666](https://github.com/TheAlgorithms/Java/pull/7666) | Wrote a differential fuzz harness that runs each algorithm on random inputs and checks it against a `java.util` reference. It found 8 bugs, and 5 fixes are merged: `SwapSort` looped forever on duplicates, `TreeSort` dropped duplicates, `FlashSort` and `DutchNationalFlagSort` crashed on 2-element and empty arrays, case-insensitive `HorspoolSearch` skipped real matches, and `SkipList` shrank its size when removing a missing element. |

Earlier AI-security work: [Zenith](https://github.com/Rishavbhattarai/Zenith) (MCP security and observability gateway), [Hyperion](https://github.com/Rishavbhattarai/Hyperion) (zero-trust validation of AI-generated infrastructure actions), [Project-Aegis](https://github.com/Rishavbhattarai/Project-Aegis) (MCP gateway with RBAC and PII redaction) and [AI Knowledge Assistant](https://github.com/Rishavbhattarai/ai-knowledge-assistant) (GraphRAG).

*More Salesforce, dashboard, and cybersecurity-risk projects on my [full portfolio →](https://rishavbhattarai.com.np/portfolio.html)*

---

### 🛠️ Tech I Work With

**Salesforce**
![Apex](https://img.shields.io/badge/Apex-00A1E0?style=flat-square&logo=salesforce&logoColor=white)
![LWC](https://img.shields.io/badge/Lightning%20Web%20Components-00A1E0?style=flat-square&logo=salesforce&logoColor=white)
![Flow](https://img.shields.io/badge/Flow%20Builder-00A1E0?style=flat-square&logo=salesforce&logoColor=white)
![Salesforce DX](https://img.shields.io/badge/Salesforce%20DX-00A1E0?style=flat-square&logo=salesforce&logoColor=white)

**Backend & Languages**
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)

**Data & Infra**
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Neo4j](https://img.shields.io/badge/Neo4j-008CC1?style=flat-square&logo=neo4j&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

**CI/CD & Tooling**
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white)
![Copado](https://img.shields.io/badge/Copado-00A1E0?style=flat-square)

---

<div align="center">

**🌐 [Full Portfolio](https://rishavbhattarai.com.np/portfolio.html)**

</div>
