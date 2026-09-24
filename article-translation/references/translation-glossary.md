# Терминология и словари перевода

Часть стандартов перевода модуля `article-translation-agent` (вынесено из
`translation-standards.md` для читаемости). Whitelist-политика перевода терминов,
приоритеты при множественной активации доменных словарей и доступность словарей
вне модуля. Общий процесс и принципы этапов — в `translation-standards.md`.

## Терминология

### Главное правило: три исхода для термина

**Политика с 2026-07-22** (по разбору редакторских комментариев к переводам для Хабра; прежняя механика «оригинал + описание в скобках» упразднена — скобочные вставки в каждой строке ломают чтение). Каждый термин получает ровно один из трёх исходов:

| Исход | Для каких терминов | Как выглядит в тексте |
|-------|--------------------|------------------------|
| **A. Русское слово или устоявшийся англицизм, инлайн** | **Распространённые** термины: есть в whitelist (активные доменные словари + Общая таблица) или прошли тест распространённости (ниже) | `platform engineering → платформенная инженерия`, `commit → коммит`. Без скобок, без сноски, без оригинала рядом |
| **B. Оригинал, чистый** | Имена продуктов / компаний / проектов, общеизвестные аббревиатуры | `Kubernetes`, `API`, `PostgreSQL` |
| **C. Термин + сноска-определение при первом упоминании** | **Узкоспециализированные** термины и малоизвестные продукты, без понимания которых читатель теряет нить | `Crossplane[^5]`, `эталонный путь (golden path)[^6]` + определение в сноске с пометкой «Прим. перев.» |

Исходы A и B решают, **как термин пишется**; исход C — надстройка «нужно ли пояснение» и совместим с обоими: сноску может получить и оригинал (`Crossplane[^5]`), и русский термин.

Whitelist по-прежнему защищает от калек и «отсебятины»: **самостоятельно придумывать русский перевод запрещено**. Русское слово инлайн берётся из словаря/Общей таблицы либо фиксируется терминологическим брифингом по проверяемым сигналам (тест распространённости) — не по ощущению переводчика.

### Пояснения — только сноской, не в скобках

- Определения и пояснения терминов живут **только в сносках** `[^N]` (формат ниже). В прозе перевода скобки допустимы ровно в двух случаях:
  1. **введение аббревиатуры**, которая дальше используется в тексте: «пользовательские определения ресурсов (CRD)»;
  2. **расшифровка аббревиатуры** при первом упоминании: «mTLS (mutual TLS)» — только расшифровка, без определения; определение, если нужно, идёт сноской.
- ❌ **Запрещён «обратный перевод» в скобках** — оригинал после уже переведённого термина: «платформенная инженерия (platform engineering)», «композиции (compositions)». Если термин переведён по политике, оригинал рядом не нужен; когда оригинал важен читателю (термин для самостоятельного гугления) — укажи его в сноске: `[^N]: Golden path (эталонный путь) — …`.
- ❌ **Запрещено описание в скобках**: «provisioning (подготовка)», «Kubernetes-native операторы (нативные для Kubernetes)». Для распространённого термина — просто русское слово; для узкого — сноска.

### Тест распространённости (как надёжно отличить A от C)

Лестница проверок; каждый шаг опирается на проверяемый факт, а не на ощущение:

1. **Словарный тест.** Термин в whitelist (активные доменные словари или Общая таблица)? → **распространённый**: используй указанный там русский вариант/англицизм, без сноски. Словарь — граница по построению: попадание в словарь означает, что вариант принят русскоязычным сообществом.
2. **Тест имени собственного.** Продукт / компания / проект (с заглавной буквы)? → оригинал (исход B). Сноска — только если верно **оба**: (а) продукт малоизвестен русскоязычному читателю — нет статьи в русской Википедии, на Хабре единичные упоминания; (б) на нём держится смысл статьи — встречается ≥ 3 раз или вынесен в заголовок/лид.
3. **Тест аудитории** (для остальных терминов). Термин **распространённый**, если верно **≥ 2 из 3** проверяемых сигналов:
   - есть статья в русской Википедии или страница в русскоязычной официальной документации (термин или его русский перевод);
   - на Хабре термин употребляется в заголовках/тексте **без пояснения** (проверка `site:habr.com`) — аудитория его знает;
   - русский перевод регулярно встречается в Tier 1-2 русскоязычных источниках (официальная документация, крупные сообщества), а не в единичных блогах.

   ≥ 2 сигналов → исход A (русское слово или устоявшийся англицизм, без сноски). < 2 → **узкоспециализированный** → исход C (сноска при первом упоминании).
