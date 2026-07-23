---
name: devops-translation-dictionary
delivery: reference
description: |
  Словарь терминологии DevOps для перевода технических статей с английского
  и немецкого на русский. Покрывает CI/CD, Infrastructure as Code (Terraform,
  Ansible), GitOps, Git-термины, мониторинг и SRE, контейнерную экосистему.
  Содержит: что переводится, что остаётся в оригинале, падежные формы,
  типовые ошибки. Подключается к article-translator, translation-editor,
  translation-verifier при переводе DevOps-статей.

  Источники: переводы Фланта и OTUS на Хабре, Selectel Blog, ZONE3000 DevOps
  Courses, werf.io документация, методология «Альянса ПРО», практика VK Tech.
activation:
  - "devops"
  - "ci/cd"
  - "continuous integration"
  - "continuous delivery"
  - "continuous deployment"
  - "terraform"
  - "ansible"
  - "infrastructure as code"
  - "iac"
  - "gitops"
  - "github actions"
  - "gitlab ci"
  - "jenkins"
  - "argocd"
  - "argo cd"
  - "flux"
  - "pipeline"
  - "sre"
---

# DevOps Translation Dictionary

Словарь для переводчиков статей по DevOps, CI/CD и Infrastructure as Code. Дополняет `k8s-translation-dictionary` (для статей, где обе области пересекаются — например, GitOps на Kubernetes — подключаются оба словаря).

**Не догма.** Отражает консенсус русскоязычного DevOps-сообщества (Флант, OTUS, Selectel, ZONE3000, переводчики werf и Альянс ПРО) на 2026 год.

## Принципы

1. **Команды CLI и инструменты — оригинал, не склоняются.** `terraform plan`, `kubectl apply`, `ansible-playbook`, `docker build`, `git rebase`. В тексте — как в коде.
2. **Имена платформ — оригинал.** GitHub Actions, GitLab CI/CD, Jenkins, CircleCI, ArgoCD, Flux, TeamCity, Drone — пишутся как в официальной документации.
3. **Базовые понятия — переводятся.** «Конвейер» (pipeline), «развёртывание» (deployment как действие), «откат» (rollback), «сборка» (build).
4. **Имена ресурсов Terraform/Ansible — оригинал.** `resource`, `provider`, `module`, `playbook`, `task` — как в коде. В нарративе — переводятся («ресурс», «провайдер», «модуль», «плейбук»).
5. **Аббревиатуры — оригинал.** CI/CD, IaC, SRE, SLO/SLA/SLI, MTTR, MTBF, RPO/RTO, DORA. При первом упоминании — расшифровка в скобках.
6. **В одном тексте — один вариант для каждого термина.** Не смешивай `pipeline` и «конвейер» в соседних абзацах.

## Раздел 1. Базовые понятия DevOps

| English | Русский (рекомендуемый) | Альтернативы | Комментарий |
|---------|-------------------------|--------------|-------------|
| DevOps | DevOps | — | Не переводится. Не «ДевОпс». Не склоняется: «DevOps-команда», «DevOps-инженер», «DevOps-практики» |
| DevOps engineer | DevOps-инженер | девопс | Через дефис, инженер склоняется |
| DevSecOps | DevSecOps | — | Не переводится |
| GitOps | GitOps | — | Не переводится, без дефиса |
| SRE (Site Reliability Engineering) | SRE | — | Расшифровка при первом упоминании. «SRE-инженер», «SRE-практика» |
| Platform Engineering | платформенная инженерия | platform engineering | Русский вариант устоялся (Хабр, ру-доки) — давать сразу по-русски, без оригинала в скобках (фидбек редакторов 2026-07-22) |
| Golden path | эталонный путь | golden path | Пояснение узкому читателю — сноской при первом упоминании, не в скобках (фидбек редакторов 2026-07-22) |
| Governance | управление и контроль / governance | — | В связках типа «квоты и governance по CVE» — русский вариант («контроль/учёт»); «governance» допустим как термин платформенных команд |
| Self-service | самообслуживание | self-service | «Provisioning в режиме самообслуживания», «интерфейс самообслуживания» |
| Service broker | брокер сервисов | service broker | Модель Open Service Broker API; «модель брокера сервисов» |
| Continuous Integration (CI) | непрерывная интеграция / CI | — | При первом упоминании — полное название + аббревиатура |
| Continuous Delivery (CD) | непрерывная поставка / CD | — | Разница с deployment важна — см. ниже |
| Continuous Deployment (CD) | непрерывное развёртывание / CD | — | Автоматическое развёртывание в production (в отличие от Delivery) |
| Continuous Testing | непрерывное тестирование | — | — |
| Continuous Monitoring | непрерывный мониторинг | — | — |
| Shift Left | shift left / «сдвиг влево» | — | При первом упоминании — пояснение |
| Toolchain | инструментарий / toolchain | — | — |

