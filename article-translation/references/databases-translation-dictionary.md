---
name: databases-translation-dictionary
delivery: reference
description: |
  Словарь терминологии баз данных для перевода технических статей с английского
  и немецкого на русский. Покрывает реляционные СУБД (PostgreSQL, MySQL/MariaDB),
  колоночные БД (ClickHouse), in-memory (Tarantool, Redis), NoSQL, шардирование,
  репликацию, транзакции, индексы, оптимизатор запросов, бэкапы.

  Источники: документация Postgres Professional (postgrespro.ru), официальный
  глоссарий ClickHouse RU, документация Tarantool RU, материалы Хабра (Postgres
  Pro, OTUS, Селектел), HighLoad конференции, методология «Альянса ПРО».
activation:
  - "база данных"
  - "базы данных"
  - "database"
  - "databases"
  - "субд"
  - "dbms"
  - "rdbms"
  - "sql"
  - "nosql"
  - "newsql"
  - "postgresql"
  - "postgres"
  - "mysql"
  - "mariadb"
  - "clickhouse"
  - "tarantool"
  - "тарантул"
  - "oracle"
  - "ms sql"
  - "sql server"
  - "mongodb"
  - "redis"
  - "elasticsearch"
  - "cassandra"
  - "vector database"
  - "репликация"
  - "replication"
  - "шардирование"
  - "sharding"
  - "партиционирование"
  - "partitioning"
  - "транзакция"
  - "transaction"
  - "acid"
  - "mvcc"
  - "wal"
  - "binlog"
  - "gtid"
  - "оптимизатор"
  - "query plan"
  - "execution plan"
  - "index"
  - "индекс"
  - "join"
  - "cte"
  - "innodb"
  - "mergetree"
  - "vshard"
---

# Databases Translation Dictionary

Словарь для переводчиков статей по базам данных. Может активироваться параллельно с другими словарями: например, для статьи про PostgreSQL в Kubernetes — `databases` + `k8s`; для статьи про CI/CD для миграций БД — `databases` + `devops`; для статьи про БД-репликацию через WireGuard — `databases` + `networking`.

**Не догма.** Отражает консенсус русскоязычного DB-сообщества (Postgres Professional, Tarantool, ClickHouse, переводы OTUS/Селектел на Хабре, HighLoad) на 2026 год.

## Принципы

1. **Имена СУБД — оригинал, не склоняются.** PostgreSQL, MySQL, MariaDB, ClickHouse, Tarantool, Redis, MongoDB, Oracle, SQL Server. «В PostgreSQL», не «в Постгресе».
2. **SQL-ключевые слова — оригинал, заглавными (по соглашению).** `SELECT`, `JOIN`, `WHERE`, `GROUP BY`, `INDEX`, `CREATE`, `INSERT`, `UPDATE`, `DELETE`. В тексте — `SELECT`, не «селект» и не «выбрать».
3. **Имена встроенных типов и движков — оригинал.** `InnoDB`, `MergeTree`, `MyISAM`, `TOAST`, `BTREE`, `GIN`, `GiST`, `BRIN`, `JSONB`, `UUID`. Не переводить.
4. **Базовые концепции — переводятся.** «Транзакция», «индекс», «репликация», «шардирование», «партиционирование», «оптимизатор», «план запроса». Это устоявшаяся русская терминология.
5. **Команды CLI — оригинал, строчная буква, не склоняются.** `psql`, `mysql`, `clickhouse-client`, `tarantoolctl`, `pg_dump`, `mysqldump`, `pg_basebackup`. «Запустить `psql`», «через `pg_dump`».
6. **Master/slave устарели — используй primary/replica.** В переводах после 2020 года использовать `primary` / `replica` (или «основной»/«реплика»). Сохранять `master/slave` только если автор оригинала использует их сознательно (старые статьи, исторический контекст).
7. **В одном тексте — один вариант для каждого термина.** Не смешивай «партиция» и «секция», «шард» и «сегмент».

## Раздел 1. Базовые понятия

| English | Русский (рекомендуемый) | Альтернативы | Комментарий |
|---------|-------------------------|--------------|-------------|
| Database (DB) | база данных / БД | — | Склоняется: базы данных, базе данных |
| DBMS (Database Management System) | СУБД | — | «Система управления базами данных» — при первом упоминании |
| RDBMS | реляционная СУБД | — | — |
| Table | таблица | — | «Таблица БД» |
| Row / Record | строка / запись | — | В таблицах — «строка». «Запись» — общий термин |
| Column / Field | колонка / столбец / поле | — | «Колонка», «столбец» — синонимы; «поле» — в контексте записи |
| Schema | схема | — | «Схема БД», «схема данных» |
| Tablespace | tablespace / табличное пространство | — | В PostgreSQL — «табличное пространство», в Oracle — оба варианта |
| View | представление | — | «Материализованное представление» |
| Materialized view | материализованное представление | — | — |
| Stored procedure | хранимая процедура | — | — |
| Function (DB) | функция | — | — |
| Trigger | триггер | — | «Триггер на UPDATE» |
| Constraint | ограничение / constraint | — | «PRIMARY KEY constraint» — «ограничение PRIMARY KEY» |
| Primary key (PK) | первичный ключ / PK | — | «Первичный ключ таблицы» |
| Foreign key (FK) | внешний ключ / FK | — | — |
| Unique key | уникальный ключ | — | — |
| Index | индекс | — | См. отдельный раздел |
| Sequence | последовательность / sequence | — | — |
| Cursor | курсор | — | — |

## Раздел 2. Типы СУБД