4. **Правило сомнения.** Сигналы проверить нечем (нет ресёрчера, нет поиска) → считай термин узким и ставь сноску. Лишняя сноска дешевле непонятного термина, и редактору её легко снять; «голый» узкий термин без пояснения ловится только человеком.

**Кто применяет лестницу.** При ≥ 10 неизвестных терминов сигналы шага 3 проверяет `terminology-researcher` (`web_search`) и фиксирует вердикт в брифинге — колонки `familiarity` (common / narrow) и `handling` (translate / original / footnote). Без ресёрчера переводчик применяет шаги 1-2 по словарям, а для шага 3 действует правило сомнения.

### Формат сноски переводчика

- Сноска ставится **только при первом упоминании** термина. Повторы — чистый термин, без сноски и скобок.
- Текст сноски: 1-2 предложения (5-25 слов) — что это и зачем; для аббревиатуры — сначала расшифровка; можно указать оригинал термина, если инлайн стоит русский вариант. В конце — пометка `— Прим. перев.` (отделяет от авторских сносок).
- **Нумерация продолжает авторские сноски** оригинала: если в оригинале `[^1]`-`[^4]`, сноски переводчика начинаются с `[^5]`.
- Где сноску НЕ ставить: заголовки H1-H3 (ставь на первое упоминание в тексте под заголовком), код, ссылки, URL, alt-тексты картинок.
- Сноски переводчика — **единственное санкционированное добавление** к структуре оригинала; контракт и счётчики проверяльщика — `translation-standards.md`, раздел «Сноски переводчика».

### Консистентность первого упоминания

Пояснение живёт на **первом** упоминании термина — не на втором и не «где удобнее». Рецидив из разбора 2026-07-22: golden path в подписи к картинке остался без пояснения, а через три раздела получил и перевод, и раскрытие. Правило: при первом упоминании — русский вариант/сноска по политике; все дальнейшие упоминания — тот же вариант написания, без повторных пояснений. Проверяльщик сверяет это отдельным проходом.

### Примеры формата

```
✓ Хорошо
«Организации продвинулись в платформенной инженерии и внедрении Kubernetes,
но выдача баз данных по запросу остаётся фрагментированной.»
   ← распространённые термины: русское слово сразу, без оригинала в скобках

«С помощью композиций Crossplane[^5] платформенные команды создают абстракции…»
[^5]: Crossplane — open source-фреймворк для управления облачной
      инфраструктурой через Kubernetes API. — Прим. перев.
   ← малоизвестный продукт, важный для статьи: оригинал + сноска при первом упоминании

«Мы внедрили eBPF[^6] для мониторинга системных вызовов. eBPF даёт…»
[^6]: eBPF (Extended Berkeley Packet Filter) — технология выполнения программ
      внутри ядра Linux без изменения его кода. — Прим. перев.
   ← узкий термин: сноска на первом упоминании, повтор — чистый

«Sidecar-контейнер обрабатывает аутентификацию.»
   ← sidecar в k8s-словаре (whitelist) — переводится по словарю, пояснение не нужно

✗ Плохо
«…продвинулись в platform engineering (платформенной инженерии)…»
   ← распространённый термин спрятан за оригиналом; русский вариант должен идти инлайн
«…с помощью композиций (compositions) Crossplane…»
   ← обратный перевод: оригинал в скобках после русского слова
«backpressure (механизм обратного давления, тормозит источник при перегрузке)»
   ← описание в скобках; должно быть сноской: backpressure[^N]
«Backpressure» без сноски при первом упоминании  ← читатель не знает термин
«Обратное давление» как самостоятельный термин   ← перевода нет в whitelist — отсебятина
Сноска при каждом упоминании термина             ← только при первом
```

