<div align="center">

# Rishav Bhattarai

**Salesforce Developer · Java / Spring Boot Backend Engineer · MS in Management Information Systems**

Las Vegas, NV · [Portfolio](https://rishavbhattarai.com.np/portfolio.html) · [LinkedIn](https://linkedin.com/in/rishav-bhattarai-nepal) · [Email](mailto:bhattarai.rishav@gmail.com)

</div>

---

### Profile

Salesforce Developer at UNLV's Office of Information Technology, with 6 years of Java and Spring Boot work on payment systems before that. Builds Apex, LWC and Flow solutions on Sales and Education Cloud, and the CI/CD pipelines that ship them. Earlier work: fintech wallet microservices on Docker and Kubernetes, tested to 15,000+ transactions per second. 15 pull requests merged into open-source projects, including Apache Beam, Apache SeaTunnel and DBeaver. MS in Management Information Systems from UNLV (May 2026), with a conference paper on CISO budget defense modeling.

### Experience

**Salesforce Developer**, Office of Information Technology, UNLV · Aug 2024 – Present
- Cut Salesforce release time 87% by automating CI/CD with GitHub Actions, saving the team an estimated 150 hours a month
- Connected a Blackthorn payment gateway to the event-registration platform, so each registration updates the moment its payment clears
- Replaced a weekly manual email process with a real-time Apex/LWC registration dashboard and Marketing Cloud automation via MuleSoft
- Kept student data access FERPA compliant with role-based access across development, staging and production

**Senior Java Developer** (Java Developer 2018–2021), Three Monks Pvt. Ltd., Nepal · Feb 2018 – Jun 2024
- Re-architected the wallet backend into Docker microservices on Kubernetes, holding 99.99% uptime and cutting cascading failures 85% in load tests
- Sustained 15,000+ transactions per second under simulated flash-sale load with Kubernetes auto-scaling
- Migrated 4 legacy Struts applications to Spring Boot and Angular, making pages load 42% faster
- Mentored 3 developers through code review and pair programming. Each went on to own payment features

---

### Selected Projects

**Backend and distributed systems**

| Project | Result | Stack |
|---|---|---|
| [Usage Metering & Billing](https://github.com/Rishavbhattarai/usage-metering-billing) | Turns raw usage events into invoices and syncs them to Salesforce. Ingested 1M events (10% duplicates) at **38,568 events/s** and stored exactly the unique ones. Rebuilt all 200 invoices from the event log with identical SHA-256 hashes, and the ledger matches Salesforce to the cent. | Python, FastAPI, PostgreSQL, Salesforce Bulk API 2.0 |
| [jobq](https://github.com/Rishavbhattarai/distributed-job-queue) | A job queue that doesn't lose jobs or run one twice by mistake. In a 10,000-job run with a worker killed every 10 seconds, all 10,000 succeeded and none ran to success twice. 63 tests, and CI runs the chaos test. | Python, FastAPI, Redis, PostgreSQL, Prometheus |
| [Tanks Arena](https://github.com/Rishavbhattarai/multiplayer-arena) | A multiplayer server where the server decides every move. Holds **1,680 players** on one Node process within the 33 ms tick (p99 26.4 ms). Delta snapshots cut per-player bandwidth 73%, and a cheating client gets rejected and corrected. | TypeScript, WebSockets, Prometheus |

**Guardrails for AI-written code** (Claude Code plugins, each measured with and without the plugin)

| Project | Result | Stack |
|---|---|---|
| [Spring Payment PCI Shield](https://github.com/Rishavbhattarai/spring-payment-pci-shield) | Flags card data in logs, unsafe `BigDecimal` money math and payment endpoints without idempotency in Java/Spring Boot services. On a checkout task, models without the plugin turned on payment-gateway wire logging (which writes card numbers to logs) in **4 of 11** runs. With the plugin, 0 of 11. | Python, Java, Spring Boot, Testcontainers |
| [FlowGuard for Salesforce DX](https://github.com/Rishavbhattarai/salesforce-flowguard) | Blocks hardcoded RecordType and Profile IDs, SOQL and DML inside loops, and Flows with no fault path. 12 rules, 55 unit tests. On the hardcoded-ID eval it scores **1.00 with the plugin and 0.00 without**. | Python, Apex, Salesforce Flow |
| [RLS & Edge Guard](https://github.com/Rishavbhattarai/rls-edge-guard) | Rejects Supabase row-level security holes, service-role keys in browser code, and Node code that won't run on Cloudflare Workers. Across 9 eval cases it raised Sonnet from **0.78 to 0.98** and Haiku from **0.76 to 0.93**. | Python, PostgreSQL, pgTAP, Cloudflare Workers |

**Data and machine learning**

| Project | Result | Stack |
|---|---|---|
| [CytoGuard](https://github.com/Rishavbhattarai/cytoguard-cell-painting) | Flags injured wells in Cell Painting drug screens and names the injury type. On compounds the model never saw, macro-F1 is **0.462 vs 0.146** for the published baseline, and injured-vs-healthy AUROC is 0.947. A label-shuffled control scores at chance. | Python, LightGBM, Cellpose-SAM |
| [CAFE-RAG](https://github.com/Rishavbhattarai/CAFE-RAG) | Plain-language search over 818 climate-health datasets on Harvard Dataverse. recall@5 **0.705** and MRR 0.635 on a 44-query gold set. | Python, SQLite FTS5, ChromaDB, Ollama |

---

### Open Source: 15 Merged Pull Requests

| Project | Merged work |
|---|---|
| Apache SeaTunnel [#12831](https://github.com/apache/seatunnel/pull/12831), [#12844](https://github.com/apache/seatunnel/pull/12844) | Two new source connectors. **Intercom**: fixed all four review items, and the integration test passes on Java 11 and 17. **Typeform**: pages with Typeform's `before` cursor and waits 500 ms between requests to stay under its 2 requests/s limit. 20 unit tests. |
| Apache Beam [#40865](https://github.com/apache/beam/pull/40865), [#40866](https://github.com/apache/beam/pull/40866) | Moved `SplittableParDoProcessFnTest` and `DatastoreV1Test` off the deprecated `DoFnTester`. Neither fits `TestPipeline`: the first advances processing time by hand, and the second verifies calls on Mockito mocks that can't be serialized. Both now run their DoFns through `DoFnRunners.simpleRunner`, the runner the DirectRunner uses. All 15 and all 62 tests pass. |
| DBeaver [#42502](https://github.com/dbeaver/dbeaver/pull/42502) | DDL for PostgreSQL functions and procedures dropped `REVOKE ... FROM PUBLIC`, so running it recreated the function open to everyone. It now emits the REVOKE the way `pg_dump` does. Checked on PostgreSQL 18. |
| TheAlgorithms/Java [#7660](https://github.com/TheAlgorithms/Java/pull/7660), [#7661](https://github.com/TheAlgorithms/Java/pull/7661), [#7662](https://github.com/TheAlgorithms/Java/pull/7662), [#7663](https://github.com/TheAlgorithms/Java/pull/7663), [#7664](https://github.com/TheAlgorithms/Java/pull/7664), [#7665](https://github.com/TheAlgorithms/Java/pull/7665), [#7666](https://github.com/TheAlgorithms/Java/pull/7666) | Wrote a differential fuzz harness that checks each algorithm against a `java.util` reference on random inputs. It found 8 bugs, and 7 fixes are merged. Among them: an infinite loop in `SwapSort`, dropped duplicates in `TreeSort`, `BoyerMoore` crashing on non-ASCII text, and `RabinKarp` returning wrong indexes after hash overflow. |
| Docling [#4996](https://github.com/docling-project/docling/pull/4996) | Added an optional `filename` to `ZipArchiveResult`, so converted zips get a real download name instead of `converted_docs.zip`. Older results still validate. |
| OpenDataLoader PDF [#776](https://github.com/opendataloader-project/opendataloader-pdf/pull/776) | Shares one marked-content ID across adjacent text operators. PDFs from Google Docs and Chrome print had one structure tag per letter. |
| Prisma Claude Code plugin [#3](https://github.com/prisma/claude-plugin/pull/3) | Pinned the local Prisma MCP server to `prisma@7.10.1`. Without the pin, `npx` pulled a release candidate with no `mcp` command, and the server failed to start. |

---

### Skills

- **Salesforce:** Apex, Lightning Web Components, Flow, Salesforce DX, Sales / Service / Education / Marketing Cloud, MuleSoft, Bulk API, Copado
- **Backend:** Java (6+ years), Spring Boot, Hibernate/JPA, REST APIs, microservices, Kafka, Vert.x, Python, FastAPI, TypeScript
- **Data:** PostgreSQL, Oracle, MySQL, Redis, SQL tuning, pandas, scikit-learn, Power BI
- **Infrastructure:** Docker, Kubernetes, GitHub Actions, Jenkins, Prometheus, JUnit, Mockito, Testcontainers

<div align="center">

More Salesforce, dashboard and cybersecurity-risk work on the **[full portfolio](https://rishavbhattarai.com.np/portfolio.html)**.

</div>
