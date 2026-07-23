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

**Кто применяет лестницу.** При ≥ 10 неизвестных терминов сигналы шага 3 проверяет `terminology-researcher` (WebSearch) и фиксирует вердикт в брифинге — колонки `familiarity` (common / narrow) и `handling` (translate / original / footnote). Без ресёрчера переводчик применяет шаги 1-2 по словарям, а для шага 3 действует правило сомнения.

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

Исключение: если термин в whitelist, но в данном контексте используется в специфическом значении, отличающемся от обычного — переводчик может оставить оригинал и пометить `[прим. перев.: ...]`.

### Доменные словари

Для часто встречающихся технических тем у нас есть отдельные словари терминов (skills модуля `article-translation-agent`). Подключаются автоматически по триггерам:

| Skill | Триггеры активации | Что внутри |
|-------|---------------------|-----------|
| `k8s-translation-dictionary` | kubernetes, k8s, kubectl, pod, deployment, helm, cluster, container orchestration | 19 разделов: имена ресурсов API (Pod, Deployment, Service), сеть, хранилище, безопасность, CLI, расширения, планирование, масштабирование, наблюдаемость, Cloud Native, глаголы, падежные формы, типовые ошибки, чек-лист |
| `devops-translation-dictionary` | devops, ci/cd, continuous integration/delivery/deployment, terraform, ansible, iac, gitops, github actions, gitlab ci, jenkins, argocd, flux, pipeline, sre | 19 разделов: понятия DevOps, CI/CD pipeline, Git/VCS, стратегии развёртывания, окружения, IaC, Terraform, Ansible, контейнеры, мониторинг/SRE, тестирование, DevSecOps, глаголы, падежные формы, типовые ошибки, чек-лист |
| `networking-translation-dictionary` | сети, networking, tcp/ip, bgp, ospf, vxlan, vpn, vpc, subnet, nat, dns, cdn, load balancer, firewall, waf, ddos, sase, sd-wan, zero trust, tls, ssl, quic, http/3, websocket, grpc, ipv4/ipv6, vlan, mpls, ipsec, wireguard, anycast | 19 разделов: модели OSI/TCP-IP, оборудование (роутер/коммутатор/файрвол), адресация, транспорт, маршрутизация, коммутация L2, туннели/overlay/underlay, DNS, HTTP-стек, TLS/SSL, cloud networking (VPC/NAT), балансировка, CDN, сетевая безопасность, SASE/SSE/SD-WAN/Zero Trust, глаголы, падежные формы, типовые ошибки, чек-лист |
| `databases-translation-dictionary` | база/базы данных, database, субд, dbms, sql, nosql, postgresql, mysql, mariadb, clickhouse, tarantool, oracle, mongodb, redis, cassandra, репликация, шардирование, партиционирование, транзакция, acid, mvcc, wal, binlog, gtid, оптимизатор, индекс, join, cte, innodb, mergetree, vshard, vector database | 19 разделов: базовые понятия БД, типы СУБД (OLTP/OLAP/HTAP/vector), SQL DDL/DML/DCL/TCL, транзакции (ACID, MVCC, уровни изоляции, блокировки), индексы (B-tree/hash/GIN/GiST/BRIN/HNSW/IVF), оптимизатор и план запроса (EXPLAIN, nested loop/hash/merge join, buffer pool), репликация (WAL, binlog, GTID, publication/subscription, primary/replica, Galera, semi-sync), шардирование/партиционирование, PostgreSQL (WAL, vacuum, TOAST, FDW, Patroni, Citus, Shardman), MySQL/MariaDB (InnoDB, binlog, GTID, Galera, ProxySQL), ClickHouse (MergeTree, materialized view, словарь, гранула, мутация, ZooKeeper), Tarantool (space, tuple, VShard, bucket, Raft), NoSQL (CAP, BASE, eventual consistency, Cassandra, MongoDB, Redis), бэкапы (PITR, RPO/RTO, pg_dump, XtraBackup), инструменты DBA (psql, pgAdmin, DBeaver, Liquibase, Flyway), глаголы, падежные формы, типовые ошибки, чек-лист |
| `ml-ai-translation-dictionary` | ml, machine learning, ии, ai, llm, gpt, claude, gemini, deep learning, нейросеть, transformer, embeddings, эмбеддинги, fine-tuning, rag, prompt engineering, tokenization, attention, rlhf, lora, qlora, peft, hugging face, pytorch, tensorflow, langchain, llamaindex, mlops, inference, ai agent, mcp, diffusion, stable diffusion, gan, cuda | 19 разделов: базовые понятия (AI/ML/DL/RL, supervised/unsupervised, transfer/few-shot/zero-shot learning), архитектуры (MLP/CNN/RNN/LSTM/Transformer, GAN, diffusion, MoE, ViT, BERT/GPT/Llama), LLM-специфика (parameters, context window, tokens/TTFT, hallucination, reasoning, CoT, thinking models, prompt, function calling), токенизация и эмбеддинги (BPE/WordPiece, embedding, vector, HNSW/IVF, FAISS), обучение моделей (epoch, batch, gradient descent, loss, RLHF/DPO, LoRA/QLoRA/PEFT, quantization, distillation), RAG (retrieval, reranker, chunking, hybrid search, vector store), AI-агенты (tool use, MCP, multi-agent, ReAct, computer use), prompt engineering (few-shot/zero-shot, CoT/ToT, self-refine), evaluation (MMLU, HumanEval, perplexity, BLEU, ROUGE, LLM-as-a-judge), данные и датасеты, MLOps (model serving, registry, drift, MLflow, vLLM, Triton), фреймворки (PyTorch/TF/JAX, Hugging Face, LangChain/LlamaIndex), hardware (GPU H100/A100, CUDA, TPU, FP16/BF16/INT8, KV cache, distributed training), AI-продукты (ChatGPT, Claude, Gemini, Midjourney, Sora, GigaChat, YandexGPT), безопасность ИИ (alignment, prompt injection, jailbreak, adversarial), глаголы, падежные формы, типовые ошибки, чек-лист |
| `frontend-translation-dictionary` | frontend, фронтенд, html, css, javascript/typescript, react, vue, angular, svelte, solid, next.js, nuxt, remix, astro, qwik, vite, webpack, esbuild, tailwind, redux, zustand, react query, ssr/ssg/isr/csr/spa/mpa/pwa, web components, shadow dom, service worker, indexeddb, webassembly, webgl/webgpu, websocket, graphql, dom, jsx, хук, usestate/useeffect, props, роутинг, a11y, lighthouse, core web vitals, lcp/cls/inp | 19 разделов: базовые понятия веба, HTML, CSS (Flexbox/Grid, BEM, Sass), JavaScript/TypeScript (closures, async/await, generics), React (hooks, Server Components, Suspense, RTK, TanStack Query), Vue (Composition API, Pinia), Angular/Svelte/Solid/Qwik, метафреймворки (Next.js/Nuxt/Remix), рендеринг (SSR/SSG/ISR, hydration, RSC), бандлеры (Webpack, Vite, esbuild, Turbopack), Web APIs (DOM, Web Components, IndexedDB, Service Worker, WebGPU), state management, тестирование (Vitest, Playwright, Cypress, Storybook), a11y/i18n (WCAG, ARIA, RTL), performance (Core Web Vitals — LCP/INP/CLS/TTFB, Lighthouse), глаголы, падежные формы, типовые ошибки, чек-лист |
| `mobile-translation-dictionary` | mobile, мобильный, ios, android, swift, swiftui, uikit, objective-c, kotlin, jetpack compose, android sdk, xcode, android studio, app store, google play, rustore, testflight, react native, flutter, dart, kotlin multiplatform (kmp/kmm), expo, activity, fragment, viewcontroller, intent, push notifications, apns, fcm, deeplink, in-app purchase (iap), biometric, face id, touch id, keychain, keystore, mdm | 19 разделов: базовые понятия мобильной разработки, iOS / Apple платформы (iOS/iPadOS/macOS/watchOS/tvOS/visionOS, Xcode, TestFlight, App Store Connect), Swift/SwiftUI/UIKit (Combine, Actor, property wrapper), iOS-фреймворки (Core Data, ARKit, CoreML, HealthKit, StoreKit), Android (Studio, ADB, Gradle, Play Console, **RuStore/NashStore**), Kotlin/Jetpack Compose (корутины, Flow, Hilt, Room, Activity/Fragment/Intent), кросс-платформенные фреймворки (React Native, Flutter/Dart, Kotlin Multiplatform), push/deeplinks/IAP (APNs, FCM, Universal Links, StoreKit 2), мобильная безопасность (Face ID, Keychain, Keystore, certificate pinning, **российские MDM — Rusbitech, ALD Pro, RuMobile**), UI/UX-паттерны, магазины (**ASO**, ревью, beta-testers), производительность (ANR, FPS, cold/warm start, baseline profiles, **российская аналитика — AppMetrica, MyTracker**), CI/CD (Fastlane, Bitrise, Xcode Cloud), тестирование (XCTest, Espresso, Detox), **российская специфика** (RuStore, AppMetrica, ЕБС, Аврора ОС), глаголы, падежные формы, типовые ошибки, чек-лист |
| `security-translation-dictionary` | security, иб, информационная безопасность, кибербезопасность, cybersecurity, infosec, appsec, devsecops, уязвимость, vulnerability, cve, cwe, cvss, owasp, mitre att&ck, attack, эксплойт, phishing, фишинг, malware, ransomware, шифровальщик, ddos, sql injection, xss, csrf, rce, threat model, stride, kill chain, zero trust, ztna, rbac, iam, oauth, oidc, saml, jwt, mfa, sso, encryption, шифрование, криптография, tls, ssl, pki, sast, dast, sca, siem, soc, soar, edr, xdr, mdr, ndr, sbom, slsa, sigstore, incident response, 152-фз, фстэк, фсб, кии, госсопка, gdpr, pci dss, hipaa, iso 27001 | 19 разделов: базовые понятия (threat/vulnerability/risk/attack/incident/breach), CIA triad, типы атак (phishing/malware/ransomware/SQLi/XSS/CSRF/RCE/MITM/privilege escalation/lateral movement/exfiltration), уязвимости и каталоги (CVE/CWE/CVSS, OWASP Top 10, KEV, EPSS, БДУ ФСТЭК), threat modeling (STRIDE/PASTA/DREAD, kill chain, MITRE ATT&CK, red/blue/purple team, pentest), криптография (AES/RSA/ECC/ECDSA, hash MD5/SHA, AEAD, PKI, post-quantum, ГОСТ Кузнечик/Стрибог/Магма), IAM (AuthN/AuthZ, MFA/SSO/SAML/OAuth/OIDC/JWT, RBAC/ABAC/MAC, PAM), AppSec/DevSecOps (SAST/DAST/IAST/SCA, fuzzing, WAF, CSP/HSTS), cloud security (CSPM/CIEM/CWPP/CNAPP/CASB, SASE/SSE/ZTNA, confidential computing), container/K8s security (Pod Security, image scanning, OPA/Gatekeeper/Kyverno, Falco/Tetragon), supply chain (SBOM, SLSA, Sigstore/cosign, dependency confusion), SOC/SIEM/SOAR/EDR/XDR/MDR/NDR (forensics, threat hunting, Sigma/YARA, Splunk/Elastic, российские MaxPatrol/R-Vision/PT NAD), compliance (ISO 27001, NIST CSF, PCI DSS, GDPR, SOC 2, FIPS), **российская специфика** (152-ФЗ/187-ФЗ/ФСТЭК/ФСБ/Роскомнадзор/КИИ/ГосСОПКА/БДУ/ПДн/УЗ-1...УЗ-4, ГОСТ Р, импортозамещение), AI security, глаголы, падежные формы, типовые ошибки, чек-лист |

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