### Когда whitelist «выигрывает»

Если термин в активном доменном словаре (или в Общей таблице) — **переводится** строго на тот вариант, который указан в словаре. Сноска с определением **не добавляется** (раз слово в whitelist — оно распространённое по определению, пояснение избыточно).

Исключение: если термин в whitelist, но в данном контексте используется в специфическом значении, отличающемся от обычного — переводчик оставляет оригинал и ставит сноску переводчика с пояснением значения (`translation-standards.md` → «Пояснения переводчика — только сноской»; инлайн-заметки `[прим. перев.: …]` упразднены).

### Доменные словари

Для часто встречающихся технических тем есть отдельные словари терминов («translation» (внутренний материал системы, в эту выгрузку не входит)). Стадии перевода получают их **по теме**: словарь инлайнится, только если его триггеры `activation:` сработали на тексте («skill_activation» (внутренняя автопроверка репозитория, в чате недоступна — проверь этот пункт вручную): границы слов, вес заголовка ×3, порог 3 очка, не более 4 словарей; остальные — манифестом + `read_skill`). Таблица ниже генерируется из frontmatter словарей:

| Skill | Триггеры активации | Что внутри |
|-------|---------------------|-----------|
| `backend-translation-dictionary` | backend, бэкенд, back-end, backend development, серверная разработка, api design, rest api design, restful, openapi, swagger, microservices, микросервисы, monolith, монолит, message queue, очередь сообщений, message broker, брокер сообщений, rabbitmq, nats, event-driven, событийная архитектура, event sourcing, cqrs, saga, ddd, domain-driven design, hexagonal architecture, clean architecture, orm, idempotency, идемпотентность, circuit breaker, connection pool, пул соединений, background job, фоновые задачи, go, golang, goroutine, горутина, java, spring boot, python, django, fastapi, node.js, nodejs, nestjs, rust, .net, asp.net, ruby on rails, rails, php, laravel, dead letter queue, outbox, graceful shutdown, health check | 217 терминов; разделы: Базовые понятия и архитектура сервисов, Слои приложения и паттерны, DDD и архитектурные стили, API-дизайн и сериализация, Обмен сообщениями, Событийная архитектура: event sourcing, CQRS, саги, Устойчивость, Конкурентность, процессы и ошибки… |
| `cloud-iaas-translation-dictionary` | cloud computing, облачные вычисления, iaas, paas, saas, faas, serverless, бессерверный, virtual machine, виртуальная машина, vm, hypervisor, гипервизор, kvm, openstack, nova, cinder, glance, keystone, object storage, объектное хранилище, s3, block storage, блочное хранилище, availability zone, зона доступности, region, регион, cloud provider, облачный провайдер, private cloud, частное облако, public cloud, публичное облако, hybrid cloud, гибридное облако, multi-cloud, мультиоблако, instance, инстанс, flavor, quota, квота, tenant, тенант, project, marketplace, autoscaling, автомасштабирование, spot instance, reserved instance, pay-as-you-go, finops, cloud migration, миграция в облако, shared responsibility, managed service | 191 терминов; разделы: Модели обслуживания и типы облаков, Виртуальные машины и гипервизоры, Образы, снапшоты и резервные копии, Хранилища: блочные, объектные, файловые, Регионы, зоны доступности и отказоустойчивость, Аккаунты, проекты, квоты и лимиты, Тарификация и модели оплаты, FinOps и управление затратами… |
| `data-engineering-translation-dictionary` | data engineering, инженерия данных, дата-инжиниринг, etl, elt, data pipeline, data lake, озеро данных, data warehouse, хранилище данных, dwh, lakehouse, apache spark, spark, pyspark, apache kafka, kafka, apache airflow, airflow, dbt, apache flink, flink, apache iceberg, iceberg, delta lake, hudi, parquet, avro, arrow, hadoop, hdfs, hive, trino, presto, data mesh, data catalog, каталог данных, data quality, качество данных, data lineage, cdc, change data capture, stream processing, потоковая обработка, batch processing, пакетная обработка, data governance, dag, backfill, medallion, data contract | 217 терминов; разделы: Базовые понятия и роли, Архитектуры хранения, Конвейеры и оркестрация, Пакетная и потоковая обработка, Kafka, брокеры сообщений и CDC, Форматы файлов и хранения, Табличные форматы, Hadoop и SQL-движки… |
| `databases-translation-dictionary` | база данных, базы данных, database, databases, субд, dbms, rdbms, sql, nosql, newsql, postgresql, postgres, mysql, mariadb, clickhouse, tarantool, oracle, ms sql, sql server, mongodb, redis, elasticsearch, cassandra, vector database, репликация, replication, шардирование, sharding, партиционирование, partitioning, транзакция, transaction, acid, mvcc, wal, binlog, gtid, оптимизатор, query plan, execution plan, index, индекс, join, cte, innodb, mergetree | 412 терминов; разделы: Базовые понятия, Типы СУБД, SQL: DDL/DML/DCL/TCL, Транзакции и параллелизм, Индексы, Запросы и оптимизатор, Репликация, Шардирование и партиционирование… |
| `devops-translation-dictionary` | devops, ci/cd, continuous integration, continuous delivery, continuous deployment, terraform, ansible, infrastructure as code, iac, gitops, github actions, gitlab ci, jenkins, argocd, argo cd, flux, pipeline, sre, docker, docker compose, dockerfile, vault, nomad, backstage, semver | 322 терминов; разделы: Базовые понятия DevOps, CI/CD pipeline — компоненты, Git и VCS, Стратегии развёртывания, Окружения, Infrastructure as Code — общие понятия, Terraform, Ansible… |
| `frontend-translation-dictionary` | frontend, фронтенд, front-end, html, css, javascript, js, typescript, ts, react, реакт, vue, vue.js, angular, svelte, solid, solidjs, next.js, nextjs, nuxt, remix, astro, qwik, vite, webpack, esbuild, rollup, turbopack, rspack, tailwind, css-in-js, redux, mobx, zustand, pinia, vuex, react query, tanstack, rtk, ssr, ssg, isr, csr, hydration, spa, mpa, pwa, web components, shadow dom, service worker, indexeddb, webassembly, wasm, webgl, webgpu, graphql, rest api, dom, virtual dom, jsx, tsx, хук, hook, useeffect, usestate, композиция, props, пропсы, роутинг, react router, vue router, accessibility, a11y, performance, lighthouse, core web vitals, lcp, fid, cls, inp, ttfb | 423 терминов; разделы: Базовые понятия веба, HTML, CSS, JavaScript / TypeScript, React, Vue, Angular, Svelte, Solid и другие, Метафреймворки (Next.js, Nuxt, Remix)… |
| `k8s-translation-dictionary` | kubernetes, k8s, kubectl, pod, deployment, helm, cluster, container orchestration, istio, ingress, cni, operator, openshift, kubelet | 197 терминов; разделы: Базовые объекты Kubernetes API, Workloads и контроллеры, Сеть, Хранилище, Конфигурация и переменные, Безопасность и доступ, Управляющий слой (Control Plane), CLI и инструменты… |
| `linux-storage-translation-dictionary` | linux, линукс, kernel, ядро linux, systemd, journald, bash, shell, ext4, xfs, btrfs, zfs, lvm, raid, nvme, ssd, hdd, iops, block device, блочное устройство, filesystem, файловая система, mount, монтирование, inode, ceph, glusterfs, minio, nfs, iscsi, san, nas, fibre channel, схд, storage system, система хранения данных, disk, диск, cgroups, ebpf, io_uring, page cache, swap, oom killer, selinux, apparmor, luks, dm-crypt, udev, tmpfs, overlayfs, backup, резервное копирование, rpo, rto, strace, perf, fio, iostat, huge pages, multipath, device mapper | 217 терминов; разделы: Ядро и пространство пользователя, Процессы, потоки, сигналы, планировщик, Память, cgroups, пространства имён, изоляция, systemd, загрузка, журналы, устройства, Дистрибутивы, пакеты, shell, права, Файловые системы, Блочный уровень: разделы, LVM, RAID, device mapper… |
| `ml-ai-translation-dictionary` | ml, machine learning, машинное обучение, ии, ai, искусственный интеллект, llm, large language model, большая языковая модель, gpt, claude, gemini, anthropic, openai, deep learning, глубокое обучение, нейросеть, neural network, transformer, embeddings, эмбеддинги, fine-tuning, файнтюнинг, дообучение, rag, retrieval, retrieval augmented generation, prompt engineering, промпт, промпт-инжиниринг, tokenization, токенизация, attention, self-attention, rlhf, lora, qlora, peft, hugging face, huggingface, pytorch, tensorflow, langchain, llamaindex, mlops, model serving, inference, инференс, ai agent, ai-агент, mcp, model context protocol, diffusion, diffusion model, stable diffusion, midjourney, gan, cuda | 445 терминов; разделы: Базовые понятия, Архитектуры моделей, LLM-специфика, Токенизация и эмбеддинги, Обучение моделей, RAG (Retrieval-Augmented Generation), AI-агенты и оркестрация, Prompt Engineering… |
| `mobile-translation-dictionary` | mobile, мобильный, мобильная разработка, mobile development, ios, android, swift, swiftui, uikit, objective-c, objc, kotlin, котлин, android java, jetpack compose, compose, android sdk, xcode, android studio, app store, google play, play market, play console, appstore connect, testflight, react native, flutter, dart, kotlin multiplatform, kmp, kmm, expo, xamarin, ionic, cordova, capacitor, nativescript, activity, fragment, viewcontroller, view controller, intent, broadcast receiver, content provider, android service, push notifications, пуш-уведомления, apns, fcm, deeplink, deep link, universal links, app links, in-app purchase, iap, subscriptions, biometric, face id, touch id, keychain, keystore, mdm, mobile device management, rustore, rumarket, huawei appgallery | 414 терминов; разделы: Базовые понятия мобильной разработки, iOS / Apple платформы, Swift / SwiftUI / UIKit, iOS-фреймворки, Android, Kotlin / Jetpack Compose / Android SDK, Кросс-платформенные фреймворки, Push, deeplinks, IAP… |
| `networking-translation-dictionary` | сети, networking, network, tcp/ip, tcp ip, bgp, ospf, vxlan, vpn, vpc, subnet, nat, dns, cdn, load balancer, балансировщик, firewall, файрвол, waf, ids, ips, ddos, sase, sse, sd-wan, zero trust, ztna, tls, ssl, quic, http/3, http/2, websocket, grpc, ipv4, ipv6, vlan, stp, mpls, ipsec, wireguard, anycast, router, роутер, маршрутизатор | 418 терминов; разделы: Базовые понятия и модели, Сетевое оборудование, Адресация, Транспортный и сетевой уровни, Маршрутизация, Коммутация и L2, Туннели, Overlay, Underlay, DNS… |
| `observability-translation-dictionary` | observability, наблюдаемость, monitoring, мониторинг, prometheus, promql, grafana, opentelemetry, otel, tracing, трейсинг, distributed tracing, распределённая трассировка, jaeger, tempo, loki, mimir, thanos, victoriametrics, metrics, метрики, logs, логи, logging, логирование, alerting, алертинг, alertmanager, slo, sli, error budget, бюджет ошибок, dashboard, дашборд, apm, profiling, профилирование, continuous profiling, pyroscope, flame graph, opensearch, kibana, fluentd, fluent bit, on-call, дежурство, postmortem, постмортем, incident management, burn rate, golden signals, synthetic monitoring, rum | 199 терминов; разделы: Три столпа и базовые понятия, Метрики: типы, временные ряды, агрегация, Prometheus и хранилища метрик, OpenTelemetry, Распределённая трассировка, Логирование, Алертинг и уведомления, SLO, SLI, SLA и бюджет ошибок… |
| `security-translation-dictionary` | security, ib, иб, информационная безопасность, кибербезопасность, cybersecurity, infosec, appsec, devsecops, уязвимость, vulnerability, cve, cwe, cvss, owasp, mitre att&ck, attack, атака, exploit, эксплойт, phishing, фишинг, malware, вредоносное по, ransomware, вымогатель, sql injection, xss, csrf, rce, threat model, threat modeling, моделирование угроз, stride, kill chain, rbac, iam, oauth, oidc, saml, jwt, mfa, sso, encryption, шифрование, криптография, cryptography, pki, sast, dast, sca, siem, soc, soar, edr, xdr, mdr, ndr, sbom, slsa, sigstore, incident response, 152-фз, фстэк, фсб, кии, госсопка, gdpr, pci dss, hipaa, iso 27001, soc 2 | 449 терминов; разделы: Базовые понятия, CIA triad и принципы, Типы атак, Уязвимости и каталоги, Threat Modeling, Криптография, IAM (Identity & Access Management), Application Security (AppSec) и DevSecOps… |