| English | Русский | Комментарий |
|---------|---------|-------------|
| Relational database | реляционная БД | — |
| NoSQL | NoSQL | Не переводится |
| NewSQL | NewSQL | — |
| Document database | документоориентированная БД / document store | MongoDB, CouchDB |
| Columnar database | колоночная БД | ClickHouse, Vertica |
| Wide-column store | wide-column store | Cassandra, HBase |
| Key-value store | key-value хранилище / БД ключ-значение | Redis, etcd, DynamoDB |
| Time-series database (TSDB) | time-series БД / БД временных рядов | InfluxDB, TimescaleDB, VictoriaMetrics |
| Graph database | графовая БД | Neo4j, JanusGraph |
| Vector database | векторная БД / vector database | Pinecone, Weaviate, Qdrant, pgvector |
| Object-relational mapping (ORM) | ORM / объектно-реляционное отображение | — |
| OLTP (Online Transaction Processing) | OLTP / транзакционная обработка | — |
| OLAP (Online Analytical Processing) | OLAP / аналитическая обработка | — |
| HTAP (Hybrid Transactional/Analytical Processing) | HTAP | Гибридная СУБД с OLAP+OLTP. Мировые примеры: SAP HANA, SingleStore, TiDB, Oracle Exadata. Российские игроки развиваются недавно (YDB, Tarantool Column Store) |
| Distributed SQL | Distributed SQL / распределённый SQL | Класс нативных HTAP СУБД. Примеры: YDB, CockroachDB, TiDB |
| HTAP platform (in-memory dual-format / engineered system) | HTAP-платформа | Oracle Exadata, SAP HANA — реализация HTAP через единую in-memory платформу |
| HTAP pipeline (OLTP + streaming + ClickHouse) | HTAP-пайплайн | Второй способ реализации гибридности: PostgreSQL + Kafka + ClickHouse |
| Embedded database | встроенная БД | SQLite, RocksDB |
| In-memory database | in-memory БД / БД в памяти | Tarantool, Redis, Memcached |
| Column store / columnar database | колоночная СУБД / колоночное хранилище | ClickHouse, Vertica, Tarantool Column Store, Greenplum |
| Intelligent Observability | Intelligent Observability / интеллектуальная наблюдаемость | Подход к мониторингу высоконагруженных систем: не только метрики, но и автоматическая интерпретация причин проблем в кластере. Направление развития в Tarantool DB |
| Text-to-SQL / Text2SQL | Text-to-SQL / Text2SQL | ИИ-агент, генерирующий SQL-запросы из естественного языка. Кейсы в РФ: X5 Tech, Газпромбанк |
| RAG (Retrieval-Augmented Generation) | RAG / поиск с дополнением генерации | Применение векторных БД для подачи контекста в LLM. Кейсы в РФ: X5 Tech, RUTUBE, Билайн |

## Раздел 3. SQL: DDL/DML/DCL/TCL

| English | Русский | Комментарий |
|---------|---------|-------------|
| DDL (Data Definition Language) | DDL | `CREATE`, `ALTER`, `DROP` |
| DML (Data Manipulation Language) | DML | `INSERT`, `UPDATE`, `DELETE`, `SELECT` |
| DCL (Data Control Language) | DCL | `GRANT`, `REVOKE` |
| TCL (Transaction Control Language) | TCL | `COMMIT`, `ROLLBACK`, `SAVEPOINT` |
| Query | запрос | — |
| Statement | оператор / statement | «SQL-оператор» |
| Clause | предложение / clause | «WHERE clause» — «предложение WHERE» |
| Subquery | подзапрос | — |
| Correlated subquery | коррелированный подзапрос | — |
| CTE (Common Table Expression) | CTE / общее табличное выражение | `WITH` |
| Window function | оконная функция | — |
| Aggregate function | агрегатная функция | `SUM`, `AVG`, `COUNT` |
| JOIN | JOIN | Не переводится. Типы: `INNER`, `LEFT`, `RIGHT`, `FULL`, `CROSS`, `LATERAL` |
| Inner join | inner join / внутреннее соединение | — |
| Outer join | outer join / внешнее соединение | — |
| Cross join | cross join / декартово произведение | — |
| Lateral join | lateral join | — |
| UNION / INTERSECT / EXCEPT | UNION / INTERSECT / EXCEPT | Не переводить |
| GROUP BY | GROUP BY | — |
| HAVING | HAVING | — |
| ORDER BY | ORDER BY | — |
| LIMIT / OFFSET | LIMIT / OFFSET | — |
| DISTINCT | DISTINCT | — |
| Wildcard (`%`, `_`) | wildcard / шаблонный символ | — |
| NULL | NULL | Не переводить. «NULL-значение», «IS NULL» |

## Раздел 4. Транзакции и параллелизм

| English | Русский | Комментарий |
|---------|---------|-------------|
| Transaction | транзакция | Склоняется: транзакции, транзакцию |
| ACID | ACID | Atomicity, Consistency, Isolation, Durability |
| Atomicity | атомарность | — |
| Consistency | согласованность / consistency | В CAP-теореме — «согласованность» |
| Isolation | изоляция | — |
| Durability | устойчивость / durability | — |
| BASE | BASE | Basically Available, Soft state, Eventual consistency |
| Eventual consistency | eventual consistency / итоговая согласованность / итогово-согласованная | — |
| Strong consistency | строгая согласованность | — |
| Linearizability | линеаризуемость | — |
| Serializability | сериализуемость | — |
| Isolation level | уровень изоляции | — |
| READ UNCOMMITTED | READ UNCOMMITTED | — |
| READ COMMITTED | READ COMMITTED | — |
| REPEATABLE READ | REPEATABLE READ | — |
| SERIALIZABLE | SERIALIZABLE | — |
| SNAPSHOT ISOLATION | SNAPSHOT ISOLATION / снапшот-изоляция | — |
| Dirty read | dirty read / грязное чтение | — |
| Non-repeatable read | non-repeatable read / неповторяющееся чтение | — |
| Phantom read | phantom read / фантомное чтение | — |
| Write skew | write skew / асимметрия записи | — |
| MVCC (Multi-Version Concurrency Control) | MVCC / многоверсионный контроль параллелизма | При первом упоминании — расшифровка |
| Snapshot | снимок / snapshot / снапшот | «Снапшот» — устоявшийся вариант |
| Lock | блокировка | «Блокировка строки», «table lock» — «блокировка таблицы» |
| Pessimistic locking | пессимистическая блокировка | — |
| Optimistic locking | оптимистическая блокировка | — |
| Row lock | блокировка строки | — |
| Table lock | блокировка таблицы | — |
| Deadlock | deadlock / взаимная блокировка | «Deadlock» — устоявшийся термин |
| Lock contention | конкуренция за блокировки | — |
| Two-phase commit (2PC) | 2PC / двухфазная фиксация | — |
| Distributed transaction | распределённая транзакция | — |
| Saga pattern | паттерн Saga | — |
| Idempotency | идемпотентность | — |
| Commit | коммит / фиксация | «Сделать коммит транзакции» |
| Rollback | откат / rollback | «Откатить транзакцию» |
| Savepoint | точка сохранения / savepoint | — |