### Тонкость: Delivery vs Deployment

В переводе важно сохранить различие:
- **Continuous Delivery** — изменения автоматически готовы к развёртыванию, но релиз — ручное решение. Русский: «непрерывная поставка».
- **Continuous Deployment** — каждый успешный коммит автоматически идёт в продакшен. Русский: «непрерывное развёртывание».

Если автор использует только «CD», уточни по контексту, какой из двух имеется в виду, и переведи соответственно.

## Раздел 2. CI/CD pipeline — компоненты

| English | Русский | Комментарий |
|---------|---------|-------------|
| Pipeline | конвейер / pipeline | Оба варианта используются. «Pipeline» — чаще в технических статьях. «Конвейер» — официальный перевод |
| Stage | этап / stage | — |
| Job | job / задача | В контексте GitLab/GitHub — `job`, в нарративе — «задача» |
| Step | шаг / step | В GitHub Actions — `step` |
| Runner | runner / раннер | «GitLab Runner», «self-hosted runner» — не переводят |
| Agent | агент | «Jenkins agent» → «агент Jenkins» |
| Worker | воркер / worker | — |
| Workflow | workflow / процесс | В GitHub Actions — `workflow`, не переводить |
| Build | сборка / build | «Сборка», но команда — `docker build` |
| Test | тест | — |
| Deploy | развёртывание / деплой | «Деплой» — допустимо в нарративе |
| Release | релиз | — |
| Artifact | артефакт | — |
| Trigger | триггер | — |
| Hook (pre-commit, post-merge) | хук | «pre-commit hook» → «pre-commit хук» |
| Webhook | webhook / вебхук | — |
| Cron / Scheduled trigger | cron / по расписанию | — |
| Matrix build | матричная сборка / matrix build | — |
| Parallel execution | параллельное выполнение | — |
| Cache | кэш | «Кэширование сборки» — «cache build» |

## Раздел 3. Git и VCS

| English | Русский | Комментарий |
|---------|---------|-------------|
| Repository / Repo | репозиторий / репо | Склоняется: репозитория, репозиторию |
| Commit | коммит | Склоняется: коммита, коммиту, коммитом |
| Branch | ветка / бранч | «Ветка» — устоявшийся перевод. «Бранч» — разговорно |
| Main / Master branch | main / master / основная ветка | Сейчас чаще `main`. В нарративе — «основная ветка» |
| Feature branch | feature-ветка / ветка фичи | — |
| Merge | слияние / merge | «Сделать merge», «слить ветку» |
| Rebase | rebase / ребейз | «Сделать rebase», «отребейзить» — допустимо разговорно |
| Cherry-pick | cherry-pick | Не переводят |
| Fork | форк | Склоняется: форка, форку. «Сделать форк» |
| Clone | клонирование | «Клонировать репозиторий» |
| Pull | pull / подтягивать | «Сделать `git pull`», «подтянуть изменения» |
| Push | push / отправить | «Сделать push», «запушить» (разг.) |
| Force-push | форс-пуш / `git push --force` | «Форс-пушить» — разг. В техконтексте — командой |
| Pull Request (PR) | pull request / PR / пулреквест | На GitHub — PR. «Пулреквест» — допустимо |
| Merge Request (MR) | merge request / MR | В GitLab — MR. Не «MR в GitHub» — там это PR |
| Code Review | code review / ревью кода | «Сделать ревью», «пройти ревью» |
| Conflict | конфликт | «Конфликт слияния» — «merge conflict» |
| Tag | тег | Склоняется: тега, тегу |
| Release tag | релиз-тег | Через дефис |
| Diff | diff / различия | «Посмотреть diff» |
| Patch | патч | «Применить патч» |
| Submodule | сабмодуль / submodule | — |
| Squash | squash / схлопывание | «Сделать squash коммитов», «схлопнуть коммиты» |
| Stash | stash / отложить | «Сделать `git stash`» |
| Blame | blame / `git blame` | Не переводить |
| Revert | revert / откатить | «Откатить коммит» |
| HEAD | HEAD | Не переводить, всегда заглавными |
| Detached HEAD | detached HEAD | — |
| Reflog | reflog | — |

### Тонкость: Pull Request vs Merge Request

Не путай на разных платформах:
- **GitHub, Bitbucket, Gitea, Forgejo** — Pull Request (PR)
- **GitLab** — Merge Request (MR)