<!-- таблица выше генерируется: python3 «check_translation_dictionaries» (внутренняя автопроверка репозитория, в чате недоступна — проверь этот пункт вручную) --glossary-table; гейт make dictionaries сверяет её с frontmatter словарей -->

## Приоритеты при множественной активации словарей

Несколько словарей могут активироваться одновременно. Типовые сценарии пересечений:

| Статья про… | Активируется | Кто главный при конфликте |
|-------------|--------------|---------------------------|
| GitOps в Kubernetes | k8s + devops | Зависит от того, что является темой: если архитектура K8s — k8s; если процесс GitOps-деплоя — devops |
| CNI (Calico, Cilium), Service Mesh (Istio) | k8s + networking | k8s (это K8s-сетевая подсистема, термины Service/Ingress/NetworkPolicy — K8s API) |
| Cloud networking в Terraform (VPC, subnet, NAT) | devops + networking | networking (это сетевые понятия, в terraform-коде они остаются как есть — `aws_vpc`, `aws_subnet`) |
| Multi-cluster K8s с Cilium через BGP | k8s + devops + networking | Все три одновременно. При конфликте — выбирать словарь, который содержит **более специфический** перевод термина |
| PostgreSQL operator в Kubernetes (Zalando, CrunchyData) | databases + k8s | databases для терминов БД (replication, WAL, primary), k8s для K8s-объектов (StatefulSet, PV, Operator). Не конфликтуют |
| Миграции БД в CI/CD pipeline | databases + devops | databases для терминов миграций (schema diff, Liquibase, Flyway), devops для CI/CD (pipeline, runner). Не конфликтуют |
| ClickHouse-кластер с репликацией через VPN | databases + networking | databases для ReplicatedMergeTree/ZooKeeper, networking для VPN/IPSec. Не конфликтуют |
| Multi-region PostgreSQL с Patroni в K8s через WireGuard | databases + k8s + devops + networking | Все четыре одновременно. Согласованность важнее идеального выбора — оркестратор фиксирует основной словарь и применяет до конца статьи |
| MLOps для LLM-инференса на Kubernetes | ml-ai + k8s + devops | ml-ai для LLM/inference, k8s для StatefulSet/GPU-нод, devops для CI/CD |
| Векторная БД для RAG (Qdrant, pgvector) | ml-ai + databases | ml-ai для RAG/embedding/vector index, databases для самой БД |
| Prompt injection и AI red teaming | ml-ai + security | Оба обязательны: ml-ai для LLM-терминов, security для атак |
| DevSecOps с SAST/DAST в CI/CD | security + devops | security для SAST/DAST/SCA/SBOM, devops для CI/CD-pipeline |
| Pod Security Standards и Falco в K8s | security + k8s | security для runtime-защиты, k8s для Pod/admission |
| Zero Trust сеть с SASE | security + networking | security для Zero Trust/ZTNA, networking для SASE/SD-WAN/firewall |
| Шифрование данных в PostgreSQL по 152-ФЗ | security + databases | security для криптографии и регуляторики, databases для PostgreSQL |
| Всеохватывающая статья «DevSecOps-платформа для AI-моделей на K8s с PostgreSQL через Zero Trust» | все 6 словарей | Согласованность важнее идеального выбора — оркестратор показывает пользователю и фиксирует основной |