## Раздел 5. Индексы

| English | Русский | Комментарий |
|---------|---------|-------------|
| Index | индекс | — |
| B-tree index | B-tree индекс / B-tree | Не переводить «B-tree» |
| Hash index | hash-индекс / хеш-индекс | — |
| GIN (Generalized Inverted Index) | GIN | PostgreSQL |
| GiST (Generalized Search Tree) | GiST | PostgreSQL |
| BRIN (Block Range Index) | BRIN | PostgreSQL |
| SP-GiST | SP-GiST | PostgreSQL |
| Bitmap index | bitmap-индекс / битовый индекс | — |
| Full-text index | полнотекстовый индекс | — |
| Spatial index | пространственный индекс | — |
| Vector index (HNSW, IVF) | векторный индекс (HNSW, IVF) | pgvector, vector databases |
| Composite index | составной индекс / composite index | — |
| Covering index | покрывающий индекс / covering index | — |
| Partial index | частичный индекс / partial index | — |
| Unique index | уникальный индекс | — |
| Clustered index | кластерный индекс | MySQL InnoDB |
| Non-clustered index | некластерный индекс | — |
| Secondary index | вторичный индекс | — |
| Index scan | сканирование по индексу / index scan | — |
| Index-only scan | index-only scan | — |
| Sequential scan / Full table scan | sequential scan / full table scan / полное сканирование | — |
| Bitmap scan | bitmap scan | — |
| Index bloat | bloat индекса / разбухание индекса | PostgreSQL |
| REINDEX | REINDEX | — |
| Cardinality | кардинальность | «Высокая/низкая кардинальность» |
| Selectivity | селективность | — |

## Раздел 6. Запросы и оптимизатор

| English | Русский | Комментарий |
|---------|---------|-------------|
| Query optimizer | оптимизатор запросов | — |
| Execution plan / Query plan | план выполнения / план запроса | — |
| `EXPLAIN` / `EXPLAIN ANALYZE` | EXPLAIN / EXPLAIN ANALYZE | Не переводить |
| Cost-based optimizer (CBO) | стоимостной оптимизатор / CBO | — |
| Rule-based optimizer (RBO) | оптимизатор на правилах / RBO | — |
| Plan node | узел плана / plan node | — |
| Nested loop join | nested loop join | Не переводить |
| Hash join | hash join | — |
| Merge join | merge join | — |
| Sort | сортировка / sort | — |
| Aggregate | агрегация / aggregate | — |
| Filter | фильтрация / filter | — |
| Projection | проекция | — |
| Statistics | статистика | «Статистика по таблице» |
| Histogram | гистограмма | — |
| `ANALYZE` (collect statistics) | ANALYZE | — |
| Estimated rows / Actual rows | оценочные/фактические строки | В EXPLAIN ANALYZE |
| Buffer pool / Buffer cache | buffer pool / буферный пул | InnoDB, PostgreSQL |
| Shared buffers | shared buffers | PostgreSQL |
| Working memory / `work_mem` | рабочая память / work_mem | PostgreSQL |
| Connection pool / Connection pooler | пул соединений / connection pooler | PgBouncer, ProxySQL |
| Prepared statement | подготовленный запрос / prepared statement | — |
| Stored procedure | хранимая процедура | — |

## Раздел 7. Репликация

| English | Русский | Комментарий |
|---------|---------|-------------|
| Replication | репликация | Склоняется: репликации, репликацию |
| Replica | реплика | — |
| Primary / Master | primary / основной (узел) / master (устар.) | После 2020 — `primary`. `Master` остаётся в старых статьях и в технических полях (`MASTER_USER`) |
| Standby / Replica / Slave | standby / реплика / slave (устар.) | «Реплика» — современный термин |
| Synchronous replication | синхронная репликация | — |
| Asynchronous replication | асинхронная репликация | — |
| Semi-synchronous replication | полусинхронная репликация | MySQL |
| Streaming replication | потоковая репликация | PostgreSQL |
| Logical replication | логическая репликация | PostgreSQL, MySQL |
| Physical replication | физическая репликация | — |
| Statement-based replication (SBR) | SBR / репликация на уровне операторов | MySQL |
| Row-based replication (RBR) | RBR / построчная репликация | MySQL |
| Mixed replication | mixed / смешанная репликация | — |
| Master-Master / Multi-master | master-master / multi-master / мульти-мастер | — |
| Master-Slave | master-slave (устар.) → primary-replica | — |
| Multi-source replication | multi-source репликация / мультиисточниковая репликация | MySQL 5.7+ |
| Failover | failover / переключение на реплику | — |
| Switchover | switchover / плановое переключение | — |
| Failback | failback / возврат | — |
| Replication lag | задержка репликации / replication lag | — |
| Replication slot | слот репликации / replication slot | PostgreSQL |
| Publication / Subscription | публикация / подписка | PostgreSQL логическая репликация |
| Replica identity | репликационный идентификатор / replica identity | PostgreSQL |
| WAL (Write-Ahead Log) | WAL / журнал предзаписи | PostgreSQL |
| Binlog (binary log) | бинарный лог / binlog | MySQL |
| GTID (Global Transaction ID) | GTID | MySQL, MariaDB |
| Redo log | redo log / журнал повтора | InnoDB |
| Undo log | undo log / журнал отмены | InnoDB |
| Hot standby | hot standby / горячий резерв | PostgreSQL |
| Warm standby | warm standby | — |
| Cold standby | cold standby | — |
| Galera Cluster | Galera Cluster | MySQL/MariaDB multi-master |
| Group Replication | Group Replication | MySQL |
| PgPool / Patroni / repmgr | PgPool / Patroni / repmgr | PostgreSQL HA-инструменты |
| Orchestrator | Orchestrator | MySQL HA |
| ProxySQL | ProxySQL | — |

