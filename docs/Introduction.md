---
id: intro
title: Introduction
slug: /intro
sidebar_position: 1
---

## What is RisingWave?

RisingWave is a cloud-native streaming database that uses SQL as the interface. It is designed to reduce the complexity and cost of developing and using a stream processing platform so that developers can build applications more efficiently. It ingests streaming data, performs the processing that you specify (aggregates, joins, maps, enrichment, etc.), and dynamically updates the results. As a streaming database, RisingWave stores the results so that users can access them in real-time.

RisingWave ingests data from sources like Kafka, Apache Pulsar, Amazon Kinesis, Redpanda, and materialized CDC sources.

## What can you do with RisingWave?

Everything you do in RisingWave is via Postgres-compatible SQL. You can:

* Collect and transform data from streams
* Create materialized views for the data that need to be incrementally aggregated
* Query for data in RisingWave, including persisted data and data you add or import to RisingWave.

## How does RisingWave work?

- See [Getting Started](Getting-Started.md) to learn about how to get started with RisingWave. 
- For the architecture of RisingWave, see [Architecture](Architecture.md).
- To learn about the supported stream sources and how to connect to the sources, see [Sources](Sources.md).
- For the supported SQL data types, operators, and statements, see [SQL overview](SQL-Overview.md).


### SQL as the interface

RisingWave makes it easy to manage streams and data. All you need to interact with RisingWave is Postgres-compatible SQL. No Java or Scala codes are needed.

### Real-time results via materialized views

With RisingWave, you define the data you need as materialized views. As new data come in, RisingWave only performs incremental aggregations as the results for previous events have already been calculated, thus reducing the processing time significantly. To further lower the latency, we optimized the storage processing logic for complex computations and high-concurrency scenarios. Queries can be processed and results can be delivered with low latency even in these demanding circumstances.

Results of materialized views are stored in RisingWave. You can issue a query to find out the latest result of a materialized view.

### Elastic and cost-effective

As a cloud-native platform, RisingWave is super elastic. You can dynamically adjust the compute and storage resources based on your actual requirements.

RisingWave is cost-effective. You pay for what you use as you scale. As compute is decoupled from storage in RisingWave, they can be scaled separately. In addition, RisingWave stores data in object storage systems (Amazon S3 and S3-compatible systems). The storage cost is down significantly compared with other centralized solutions that store data in expensive data warehouses.

### Data are correct and consistent

When data are processed in batches, if a job goes wrong, you can do some troubleshooting and rerun the job. However, it’s not practical to rerun a stream processing job, because the stream never ends. In stream processing, it is crucial that data are calculated correctly and events are not missed or calculated twice. Otherwise, the data will not match data in upstream or downstream systems.

In RisingWave, data correctness is ensured by a snapshot-based mechanism. Every time a snapshot is triggered, the internal states of each operator will be flushed to the cloud storage. Upon failovers, the operator recovers from the latest checkpoint on the cloud storage. 