### Правила приоритизации

1. **Совпадающие термины в двух словарях** — приоритет за словарём с **более конкретным** контекстом. Например, термин `Service` в K8s-словаре = «Service (имя ресурса API)», в сетевом — нет такого, поэтому в K8s-статье побеждает K8s-словарь.
2. **Конфликт переводов** — приоритет за словарём, имеющим **больше триггеров** в заголовке/первых абзацах статьи. Если в статье 5 упоминаний Kubernetes и 1 упоминание BGP — побеждает k8s.
3. **Согласованность важнее идеального выбора** — если по терминам словари разошлись, оркестратор фиксирует выбор в начале и применяет один словарь как основной до конца статьи. Не переключайся в середине текста.
4. **Имена ресурсов API всегда из своего словаря** — `Pod`, `Deployment`, `Service` пишутся как в Kubernetes API независимо от темы статьи. `resource "aws_vpc"` — как в Terraform HCL независимо от темы.

### Подключённые словари в сводке

На шаге подтверждения оркестратор показывает строку `| Активные словари | k8s-translation-dictionary, networking-translation-dictionary |` (список — из «skill_activation» (внутренний материал системы, в эту выгрузку не входит)). Пользователь может уточнить: «исключи сетевой» или «добавь devops» — оркестратор правит список руками и прикладывает словари в промты стадий сам.