### Когда оркестратор сообщает пользователю о подключённых словарях

На шаге 4 wizard'а (подтверждение запуска) — оркестратор показывает в сводке параметров строку:

```
| Подключённые словари | k8s-translation-dictionary, networking-translation-dictionary |
```

Пользователь может на этом шаге уточнить: «исключи сетевой» или «добавь devops». Подключённые словари автоматически передаются всем трём субагентам через frontmatter — менять программно при ответе пользователя не нужно, достаточно учесть пожелание в промте субагента.

## Доступность словарей вне модуля перевода

Все 8 доменных словарей физически лежат в **«translation» (внутренний материал системы, в эту выгрузку не входит)** (корень репо) — source of truth с тематической организацией. В `.claude/skills/` — symlinks на эти файлы для автодискаверинга Claude Code. Это означает, что словарями могут пользоваться **любые агенты репозитория**, не только субагенты модуля `article-translation-agent`. Подробности про структуру `skills/` — в «README» (внутренний материал системы, в эту выгрузку не входит).

### Зачем

Терминологические таблицы в словарях полезны для любого русскоязычного контента:

- **SEO-статьи и колонки** по K8s, DevOps, ML/AI, безопасности — `seo-writer` использует словари для унификации терминов
- **Документация VK Cloud** — `docs-article-writer` опирается на словари для K8s/databases/networking
- **Пресс-релизы** про мобильные приложения, AI-продукты — `press-release-writer` использует mobile/ml-ai-словари
- **Дайджесты** по сетевым технологиям, БД, мобильному рынку — `digest-writer` подтягивает соответствующие словари
- **Лендинги** про облачные/AI/security-продукты — `landing-creator` использует словари для согласованности с экспертным контентом
- **Редактура `content-editor`** — использует словари для проверки терминологии при редактуре любого контента