## Раздел 8. Шардирование и партиционирование

| English | Русский | Комментарий |
|---------|---------|-------------|
| Sharding | шардирование / шардинг | «Шардирование» — современный термин, «шардинг» — встречается реже |
| Shard | шард / сегмент | «Шард» — устоявшийся термин, «сегмент» — встречается в ClickHouse |
| Sharding key | ключ шардирования / sharding key | — |
| Hash sharding | хеш-шардирование | — |
| Range sharding | range-шардирование / шардирование по диапазону | — |
| Directory-based sharding | directory-based sharding / каталоговое шардирование | — |
| Geo-sharding | гео-шардирование | — |
| Resharding | решардирование / resharding | — |
| Partitioning | партиционирование / секционирование | «Партиционирование» чаще, «секционирование» — официальная документация PostgreSQL |
| Partition | партиция / секция / partition | В одном тексте — один вариант |
| Range partitioning | range partitioning / по диапазону | — |
| List partitioning | list partitioning / по списку | — |
| Hash partitioning | hash partitioning / по хешу | — |
| Composite partitioning | composite partitioning / составное партиционирование | — |
| Partition pruning | partition pruning / отсечение партиций | — |
| Sub-partition | sub-partition / подсекция | — |
| Distributed database | распределённая БД | — |
| Distributed transaction | распределённая транзакция | — |
| Coordinator / Router | координатор / роутер | В Tarantool VShard — `router` |
| Routing | маршрутизация (запросов) | — |
| Bucket (Tarantool VShard) | bucket / бакет | Виртуальный шард в VShard |
| Replica set | replica set / набор реплик | Tarantool, MongoDB |
| Quorum | кворум | — |
| Consensus (Raft, Paxos) | консенсус (Raft, Paxos) | — |
| Leader election | выборы лидера | Raft |
| Split-brain | split-brain | Не переводить — устоявшийся термин |

## Раздел 9. PostgreSQL-специфика

| English | Русский | Комментарий |
|---------|---------|-------------|
| PostgreSQL / Postgres | PostgreSQL / Postgres | Не «постгрес» в текстах. В разговорной — допустимо |
| pgBouncer / PgBouncer | PgBouncer | — |
| Postgres Pro / Postgres Professional | Postgres Pro / Postgres Professional | Российский форк PostgreSQL |
| WAL (Write-Ahead Log) | WAL / журнал предзаписи | — |
| `wal_level` | wal_level | Параметр |
| Autovacuum | autovacuum / автовакуум | — |
| VACUUM | VACUUM | Не переводить, заглавными |
| VACUUM FULL | VACUUM FULL | — |
| Bloat | bloat / разбухание | «Table bloat», «index bloat» |
| TOAST (The Oversized Attribute Storage Technique) | TOAST | Не переводится |
| FDW (Foreign Data Wrapper) | FDW / обёртка сторонних данных | — |
| Foreign table | внешняя таблица / foreign table | — |
| Tablespace | tablespace / табличное пространство | — |
| Schema (PostgreSQL) | схема | «Схема `public`» |
| `search_path` | search_path | — |
| Extension | расширение / extension | «Расширение `pg_stat_statements`» |
| pg_stat_statements | pg_stat_statements | Не переводить |
| pgvector | pgvector | Векторный индекс |
| PostGIS | PostGIS | Геоданные |
| TimescaleDB | TimescaleDB | Time-series расширение |
| Citus | Citus | Шардирование |
| Patroni | Patroni | HA |
| pg_dump / pg_restore | pg_dump / pg_restore | — |
| pg_basebackup | pg_basebackup | — |
| psql | psql | CLI, не склоняется |
| Logical replication slot | слот логической репликации | — |
| Physical replication slot | слот физической репликации | — |
| Hot standby | hot standby | — |
| Streaming replication | потоковая репликация | — |
| Synchronous commit | синхронный commit / синхронная фиксация | — |
| Parallel query | параллельный запрос | — |
| JIT compilation | JIT-компиляция | — |
| Declarative partitioning | декларативное партиционирование | PostgreSQL 10+ |
| Inheritance | наследование таблиц | Старый способ партиционирования |
| Shardman | Shardman | Postgres Pro |

## Раздел 10. MySQL / MariaDB-специфика

