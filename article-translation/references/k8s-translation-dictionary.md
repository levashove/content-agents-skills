---
name: k8s-translation-dictionary
delivery: reference
description: |
  Словарь терминологии Kubernetes для перевода технических статей с английского
  и немецкого на русский. Содержит: что переводится, что остаётся в оригинале,
  падежные формы и склонения, типовые ошибки. Подключается к article-translator,
  translation-editor и translation-verifier при переводе K8s-статей.

  Источники: CNCF Cloud Native Glossary (RU), Kubernetes Standardized Glossary,
  переводы Фланта на Хабре, методология «Альянса ПРО», devopsgu.ru,
  внутренний skill kubernetes-vk-cloud-expert.
activation:
  - "kubernetes"
  - "k8s"
  - "kubectl"
  - "pod"
  - "deployment"
  - "helm"
  - "cluster"
  - "container orchestration"
---

# K8s Translation Dictionary

Словарь для переводчиков технических статей по Kubernetes. **Не догма** — отражает консенсус русскоязычного K8s-сообщества (Флант, CNCF локализация, devopsgu.ru, Альянс ПРО) на 2026 год. Если автор оригинала использует устоявшийся в его команде вариант, и он не противоречит словарю — оставляй авторский.

## Принципы

1. **Имена ресурсов Kubernetes API — не переводятся.** `Pod`, `Deployment`, `Service`, `Ingress`, `StatefulSet` — это идентификаторы в API, как имена функций в коде. В тексте пишутся с заглавной, как в YAML.
2. **Транслитерация допустима для частых терминов.** `pod` → `под`, `node` → `нода`. Используй в одном тексте **один** вариант, не смешивай «под» и `Pod`.
3. **Сложные концепции — переводятся.** `Control Plane` → «управляющий слой», `Workload` → «рабочая нагрузка», `Self-Healing` → «самовосстановление».
4. **CLI-команды и компоненты-сервисы — оригинал.** `kubectl`, `kubelet`, `kube-proxy`, `etcd` — пишутся как в коде, не склоняются.
5. **Аббревиатуры — оригинал.** API, RBAC, CRD, CRI, CNI, CSI, HPA, VPA, PV, PVC. При первом упоминании можно расшифровать в скобках.
6. **При первом упоминании сложного термина — пояснение в скобках.** `Sidecar (контейнер-помощник)`, `Taint (метка отторжения)`. Дальше — без пояснения.

## Раздел 1. Базовые объекты Kubernetes API

| English | Русский (рекомендуемый) | Альтернативы | Комментарий |
|---------|-------------------------|--------------|-------------|
| Pod | Pod / под | поды (мн.ч.) | Идентификатор ресурса — `Pod` с заглавной; в нарративе — «под». Не смешивай в одном тексте |
| Node | узел / нода | nodes | В технических текстах чаще «нода» — устоялось. «Узел» — официальный перевод CNCF |
| Cluster | кластер | — | Склоняется: кластера, кластеру, кластером |
| Namespace | пространство имён | namespace | В подписях команд/YAML — `namespace`; в нарративе — «пространство имён» |
| Container | контейнер | — | Базовый перевод, без вариантов |
| Image | образ | — | «Образ контейнера», не «имидж» |
| Container Image | образ контейнера | — | — |
| Registry | реестр / registry | — | «Registry образов», «container registry» можно оставлять |
| Object | объект (Kubernetes) | — | «Объекты Kubernetes», «K8s-объекты» |
| Resource | ресурс | — | «Ресурс Kubernetes», `apiResource` |
| Manifest | манифест | YAML-манифест | — |
| Label | метка (label) | — | При первом упоминании — «метка (label)», далее можно просто «label» |
| Selector | селектор | — | «label selector» → «селектор меток» |
| Annotation | аннотация | — | — |

## Раздел 2. Workloads и контроллеры