При переводе **сохраняй термин из оригинала** — это даёт читателю понять, на какой платформе работает автор. Если в оригинале «pull request», не переводи как «merge request», даже если рассказываешь про GitLab.

## Раздел 4. Стратегии развёртывания

| English | Русский | Комментарий |
|---------|---------|-------------|
| Rolling update | rolling update / поэтапное обновление | — |
| Blue/Green deployment | blue/green деплой | Не переводить «синий/зелёный» |
| Canary deployment | canary deployment / канареечный деплой | — |
| Canary release | canary-релиз | — |
| Canary rollout | канареечная выкатка / канареечный деплой | На Хабре чаще «канареечный деплой». Контекст Gateway API — `HTTPRoute backendRefs` + `weight` |
| Traffic splitting | разделение трафика | Устоявшийся. В Gateway API — через `weight` в `backendRefs` |
| Header modification | модификация заголовков | Стандартизировано в Gateway API через filters |
| Cross-namespace routing | маршрутизация между неймспейсами | В Gateway API — через `ReferenceGrant` |
| Feature flag | feature flag / фича-флаг | Чаще оставляют английский |
| Feature toggle | feature toggle | — |
| A/B testing | A/B-тестирование | Через дефис |
| Dark launch | dark launch / тёмный запуск | — |
| Shadow deployment | shadow deployment / теневой деплой | — |
| Rollback | откат / rollback | «Сделать rollback», «откатить релиз» |
| Hotfix | hotfix / хотфикс | — |
| Cutover | cutover / переключение | — |

## Раздел 5. Окружения

| English | Русский | Комментарий |
|---------|---------|-------------|
| Environment | окружение / environment | «Окружение разработки», «production environment» → «production-окружение» |
| Development (dev) | dev / разработка | «dev-окружение» |
| Staging | staging / стейджинг | «Стейдж», «staging-окружение» |
| Pre-production | preprod / препрод | — |
| Production (prod) | production / продакшен / прод | «Прод» — разговорно, в статьях — «production». Склоняется: «в проде», «на проде» |
| QA / Test environment | QA-окружение / тестовое окружение | — |
| Sandbox | sandbox / песочница | — |
| Ephemeral environment | ephemeral environment / временное окружение | Также «preview environment» |
| Preview environment | preview environment / preview-окружение | Для PR/MR |
| On-premises (on-prem) | on-prem / on-premise / локальный | «Локальная инфраструктура» — официально, «on-prem» — разговорно |

## Раздел 6. Infrastructure as Code — общие понятия

| English | Русский | Комментарий |
|---------|---------|-------------|
| Infrastructure as Code (IaC) | инфраструктура как код / IaC | При первом упоминании — расшифровка |
| Configuration as Code (CaC) | конфигурация как код / CaC | — |
| Pipeline as Code | pipeline as code | Чаще оставляют английский |
| GitOps | GitOps | Не переводится |
| Declarative | декларативный | «Декларативный подход», «декларативная конфигурация» |
| Imperative | императивный | — |
| Idempotent | идемпотентный | «Идемпотентность» |
| Immutable infrastructure | неизменяемая инфраструктура / immutable infrastructure | — |
| Mutable infrastructure | изменяемая инфраструктура | — |
| Configuration management | управление конфигурацией | — |
| Provisioning | подготовка (инфраструктуры) / выдача (ресурсов) | provisioning допустим как англицизм, но без пояснения в скобках; «провижининг» не использовать (фидбек редакторов 2026-07-22: русский вариант — сразу) |
| Drift | drift / расхождение конфигурации | При первом упоминании — пояснение |
| Drift detection | обнаружение drift | — |
| Convergence | сходимость | — |
| Desired state | желаемое состояние | — |
| Current state | текущее состояние | — |
| Reconciliation | reconciliation / согласование | — |

## Раздел 7. Terraform