## Доступность словарей вне модуля перевода

Словари лежат в «translation» (внутренний материал системы, в эту выгрузку не входит) (source of truth), симлинки — в «skills» (внутренний материал системы, в эту выгрузку не входит); ими пользуются и другие агенты (seo-writer, docs-article-writer, media-content-writer, content-editor) для унификации терминологии. Как подключить словарь к субагенту и кто уже подключён — «README» (внутренний материал системы, в эту выгрузку не входит) (в правило это не входит: стадиям перевода оркестраторская инструкция не нужна).

Если темы нет в словарях — действуй по Общей таблице ниже + тесту распространённости для всего остального (распространённое — русское слово/англицизм инлайн, узкое — оригинал + сноска при первом упоминании).

### Общая таблица терминов (whitelist принятых переводов)

Эта таблица — часть whitelist'а наравне с доменными словарями и **канон при конфликте** (решение владельца 2026-09-17): при расхождении словаря с этой таблицей выигрывает таблица, при расхождении двух словарей — словарь домена, которому термин принадлежит; гейт внутренний гейт репозитория (в чате недоступен) (`check_translation_dictionaries.py`, сигналы `canon_conflict` / `cross_conflict`) не пропускает новых расхождений. Класс 1 «english-terms» (внутренний материал системы, в эту выгрузку не входит) («русский аналог существует и привычен») входит в канон целиком.