### Что переиспользуется, а что специфично для перевода

В каждом словаре 19 разделов. Для **не-переводческих** агентов полезны разделы 1-15 (терминологические таблицы по доменам, имена продуктов, аббревиатуры, единые названия). Разделы **17-19** (падежные формы для частых терминов, типовые ошибки переводчика, чек-лист переводчика) специфичны для модуля перевода и могут пропускаться.

В заголовке каждого словаря явно указано: «Для авторов и редакторов (не только переводчиков) — опирайся в первую очередь на разделы 2-15».

### Как подключить словарь к другому субагенту

В frontmatter любого субагента добавь нужные словари в массив `skills`:

```yaml
---
name: seo-writer
model: sonnet
skills:
  - vk-tech-redstandards
  - seo-knowledge
  - k8s-translation-dictionary       # для статей про Kubernetes
  - networking-translation-dictionary # для статей про сети
  - security-translation-dictionary   # для security-тем
---
```

Claude Code находит словари по имени через индекс в `.claude/skills/` (symlinks на «translation» (внутренний материал системы, в эту выгрузку не входит)) и подгружает в контекст субагента при срабатывании активационных триггеров (см. блок `activation:` в начале каждого словаря). Редактируй файлы в «name» (внутренний материал системы, в эту выгрузку не входит) — symlinks подтянутся автоматически.