| English | Русский | Комментарий |
|---------|---------|-------------|
| MySQL | MySQL | Не «МайСКЛ» |
| MariaDB | MariaDB | — |
| InnoDB | InnoDB | Не переводить |
| MyISAM | MyISAM | Устаревший движок |
| Memory / HEAP engine | Memory / HEAP | — |
| Archive engine | Archive | — |
| ColumnStore | ColumnStore | MariaDB колоночный движок |
| Aria | Aria | MariaDB engine |
| Storage engine | движок хранения / storage engine | — |
| Binlog (binary log) | binlog / бинарный лог | «Включить binlog» |
| Binlog format (STATEMENT, ROW, MIXED) | формат binlog (STATEMENT, ROW, MIXED) | — |
| Redo log | redo log | InnoDB |
| Undo log | undo log | InnoDB |
| Doublewrite buffer | doublewrite buffer | InnoDB |
| Buffer pool (InnoDB) | buffer pool / буферный пул | — |
| Adaptive hash index (AHI) | AHI / адаптивный хеш-индекс | — |
| Change buffer | change buffer | — |
| GTID (Global Transaction ID) | GTID / глобальный идентификатор транзакции | — |
| Master / Source | master / source | MySQL 8.0+ переходит на `source` |
| Slave / Replica | slave / replica | MySQL 8.0+ — `replica` |
| `mysqldump` | mysqldump | — |
| `mysqlpump` | mysqlpump | — |
| `XtraBackup` / `MariaBackup` | XtraBackup / MariaBackup | Percona и MariaDB |
| Percona Server / Percona XtraDB Cluster (PXC) | Percona Server / PXC | — |
| Galera Cluster | Galera Cluster | Multi-master синхронная репликация |
| Group Replication | Group Replication | MySQL native |
| InnoDB Cluster | InnoDB Cluster | MySQL |
| MySQL Router | MySQL Router | — |
| ProxySQL | ProxySQL | — |
| MHA (Master High Availability) | MHA | — |
| Orchestrator | Orchestrator | — |
| Semi-sync replication | semi-sync репликация | — |
| Parallel replication | параллельная репликация | — |
| Multi-source replication | multi-source репликация | MySQL 5.7+ |
| `mysql` (CLI) | mysql | Не склоняется |
| `mysqlsh` (MySQL Shell) | MySQL Shell / mysqlsh | — |

## Раздел 11. ClickHouse-специфика

| English | Русский | Комментарий |
|---------|---------|-------------|
| ClickHouse | ClickHouse | Не «КликХаус» |
| MergeTree | MergeTree | Не переводится — название движка |
| ReplacingMergeTree, SummingMergeTree, AggregatingMergeTree, CollapsingMergeTree | оригинал | Движки таблиц |
| ReplicatedMergeTree | ReplicatedMergeTree | — |
| Distributed table | распределённая таблица / Distributed | — |
| Materialized view | материализованное представление | — |
| Dictionary (ClickHouse) | словарь | «Внешний словарь», «словарь ClickHouse» |
| Granule | гранула | Минимальная неделимая часть данных (8192 строк по умолчанию) |
| Mark | mark / засечка | Метка в гранулярном индексе |
| Block | блок | Логическая единица обработки колоночных данных |
| Part | парт / part | Партиция на уровне файлов |
| Mutation | мутация | Асинхронное изменение данных |
| Sampling | сэмплирование / выборка | — |
| Sharding key (ClickHouse) | ключ шардирования | — |
| Distributed engine | движок Distributed | — |
| Replica | реплика | — |
| Quorum writes | кворумная запись | — |
| ZooKeeper / ClickHouse Keeper | ZooKeeper / ClickHouse Keeper | Координация репликации |
| TTL (Time-To-Live) | TTL | Не переводится |
| Compression codec (LZ4, ZSTD, Delta, T64) | кодек сжатия (LZ4, ZSTD, Delta, T64) | — |
| Primary key (ClickHouse) | первичный ключ | В ClickHouse — это сортировочный ключ, не uniqueness |
| ORDER BY (table definition) | ORDER BY (в определении таблицы) | Не путать с ORDER BY в запросе |
| `PARTITION BY` | PARTITION BY | — |
| `SAMPLE BY` | SAMPLE BY | — |
| `clickhouse-client` | clickhouse-client | — |
| `clickhouse-server` | clickhouse-server | — |
| `clickhouse-copier` | clickhouse-copier | — |
| Chproxy | Chproxy | Прокси для ClickHouse |
| Vectorized execution | векторизованное выполнение | — |
| LLVM JIT | LLVM JIT | — |

## Раздел 12. Tarantool-специфика

| English | Русский | Комментарий |
|---------|---------|-------------|
| Tarantool | Tarantool | Не «Тарантул» в технических текстах. В разговорной — допустимо |
| Space | space / спейс / спэйс | Аналог таблицы. «Space `users`» |
| Tuple | tuple / кортеж | Аналог строки. «Кортеж» — официальный перевод |
| Index (Tarantool) | индекс | TREE, HASH, RTREE, BITSET |
| Primary index | первичный индекс | — |
| Secondary index | вторичный индекс | — |
| Engine (memtx, vinyl) | движок (memtx, vinyl) | memtx — in-memory, vinyl — LSM-tree |
| memtx | memtx | In-memory движок |
| vinyl | vinyl | On-disk LSM-tree |
| WAL (Tarantool) | WAL / журнал записи | — |
| Snapshot | snapshot / снапшот | — |
| Replication (Tarantool) | репликация | — |
| Replica set | replica set / набор реплик | — |
| Master | master / мастер | Сейчас встречается чаще, чем в MySQL |
| Synchronous replication | синхронная репликация | Tarantool 2.6+ |
| Raft consensus | Raft / консенсус Raft | Tarantool 2.6.1+ |
| Quorum | кворум | — |
| VShard | VShard | Шардирование Tarantool |
| Bucket | bucket / бакет | Виртуальный шард в VShard |
| Bucket ID | ID бакета / bucket id | — |
| Router (VShard) | router / роутер | Перенаправляет запросы по бакетам |
| Storage (VShard) | storage | Узел, хранящий данные |
| Discovery | discovery / обнаружение | — |
| Rebalancer | rebalancer / ребалансировщик | Перераспределяет бакеты |
| `box` module | модуль box / box | — |
| Stored procedure (Tarantool) | хранимая процедура | На Lua |
| Cartridge | Cartridge | Фреймворк для кластеров |
| TDG (Tarantool Data Grid) | TDG | — |
| TQE (Tarantool Queue Enterprise) | TQE | — |
| tarantoolctl | tarantoolctl | CLI |
| Tarantool Column Store | Tarantool Column Store | Колоночное хранилище |

