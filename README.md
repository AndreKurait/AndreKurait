# Andre Kurait

**Cloud infrastructure · distributed systems · developer tooling**

I'm a senior engineer at AWS, a maintainer of [OpenSearch Migrations](https://github.com/opensearch-project/opensearch-migrations), and a contributor to [Floci](https://github.com/floci-io/floci), an open-source AWS emulator. I build concurrent Java systems, cloud API emulation, Kubernetes deployment tooling, and integration tests.

## Floci — AWS emulation

[**182 merged upstream pull requests**](https://github.com/floci-io/floci/pulls?q=is%3Apr+is%3Amerged+author%3AAndreKurait), spanning workflow execution, service compatibility, and concurrency.

- **Workflow and runtime execution.** Implemented [SWF emulation covering 39 modeled operations](https://github.com/floci-io/floci/pull/2257), including workflow state transitions and activity lifecycles. Added [Lambda provisioned-concurrency runtime initialization, routing, and cleanup](https://github.com/floci-io/floci/pull/6320).
- **Concurrency primitives.** Built [bounded work queues and versioned signals](https://github.com/floci-io/floci/pull/6547) to limit workers and retained keys, coalesce notifications, and prevent concurrent execution for the same key.
- **Compatibility verified against AWS.** Corrected [Step Functions callback authorization](https://github.com/floci-io/floci/pull/7277) using comparisons against real AWS APIs and signed SDK regression tests, including resource-scoped grants, explicit denies, and completed-token retries.

## OpenSearch Migrations — search infrastructure

**Maintainer** · [**515 merged pull requests**](https://github.com/opensearch-project/opensearch-migrations/pulls?q=is%3Apr+is%3Amerged+author%3AAndreKurait) · [Maintainer roster](https://github.com/opensearch-project/opensearch-migrations/blob/main/MAINTAINERS.md)

- **Java memory and concurrency.** Replaced a large in-heap term-position index with [external sorting and memory-mapped sidecars](https://github.com/opensearch-project/opensearch-migrations/pull/2886) for source reconstruction. Fixed a [Netty event-loop deadlock](https://github.com/opensearch-project/opensearch-migrations/pull/2718) by moving blocking response collection off the event loop.
- **Kubernetes deployment and CI.** [Parallelized EKS provisioning and teardown and extracted shared Jenkins functions](https://github.com/opensearch-project/opensearch-migrations/pull/2678), improved [bootstrap readiness and cleanup after partial failures](https://github.com/opensearch-project/opensearch-migrations/pull/3448), and contributed [GitHub Actions test sharding](https://github.com/opensearch-project/opensearch-migrations/pull/1376).
- **Incremental migration and correctness.** Authored the [delta-snapshot RFC](https://github.com/opensearch-project/opensearch-migrations/issues/1517) and implemented [update](https://github.com/opensearch-project/opensearch-migrations/pull/1762) and [delete](https://github.com/opensearch-project/opensearch-migrations/pull/1784) processing using Lucene segments and live-document bitsets. More recently, corrected [bulk request limits using exact serialized sizes](https://github.com/opensearch-project/opensearch-migrations/pull/3483).

## docker-cache — GitHub Actions caching

I maintain [docker-cache](https://github.com/AndreKurait/docker-cache), a fork of [ScribeMD/docker-cache](https://github.com/ScribeMD/docker-cache) for caching built and pulled Docker images. Published [0.7.0](https://github.com/AndreKurait/docker-cache/releases/tag/0.7.0) with updated runtime and cache dependencies and a rebuilt action bundle.

Used in public CI workflows for [OpenTelemetry Collector Contrib](https://github.com/open-telemetry/opentelemetry-collector-contrib/blob/main/.github/workflows/build-and-test.yml#L465), [authentik](https://github.com/goauthentik/authentik/blob/main/.github/actions/setup/action.yml#L113), and [FS Crawler](https://github.com/dadoonet/fscrawler/blob/main/.github/workflows/maven.yml#L37).

## Developer and agent tooling

- **[AWS agent toolkit](https://github.com/aws/agent-toolkit-for-aws/pull/101)** — contributed the Amazon OpenSearch Service skill, covering migration, provisioning, search, and observability guidance for coding agents.

### Proofs of concept

- **[acp-traces](https://github.com/AndreKurait/acp-traces)** — a Rust proxy that adds OpenTelemetry tracing to Agent Client Protocol interactions, including prompt turns, tool calls, and timing.
- **[TemporalCI](https://github.com/AndreKurait/TemporalCI)** — a Kubernetes-native CI project using Temporal workflows for build orchestration and EKS test-cluster lifecycle management.

*Contribution counts checked November 2, 2026; upstream merged PRs only.*

[LinkedIn](https://www.linkedin.com/in/andrekurait/) · [Email](mailto:andrekurait@gmail.com)