**Принцип: русское слово по умолчанию.** Устоявшийся англицизм инлайн («нода», «деплой», «под», «коммит», «пулреквест») — только если словарь явно помечает его как узус техтекста; в клиентских текстах (`english-terms.md` → «Приоритет») — русское слово всегда.

| Английский | Русский (whitelist) | Примечание |
|------------|---------------------|------------|
| cloud | облако | в названиях продуктов сохраняй оригинал: VK Cloud, Google Cloud |
| container | контейнер | — |
| cluster | кластер | — |
| node | узел | в техтексте (Хабр, документация) допустима «нода» — по k8s-словарю; в клиентских текстах — «узел» |
| pod (k8s) | под | как имя ресурса API — `Pod`; в нарративе — «под» (склоняется: пода, поду); один вариант на текст |
| deployment (действие) | развёртывание | `english-terms` класс 1; «деплой» — разг. англицизм техтекста; объект Kubernetes — `Deployment` (оригинал) |
| pipeline | конвейер | одиночный термин — «конвейер»; оригинал `pipeline` допустим как имя сущности CI (GitLab pipeline); «пайплайн» — только в составных (CI/CD-пайплайн, ETL-пайплайн); приоритет — `devops-translation-dictionary` |
| repository | репозиторий | — |
| commit | коммит | глагол — «закоммитить» (техтекст) / «зафиксировать» (транзакция в БД) |
| pull request | пулреквест | при повторах — PR; на GitLab — merge request / MR |
| machine learning | машинное обучение | ML при повторе |
| dataset | датасет | «набор данных» — только если в исходнике делается акцент |
| backend / frontend | бэкенд / фронтенд | — |
| throughput | пропускная способность | — |
| latency | задержка | `english-terms` класс 1; «латентность» — не использовать |
| observability | наблюдаемость | `english-terms` класс 1; `observability` — допустимый англицизм в техтексте, но один вариант на текст |
| failover | аварийное переключение | для БД — «переключение на реплику» как пояснение в комментарии словаря, не как второй термин |
| throttling / rate limiting | ограничение частоты запросов | «троттлинг» — только как термин ядра/оборудования; «ограничение скорости» — не использовать |
| performance | производительность | — |
| scalability | масштабируемость | — |
| registry | реестр | container registry → «реестр образов»; `registry` — только в именах (Docker Registry) |
| rollback | откат | глагол — «откатить» |
| lifecycle | жизненный цикл | — |
| unit test | юнит-тест | не «unit-тест»; «модульный тест» — в академическом регистре |
| canary deployment | канареечное развёртывание | не «canary-деплой», не «канареечная выкатка» |
| eventual consistency | согласованность в конечном счёте | не «итоговая согласованность», не «возможная согласованность» |
| provisioning | выделение ресурсов | глагол — «выделить ресурсы» / «подготовить»; «провижининг» — не использовать; provisioning profile (iOS) — оригинал |
| lock | блокировка | lock-файл — «lock-файл» |
| orchestrator | оркестратор | — |
| honeypot | ханипот | устоявшийся англицизм ИБ-сообщества; «приманка» — пояснение |
| streaming | стриминг | потоковый вывод LLM, потоковая передача — по контексту, но один вариант на текст |