## Раздел 13. NoSQL и распределённые БД

| English | Русский | Комментарий |
|---------|---------|-------------|
| CAP theorem | теорема CAP | Consistency, Availability, Partition tolerance |
| Consistency (CAP) | согласованность | — |
| Availability | доступность | — |
| Partition tolerance | устойчивость к разделению / partition tolerance | — |
| PACELC theorem | теорема PACELC | Расширение CAP |
| Eventual consistency | eventual consistency / итоговая согласованность | — |
| Strong consistency | строгая согласованность | — |
| Read your writes | read-your-writes consistency | — |
| Causal consistency | каузальная согласованность | — |
| Vector clock | векторные часы | — |
| Lamport timestamp | временные метки Лампорта | — |
| Conflict-free Replicated Data Type (CRDT) | CRDT | — |
| Quorum (R+W>N) | кворум (R+W>N) | — |
| Read repair | read repair | Cassandra, ScyllaDB |
| Anti-entropy | anti-entropy | — |
| Gossip protocol | gossip protocol / gossip-протокол | — |
| MongoDB | MongoDB | — |
| Cassandra / ScyllaDB | Cassandra / ScyllaDB | — |
| DynamoDB | DynamoDB | — |
| Redis | Redis | — |
| etcd | etcd | — |
| Consul | Consul | — |
| CockroachDB | CockroachDB | NewSQL |
| YugabyteDB | YugabyteDB | NewSQL |
| TiDB | TiDB | NewSQL |
| Spanner | Spanner | Google |
| Document | документ | MongoDB |
| Collection | коллекция | MongoDB |
| Pipeline (MongoDB aggregation) | конвейер агрегации / aggregation pipeline | — |

## Раздел 14. Бэкап и восстановление

| English | Русский | Комментарий |
|---------|---------|-------------|
| Backup | бэкап / резервная копия | «Бэкап» — устоявшийся термин |
| Full backup | полный бэкап / full backup | — |
| Incremental backup | инкрементальный бэкап | — |
| Differential backup | дифференциальный бэкап | — |
| Continuous backup | непрерывный бэкап | — |
| Logical backup | логический бэкап | `pg_dump`, `mysqldump` |
| Physical backup | физический бэкап | `pg_basebackup`, `XtraBackup` |
| Restore | восстановление / restore | — |
| Recovery | восстановление / recovery | — |
| PITR (Point-In-Time Recovery) | PITR / восстановление на момент времени | — |
| RPO (Recovery Point Objective) | RPO | — |
| RTO (Recovery Time Objective) | RTO | — |
| Hot backup | hot backup / горячий бэкап | — |
| Cold backup | cold backup / холодный бэкап | — |
| Snapshot backup | снапшот-бэкап | — |
| Archive | архив | — |
| WAL archiving | архивация WAL | PostgreSQL |
| `pg_dump`, `pg_restore` | pg_dump, pg_restore | — |
| `mysqldump` | mysqldump | — |
| `XtraBackup` / Percona Backup | XtraBackup / Percona Backup | — |
| `wal-g` / `wal-e` | wal-g / wal-e | — |
| `barman` / `pgbackrest` | barman / pgbackrest | PostgreSQL |
| Replication as backup | репликация как бэкап | Антипаттерн |

## Раздел 15. Инструменты и DBA

| English | Русский | Комментарий |
|---------|---------|-------------|
| DBA (Database Administrator) | DBA / администратор БД | — |
| psql | psql | PostgreSQL CLI |
| mysql (CLI) | mysql | — |
| `clickhouse-client` | clickhouse-client | — |
| tarantoolctl | tarantoolctl | — |
| `redis-cli` | redis-cli | — |
| `mongosh` | mongosh | MongoDB shell |
| pgAdmin | pgAdmin | GUI |
| DBeaver | DBeaver | Универсальный GUI |
| MySQL Workbench | MySQL Workbench | — |
| DataGrip | DataGrip | JetBrains |
| HeidiSQL | HeidiSQL | — |
| Migration tool | инструмент миграций | — |
| Liquibase | Liquibase | — |
| Flyway | Flyway | — |
| Alembic | Alembic | Python (SQLAlchemy) |
| Sqitch | Sqitch | — |
| Connection string | строка подключения / connection string | — |
| DSN (Data Source Name) | DSN | — |
| Driver | драйвер | «JDBC-драйвер», «ODBC-драйвер» |
| JDBC / ODBC | JDBC / ODBC | — |
| ORM | ORM | Sequelize, Hibernate, SQLAlchemy, Django ORM, GORM |
| Object-Relational Mapper | объектно-реляционное отображение | — |
| Migration | миграция | «Миграция БД», «применить миграцию» |
| Up / Down migration | up/down миграция / прямая/обратная миграция | — |
| Schema diff | дифф схемы / schema diff | — |
| Data drift | дрейф данных / data drift | — |

## Раздел 16. Глаголы и действия