| English | Русский | Комментарий |
|---------|---------|-------------|
| Deployment | Deployment | Не переводится. «Деплоймент» — допустимо в разговорной речи, но в статьях лучше Deployment |
| ReplicaSet | ReplicaSet | — |
| StatefulSet | StatefulSet | — |
| DaemonSet | DaemonSet | — |
| Job | Job | Не переводить — конфликт с общим «работа» |
| CronJob | CronJob | — |
| ReplicationController | ReplicationController | Устаревший термин (deprecated) |
| Workload | рабочая нагрузка / workload | «K8s workloads» можно оставлять. В нарративе — «рабочая нагрузка» |
| Pod template | шаблон пода / pod template | — |
| Rollout | rollout / выкатка | «Выкатка обновления» — допустимо в практическом тексте |
| Rollback | rollback / откат | «Откат к предыдущей версии» |
| Rolling update | rolling update / поэтапное обновление | — |
| Canary deployment | canary-деплой / канареечный деплой | Часто оставляют английский |
| Blue/Green deployment | blue/green деплой | Не переводят |

## Раздел 3. Сеть

| English | Русский | Комментарий |
|---------|---------|-------------|
| Service | Service | Не переводить — конфликт с общим «сервис». В YAML — `Service` |
| ClusterIP | ClusterIP | Тип Service |
| NodePort | NodePort | Тип Service |
| LoadBalancer | LoadBalancer | Тип Service |
| ExternalName | ExternalName | Тип Service |
| Headless Service | headless Service / «бесшапочный» Service | Транслитерация редкая, чаще оставляют английский |
| Ingress | Ingress | — |
| Ingress Controller | Ingress-контроллер | Через дефис, без «of» |
| Gateway API | Gateway API | — |
| `Gateway` (CRD Gateway API) | `Gateway` | Не путать с `Gateway` Istio (legacy CRD). В backtick |
| `GatewayClass` | `GatewayClass` | Шаблон контроллера в Gateway API |
| `HTTPRoute`, `GRPCRoute`, `TLSRoute`, `TCPRoute`, `UDPRoute` | как есть, в backtick | CRD Gateway API для маршрутов |
| `ReferenceGrant` | `ReferenceGrant` | CRD для cross-namespace разрешений |
| `BackendTrafficPolicy` / `SecurityPolicy` / `EnvoyPatchPolicy` | как есть, в backtick | Кастомные Policy-CRD Envoy Gateway |
| `KongPlugin` | `KongPlugin` | CRD Kong |
| `HTTPProxy` | `HTTPProxy` | Legacy CRD Contour |
| `AuthorizationPolicy` / `VirtualService` / `EnvoyFilter` | как есть, в backtick | CRD Istio. `VirtualService` deprecated в пользу Gateway API |
| `Ambient Mode` (Istio) | `Ambient Mode` (далее «амбиент-режим») | Архитектура Istio без sidecar |
| `Sidecar Mode` (Istio) | `Sidecar Mode` (далее «sidecar-режим») | Традиционная архитектура Istio |
| `Waypoint proxy` | `Waypoint proxy` (далее «waypoint-прокси») | L7-прокси на service account в Ambient |
| `ztunnel` | `ztunnel` | L4-прокси на ноде в Ambient (zero-trust tunnel). Не склонять |
| Имена ingress-/gateway-проектов | как есть, в backtick где это название продукта: `Envoy Gateway`, `NGINX Gateway Fabric`, `NGINX Plus`, `NGINX OSS` | См. devops-словарь |
| Имена контроллеров и продуктов | как есть, без backtick: Envoy, Contour, Gloo, Kong, Traefik, HAProxy, ingress-nginx, Pipy, OpenResty, Tetrate, Ambassador | — |
| `xDS` (protocol / server / stream) | `xDS` (xDS-протокол, xDS-сервер, xDS-поток, xDS-конфигурация) | Конфигурационный протокол Envoy |
| Policy attachment (паттерн Gateway API) | policy attachment (паттерн привязки политик) | Латиницей с пояснением при первом упоминании |
| `listeners` (поле Gateway) | `listeners` / «слушатели» | В контексте поля — в backtick; в нарративе — «слушатели» |
| North-South / East-West traffic | north-south / east-west трафик | См. networking-словарь |
| Network Policy | Network Policy / сетевая политика | — |
| Service Mesh | Service Mesh / сервисная сетка | Чаще оставляют английский |
| Sidecar | sidecar / сайдкар / контейнер-помощник | При первом упоминании — пояснение |
| CNI (Container Network Interface) | CNI | Аббревиатура. Расшифровка при первом упоминании |
| Calico, Cilium, Flannel, Weave | оригинал | Названия CNI-плагинов не переводятся |
| kube-proxy | kube-proxy | Компонент |
| CoreDNS | CoreDNS | Имя продукта |
| DNS | DNS | — |
| Endpoint | endpoint / эндпойнт / точка доступа | — |
| EndpointSlice | EndpointSlice | — |