**Термины, которые остаются в оригинале** — имена ресурсов API, продуктов и термины без принятого русского варианта. Нужна ли сноска — решает тест распространённости: для профильной аудитории Хабра большинство из них — знакомые англицизмы (сноска не нужна), для широкой аудитории — узкие (сноска при первом упоминании):

| Английский | Действие | Пример текста сноски (если термин узкий для целевой аудитории) |
|------------|----------|----------------------------------------------------------------|
| Deployment / Service / Ingress / StatefulSet (k8s) | оригинал как имя ресурса API, с заглавной, не склоняется | «Deployment — объект Kubernetes для управления версионированным развёртыванием. — Прим. перев.» |
| workflow | оригинал «workflow» | «Workflow — процесс автоматизации, например в GitHub Actions. — Прим. перев.» |
| feature flag | оригинал «feature flag» | «Feature flag — флаг для управляемого включения функциональности на части пользователей. — Прим. перев.» |
| admission controller (k8s) | оригинал «admission controller» | «Admission controller — компонент Kubernetes, проверяющий и изменяющий запросы к API до записи объекта. — Прим. перев.» |
| open source | «open source» строчными в составных («open source-фреймворк», «open source-проект»); как понятие/движение — Open Source (`brand-terminology`) | обычно не нужна (распространённый англицизм) |
| backpressure | оригинал «backpressure» | «Backpressure — механизм обратного давления: источник данных замедляется, если потребитель не успевает. — Прим. перев.» |

Термин из второй таблицы **переводится только тогда**, когда явно указан как whitelist в доменном словаре (например, `pod` в нарративе — «под» по k8s-словарю).

### Падежи и склонения иностранных слов

- Kubernetes — несклоняемое.
- Docker — несклоняемое.
- API → API (несклоняемое), API-вызов, API-эндпоинт.
- pod → под (склоняется): пода, поду, подом.
- Если устоявшегося склонения нет — оставлять оригинал в im. п. с дефисом: `Cilium-кластер`, `eBPF-программа`.

### Глаголы

| Английский паттерн | Русский паттерн |
|---------------------|-----------------|
| The system processes... | Система обрабатывает... |
| You can configure... | Можно настроить... / Настройте... (в инструкциях) |
| It is recommended to... | Рекомендуется... / Лучше... |
| Note that... | Обратите внимание: ... |
| Let's look at... | Рассмотрим... |

Активный залог предпочтительнее пассивного. На этапе перевода — сохраняй залог автора. На этапе редактуры — конвертируй пассив в актив, где уместно.