| English | Русский | Комментарий |
|---------|---------|-------------|
| to commit | сделать коммит / закоммитить | «Закоммитить транзакцию» |
| to rollback | откатить (транзакцию) | — |
| to query | сделать запрос / выполнить запрос | — |
| to index | индексировать / создать индекс | — |
| to migrate | мигрировать / применить миграцию | — |
| to replicate | реплицировать | — |
| to shard | шардировать | «Шардировать таблицу» |
| to partition | партиционировать / секционировать | — |
| to vacuum | вакуумить (разг.) / запустить VACUUM | PostgreSQL |
| to analyze (statistics) | выполнить ANALYZE / собрать статистику | — |
| to dump | сделать дамп / сдампить | «Сделать дамп БД» |
| to restore | восстановить | — |
| to join (tables) | сджойнить / соединить (таблицы) | — |
| to upsert (insert or update) | сделать upsert | `INSERT ON CONFLICT DO UPDATE` |
| to truncate | очистить таблицу / TRUNCATE | «`TRUNCATE TABLE`» |
| to alter | изменить (через ALTER) / выполнить ALTER | — |
| to lock | заблокировать (строку/таблицу) | — |
| to deadlock | попасть в deadlock | — |
| to optimize (table) | оптимизировать таблицу | MySQL `OPTIMIZE TABLE` |
| to refresh (materialized view) | обновить (мат. представление) | `REFRESH MATERIALIZED VIEW` |
| to backup | сделать бэкап / забэкапить | — |

## Раздел 17. Падежные формы

### PostgreSQL / MySQL / ClickHouse / Tarantool

**Не склоняются.** «В PostgreSQL», «для MySQL», «через ClickHouse», «с Tarantool». НЕ «в Постгресе», «через КликХаус».

В разговорной речи — допустимо «постгрес», «постгреса», но в технических статьях — `PostgreSQL` / `Postgres`.

### Транзакция / Репликация / Партиция / Шард

- **Транзакция** (ж.р.): транзакции, транзакцию, транзакцией. Мн.ч.: транзакции, транзакций
- **Репликация** (ж.р.): репликации, репликацию
- **Партиция / Партиции / Партицию** (ж.р.); **Секция** (ж.р.) — синоним
- **Шард** (м.р.): шарда, шарду, шардом. Мн.ч.: шарды, шардов
- **Реплика** (ж.р.): реплики, реплику. Мн.ч.: реплики, реплик
- **Кластер** (м.р.): кластера, кластеру, кластером

### SQL / WAL / GTID / TTL / OLTP / OLAP / ACID / BASE

**Не склоняются.** «SQL-запрос», «WAL-сегмент», «GTID-режим», «OLAP-нагрузка». В составных словах — через дефис.

### Индекс / Бэкап / Запрос

Склоняются как обычные существительные мужского рода: индекса, индексу, индексом; бэкапа, бэкапу, бэкапом; запроса, запросу, запросом.

### Bloat / Vacuum

- **Bloat** (м.р., не склоняется): «bloat таблицы», «уменьшить bloat». Альтернатива: «разбухание» — склоняется
- **VACUUM**: не склоняется (имя команды): «запустить VACUUM», «после VACUUM». «Вакуум» — разговорная форма, склоняется

### Псqls / mysql / clickhouse-client / pg_dump

**Не склоняются**, всегда строчные. «Через psql», «команда `psql`», но не «psql'ом», не «через psql-у».

### Postgres Pro / Postgres Professional

**Не склоняется как название компании.** «От Postgres Pro», «выпустила Postgres Professional». Без дефиса.

## Раздел 18. Типовые ошибки переводчика

### 1. «База данных» во всех значениях

```
✗ «База данных PostgreSQL получила обновление»
✓ «СУБД PostgreSQL получила обновление»
```

PostgreSQL — это **СУБД** (система), а не **БД** (конкретная база). Аналогично MySQL, ClickHouse, MongoDB — это СУБД. БД (`database`) — это конкретный экземпляр (`CREATE DATABASE mydb`).

### 2. Master/slave в современных статьях

```
✗ «MySQL master-slave репликация» (статья 2026 года)
✓ «MySQL primary-replica репликация» / «репликация primary → replica»
```

Если автор оригинала использует современную терминологию `primary/replica` — сохраняй её. Если в оригинале `master/slave` — допустимо сохранить (исторически).

### 3. Перевод имён СУБД

```
✗ «КликХаус», «Постгрес», «МонгоДБ», «Тарантул»
✓ «ClickHouse», «PostgreSQL», «MongoDB», «Tarantool»
```

В разговорных текстах «постгрес» — допустимо. В технических статьях — оригинал.

### 4. Перевод SQL-ключевых слов

```
✗ «оператор ВЫБРАТЬ», «команда СОЕДИНЕНИЕ»
✓ «оператор SELECT», «команда JOIN»
```

SQL — международный язык, ключевые слова не переводятся.

### 5. «Запись» vs «строка»

```
✗ «Таблица содержит 1 000 записей»
✓ «Таблица содержит 1 000 строк»
```

В контексте таблицы — «строка» (`row`). «Запись» (`record`) — общий термин, чаще встречается в файлах журналов и логах.

### 6. «Колонка» vs «столбец» vs «поле»

Все три используются в русской документации БД. В одном тексте — один вариант:
- «Колонка таблицы» — современный термин, ClickHouse RU использует
- «Столбец таблицы» — официальный перевод Oracle, IBM
- «Поле записи» — старая терминология, в контексте конкретной строки

### 7. «Партиция» vs «секция»

Оба используются:
- «Партиция» — устоявшийся англицизм, чаще встречается
- «Секция» — официальный перевод PostgreSQL RU и стандарта SQL

В одном тексте — один вариант. Если переводишь документацию PostgreSQL — лучше «секция»; если ClickHouse — «партиция»; в общих статьях — на выбор.

### 8. Перевод EXPLAIN-планов

```
✗ «Узел плана Вложенный цикл соединения»
✓ «Узел плана Nested Loop Join»
```

Имена операторов в EXPLAIN-выводе — не переводить, это идентификаторы.

### 9. «Шард» vs «сегмент»

ClickHouse использует «сегмент», другие СУБД — «шард». В одном тексте — один вариант. Если переводишь общую статью про шардирование — «шард» предпочтительнее, как более распространённый.

### 10. Перевод значений ENUM/типов данных

