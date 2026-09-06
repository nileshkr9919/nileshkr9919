## Nilesh Kumar

Backend engineer working on payments and distributed systems. Currently founding engineer at
**BON Credit**, a consumer fintech — I own subscription billing on Stripe, the bank and bureau
integrations behind it, and the money-movement alerting that sits on top.

Most of what I do is correctness under concurrency: idempotent webhook processing, deduplication
keys that survive a redelivery, transactional outboxes, and per-domain queue isolation so one
provider's outage doesn't take the rest of the system with it.

---

### Public work

**[grocery-booking-api](https://github.com/nileshkr9919/grocery-booking-api)** — six NestJS
services in an Nx monorepo, communicating over Redis pub/sub behind an API gateway. Distributed
transactions use the saga pattern with a compensating action per step, so a failure part-way
through a booking unwinds rather than leaving inventory reserved against an order that never
existed. OpenTelemetry tracing, Prometheus metrics, Terminus health probes, Redis-backed rate
limiting, Docker Compose for the whole thing.
`TypeScript · NestJS · PostgreSQL · Redis · OpenTelemetry`

**[distributed-mq](https://github.com/nileshkr9919/distributed-mq)** — a message log built to
understand the storage layer from the inside: topics, partitions, per-partition offsets,
acknowledgement tracking, and an append-only segmented file store. Single-node today; the
networking, replication and leader-election phases are designed in `docs/architecture.md` and not
yet built, which the README says plainly.
`TypeScript`

**[sales-tax](https://github.com/nileshkr9919/sales-tax)** — a small, deliberately
over-structured receipt calculator. Rounding rules isolated as pure functions with their own
tests, because rounding is where money problems actually come from.
`TypeScript`

---

### At work

Things I've shipped recently that I'd happily talk through:

- A Strangler Fig replacement of a 219K-line untyped Express backend with a NestJS/TypeScript
  monorepo serving the byte-identical wire contract — 42 modules, architecture invariants
  enforced by ESLint in CI rather than by code review.
- Cutting 61% of that service's HTTP surface by generating the route ledger from the mobile
  client's own source, so what gets dropped is decided by evidence rather than by memory.
- A golden-fixture contract suite that replays recorded HTTP exchanges byte-for-byte, so a
  backend cutover doesn't need a coordinated mobile release.
- Security and compliance remediation across OWASP Top 10, SOC 2, GDPR and PCI-DSS.
- SLOs that separate the defect budget from the capacity budget, with a runbook behind every
  alert.

---

### Tools

`TypeScript` `Node.js` `NestJS` `Fastify` `Rust` `Python` `PostgreSQL` `Redis` `BullMQ`
`Stripe` `Plaid` `AWS` `Docker` `Kubernetes` `Prometheus` `Grafana` `Vitest` `Testcontainers`

---

[LinkedIn](https://www.linkedin.com/in/nilesh-kr/)