### Уже подключённые субагенты (на 2026-05-16)

| Субагент | Подключённые словари | Зачем |
|----------|----------------------|-------|
| `article-translator`, `translation-editor`, `translation-verifier` | все 8 | Pipeline перевода |
| `seo-writer` | k8s, networking, databases, ml-ai, security | Унификация терминологии в SEO-статьях по этим темам |
| `docs-article-writer` | k8s, networking, databases, security | Документация VK Cloud |
| `content-editor` | все 8 (опционально) | Проверка терминологии при редактуре любого контента |

Список будет расширяться по мере подключения новых субагентов. Добавление словаря к субагенту не имеет «побочных эффектов» — он подгружается только когда сработает триггер активации в тексте задачи.

Если темы нет в словарях — действуй по Общей таблице ниже + тесту распространённости для всего остального (распространённое — русское слово/англицизм инлайн, узкое — оригинал + сноска при первом упоминании).

### Общая таблица терминов (whitelist принятых переводов)

Эта таблица — часть whitelist'а наравне с доменными словарями. Термины из неё **переводятся** на указанный русский вариант (без скобок-описания, потому что это уже устоявшаяся норма).

| Английский | Русский (whitelist) | Примечание |
|------------|---------------------|------------|
| cloud | облако | в названиях продуктов сохраняй оригинал: VK Cloud, Google Cloud |
| container | контейнер | — |
| cluster | кластер | — |
| pipeline | конвейер / pipeline | одиночный термин — «конвейер» (офиц.) или оригинал `pipeline`; склонения и приоритет — в `devops-translation-dictionary`. «Пайплайн» — только в составных (CI/CD-пайплайн, ETL-пайплайн) |
| repository | репозиторий | — |
| commit | коммит | — |
| pull request | пулреквест (PR при повторе) | — |
| machine learning | машинное обучение (ML при повторе) | — |
| dataset | датасет | альтернатива «набор данных» — только если в исходнике делается акцент |
| backend / frontend | бэкенд / фронтенд | — |
| throughput | пропускная способность | — |

**Термины, которые остаются в оригинале** (даже если кажутся «русифицированными» в Habr-постах) — без принятого однозначного русского варианта, поэтому переводить их не нужно. Нужна ли сноска — решает тест распространённости: для профильной аудитории Хабра большинство из них — знакомые англицизмы (сноска не нужна), для широкой аудитории — узкие (сноска при первом упоминании):

| Английский | Действие | Пример текста сноски (если термин узкий для целевой аудитории) |
|------------|----------|----------------------------------------------------------------|
| pod (k8s) | оригинал «pod» | «Pod — минимальная единица развёртывания в Kubernetes: один или несколько контейнеров. — Прим. перев.» |
| node | оригинал «node» | «Node — узел кластера Kubernetes, физическая или виртуальная машина. — Прим. перев.» |
| workflow | оригинал «workflow» | «Workflow — процесс автоматизации, например в GitHub Actions. — Прим. перев.» |
| deployment (k8s) | оригинал «Deployment» | «Deployment — объект Kubernetes для управления версионированным развёртыванием. — Прим. перев.» |
| service (k8s) | оригинал «Service» | «Service — объект Kubernetes для сетевого доступа к группе подов. — Прим. перев.» |
| ingress | оригинал «Ingress» | «Ingress — объект Kubernetes для маршрутизации входящего HTTP-трафика. — Прим. перев.» |
| open source | оригинал «open source» | обычно не нужна (распространённый англицизм) |
| feature flag | оригинал «feature flag» | «Feature flag — флаг для управляемого включения функциональности на части пользователей. — Прим. перев.» |
| latency | оригинал «latency» | обычно не нужна (распространённый англицизм) |
| observability | оригинал «observability» | «Observability (наблюдаемость) — метрики, логи и трассировки для понимания состояния системы. — Прим. перев.» |

Эти и подобные термины **переводятся только тогда**, когда явно указаны как whitelist в доменном словаре (например, в k8s-словаре `pod` помечен как переводимый под определённые правила склонения — тогда применяется именно этот вариант).

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