## Раздел 4. Хранилище

| English | Русский | Комментарий |
|---------|---------|-------------|
| Volume | volume / том | Чаще «volume». «Том» — официальный перевод CNCF |
| PersistentVolume (PV) | PersistentVolume / PV | Не переводить — имя ресурса |
| PersistentVolumeClaim (PVC) | PersistentVolumeClaim / PVC | — |
| StorageClass | StorageClass | — |
| Provisioner | provisioner / провижионер | — |
| Reclaim Policy | reclaim policy / политика освобождения | — |
| ConfigMap | ConfigMap | Не переводить |
| Secret | Secret | Не «секрет» в кавычках — `Secret` |
| CSI (Container Storage Interface) | CSI | Аббревиатура |
| StatefulSet | StatefulSet | См. раздел 2 |
| Stateful / Stateless | stateful / stateless | Часто оставляют английский: «stateful-приложение», «stateless-сервис» |

## Раздел 5. Конфигурация и переменные

| English | Русский | Комментарий |
|---------|---------|-------------|
| Environment variable | переменная окружения | — |
| ConfigMap | ConfigMap | — |
| Secret | Secret | — |
| Resource quota | ResourceQuota / квота ресурсов | — |
| LimitRange | LimitRange | — |
| Requests / Limits | requests / limits | Не переводить — это поля YAML |
| QoS (Quality of Service) Class | QoS Class / класс QoS | Расшифровка при первом упоминании |

## Раздел 6. Безопасность и доступ

| English | Русский | Комментарий |
|---------|---------|-------------|
| RBAC (Role-Based Access Control) | RBAC | При первом упоминании — расшифровка |
| Role / ClusterRole | Role / ClusterRole | Имена ресурсов |
| RoleBinding / ClusterRoleBinding | RoleBinding / ClusterRoleBinding | — |
| ServiceAccount | ServiceAccount | — |
| Pod Security Standards (PSS) | Pod Security Standards / PSS | — |
| Pod Security Admission (PSA) | Pod Security Admission / PSA | — |
| Security Context | Security Context / контекст безопасности | — |
| Network Policy | Network Policy / сетевая политика | — |
| Admission Controller | Admission Controller / контроллер допуска | — |
| OPA (Open Policy Agent) | OPA | — |
| Gatekeeper | Gatekeeper | Имя продукта |
| Image Pull Secret | imagePullSecret | Поле YAML |

## Раздел 7. Управляющий слой (Control Plane)

| English | Русский | Комментарий |
|---------|---------|-------------|
| Control Plane | управляющий слой / Control Plane | Оба варианта приемлемы. «Управляющий слой» — официальный перевод CNCF |
| Data Plane | плоскость данных / Data Plane | — |
| kube-apiserver / API Server | API Server / kube-apiserver | Компонент. Не переводить |
| etcd | etcd | Имя продукта, не склоняется |
| kube-scheduler / Scheduler | Scheduler / планировщик | Чаще оставляют «Scheduler» |
| kube-controller-manager | kube-controller-manager / Controller Manager | — |
| cloud-controller-manager | cloud-controller-manager | — |
| kubelet | kubelet | Не переводить, не склоняется |
| Master node | мастер-нода / master-нода | Через дефис. Устаревает в пользу «control plane node» |
| Worker node | рабочая нода / worker-нода / нода | — |