| English | Русский | Комментарий |
|---------|---------|-------------|
| Terraform | Terraform | Не переводится, не склоняется |
| HCL (HashiCorp Configuration Language) | HCL | Аббревиатура |
| State / Terraform state | state / стейт | «Файл state», «terraform.tfstate» — не переводить |
| Remote state | remote state / удалённое состояние | — |
| Backend | backend / бэкенд (Terraform) | «S3 backend», «Terraform Cloud backend» |
| Provider | provider / провайдер | В коде — `provider`, в нарративе — «провайдер AWS» |
| Resource | resource / ресурс | В коде — `resource "aws_instance"`, в нарративе — «ресурс» |
| Data source | data source | Часто не переводят, особенно с примером кода |
| Module | модуль | «Terraform-модуль», «Terraform module» |
| Variable | переменная | «Variable `region`», «переменная region» |
| Output | output / выходное значение | В коде — `output`, в нарративе — «output», «output-значение» |
| Workspace | workspace / рабочее пространство | Чаще оставляют английский |
| Lock | lock / блокировка | «State lock», «блокировка state» |
| Plan | plan / план | «`terraform plan`», «план изменений» |
| Apply | apply | Команда: `terraform apply`. В нарративе — «применить изменения» |
| Destroy | destroy | Команда: `terraform destroy`. «Удалить ресурсы» |
| Init | init | `terraform init` — «инициализация» |
| Refresh | refresh | `terraform refresh` |
| Import | import | `terraform import` — «импорт ресурса в state» |
| Plugin | плагин | — |
| Registry | registry / реестр | «Terraform Registry» — не переводить |
| OpenTofu | OpenTofu | Форк Terraform — не переводить |
| Lifecycle | lifecycle / жизненный цикл | В коде — блок `lifecycle` |

## Раздел 8. Ansible

| English | Русский | Комментарий |
|---------|---------|-------------|
| Ansible | Ansible | Не переводится |
| Playbook | плейбук / playbook | «Ansible playbook», «плейбук» |
| Play | play | Внутри playbook |
| Task | задача / task | В коде — `task`, в нарративе — «задача» |
| Role | роль | «Ansible-роль» |
| Handler | хендлер / handler | — |
| Inventory | inventory / инвентарь | «Файл inventory», «инвентарь» |
| Host | хост / хосты | — |
| Group | группа | «Группа хостов» |
| Module (Ansible) | модуль Ansible | — |
| Collection | коллекция / collection | — |
| Galaxy | Galaxy / Ansible Galaxy | Имя продукта |
| Vault | Vault / Ansible Vault | Не переводить — имя инструмента |
| Fact | факт / fact | «Факты хоста», «Ansible facts» |
| Ad-hoc command | ad-hoc команда | — |
| Idempotent | идемпотентный | — |
| Become / Privilege escalation | become / повышение привилегий | — |

## Раздел 9. Прочие IaC инструменты

| English | Русский | Комментарий |
|---------|---------|-------------|
| Pulumi | Pulumi | — |
| AWS CloudFormation | CloudFormation | — |
| Azure ARM templates | ARM templates | — |
| Google Cloud Deployment Manager | Deployment Manager | — |
| Crossplane | Crossplane | — |
| Chef | Chef | — |
| Puppet | Puppet | — |
| Salt / SaltStack | Salt / SaltStack | — |
| Packer | Packer | — |
| Vagrant | Vagrant | — |
| werf | werf | — |
| Spacelift, Atlantis, env0, Scalr | оригинал | Платформы управления Terraform |

## Раздел 10. CI/CD платформы

| English | Русский | Комментарий |
|---------|---------|-------------|
| GitHub Actions | GitHub Actions | — |
| GitLab CI/CD | GitLab CI/CD | Не «GitLab CI-CD», именно `/` |
| Jenkins | Jenkins | — |
| CircleCI | CircleCI | — |
| TeamCity | TeamCity | — |
| Bamboo | Bamboo | — |
| Travis CI | Travis CI | — |
| Drone | Drone | — |
| Bitbucket Pipelines | Bitbucket Pipelines | — |
| Azure DevOps / Azure Pipelines | Azure DevOps / Azure Pipelines | — |
| AWS CodePipeline | CodePipeline | — |
| ArgoCD / Argo CD | Argo CD / ArgoCD | Официально — «Argo CD» с пробелом |
| Flux / FluxCD | Flux | — |
| Tekton | Tekton | — |
| Spinnaker | Spinnaker | — |
| Harness | Harness | — |
| Octopus Deploy | Octopus Deploy | — |
| Buildkite | Buildkite | — |
| Concourse | Concourse | — |
| werf | werf | Российский опенсорс-инструмент Фланта |

## Раздел 11. Контейнеры и образы

| English | Русский | Комментарий |
|---------|---------|-------------|
| Docker | Docker | Не переводится |
| Container | контейнер | — |
| Image | образ | «Образ контейнера», «Docker-образ» |
| Dockerfile | Dockerfile | Не переводить |
| Layer | слой | «Слой образа» |
| Tag (image tag) | тег | «Тег образа» |
| Digest | digest / хеш | — |
| Registry | registry / реестр | «Container registry» |
| Docker Hub | Docker Hub | — |
| Harbor | Harbor | — |
| ECR (Elastic Container Registry) | ECR | AWS |
| GCR / Artifact Registry | GCR / Artifact Registry | Google Cloud |
| Multi-stage build | multi-stage сборка | — |
| Container runtime | container runtime / среда исполнения контейнеров | — |
| containerd, CRI-O, runc | оригинал | Имена runtime'ов |
| OCI (Open Container Initiative) | OCI | — |
| Image scanning | сканирование образов | — |
| Trivy, Clair, Snyk, Grype | оригинал | Имена сканеров |