Имена типов данных (`INT`, `VARCHAR`, `TIMESTAMP`, `JSONB`, `UUID`, `Array`, `Tuple`) — **не переводятся**. Это идентификаторы языка SQL и DDL конкретной СУБД.

### 11. «Транзакция БД» при упоминании финансовых транзакций

В контексте БД `transaction` — это атомарная единица работы (BEGIN…COMMIT). Не путать с финансовыми транзакциями (например, в статьях про блокчейн): они тоже называются `transaction`, но контекст другой.

### 12. Калька «производительность работы запроса»

```
✗ «производительность работы запроса увеличилась»
✓ «производительность запроса выросла» / «запрос стал быстрее на X%»
```

«Производительность работы» — двойная калька.

### 13. «Хранится в БД» vs «находится в БД»

Оба верны. «Хранится» — для данных, «находится» — для объектов БД.

```
✓ «Данные хранятся в таблице `users`»
✓ «Триггер находится в схеме `audit`»
```

## Раздел 19. Чек-лист переводчика и источники

### Чек-лист

- [ ] **Имена СУБД** (PostgreSQL, MySQL, MariaDB, ClickHouse, Tarantool, MongoDB, Redis, Oracle, SQL Server) — оригинал, не транслитерированы и не склоняются
- [ ] **SQL-ключевые слова** (`SELECT`, `FROM`, `JOIN`, `GROUP BY`, `INSERT`, `UPDATE`, `WHERE`, `EXPLAIN`) — оригинал, не переведены
- [ ] **Имена встроенных типов и движков** (`InnoDB`, `MergeTree`, `MyISAM`, `TOAST`, `BTREE`, `GIN`, `GiST`, `JSONB`, `UUID`, `memtx`, `vinyl`) — оригинал
- [ ] **Команды CLI** (`psql`, `mysql`, `clickhouse-client`, `tarantoolctl`, `pg_dump`, `mysqldump`, `pg_basebackup`) — оригинал, строчная буква, не склоняются
- [ ] **Master/slave** — заменены на `primary/replica` (если оригинал современный); сохранены, если автор использует их сознательно
- [ ] **«Партиция/секция» и «шард/сегмент»** — в тексте один вариант для каждой пары
- [ ] **«Колонка/столбец/поле»** — в тексте один вариант
- [ ] **СУБД ≠ БД** — система ≠ конкретный экземпляр
- [ ] **Узлы планов EXPLAIN** (Nested Loop, Hash Join, Seq Scan, Index Scan) — оригинал
- [ ] **Имена типов данных** (`INT`, `BIGINT`, `VARCHAR`, `TIMESTAMP`, `Array`, `Tuple`) — оригинал
- [ ] **Калек избегли** — нет «является», «позволяет», «производит»
- [ ] **WAL/GTID/TTL/ACID/MVCC** — не склоняются
- [ ] **Кавычки** — «ёлочки»
- [ ] **Атрибуция оригинала** — в конце есть блок «Оригинал»

### Что делать с новыми терминами

1. **Проверь официальную документацию СУБД на русском:**
   - PostgreSQL: https://postgrespro.ru/docs/postgresql/current/ (русская локализация Postgres Pro)
   - ClickHouse: https://clickhouse.com/docs/ru/concepts/glossary
   - Tarantool: https://www.tarantool.io/ru/doc/latest/
   - MySQL/MariaDB: https://mariadb.com/docs/ (есть русская версия для отдельных страниц)
2. **Проверь публикации на Хабре от первоисточников:** habr.com/ru/companies/postgrespro/, habr.com/ru/companies/clickhouse/, habr.com/ru/companies/vk/ (Tarantool — продукт VK)
3. **Если нигде нет** — оставь в оригинале + `[прим. перев.: устоявшегося перевода нет]`

### Источники

| Источник | Назначение |
|----------|-----------|
| Postgres Professional docs (RU) — https://postgrespro.ru/docs/postgresql/current/ | Эталонная русская локализация PostgreSQL |
| ClickHouse Glossary (RU) — https://clickhouse.com/docs/ru/concepts/glossary | Официальный глоссарий ClickHouse |
| Tarantool docs (RU) — https://www.tarantool.io/ru/doc/latest/ | Документация Tarantool |
| Postgres Pro на Хабре — https://habr.com/ru/companies/postgrespro/ | Глубокие технические статьи по PostgreSQL |
| OTUS на Хабре — https://habr.com/ru/companies/otus/ | Серия статей по СУБД, репликации, миграциям |
| Селектел Blog | Статьи по PostgreSQL, MySQL, ClickHouse в практике облака |
| HighLoad++ — https://highload.ru/ | Доклады по архитектуре высоконагруженных БД |
| Альянс ПРО — https://tran.su/ | Методология для ИТ-переводчиков |
| MariaDB Knowledge Base | Эталонная английская терминология MySQL/MariaDB |
| Oracle Documentation | Эталонная терминология SQL и реляционных БД |

Версия словаря: **2026-05-16 v1.0**.

## Связь с другими словарями

База данных часто встречается в стыке тем — словарь активируется параллельно с другими:

- **БД + K8s** — статья про operator для PostgreSQL (Zalando, CrunchyData), StatefulSet для БД, persistent volumes. Подключаются `databases` + `k8s`.
- **БД + DevOps** — миграции БД в CI/CD pipeline, Terraform для RDS/Cloud SQL, бэкапы через Ansible. Подключаются `databases` + `devops`.
- **БД + Networking** — репликация через VPN/WireGuard, балансировка чтений через ProxySQL/PgBouncer, multi-region кластеры. Подключаются `databases` + `networking`.
- **БД + K8s + DevOps + Networking** — статья «GitOps для multi-region PostgreSQL кластера с Patroni в Kubernetes через WireGuard mesh» — активируются все четыре.

Приоритеты при конфликте — в `references/translation-standards.md`, секция «Приоритеты при множественной активации словарей».
