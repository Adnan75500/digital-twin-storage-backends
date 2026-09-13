Storage Backend Trade-offs for Digital Twin Historian Data

Group 33: Huzaifa Tahir (i230731) & Adnan Ahmed (i230715)

Research Problem

Digital twins continuously accumulate historical sensor and state data—the twin's "historian"—which must be stored for query analysis, system replay, and predictive modeling. While cloud platforms offer several viable storage backends (time-series, NoSQL, and relational databases), each makes different trade-offs across ingestion throughput, query latency, and storage cost.

Currently, developers often select backends based on general-purpose IoT benchmarks or vendor familiarity rather than empirical evidence matched to a digital twin's unique access pattern. This access pattern is distinctive: it requires near-continuous multi-sensor ingestion, frequent "current state" point lookups, and periodic long-range historical queries. Our research aims to evaluate these backends under this specific workload to determine the best latency/cost trade-offs as data volumes scale.

Planned Approach

Workload Generation: Design and build a synthetic workload generator that accurately reproduces a digital twin historian's specific access pattern.

Environment Setup: Deploy three distinct database backends (e.g., InfluxDB/TimescaleDB for time-series, MongoDB for NoSQL, and PostgreSQL for relational) on equivalent-resource cloud virtual machines or resource-capped containers.

Benchmarking: Load-test each backend with a common benchmark harness. The harness will issue continuous writes, latest-value point queries, and time-range aggregation queries at increasing data volumes (e.g., 1x, 10x, 100x sensor-days).

Metrics Collection: Measure and compare ingestion throughput, write latency, and query latency (p50/p95/p99) for both point and range queries.

Cost Analysis: Evaluate the on-disk storage size and compression ratio for each backend to estimate monthly cloud storage costs based on standard public cloud pricing.

License

This project is licensed under the MIT License - see the LICENSE file for details.