## Раздел 12. Мониторинг, SRE, инциденты

| English | Русский | Комментарий |
|---------|---------|-------------|
| Monitoring | мониторинг | — |
| Alerting | алертинг / оповещения | — |
| Alert | алерт | Склоняется: алерта, алерту |
| On-call | on-call / дежурство | «Дежурный инженер» — «on-call engineer» |
| Incident | инцидент | — |
| Outage | даунтайм / outage / отказ | — |
| Downtime | даунтайм / время простоя | — |
| Uptime | uptime / время работы | — |
| Postmortem | постмортем / postmortem / разбор инцидента | — |
| Root Cause Analysis (RCA) | RCA / анализ первопричины | — |
| Mean Time to Recovery (MTTR) | MTTR / среднее время восстановления | — |
| Mean Time Between Failures (MTBF) | MTBF | — |
| Recovery Point Objective (RPO) | RPO | — |
| Recovery Time Objective (RTO) | RTO | — |
| Service Level Objective (SLO) | SLO | — |
| Service Level Agreement (SLA) | SLA | Среднего рода: «SLA соблюдено» |
| Service Level Indicator (SLI) | SLI | — |
| Error budget | error budget / бюджет ошибок | — |
| Burn rate | burn rate / скорость расхода | — |
| Toil | toil | Не переводить — устоявшийся SRE-термин |
| Chaos engineering | chaos engineering / хаос-инжиниринг | — |
| Game day | game day / день учений | — |
| Runbook | runbook / руководство по инциденту | — |
| Playbook (SRE) | playbook | — |
| Observability | observability / наблюдаемость | Оба варианта приемлемы |
| Telemetry | телеметрия | — |
| Trace | трейс / трассировка | «Distributed tracing» → «распределённая трассировка» |
| Span | спан | OpenTelemetry-термин |
| Log aggregation | агрегация логов | — |
| DORA metrics | DORA-метрики | Deployment Frequency, Lead Time, MTTR, Change Failure Rate |
| Deployment Frequency | частота деплоев | — |
| Lead Time for Changes | lead time / время выпуска изменения | — |
| Change Failure Rate | доля неуспешных изменений | — |

## Раздел 13. Тестирование

| English | Русский | Комментарий |
|---------|---------|-------------|
| Unit test | юнит-тест / модульный тест | — |
| Integration test | интеграционный тест | — |
| End-to-end test (E2E) | E2E-тест / сквозной тест | — |
| Smoke test | smoke-тест / дымовой тест | — |
| Regression test | регрессионный тест | — |
| Load test | нагрузочный тест | — |
| Stress test | стресс-тест | — |
| Performance test | тест производительности | — |
| Acceptance test | приёмочный тест | — |
| TDD (Test-Driven Development) | TDD / разработка через тестирование | — |
| BDD (Behavior-Driven Development) | BDD | — |
| Coverage | покрытие тестами | «Code coverage» → «покрытие кода» |
| Mock / Stub | мок / стаб | «Замокать», «застабить» — разг. |
| Fixture | фикстура | — |
| Test runner | test runner | — |

## Раздел 14. Безопасность DevOps (DevSecOps)

