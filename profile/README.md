# jardisAdapter

**JARDIS** — *Just A Reliable Domain Integration System* — is a platform for Domain-Driven Design in the PHP ecosystem. You model your domain; Jardis generates the production-ready hexagonal code. Modelling stays human; the implementation work that repeats with every aggregate is what Jardis handles.

*"Works with any framework."* The hexagonal architecture Jardis generates keeps your domain core free of infrastructure concerns — and the packages in this organisation are the infrastructure side of that boundary. → [jardis.io](https://jardis.io)

---

**jardisAdapter** contains the open-source infrastructure adapters that sit behind the ports of Jardis-generated hexagonal applications. Each package implements a well-defined contract (PSR where one exists; `jardissupport/contract` where one does not) so that no framework or infrastructure choice bleeds into the domain layer.

> These packages are MIT-licensed building blocks of the open-source foundation that Jardis-generated DDD code runs on. The platform that generates production-ready hexagonal code for PHP is available at [jardis.io](https://jardis.io).

---

## Packages

| Package | Description |
|---|---|
| [Cache](https://github.com/jardisAdapter/cache) | PSR-16 multi-layer cache for PHP — stack Memory, APCu, Redis, and Database backends with automatic read-through backfill and write-through propagation |
| [DbConnection](https://github.com/jardisAdapter/dbConnection) | PDO connection pool for PHP with read/write splitting, round-robin load balancing across replicas, and automatic health checks — supports MySQL, PostgreSQL, and SQLite |
| [EventDispatcher](https://github.com/jardisAdapter/eventdispatcher) | PSR-14 event dispatcher for PHP with priority-ordered listeners, type-hierarchy matching, stoppable events, and deferred dispatch via EventCollector |
| [Filesystem](https://github.com/jardisAdapter/filesystem) | Filesystem abstraction for PHP covering local and S3-compatible storage — unified read, write, stream, and visibility API without Flysystem or the AWS SDK |
| [Http](https://github.com/jardisAdapter/http) | PSR-18 HTTP client with cURL transport, Bearer and Basic auth, retry with exponential backoff, and minimal footprint |
| [Logger](https://github.com/jardisAdapter/logger) | PSR-3 logging pipeline with 20+ handlers, 7 formatters, 6 enrichers, and fluent builder API |
| [Mailer](https://github.com/jardisAdapter/mailer) | SMTP mail client with STARTTLS, authentication, HTML and plain text support, attachments, and retry with exponential backoff |
| [Messaging](https://github.com/jardisAdapter/messaging) | Multi-transport messaging for Redis, Kafka, RabbitMQ, and Database with automatic serialisation and consumer groups |

---

## Design principle

Each adapter implements a contract interface, not a framework abstraction. Swapping out the implementation — for example, replacing a database-backed cache with Redis — means replacing one class, not refactoring the domain. *"Architecture that prevents shortcuts."*

PHPStan Level 8 · Code Coverage ≥ 80 % · PSR-4/PSR-12 · MIT License
