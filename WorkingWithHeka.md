# Handling logs, events and metrics using Heka

From Sid Ramesh, from Exotel, @sidramesh

> [Heka](https://github.com/mozilla-services/heka) - Data collection and processing made easy. http://hekad.readthedocs.org/


### Context
Distributed systems produce different types of data
- Logs
  - Delayed
  - It's fine even if we miss them
- Metrics
  - More realtime in nature
  - Metrics are also lossly in nature
- Events
  - Had to be handled within a factor of milli seconds
  - Async way of processing a workflow
  - These need to be more robust in nature

Each type of data has unique (aggregation / processing / freshness) characteristics

### Why? (The Problem)
Collecting, aggregating, processing these distinct types of data require a variety of problems

#### Logs
- Logstash
- rsyslogd
- fluentd

#### Metrics
- StatsD
- Perf Collectors
- Datadog / New Relic

#### Events
- There's no standard
- Brokered Queues (SQS, RabbitMQ, Beanstalkd)
- Websocks / XMPP

#### Application dEveloper
- User many different libraries

#### DevOps Team
- Different tech stack to maintain

### What? (is Heka)
> Heka is a high performance, extremely extensible tool for gathering, analyzing, monitoring and reporting data

#### Simple Semantics
- Acquire Data
- Transform Data
- Output Data

> Internally modeled as a generic message router

> "Swiss Army Knife"

### Various Inputs
- Logs
- TCP / UDP / HTTP
- StatsD
- ...

Inbuilt Realtime Graphing
Complex Processing
- Aggregation
- Anamoly detection (including Alerting!)

### How? (do we use it)
- Library (currently in Go) to emit logs, events or metrics
- Only `hekad` runs every machine
  - Log input for logs, StatsD input for metrics, TCP input for events
- Local `hekad` captures data and pushes to Queue (Kafka)
- Global `hekad` reads off Kakfa and pushes logs and metrics to respective stores

> Basically a single datapipeline at exotel

### Our Experience
- Dev Win
  - Single library to integrate with
  - Consistent interface
- DevOps Win
  - Ability to change the underlying pieces without dev support
  - Super light weight
  - Single instance of data pipeline