| English | Русский | Комментарий |
|---------|---------|-------------|
| SAST (Static Application Security Testing) | SAST / статический анализ безопасности | — |
| DAST (Dynamic Application Security Testing) | DAST | — |
| SCA (Software Composition Analysis) | SCA | — |
| Secret scanning | сканирование секретов | — |
| Vulnerability | уязвимость | — |
| CVE | CVE | — |
| Patch | патч / исправление | — |
| Compliance | комплаенс / соответствие требованиям | — |
| Audit log | аудит-лог / журнал аудита | — |
| Zero Trust | Zero Trust / нулевое доверие | Чаще оставляют английский |
| Least privilege | принцип минимальных привилегий | — |
| Supply chain attack | атака на цепочку поставок | — |
| SBOM (Software Bill of Materials) | SBOM | — |
| Sigstore, cosign | оригинал | Инструменты подписи |
| Vendoring (Go) | вендоринг | Калька, кириллицей. Папка остаётся `vendor`. CI проверяет drift между `go.mod`, `go.sum`, `vendor/` |
| Transitive dependencies | транзитивные зависимости | Устоявшийся. Контекст: dep-trees Go/npm/PyPI, GitHub Actions |
| Nested dependency | вложенная зависимость | Безопасно |
| SHA pinning / pin by digest | закрепление по SHA / SHA-пиннинг | Первое упоминание: «закрепление action по полному SHA коммита (SHA pinning)». Также `@sha256:` digest для контейнерных образов |
| Mutable tags | изменяемые теги | Контекст: «перестать доверять изменяемым тегам» — основа SHA-пиннинга |
| Yanked (package) | отозван (npm) / помечен как yanked (PyPI) | Контекст важен: yank в PyPI ≠ unpublish в npm |
| Expression injection (GitHub Actions) | инъекция выражений | Контекст — синтаксис `${{ }}` в YAML workflow. По аналогии с «SQL-инъекция» |
| Scoped secrets | секреты с ограниченной областью действия / scoped-секреты | Первое упоминание — оба варианта; далее «scoped-секреты» |
| Allow-list / Deny-list | allow-list / deny-list (или: список разрешённых / запрещённых) | Современный гайд OSSF. «Белый/чёрный список» — допустимо, но менее точно |
| Composite actions | `composite actions` / составные actions | На Хабре чаще латиницей в обратных кавычках. В пояснении — «составные действия GitHub Actions» |
| Reusable workflows | reusable workflows / переиспользуемые workflow | В ru-доках GitHub нередко латиницей |
| Cooldown (Renovate / Dependabot) | период ожидания (cooldown) | В техконтексте часто оставляют латиницей |
| Self-hosted runner | self-hosted раннер / собственный раннер | «Самохостимый» — НЕ использовать (жаргон) |
| BuildKit | BuildKit | Имя продукта (Docker build engine) |
| Renovate | Renovate | Имя бота. См. также Dependabot |
| OpenSSF Scorecard | OpenSSF Scorecard | Имя метрики/инструмента |
| govulncheck | govulncheck | Имя CLI (официальный сканер уязвимостей Go) |
| actionlint | actionlint | Имя CLI (статический анализ GitHub Actions workflow) |
| CodeQL | CodeQL | Имя продукта статического анализа GitHub |
| Quay | Quay (контейнерный реестр Red Hat) | Имя продукта |
| Trivy | Trivy | Имя сканера уязвимостей (Aqua Security) |
| DCO sign-off | DCO sign-off (Developer Certificate of Origin, строка `Signed-off-by`) | Не переводить аббревиатуру |

## Раздел 14.5. Ingress / Gateway / Service Mesh — операционные концепции

Контекст: статьи про CNI, Service Mesh (Istio, Cilium), Gateway API. Имена CRD и продуктов — в k8s-словаре.

| English | Русский | Комментарий |
|---------|---------|-------------|
| Annotation sprawl | зоопарк аннотаций / разрастание аннотаций | «Зоопарк» — где автор передаёт раздражение; «разрастание» — нейтрально. При первом упоминании — англ. в скобках |
| Impedance mismatch | несоответствие моделей (impedance mismatch) | При первом упоминании — англ. в скобках. «Рассогласование» — не использовать |
| Noisy tenant / noisy neighbour | шумный тенант / шумный сосед | Устоявшееся в cloud/k8s |
| Route churn / high route churn | частые изменения маршрутов | Устоявшегося перевода нет. «Churn маршрутов» — допустимо в техконтексте |
| Resource contention | конкуренция за ресурсы | — |
| Policy Gap (Gateway API) | Policy Gap | Имя проблемы Gateway API — отсутствие стандартных policy-полей |
| Provisioner (Kubernetes) | provisioner / поставщик ресурсов | «Статический provisioner» — допустимо латиницей |
| Reconcile loop | цикл согласования / reconcile loop | На Хабре оба варианта |
| Eventual consistency | согласованность в конечном счёте | CS-литература. «Возможная согласованность» — неточно |
| Config reload | перезагрузка конфигурации | — |
| Graceful reload | плавная перезагрузка / graceful-перезагрузка | — |
| Blast radius | радиус поражения (blast radius) | При первом упоминании — англ. в скобках |

## Раздел 15. Глаголы и действия

