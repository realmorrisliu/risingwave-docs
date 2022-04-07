---
id: sql-statements
slug: /sql-statements
title: Statements
---

RisingWave supports the following SQL statements.

* CREATE SOURCE
* CREATE MATERIALIZED VIEW
* CREATE TABLE
* DROP TABLE
* INSERT INTO
* DELETE

## Notes about CREATE MATERIALIZED VIEW

* Materialized views can be created from tables or existing materialized views.
* LATERAL subqueries are not supported yet.
* JOIN USING and NATURAL JOIN are not supported.
* The HAVING clause is not supported yet.
* The GROUP BY clause only supports grouping by input column names now.
* The HAVING clause is not supported yet
* The ORDER BY clause only supports ordering by output column names now.