## Раздел 8. CLI и инструменты

| English | Русский | Комментарий |
|---------|---------|-------------|
| kubectl | kubectl | Не переводить, не склоняется. «Команда kubectl», но не «kubectl-у» |
| kubeadm | kubeadm | — |
| minikube, kind, k3s, k3d, microk8s | оригинал | Названия дистрибутивов / runtime'ов |
| Helm | Helm | Имя продукта |
| Helm Chart | Helm Chart / чарт | «Чарт» — допустимо в нарративе. «Helm-чарт» через дефис |
| Helm Release | Helm Release / релиз | — |
| Helm Repository | Helm-репозиторий | — |
| Kustomize | Kustomize | — |
| ArgoCD | Argo CD / ArgoCD | Официально пишется «Argo CD» с пробелом |
| Flux | Flux | — |
| GitOps | GitOps | Не переводить |
| Tilt, Skaffold, Telepresence | оригинал | Инструменты разработки |

## Раздел 9. Расширения API

| English | Русский | Комментарий |
|---------|---------|-------------|
| CRD (Custom Resource Definition) | CRD | При первом упоминании — расшифровка |
| Custom Resource (CR) | Custom Resource / CR | — |
| Operator | Operator / оператор | «Оператор» — допустимо. В YAML — `Operator` |
| Operator pattern | паттерн «оператор» | — |
| Controller | контроллер | — |
| Webhook | webhook / вебхук | — |
| Admission Webhook | admission webhook | — |
| Validating / Mutating Webhook | Validating / Mutating Webhook | — |
| Aggregation Layer | Aggregation Layer / слой агрегации | — |
| API Group | группа API / API group | — |
| API Version | версия API | — |

## Раздел 10. Планирование подов и ресурсы нод

| English | Русский | Комментарий |
|---------|---------|-------------|
| Scheduling | планирование | «Pod scheduling» → «планирование подов» |
| Affinity / Anti-Affinity | affinity / anti-affinity | Часто оставляют английский с пояснением «правила привязки» |
| Node Affinity | node affinity | — |
| Pod Affinity | pod affinity | — |
| Taint | taint / «метка отторжения» | При первом упоминании — пояснение |
| Toleration | toleration / «толерантность» | — |
| nodeSelector | nodeSelector | Поле YAML |
| Topology Spread Constraints | topology spread constraints / правила распределения по топологии | — |
| Eviction | вытеснение / eviction | — |
| Drain | drain / осушение ноды | «Сделать `kubectl drain`», «осушить ноду» |
| Cordon | cordon / запретить новые поды | — |
| Preemption | preemption / вытеснение по приоритету | — |
| PriorityClass | PriorityClass | — |
| Probe (Liveness / Readiness / Startup) | Liveness/Readiness/Startup Probe / проверка работоспособности | При первом упоминании — пояснение |

## Раздел 11. Масштабирование и автоматизация

| English | Русский | Комментарий |
|---------|---------|-------------|
| Scaling | масштабирование | — |
| Horizontal Pod Autoscaler (HPA) | HPA / горизонтальный автоскейлер | — |
| Vertical Pod Autoscaler (VPA) | VPA / вертикальный автоскейлер | — |
| Cluster Autoscaler | Cluster Autoscaler | — |
| Karpenter | Karpenter | Имя продукта |
| Autoscaling | автомасштабирование / автоскейлинг | Оба варианта используются. «Автоскейлинг» — частая калька |
| Replica | реплика | Склоняется: реплики, реплику |
| Replicas (field) | replicas | Поле YAML |