| English | Русский | Комментарий |
|---------|---------|-------------|
| to deploy | развернуть / задеплоить | «Развернуть приложение». «Задеплоить» — разговорно |
| to roll out | выкатить | «Выкатить релиз» |
| to roll back | откатить | — |
| to promote (build) | продвинуть (сборку) | «Продвинуть сборку в production» |
| to provision | подготовить / провижионинг | — |
| to commit | закоммитить / сделать коммит | «Закоммитить изменения» |
| to push | запушить / отправить | — |
| to pull | подтянуть | «Подтянуть изменения» |
| to merge | слить / смержить | «Слить ветку», «смержить PR» |
| to rebase | отребейзить / сделать rebase | — |
| to fork | сделать форк / форкнуть | — |
| to clone | клонировать | — |
| to apply (manifest, terraform) | применить | «Применить манифест» |
| to plan (terraform) | сделать plan | — |
| to build | собрать | — |
| to ship | поставить / выпустить | — |
| to monitor | мониторить | — |
| to alert | алертить / оповестить | — |
| to scale | масштабировать | — |
| to automate | автоматизировать | — |
| to orchestrate | оркестрировать | — |

## Раздел 16. Падежные формы

### Pipeline → конвейер / pipeline

| Форма | Конвейер | Pipeline |
|-------|----------|----------|
| Им. | конвейер | pipeline (не склоняется) |
| Род. | конвейера | — |
| Дат. | конвейеру | — |
| Мн.ч. | конвейеры | pipelines (или «pipeline'ы») |

### Commit / коммит

«Коммит», «коммита», «коммиту», «коммитом». Мн.ч.: «коммиты», «коммитов».

### Build / сборка

«Сборка» — женский род: «сборки», «сборке», «сборкой». Мн.ч.: «сборки», «сборок».

### Деплой / Rollback / Rollout

Не склоняются по падежам: «после деплоя» — допустимо разговорно, в статьях — «после развёртывания» или «после деплоя» (как существительное мужского рода — допустимо в технических текстах).

### Terraform / Ansible / Jenkins / Docker

**Не склоняются.** «В Terraform», «через Ansible», «с Jenkins», «с помощью Docker». НЕ «Терраформом», «Ансиблем».

### kubectl, terraform, ansible (команды)

**Строчная буква, не склоняются.** «Запустить `terraform`», «вызвать `kubectl`», «через `ansible-playbook`».

### PR / MR

«PR», «MR» — не склоняются. «Создать PR», «закрыть MR», «после ревью PR».

«Пулреквест», «мержреквест» — склоняются: «пулреквеста», «мержреквесту». Но в техническом тексте чаще PR/MR без склонения.

### Production / Prod

- «Production» — не склоняется: «в production», «на production»
- «Прод» (разг.) — склоняется: «в проде», «на прод», «с прода»

## Раздел 17. Типовые ошибки переводчика DevOps-статей

### 1. Смешение Continuous Delivery и Continuous Deployment

```
✗ «Continuous Deployment — это когда команда сама решает, когда релизить»
✓ «Continuous Delivery — это когда команда сама решает, когда релизить.
   Continuous Deployment — автоматический релиз каждого изменения»
```

### 2. Перевод имён инструментов

```
✗ «Гитлаб», «Дженкинс», «Терраформ»
✓ «GitLab», «Jenkins», «Terraform»
```

### 3. Перевод названий CLI-команд

```
✗ «применить план Терраформ»
✓ «выполнить `terraform apply`» / «применить план Terraform»
```

### 4. Калька «является» / «позволяет»

```
✗ «Terraform является инструментом для управления инфраструктурой»
✓ «Terraform — инструмент для управления инфраструктурой»

✗ «GitOps позволяет автоматизировать развёртывание»
✓ «GitOps автоматизирует развёртывание»
```

### 5. PR vs MR на разных платформах

```
✗ (статья про GitHub) «Создайте merge request»
✓ (статья про GitHub) «Создайте pull request»
```

### 6. Перевод полей YAML / HCL

В Terraform, GitHub Actions, GitLab CI поля **не переводятся**:

```hcl
resource "aws_instance" "web" {   # НЕ "ресурс"
  ami           = "ami-123"        # НЕ "ами"
  instance_type = "t3.micro"       # НЕ "тип_инстанса"
  tags = {
    Name = "web-server"            # НЕ "Имя"
  }
}
```

```yaml
jobs:
  build:                            # НЕ "сборка:"
    runs-on: ubuntu-latest          # НЕ "запускается_на:"
    steps:                          # НЕ "шаги:"
      - uses: actions/checkout@v4   # НЕ "использует:"
```

### 7. Перевод «production» как «продукция»

```
✗ «Релиз в продукцию»
✓ «Релиз в production» / «Релиз в прод» / «Релиз в продакшен»
```

### 8. Перевод «environment» как «среда»

«Среда» допустима, но в DevOps-контексте «окружение» — устоявшийся вариант:

```
✗ «производственная среда»
✓ «production-окружение» / «продакшен-окружение»
```

### 9. «commit» как «фиксация»

В технических переводах «коммит» — стандарт. «Фиксация» режет глаз:

```
✗ «Сделайте фиксацию изменений»
✓ «Сделайте коммит» / «Закоммитьте изменения»
```

### 10. Перевод состояния Terraform

```
✗ «государство Терраформ» (буквальный перевод «state»)
✓ «Terraform state» / «state-файл Terraform»
```

## Раздел 18. Чек-лист переводчика DevOps-статьи

Перед сдачей литерального перевода пройди по чеклисту:

- [ ] **Имена инструментов** (Terraform, Ansible, Jenkins, GitLab, GitHub, Docker, Helm…) — не переведены и не транслитерированы
- [ ] **Команды CLI** (`terraform apply`, `kubectl get pods`, `ansible-playbook`, `docker build`, `git rebase`) — не изменены
- [ ] **Поля HCL/YAML/Dockerfile** (`resource`, `provider`, `tags`, `jobs`, `steps`, `FROM`, `RUN`) — не переведены
- [ ] **CI/CD конструкции** (`workflow`, `job`, `step`, `runner`) — оригинал в коде, в нарративе — по словарю
- [ ] **Аббревиатуры** (CI/CD, IaC, SRE, SLO, MTTR, RPO/RTO, DORA, CVE, SBOM, RBAC) — оригинал, при первом упоминании — расшифровка
- [ ] **Continuous Delivery vs Deployment** — разница сохранена
- [ ] **Pull Request / Merge Request** — соответствует платформе оригинала (GitHub → PR, GitLab → MR)
- [ ] **Production / Production environment** — не переведено как «продукция»
- [ ] **Terraform / Ansible / Docker / Kubernetes** — не склоняются («в Terraform», не «в Терраформе»)
- [ ] **Согласованность транслитерации** — в тексте один вариант (либо `pipeline`, либо «конвейер»)
- [ ] **Калек избегли** — нет «является», «позволяет», «осуществляет»
- [ ] **Кавычки** — «ёлочки»
- [ ] **Атрибуция оригинала** — в конце есть блок «Оригинал: {Title} — {Author}» + URL

## Раздел 19. Что делать с новыми терминами

Если в статье встречается DevOps-термин, которого нет в этом словаре:

1. **Проверь документацию инструмента** — например, для Terraform: https://developer.hashicorp.com/terraform/docs (русской локализации нет, опирайся на сложившуюся практику)
2. **Проверь публикации Фланта на Хабре** — https://habr.com/ru/companies/flant/ — основной русский локализатор DevOps-контента
3. **Проверь блог Selectel и OTUS на Хабре** — много DevOps-переводов
4. **Если нигде нет** — оставь **в оригинале** + пометь `[прим. перев.: устоявшегося перевода нет, оставлен оригинал]`.
5. Не придумывай свой перевод — это вносит непоследовательность в экосистему.

## Источники

| Источник | Назначение |
|----------|-----------|
| Флант на Хабре — https://habr.com/ru/companies/flant/ | Основной русский локализатор DevOps и K8s |
| OTUS на Хабре — https://habr.com/ru/companies/otus/ | CI/CD статьи с устоявшейся терминологией |
| Selectel Blog — https://selectel.ru/blog/ | DevOps статьи на русском |
| ZONE3000 DevOps Courses — https://devops-courses.zone3000.net/ | Глоссарии и обучающие материалы |
| werf documentation — https://werf.io/documentation/ | Русская документация Terraform/CI/CD-инструмента Фланта |
| Альянс ПРО — https://tran.su/ | Методология для ИТ-переводчиков |
| Terraform Docs — https://developer.hashicorp.com/terraform/docs | Эталонная терминология (английский) |
| Ansible Docs — https://docs.ansible.com/ | Эталонная терминология (английский) |
| DORA State of DevOps Report | Метрики DORA (Lead Time, Deployment Frequency, MTTR, Change Failure Rate) |

Версия словаря: **2026-05-16 v1.0**. Обновляется по мере появления новых терминов.

## Связь с другими словарями

- **`k8s-translation-dictionary`** — для статей на стыке DevOps и Kubernetes (GitOps на K8s, deployment стратегии в K8s, Helm) подключаются оба словаря. При конфликте — приоритет за словарём, более релевантным теме статьи.
- **Будущие словари** (databases, ml-ai, security) — также могут подключаться параллельно при пересечении тем.
