# Andre Kurait

**Senior Software Engineer at AWS · Austin, TX**

I'm a maintainer of the OpenSearch project's [OpenSearch Migrations](https://github.com/opensearch-project/opensearch-migrations), where I've authored [500+ merged pull requests](https://github.com/opensearch-project/opensearch-migrations/pulls?q=is%3Apr+is%3Amerged+author%3AAndreKurait). [Maintainer roster](https://github.com/opensearch-project/opensearch-migrations/blob/main/MAINTAINERS.md).

I build search migration infrastructure and developer tools, working directly with enterprise customers and partners to turn deployment constraints, compatibility gaps, and production failures into reusable software. My work spans Lucene internals, concurrent Java pipelines, Kafka, Kubernetes, and the APIs and interfaces engineers use to operate them.

## Selected engineering work

- **Reindexing performance.** Improved snapshot reindexing throughput by [**135% on the same compute size**](https://github.com/opensearch-project/opensearch-migrations/pull/905) through parallel document processing and separate CPU/I/O thread pools. A [separate buffering and scheduling optimization](https://github.com/opensearch-project/opensearch-migrations/pull/914) reduced benchmark memory usage by approximately **50%**.

- **Incremental indexing and data recovery.** Authored the [delta-snapshot RFC](https://github.com/opensearch-project/opensearch-migrations/issues/1517) and implemented [update](https://github.com/opensearch-project/opensearch-migrations/pull/1762) and [delete](https://github.com/opensearch-project/opensearch-migrations/pull/1784) processing by comparing Lucene segments and live-document bitsets. More recently, built [recovery paths for indices with disabled or partially excluded `_source`](https://github.com/opensearch-project/opensearch-migrations/pull/2985), including streaming postings and regression tests for phrase-query behavior.

- **Compatibility without excessive overhead.** Built shared JavaScript transformations across traffic replay, metadata migration, and backfill so customers could adapt schemas and requests. [Changed Java/JavaScript data conversion and added batching](https://github.com/opensearch-project/opensearch-migrations/pull/1337), reducing overhead in the type-mapping sanitization benchmark from **43% to approximately 9%**.

- **Failures operators can diagnose.** Fixed [Kafka offset stalls caused by asynchronous cleanup, partition reassignment, and idle output buffers](https://github.com/opensearch-project/opensearch-migrations/pull/3078). Added per-partition time-lag reporting and a diagnostic command that inspects records without changing consumer-group offsets.

- **Deployment within customer constraints.** Redesigned [ECS ingress for managed search sources and GovCloud](https://github.com/opensearch-project/opensearch-migrations/pull/721), removing the need to install a capture proxy on customer hosts. Helped build Migration Assistant on Kubernetes through [workflow CLIs](https://github.com/opensearch-project/opensearch-migrations/pull/1858) and [integration tests with Argo Workflows](https://github.com/opensearch-project/opensearch-migrations/pull/2032).

- **Faster feedback for the team.** Established [Testcontainers integration tests](https://github.com/opensearch-project/opensearch-migrations/pull/508) and helped reduce CI runtime from **44 to 8 minutes** through [parallel execution](https://github.com/opensearch-project/opensearch-migrations/pull/1302), caching, and [test sharding](https://github.com/opensearch-project/opensearch-migrations/pull/1376). Also [unified Elasticsearch and Solr migration paths](https://github.com/opensearch-project/opensearch-migrations/pull/2982) around shared orchestration, document readers, and work coordination.

## Projects beyond the migration engine

| Project | What I built |
| --- | --- |
| [TemporalCI](https://andrekurait.github.io/TemporalCI/) · [Code](https://github.com/AndreKurait/TemporalCI) | Began as a weekend proof of concept after encountering limitations in our Jenkins setup. Declarative CI built on Temporal and Kubernetes, with Go APIs and a Svelte dashboard for build history, durations, and failure analysis. |
| [acp-traces](https://github.com/AndreKurait/acp-traces) | A Rust proxy that turns Agent Client Protocol interactions into OpenTelemetry traces: agent turns, tool execution, and approval latency. Makes coding-agent behavior inspectable without modifying the agent; prompt/response recording is opt-in. |
| [OpenSearch Benchmark Framework](https://github.com/AndreKurait/opensearch-benchmark-framework) | Automated provisioning, workload execution, reporting, and teardown for compute/storage comparisons on EKS. Includes a [published 18-configuration geonames benchmark](https://github.com/AndreKurait/opensearch-benchmark-framework/blob/main/results/REPORT.md). |
| [MovieSearchDemo](https://github.com/AndreKurait/MovieSearchDemo) | A React/TypeScript and Next.js application with Elasticsearch/OpenSearch APIs, Kubernetes deployment, and continuous Locust load testing for migration demonstrations. |

I also contributed the [Amazon OpenSearch Service skill to AWS's agent toolkit](https://github.com/aws/agent-toolkit-for-aws/pull/101), packaging migration assessment, provisioning, search, and observability guidance for coding agents.

## Customer work and public explanations

I supported Octus's migration and co-authored the [AWS case study documenting 85% lower infrastructure costs after migration and subsequent resizing](https://aws.amazon.com/blogs/big-data/how-octus-achieved-85-infrastructure-cost-reduction-with-zero-downtime-migration-to-amazon-opensearch-service/). I've also delivered dozens of technical demos to enterprise customers and AWS partners.

- [Accelerate your migration with reindexing from snapshot](https://aws.amazon.com/blogs/big-data/accelerate-your-migration-to-amazon-opensearch-service-with-reindexing-from-snapshot/) — co-authored AWS article.
- [Migration Assistant: Capture and Replay](https://www.youtube.com/watch?v=WyOWlV7-By4) — public technical presentation.

I like taking a problem from a customer conversation through a design document, implementation, testing, and operational tooling. The goal is software another engineer can understand, validate, and run.

[LinkedIn](https://www.linkedin.com/in/andrekurait/) · [Email](mailto:andrekurait@gmail.com)