## Раздел 12. Мониторинг и наблюдаемость

| English | Русский | Комментарий |
|---------|---------|-------------|
| Observability | observability / наблюдаемость | Оба варианта приемлемы. «Observability» чаще в технических текстах |
| Metrics | метрики | — |
| Logs | логи | — |
| Tracing | трассировка | «Distributed tracing» → «распределённая трассировка» |
| Prometheus | Prometheus | — |
| Grafana | Grafana | — |
| Loki, Tempo, Mimir | оригинал | Имена продуктов |
| OpenTelemetry (OTel) | OpenTelemetry / OTel | — |
| Jaeger | Jaeger | — |
| Alertmanager | Alertmanager | — |
| Dashboard | дашборд / дашборд / панель | «Дашборд» — устоявшаяся транслитерация |
| SLO / SLA / SLI | SLO / SLA / SLI | Аббревиатуры |

## Раздел 13. Cloud Native концепции

| English | Русский | Комментарий |
|---------|---------|-------------|
| Cloud Native | Cloud Native / облачно-нативный | Чаще оставляют английский |
| Kubernetes-native | Kubernetes-native / нативный для Kubernetes | Без пояснения в скобках — термин знаком аудитории; «Kubernetes-native операторы (нативные для Kubernetes)» — избыточно (фидбек редакторов 2026-07-22) |
| Container Orchestration | оркестрация контейнеров | — |
| Microservices | микросервисы | — |
| Service Mesh | Service Mesh / сервисная сетка | — |
| Serverless | serverless / без серверов | Чаще «serverless» |
| Function-as-a-Service (FaaS) | FaaS | — |
| Multi-tenancy | мультитенантность / multi-tenancy | — |
| Multi-cluster | мульти-кластер | — |
| Hybrid Cloud | гибридное облако | — |
| Edge Computing | edge computing / периферийные вычисления | — |
| Immutable Infrastructure | неизменяемая инфраструктура | — |
| Infrastructure as Code (IaC) | инфраструктура как код / IaC | — |
| GitOps | GitOps | Не переводить |
| Self-Healing | самовосстановление | — |
| Declarative | декларативный | — |
| Imperative | императивный | — |
| Reconciliation Loop | reconciliation loop / цикл согласования | — |

## Раздел 14. Глаголы и действия

| English | Русский | Комментарий |
|---------|---------|-------------|
| to deploy | развернуть / задеплоить | «Развернуть приложение». «Задеплоить» — разговорно, в статьях лучше «развернуть» |
| to apply (kubectl apply) | применить | «Применить манифест» |
| to scale | масштабировать | — |
| to scale up / down | масштабировать вверх / вниз | — |
| to roll out | выкатить | «Выкатить обновление» |
| to roll back | откатить | — |
| to provision | подготовить / предоставить (ресурсы) | — |
| to evict | вытеснить (под) | — |
| to schedule | разместить / запланировать (под) | — |
| to spin up | поднять / запустить | «Поднять кластер» |
| to tear down | свернуть / удалить | — |
| to expose | пробросить / открыть наружу | «Expose Service» → «открыть Service наружу» |
| to label | пометить / навесить метку | — |
| to taint a node | поставить taint на ноду | — |

## Раздел 15. Падежные формы (для частых терминов)

### Pod → под

| Падеж | Форма |
|-------|-------|
| Именительный | под |
| Родительный | пода |
| Дательный | поду |
| Винительный | под |
| Творительный | подом |
| Предложный | поде |
| Мн.ч. им. | поды |
| Мн.ч. род. | подов |

Если используешь `Pod` без транслитерации — не склоняй: «создать Pod», «удалить Pod», «у этого Pod», не «Pod'а».

### Node → нода / узел

| Форма | Нода | Узел |
|-------|------|------|
| Им. ед. | нода | узел |
| Род. ед. | ноды | узла |
| Дат. ед. | ноде | узлу |
| Мн.ч. | ноды | узлы |

### Cluster → кластер

Склоняется как обычное существительное мужского рода: кластер, кластера, кластеру, кластером, о кластере.

### Helm Chart → чарт

«Чарт», «чарта», «чарту», «чартом». Мн.ч.: «чарты», «чартов».

### Kubernetes / K8s

**Не склоняется:** «в Kubernetes», «для Kubernetes», «с Kubernetes», но НЕ «в Кубернетесе». Это имя собственное продукта.

`K8s` — тоже не склоняется. Род — мужской: «Kubernetes запустил», «K8s применил».

### kubectl, kubelet, etcd

**Не склоняются и не имеют рода.** Всегда строчная буква, как в коде. «Запустить kubectl», «команда kubectl», но не «kubectl'ом», не «через kubectl-у».

## Раздел 16. Типовые ошибки переводчика K8s-статей

### 1. Перевод имён ресурсов

```
✗ «Создайте Развертывание»
✓ «Создайте Deployment»

✗ «Откатить службу»
✓ «Откатить Service» / «откатить сервис» (если имеется в виду микросервис, не K8s Service)
```

### 2. Несогласованность транслитерации

В одном тексте — один вариант. Не смешивай:

```
✗ В кластере 5 подов. Pod'ы запускаются на 3 нодах. Поды переходят в Running.
✓ В кластере 5 подов. Поды запускаются на 3 нодах. Поды переходят в Running.
```

### 3. Склонение несклоняемых

```
✗ «Запустить kubectl'ом»  →  ✓ «Запустить с помощью kubectl» / «через kubectl»
✗ «У kubelet'а есть...»    →  ✓ «У kubelet есть...» / «Kubelet имеет...»
✗ «В Кубернетесе»           →  ✓ «В Kubernetes»
```

### 4. Перевод полей YAML

Имена полей в YAML/JSON — **никогда** не переводи:

```yaml
spec:
  replicas: 3        # НЕ «реплики: 3»
  selector:          # НЕ «селектор:»
    matchLabels:     # НЕ «совпадающиеМетки:»
      app: nginx
```

Это правило относится и к комментариям в коде — переводи **только** комментарии, не сами поля.

### 5. Калька «является»

```
✗ «Pod является минимальной единицей»
✓ «Pod — минимальная единица»
```

### 6. Калька «позволяет»

```
✗ «HPA позволяет масштабировать поды»
✓ «HPA масштабирует поды» / «С HPA можно масштабировать поды»
```

### 7. Английский порядок слов

```
✗ «Это позволяет вам легко управлять кластером»  (калька с «allows you to easily»)
✓ «Кластером легко управлять» / «Вы легко управляете кластером»
```

### 8. Пассив без необходимости

```
✗ «Поды могут быть запущены на разных нодах»
✓ «Поды можно запускать на разных нодах» / «Kubernetes запускает поды на разных нодах»
```

### 9. Двойное название одного объекта

```
✗ «Service, или сервис, или служба, обеспечивает...»
✓ Выбери один вариант. В технических статьях обычно — `Service`.
```

### 10. Перевод устоявшихся английских составных

```
✗ «контроллер реплик» (для ReplicaSet)
✓ «ReplicaSet» — имя ресурса
```

## Раздел 17. Чек-лист переводчика K8s-статьи

Перед сдачей литерального перевода пройди по чеклисту:

- [ ] **Имена ресурсов API (Pod, Deployment, Service, Ingress, и т.д.)** — не переведены, написаны как в оригинале
- [ ] **Поля YAML** — не переведены (replicas, selector, matchLabels, spec, status и т.д.)
- [ ] **Команды CLI** — не изменены (`kubectl apply`, `helm install`, `kubectl get pods`)
- [ ] **kubectl, kubelet, etcd, kube-proxy** — везде строчными, не склоняются
- [ ] **Kubernetes / K8s** — не склоняются («в Kubernetes», не «в Кубернетесе»)
- [ ] **Транслитерация согласована** — в тексте один вариант для каждого термина (либо «под», либо `Pod`, не смесь)
- [ ] **Аббревиатуры (RBAC, CRD, HPA, VPA, PV, PVC, CRI, CNI, CSI)** — оригинал, расшифровка при первом упоминании
- [ ] **Названия продуктов экосистемы** (Helm, Prometheus, Grafana, Calico, Cilium, Istio, ArgoCD) — оригинал
- [ ] **Названия дистрибутивов** (minikube, k3s, kind, OpenShift) — оригинал
- [ ] **Калек избегли** — нет «является», «позволяет», «осуществляет», «производит»
- [ ] **Кавычки** — «ёлочки», внутри — „лапки"
- [ ] **Числа** — `10 000` (пробел), `3,14` (запятая), `5 ГБ`, `100 мс`
- [ ] **Атрибуция оригинала** — в конце есть блок «Оригинал: {Title} — {Author}, {date}» + URL

## Раздел 18. Когда термин имеет несколько устоявшихся переводов

Если в русскоязычном сообществе K8s нет единого варианта (например, `node` → «нода» / «узел», `observability` → «observability» / «наблюдаемость»), действуй по приоритету:

1. **Смотри на оригинал.** Если автор сам в английском тексте использует жаргонизм («k8s» вместо «Kubernetes»), сохраняй такой же уровень формальности в переводе.
2. **Смотри на площадку.** Хабр + Флант — чаще «нода», «под», «observability». Документация и формальные тексты — «узел», `Pod`, «наблюдаемость».
3. **Если переводишь в первый раз — выбирай устоявшееся в K8s-комьюнити.** Для большинства практических статей это будет «нода» / «под».
4. **В одном тексте — один вариант.** Это правило важнее любого «правильного» выбора.

## Раздел 19. Что делать с новыми терминами

Если в статье встречается термин, которого нет в этом словаре:

1. **Проверь CNCF Glossary RU** — https://glossary.cncf.io/ru/
2. **Проверь Kubernetes Docs RU** — https://kubernetes.io/ru/docs/
3. **Поищи в публикациях Фланта на Хабре** — https://habr.com/ru/companies/flant/
4. Если нигде нет — оставь **в оригинале** + пометь `[прим. перев.: устоявшегося перевода нет, оставлен оригинал]`.
5. Не придумывай свой перевод — это вносит непоследовательность в экосистему.

Все новые термины, которые встретились в работе, проверяльщик (`translation-verifier`) может предложить добавить в словарь. Решение о добавлении — за оркестратором и редактором.

## Источники

Словарь составлен на основе следующих авторитетных русскоязычных ресурсов K8s-сообщества:

| Источник | Назначение |
|----------|-----------|
| CNCF Cloud Native Glossary (RU) — https://glossary.cncf.io/ru/ | Официальный глоссарий CNCF на русском; локализация ведётся коллективно через GitHub |
| Kubernetes Standardized Glossary — https://kubernetes.io/docs/reference/glossary/ | Официальный глоссарий проекта Kubernetes; русская локализация в kubernetes/website |
| Документация Kubernetes на русском — https://kubernetes.io/ru/docs/ | Локализация ведётся коллективно |
| Флант на Хабре — https://habr.com/ru/companies/flant/ | Основной русский локализатор K8s-документации; устоявшиеся переводы |
| Альянс ПРО — методология для ИТ-переводчиков — https://tran.su/ | Подход «русский термин [английский оригинал]» для составных понятий |
| devopsgu.ru/glossary/glossary-kubernetes/ | Практический глоссарий с переводами и пояснениями |
| Внутренний skill kubernetes-vk-cloud-expert | Терминология VK Cloud Managed Kubernetes (Cloud Containers) |

Версия словаря: **2026-05-16 v1.0**. Обновляется по мере появления новых терминов и устоявшихся переводов.
