---
name: networking-translation-dictionary
delivery: reference
description: |
  Словарь терминологии сетевых технологий для перевода технических статей
  с английского и немецкого на русский. Покрывает TCP/IP, маршрутизацию,
  коммутацию, туннели и overlay, DNS, HTTP/QUIC, TLS, cloud networking,
  балансировку, CDN, сетевую безопасность (firewall/WAF/IDS/IPS/DDoS),
  современные архитектуры (SASE/SSE/SD-WAN/Zero Trust).

  Источники: переводы Хабра (Cisco, Cloudflare, RFC), документация Selectel
  и Yandex Cloud, Cloud4box, OSP.ru, статьи bitworks.software по EVPN/VXLAN,
  методология «Альянса ПРО».
activation:
  - "сети"
  - "networking"
  - "network"
  - "tcp/ip"
  - "tcp ip"
  - "bgp"
  - "ospf"
  - "vxlan"
  - "vpn"
  - "vpc"
  - "subnet"
  - "nat"
  - "dns"
  - "cdn"
  - "load balancer"
  - "балансировщик"
  - "firewall"
  - "файрвол"
  - "waf"
  - "ids"
  - "ips"
  - "ddos"
  - "sase"
  - "sse"
  - "sd-wan"
  - "zero trust"
  - "ztna"
  - "tls"
  - "ssl"
  - "quic"
  - "http/3"
  - "http/2"
  - "websocket"
  - "grpc"
  - "ipv4"
  - "ipv6"
  - "vlan"
  - "stp"
  - "mpls"
  - "ipsec"
  - "wireguard"
  - "anycast"
---

# Networking Translation Dictionary

Словарь для переводчиков статей по сетевым технологиям. Дополняет `k8s-translation-dictionary` (для K8s-сетевой подсистемы — Service, Ingress, CNI, Network Policy) и `devops-translation-dictionary` (для сетевой инфраструктуры в облаке — VPC, NAT, балансировщики). Может активироваться параллельно с ними.

**Не догма.** Отражает консенсус русскоязычного сетевого сообщества (переводчики Cisco-курсов на Хабре, документация Selectel/Yandex Cloud, OSP.ru, переводы RFC) на 2026 год.

## Принципы

1. **Аббревиатуры протоколов и сервисов — оригинал.** IP, TCP, UDP, BGP, OSPF, DNS, DHCP, VXLAN, MPLS, IPSec, TLS, ACL, NAT, CIDR, VPC, WAF, IDS, IPS, DDoS. При первом упоминании сложной — расшифровка в скобках.
2. **Базовые роли оборудования — переводятся.** «Маршрутизатор», «коммутатор», «шлюз», «межсетевой экран». Допустимы транслитерации («роутер», «свитч», «файрвол») — в разговорных и блоговых текстах.
3. **Адреса и идентификаторы — оригинал.** `IP-адрес`, `MAC-адрес`, `IPv4`, `IPv6`, `CIDR`, `AS-номер`.
4. **Имена облачных сервисов — оригинал.** `VPC`, `Subnet`, `NAT Gateway`, `Internet Gateway`, `Transit Gateway`, `Route Table` — пишутся как в документации AWS/GCP/Azure. В нарративе — соответствующий перевод.
5. **Команды CLI — оригинал.** `ping`, `traceroute`, `tcpdump`, `nslookup`, `dig`, `ip route`, `iptables`, `nft`. Не склоняются.
6. **В одном тексте — один вариант для каждого термина.** Не смешивай «маршрутизатор» и «роутер», «коммутатор» и «свитч» в соседних абзацах.

## Раздел 1. Базовые понятия и модели

| English | Русский (рекомендуемый) | Альтернативы | Комментарий |
|---------|-------------------------|--------------|-------------|
| Networking | сети / сетевые технологии | — | «Сетевые технологии», «сетевая инфраструктура» |
| Computer network | компьютерная сеть | — | — |
| Protocol | протокол | — | «Сетевой протокол» |
| Stack (protocol stack) | стек (протоколов) | — | «Стек TCP/IP», «сетевой стек» |
| Layer | уровень / слой | — | «Сетевой уровень», «L3-уровень» |
| OSI model | модель OSI | — | — |
| TCP/IP model | модель TCP/IP | — | — |
| Layer 2 / L2 | L2 / канальный уровень | — | «На L2», «на канальном уровне» |
| Layer 3 / L3 | L3 / сетевой уровень | — | — |
| Layer 4 / L4 | L4 / транспортный уровень | — | — |
| Layer 7 / L7 | L7 / прикладной уровень | — | «L7-балансировщик», «L7-фильтрация» |
| Bandwidth | пропускная способность / bandwidth | — | — |
| Throughput | пропускная способность | — | Отличать от bandwidth: throughput — фактическая, bandwidth — теоретическая |
| Latency | задержка / латентность | — | «Сетевая задержка» |
| Jitter | джиттер | — | — |
| Packet loss | потеря пакетов | — | — |
| QoS (Quality of Service) | QoS / качество обслуживания | — | При первом упоминании — расшифровка |
| Bit / Byte | бит / байт | — | — |
| Packet | пакет | — | На L3 |
| Frame | кадр | — | На L2 |
| Segment | сегмент | — | На L4 (TCP) |
| Datagram | дейтаграмма | — | На L4 (UDP) |
| Payload | полезная нагрузка / payload | — | — |
| Header | заголовок | — | «Заголовок пакета», «HTTP-заголовок» |
| Encapsulation | инкапсуляция | — | — |

## Раздел 2. Сетевое оборудование

| English | Русский | Комментарий |
|---------|---------|-------------|
| Router | маршрутизатор / роутер | «Маршрутизатор» — официально, «роутер» — разговорно, но также используется в технических текстах. В одном тексте — один вариант |
| Switch | коммутатор / свитч | «Коммутатор» — официально, «свитч» — разговорно |
| Hub | концентратор / хаб | Устаревшее устройство. «Хаб» — устоялось |
| Bridge | мост | На L2, между сегментами |
| Gateway | шлюз | «Шлюз по умолчанию» — `default gateway` |
| Default gateway | шлюз по умолчанию | — |
| Modem | модем | Не склоняется по модели, но склоняется как существительное: модема, модему |
| Access Point (AP) | точка доступа (AP) | Wi-Fi |
| Firewall | межсетевой экран / файрвол / firewall | «Межсетевой экран» — официально, «файрвол» — практический термин, «firewall» — допустимо в технических статьях |
| Next-Generation Firewall (NGFW) | NGFW / межсетевой экран нового поколения | — |
| Load balancer | балансировщик нагрузки | Склоняется: балансировщика, балансировщику |
| Proxy server | прокси-сервер / прокси | Через дефис |
| Reverse proxy | reverse proxy / обратный прокси | — |
| Forward proxy | forward proxy / прямой прокси | — |
| WAF (Web Application Firewall) | WAF | При первом упоминании — расшифровка |
| IDS (Intrusion Detection System) | IDS / система обнаружения вторжений | — |
| IPS (Intrusion Prevention System) | IPS / система предотвращения вторжений | — |
| NAS (Network Attached Storage) | NAS | Сетевое хранилище |
| SAN (Storage Area Network) | SAN | Сеть хранения данных |
| NIC (Network Interface Card) | NIC / сетевая карта / сетевой адаптер | — |

## Раздел 3. Адресация

| English | Русский | Комментарий |
|---------|---------|-------------|
| IP address | IP-адрес | Через дефис |
| IPv4 | IPv4 | Не «АйПи v4» |
| IPv6 | IPv6 | — |
| MAC address | MAC-адрес | Через дефис |
| Subnet | подсеть | Склоняется: подсети, подсетей |
| Subnet mask | маска подсети | — |
| CIDR (Classless Inter-Domain Routing) | CIDR | При первом упоминании — расшифровка |
| Prefix length | длина префикса / `/24` нотация | — |
| Public IP | публичный IP / public IP | — |
| Private IP | приватный IP / частный IP | — |
| RFC 1918 (private ranges) | приватные диапазоны RFC 1918 | — |
| Loopback (127.0.0.1, ::1) | loopback / локальная петля | «Loopback-адрес» |
| Multicast | multicast / групповая адресация | — |
| Broadcast | broadcast / широковещание | — |
| Unicast | unicast / однонаправленная адресация | — |
| Anycast | anycast | Чаще оставляют английский |
| DHCP (Dynamic Host Configuration Protocol) | DHCP | При первом упоминании — расшифровка |
| Static IP | статический IP / static IP | — |
| Dynamic IP | динамический IP | — |
| NAT (Network Address Translation) | NAT / трансляция сетевых адресов | — |
| SNAT (Source NAT) | SNAT | — |
| DNAT (Destination NAT) | DNAT | — |
| PAT (Port Address Translation) | PAT | — |
| ARP (Address Resolution Protocol) | ARP | — |
| RARP | RARP | — |
| NDP (Neighbor Discovery Protocol) | NDP | Для IPv6 |

## Раздел 4. Транспортный и сетевой уровни

| English | Русский | Комментарий |
|---------|---------|-------------|
| TCP (Transmission Control Protocol) | TCP | — |
| UDP (User Datagram Protocol) | UDP | — |
| QUIC | QUIC | RFC 9000. Не «КВИК» |
| ICMP | ICMP | — |
| IP (protocol) | протокол IP / IP | — |
| MTU (Maximum Transmission Unit) | MTU | — |
| MSS (Maximum Segment Size) | MSS | — |
| TTL (Time To Live) | TTL | — |
| Port | порт | Склоняется. «TCP-порт», «UDP-порт» |
| Well-known ports | well-known порты / системные порты | 0–1023 |
| Ephemeral port | эфемерный порт | — |
| Socket | сокет | — |
| Three-way handshake | трёхэтапное рукопожатие / three-way handshake | TCP SYN/SYN-ACK/ACK |
| Connection | соединение | — |
| Session | сессия | — |
| Stateful / Stateless | stateful / stateless | Часто оставляют английский |
| Congestion | перегрузка | — |
| Congestion control | управление перегрузкой / congestion control | — |
| Flow control | управление потоком | — |
| Retransmission | переотправка / retransmission | — |
| Window size | размер окна | TCP window |
| Sliding window | скользящее окно | — |
| Sequence number | номер последовательности / sequence number | — |
| ACK / SYN / FIN / RST | ACK / SYN / FIN / RST | Флаги TCP, не переводить |
| Half-open connection | half-open соединение | — |
| Half-closed connection | half-closed соединение | — |

## Раздел 5. Маршрутизация

| English | Русский | Комментарий |
|---------|---------|-------------|
| Routing | маршрутизация | — |
| Route | маршрут / route | «Сетевой маршрут», «таблица маршрутов» |
| Routing table | таблица маршрутизации | — |
| Static routing | статическая маршрутизация | — |
| Dynamic routing | динамическая маршрутизация | — |
| Routing protocol | протокол маршрутизации | — |
| BGP (Border Gateway Protocol) | BGP | При первом упоминании — расшифровка |
| eBGP / iBGP | eBGP / iBGP | External / Internal BGP |
| OSPF (Open Shortest Path First) | OSPF | — |
| IS-IS | IS-IS | — |
| RIP (Routing Information Protocol) | RIP | — |
| EIGRP | EIGRP | Cisco proprietary |
| AS (Autonomous System) | AS / автономная система | «AS-номер» |
| ASN (AS Number) | ASN / номер AS | — |
| Peering | peering / пиринг | «BGP peering», «пиринговое соглашение» |
| Transit | transit / транзит | «Transit provider» |
| Route reflector | route reflector | Не переводить |
| Hop | хоп / hop / переход | «Next hop» → «следующий хоп» |
| Metric | метрика | «Метрика маршрута» |
| TTL (in routing) | TTL | — |
| Convergence | конвергенция / сходимость | «Сходимость маршрутизации» |
| Loop | петля | «Маршрутная петля» |
| Black hole | чёрная дыра / blackhole | — |
| BFD (Bidirectional Forwarding Detection) | BFD | — |
| ECMP (Equal-Cost Multi-Path) | ECMP | — |
| Default route | маршрут по умолчанию / default route | — |
| Route table | таблица маршрутов | — |
| Routing daemon | демон маршрутизации | — |
| FRR / Quagga / BIRD | FRR / Quagga / BIRD | Названия демонов |

## Раздел 6. Коммутация и L2

| English | Русский | Комментарий |
|---------|---------|-------------|
| Switching | коммутация | — |
| VLAN (Virtual LAN) | VLAN | При первом упоминании — расшифровка |
| Trunk port | trunk-порт / транковый порт | — |
| Access port | access-порт / порт доступа | — |
| Native VLAN | native VLAN | — |
| 802.1Q | 802.1Q | Стандарт тегирования VLAN |
| STP (Spanning Tree Protocol) | STP | — |
| RSTP, MSTP | RSTP, MSTP | — |
| LACP (Link Aggregation Control Protocol) | LACP | — |
| EtherChannel / Port channel | EtherChannel / port channel | — |
| LAG (Link Aggregation Group) | LAG | — |
| Bonding | bonding / агрегация интерфейсов | Linux |
| Bridge domain | bridge domain | — |
| MAC table / CAM table | таблица MAC / CAM-таблица | — |
| Broadcast domain | домен широковещания | — |
| Collision domain | домен коллизий | Устаревшее, исторический термин |
| Frame | кадр | — |
| Ethernet | Ethernet | — |
| Gigabit Ethernet (GbE) | Gigabit Ethernet | — |
| 10G / 25G / 40G / 100G | 10G / 25G / 40G / 100G | Скорости |
| QSFP, SFP | QSFP, SFP | Форм-факторы трансиверов |
| Half-duplex / Full-duplex | half-duplex / full-duplex | — |
| Auto-negotiation | автосогласование / auto-negotiation | — |
| Jumbo frames | jumbo frames | — |

## Раздел 7. Туннели, Overlay, Underlay

| English | Русский | Комментарий |
|---------|---------|-------------|
| Tunnel | туннель | Склоняется: туннеля, туннелю |
| Tunneling | туннелирование | — |
| Overlay network | overlay-сеть / наложенная сеть | «Наложенная сеть» — официальный перевод |
| Underlay network | underlay-сеть / опорная сеть / базовая сеть | — |
| Encapsulation | инкапсуляция | — |
| VXLAN | VXLAN | Не переводится |
| VNI / VNID (VXLAN Network Identifier) | VNI / VNID | — |
| VTEP (VXLAN Tunnel Endpoint) | VTEP | Не переводить |
| NVE (Network Virtualization Edge) | NVE | — |
| GRE (Generic Routing Encapsulation) | GRE | — |
| GENEVE | GENEVE | — |
| MPLS (Multiprotocol Label Switching) | MPLS | — |
| Label, LSP (Label Switched Path) | label, LSP | — |
| LDP, RSVP-TE | LDP, RSVP-TE | — |
| Segment Routing (SR / SR-MPLS / SRv6) | Segment Routing / SR | — |
| IPSec | IPSec | Не «АйПи Сек» |
| IKE (Internet Key Exchange) | IKE / IKEv2 | — |
| ESP / AH (IPSec headers) | ESP / AH | — |
| Site-to-site VPN | site-to-site VPN | — |
| Client VPN / Remote access VPN | client VPN / VPN для удалённого доступа | — |
| WireGuard | WireGuard | Не переводится |
| OpenVPN | OpenVPN | — |
| L2TP, PPTP | L2TP, PPTP | — |
| SSL VPN | SSL VPN | Устаревший термин — теперь TLS VPN |
| Split tunneling | split tunneling / раздельное туннелирование | — |
| Full tunnel | full tunnel | — |
| EVPN | EVPN | Ethernet VPN |
| VPLS | VPLS | — |
| L2VPN / L3VPN | L2VPN / L3VPN | — |
| Spine-Leaf | Spine-Leaf | Архитектура ЦОД, не переводить |
| Fabric | fabric / фабрика | «Сетевая фабрика», «VXLAN-фабрика» |

## Раздел 8. DNS

| English | Русский | Комментарий |
|---------|---------|-------------|
| DNS (Domain Name System) | DNS | — |
| Domain | домен | «Доменное имя» |
| Domain name | доменное имя | — |
| FQDN (Fully Qualified Domain Name) | FQDN / полное доменное имя | — |
| Subdomain | поддомен / субдомен | — |
| TLD (Top-Level Domain) | TLD / домен верхнего уровня | — |
| Root domain | корневой домен | — |
| DNS zone | DNS-зона / зона DNS | — |
| Zone file | файл зоны | — |
| DNS record | DNS-запись / запись DNS | Через дефис |
| A / AAAA record | A-запись / AAAA-запись | — |
| CNAME | CNAME | — |
| MX record | MX-запись | — |
| TXT record | TXT-запись | — |
| NS record | NS-запись | — |
| SOA record | SOA-запись | — |
| PTR record | PTR-запись | Для reverse DNS |
| SRV record | SRV-запись | — |
| Authoritative DNS server | авторитативный DNS-сервер | — |
| Recursive resolver | рекурсивный резолвер / рекурсивный DNS-сервер | — |
| Caching resolver | кэширующий резолвер | — |
| Forwarder | DNS-форвардер | — |
| DNSSEC | DNSSEC | — |
| DNS-over-HTTPS (DoH) | DNS-over-HTTPS / DoH | — |
| DNS-over-TLS (DoT) | DNS-over-TLS / DoT | — |
| DNS-over-QUIC (DoQ) | DNS-over-QUIC | — |
| GeoDNS / GSLB (Global Server Load Balancing) | GeoDNS / GSLB | — |
| DNS hijacking | перехват DNS | — |
| DNS poisoning | отравление DNS-кэша | — |
| Reverse DNS / rDNS | reverse DNS / обратный DNS | — |
| TTL (DNS) | TTL DNS-записи | — |

## Раздел 9. HTTP стек и application protocols

| English | Русский | Комментарий |
|---------|---------|-------------|
| HTTP/1.0, HTTP/1.1 | HTTP/1.0, HTTP/1.1 | — |
| HTTP/2 | HTTP/2 | — |
| HTTP/3 | HTTP/3 | На базе QUIC |
| HTTPS | HTTPS | — |
| Request / Response | запрос / ответ | «HTTP-запрос», «HTTP-ответ» |
| Method (GET, POST, PUT, DELETE) | метод | — |
| Header | заголовок | «HTTP-заголовок» |
| Body | тело (запроса/ответа) | — |
| Status code | код состояния / status code | «200 OK», «404 Not Found» |
| Cookie | cookie / кука / куки | «Кука» — разговорное |
| Session | сессия | — |
| Cache | кэш | — |
| ETag | ETag | — |
| Connection: keep-alive | keep-alive соединение | — |
| Head-of-line blocking (HoL) | HoL blocking / блокировка начала очереди | Проблема HTTP/1 и TCP |
| Multiplexing | мультиплексирование | — |
| Server push | server push | — |
| Pipelining | пайплайнинг | — |
| Compression (gzip, brotli) | сжатие (gzip, brotli) | — |
| WebSocket | WebSocket | — |
| gRPC | gRPC | — |
| REST API | REST API | — |
| GraphQL | GraphQL | — |
| MQTT | MQTT | — |
| AMQP, Kafka protocol | AMQP, Kafka | — |
| SMTP, IMAP, POP3 | SMTP, IMAP, POP3 | — |
| FTP, SFTP | FTP, SFTP | — |
| SSH | SSH | — |
| Telnet | Telnet | — |

## Раздел 10. TLS / SSL и сертификаты

| English | Русский | Комментарий |
|---------|---------|-------------|
| TLS (Transport Layer Security) | TLS | — |
| SSL (Secure Sockets Layer) | SSL | Устарел, но термин остался |
| TLS 1.2 / TLS 1.3 | TLS 1.2 / TLS 1.3 | — |
| Handshake | рукопожатие / handshake | «TLS handshake», «TLS-рукопожатие» |
| Cipher suite | cipher suite / набор шифров | — |
| Certificate | сертификат | «TLS-сертификат», «SSL-сертификат» |
| Certificate Authority (CA) | удостоверяющий центр (CA) / центр сертификации | — |
| Root CA | корневой CA / корневой удостоверяющий центр | — |
| Intermediate CA | промежуточный CA | — |
| X.509 | X.509 | Стандарт сертификатов |
| Public key | открытый ключ / public key | — |
| Private key | закрытый ключ / private key | — |
| Key exchange | обмен ключами | — |
| Diffie-Hellman | Диффи-Хеллман | — |
| RSA, ECDSA, Ed25519 | RSA, ECDSA, Ed25519 | Алгоритмы |
| SAN (Subject Alternative Name) | SAN | В сертификате |
| CN (Common Name) | CN | — |
| Wildcard certificate | wildcard-сертификат | — |
| Self-signed certificate | самоподписанный сертификат | — |
| mTLS (Mutual TLS) | mTLS / взаимный TLS | — |
| TLS termination | терминация TLS | Расшифровка зашифрованного трафика на балансировщике/прокси |
| TLS passthrough | TLS passthrough | Прокидывание зашифрованного TLS на бэкенд без терминации |
| Certificate pinning | certificate pinning / привязка сертификата | — |
| Certificate revocation (CRL, OCSP) | отзыв сертификата (CRL, OCSP) | — |
| ACME (Let's Encrypt protocol) | ACME | — |
| Let's Encrypt | Let's Encrypt | — |
| cert-manager | cert-manager | Инструмент |

## Раздел 11. Cloud networking

| English | Русский | Комментарий |
|---------|---------|-------------|
| VPC (Virtual Private Cloud) | VPC | AWS, Google Cloud, Yandex Cloud. При первом упоминании — расшифровка |
| VNet | VNet / виртуальная сеть | Azure |
| Subnet | subnet / подсеть | В облаке чаще `subnet`. В нарративе — «подсеть» |
| Public subnet / Private subnet | public/private subnet | — |
| Internet Gateway (IGW) | Internet Gateway / интернет-шлюз | AWS |
| NAT Gateway | NAT Gateway / NAT-шлюз | — |
| Egress-only Internet Gateway | egress-only IGW | Для IPv6 |
| Transit Gateway | Transit Gateway | AWS |
| VPC Peering | VPC Peering / пиринг VPC | — |
| Route Table | таблица маршрутизации / route table | — |
| Security Group | Security Group / группа безопасности | — |
| Network ACL (NACL) | NACL / сетевой ACL | — |
| Elastic IP (EIP) | Elastic IP / EIP | AWS |
| Floating IP | floating IP / плавающий IP | OpenStack, VK Cloud |
| Availability Zone (AZ) | зона доступности / AZ | — |
| Region | регион | — |
| Edge location | edge-локация | — |
| PrivateLink / Service Endpoint | PrivateLink / приватная конечная точка | — |
| Direct Connect / ExpressRoute | Direct Connect / ExpressRoute | AWS / Azure |
| Cloud Interconnect | Cloud Interconnect | GCP |
| VPN Gateway | VPN Gateway / VPN-шлюз | — |
| Bastion host | bastion / бастион-хост | — |
| Jumpbox | jumpbox | — |

## Раздел 12. Балансировка нагрузки

| English | Русский | Комментарий |
|---------|---------|-------------|
| Load balancer (LB) | балансировщик нагрузки | — |
| L4 load balancer | L4-балансировщик / TCP-балансировщик | — |
| L7 load balancer | L7-балансировщик / HTTP-балансировщик | — |
| GSLB (Global Server Load Balancing) | GSLB | — |
| Round robin | round robin / круговой / циклический | — |
| Weighted round robin | weighted round robin / взвешенный | — |
| Least connections | least connections | — |
| IP hash | IP hash | — |
| Sticky session / Session affinity | sticky session / привязка сессии | — |
| Health check | health check / проверка работоспособности | — |
| Active health check | активная проверка работоспособности | NGINX Plus, Envoy. При первом упоминании — «active health check» |
| Backend / Upstream | backend / upstream / бэкенд | — |
| Pool | pool / пул | «Пул бэкендов» |
| Frontend / Listener | frontend / listener | В Gateway API — поле `listeners`, см. k8s-словарь |
| Target group | target group / целевая группа | AWS |
| Algorithm | алгоритм (балансировки) | — |
| Circuit breaking | circuit breaking (размыкатель цепи) | Латиницей с пояснением. «Прерывание цепи» — НЕ использовать |
| Circuit breaker | circuit breaker (предохранитель / автоматический выключатель) | Латиницей |
| Rate limiting | ограничение частоты запросов | Глобальное / локальное — global / local rate limiting |
| Bare-metal line rate | линейная скорость на bare-metal | При первом упоминании — пояснение «обработка на полной скорости интерфейса» |
| Line rate | линейная скорость | Скорость интерфейса без потерь |
| Double hop penalty | штраф за двойной hop | Контекст service mesh: sidecar добавляет лишний hop |
| Update latency (control plane) | задержка обновления | Время от изменения конфига до применения на data plane |
| Active-active / Active-passive | active-active / active-passive | — |
| Failover | failover / переключение при отказе | — |
| HA (High Availability) | HA / высокая доступность | — |
| Anycast | anycast | — |
| Octavia | Octavia | OpenStack LB |
| HAProxy | HAProxy | — |
| NGINX | NGINX | — |
| Envoy | Envoy | — |
| Traefik | Traefik | — |
| F5 / NetScaler | F5 / NetScaler | Имена производителей |

## Раздел 13. CDN и edge

| English | Русский | Комментарий |
|---------|---------|-------------|
| CDN (Content Delivery Network) | CDN / сеть доставки контента | При первом упоминании — расшифровка |
| Edge | edge / периферия | «Edge-сервер», «edge-сеть» |
| Edge computing | edge computing / периферийные вычисления | — |
| Edge node | edge-нода / периферийный узел | — |
| Origin | origin / origin-сервер / исходный сервер | — |
| Origin shield | origin shield | — |
| Cache hit / Cache miss | cache hit / cache miss / попадание/промах в кэш | — |
| Cache warming | прогрев кэша | — |
| Cache invalidation / Purge | инвалидация кэша / purge | — |
| TTL (in CDN) | TTL кэша | — |
| PoP (Point of Presence) | PoP / точка присутствия | — |
| Anycast | anycast | — |
| Geolocation routing | геомаршрутизация | — |
| Streaming (HLS, DASH) | стриминг (HLS, DASH) | — |
| Adaptive bitrate | адаптивный битрейт | — |
| Cloudflare, Fastly, Akamai, CloudFront | Cloudflare, Fastly, Akamai, CloudFront | Имена сервисов |
| CDN77, EdgeCenter, NGENIX | CDN77, EdgeCenter, NGENIX | Российские CDN |

## Раздел 14. Сетевая безопасность

| English | Русский | Комментарий |
|---------|---------|-------------|
| Firewall | межсетевой экран / файрвол / firewall | См. раздел 2 |
| Stateful firewall | stateful firewall | — |
| Stateless firewall | stateless firewall | — |
| NGFW | NGFW | — |
| WAF (Web Application Firewall) | WAF | — |
| IDS (Intrusion Detection System) | IDS / система обнаружения вторжений | — |
| IPS (Intrusion Prevention System) | IPS / система предотвращения вторжений | — |
| HIDS / NIDS | HIDS / NIDS | Host- / Network-based |
| DPI (Deep Packet Inspection) | DPI / глубокая инспекция пакетов | — |
| ACL (Access Control List) | ACL / список контроля доступа | — |
| Port scan | сканирование портов | — |
| Port forwarding | проброс портов / port forwarding | — |
| Reverse SSH tunnel | обратный SSH-туннель | — |
| MITM (Man-in-the-Middle) attack | MITM-атака / атака «человек посередине» | — |
| Spoofing (IP, MAC, DNS) | спуфинг (IP, MAC, DNS) / подмена | — |
| Sniffing | сниффинг / прослушивание | — |
| DDoS (Distributed Denial of Service) | DDoS-атака | При первом упоминании — расшифровка. «DDoS» не склоняется |
| DoS | DoS | — |
| SYN flood | SYN flood / SYN-флуд | — |
| UDP flood | UDP flood | — |
| Amplification attack | amplification / атака с усилением | — |
| Reflection attack | reflection / атака с отражением | — |
| Volumetric attack | объёмная атака | — |
| Application-layer attack | атака уровня приложений / L7-атака | — |
| Rate limiting | rate limiting / ограничение скорости запросов | — |
| Blackholing / Sinkholing | blackholing / sinkholing | — |
| Bot mitigation | защита от ботов | — |
| Bot management | bot management | — |
| Captcha | капча / CAPTCHA | — |
| Honeypot | honeypot | — |
| SIEM | SIEM | Security Information and Event Management |
| SOC (Security Operations Center) | SOC / центр безопасности | — |
| Zero-day | zero-day / уязвимость нулевого дня | — |
| Patching | патчинг / установка патчей | — |

## Раздел 15. Современные архитектуры

| English | Русский | Комментарий |
|---------|---------|-------------|
| Zero Trust | Zero Trust / нулевое доверие | При первом упоминании — пояснение |
| Zero Trust Network Access (ZTNA) | ZTNA | — |
| SASE (Secure Access Service Edge) | SASE / пограничный сервис безопасного доступа | При первом упоминании — расшифровка |
| SSE (Security Service Edge) | SSE | Подмножество SASE без сетевой части |
| SD-WAN (Software-Defined WAN) | SD-WAN | — |
| SDN (Software-Defined Networking) | SDN / программно-определяемые сети | — |
| NFV (Network Functions Virtualization) | NFV / виртуализация сетевых функций | — |
| Network slicing | network slicing | 5G |
| Microsegmentation | микросегментация | — |
| East-west traffic | east-west трафик | Внутрицодовый |
| North-south traffic | north-south трафик | Между ЦОД и интернетом |
| Service mesh | Service Mesh / сервисная сетка | См. также k8s-dictionary |
| Sidecar proxy | sidecar proxy | — |
| Envoy, Istio, Linkerd | Envoy, Istio, Linkerd | — |
| eBPF | eBPF | extended Berkeley Packet Filter |
| XDP (Express Data Path) | XDP | — |
| Cilium | Cilium | — |
| Tetragon | Tetragon | — |
| Cloudflare Tunnel | Cloudflare Tunnel | — |
| Tailscale | Tailscale | WireGuard mesh |
| Twingate | Twingate | ZTNA-решение |
| Identity Provider (IdP) | IdP / провайдер идентификации | — |
| SSO (Single Sign-On) | SSO / единый вход | — |
| MFA (Multi-Factor Authentication) | MFA / многофакторная аутентификация | — |
| Federated identity | федеративная идентификация | — |
| BeyondCorp | BeyondCorp | Модель Google Zero Trust |

## Раздел 16. Глаголы и действия

| English | Русский | Комментарий |
|---------|---------|-------------|
| to route | маршрутизировать | «Маршрутизировать пакеты» |
| to forward | переслать / форвардить | «Forward-портов» — «проброс портов» |
| to switch (L2) | коммутировать | — |
| to encapsulate | инкапсулировать | — |
| to decapsulate | декапсулировать | — |
| to advertise (routes) | анонсировать (маршруты) | — |
| to propagate | распространять / propagate | «BGP-маршруты распространяются» |
| to peer | устанавливать peering / пириться | «Пириться» — разговорно |
| to filter | фильтровать | — |
| to drop (packets) | отбрасывать (пакеты) | «Drop packets» |
| to allow / deny | разрешить / запретить | «Allow rule», «deny rule» |
| to NAT (verb) | NAT-ить / трансляция через NAT | — |
| to balance (load) | балансировать (нагрузку) | — |
| to resolve (DNS) | резолвить / разрешать (DNS-имя) | — |
| to tunnel | туннелировать | — |
| to encrypt / decrypt | шифровать / дешифровать | — |
| to sniff | сниффить / прослушивать | — |
| to scan (ports) | сканировать (порты) | — |
| to mirror (traffic) | зеркалировать (трафик) | «Port mirroring» |
| to shape (traffic) | шейпить (трафик) | «Traffic shaping» |
| to throttle | дросселировать / троттлить | — |
| to fail over | переключаться при отказе / делать failover | — |

## Раздел 17. Падежные формы

### Маршрутизатор / роутер

- **Маршрутизатор**: маршрутизатора, маршрутизатору, маршрутизатором; мн.ч. маршрутизаторы, маршрутизаторов
- **Роутер**: роутера, роутеру, роутером

### Коммутатор / свитч

- **Коммутатор**: коммутатора, коммутатору, коммутатором
- **Свитч**: свитча, свитчу, свитчом

### IP, TCP, UDP, BGP, OSPF, VLAN, MAC, NAT, VPN, DNS

**Не склоняются.** Род — мужской: «IP передал», «TCP установил». В составных словах через дефис: «IP-адрес», «TCP-сегмент», «BGP-сессия», «DNS-запрос», «MAC-таблица», «VLAN-тег», «NAT-шлюз», «VPN-туннель».

### Cloudflare, Cisco, Juniper, Mikrotik

**Не склоняются.** «От Cloudflare», «для Cisco», «через Mikrotik». НЕ «Циской», «Микротиком».

### Файрвол / firewall

- **Файрвол** (м.р.): файрвола, файрволу, файрволом
- **Firewall** (не склоняется): «через firewall», «правила firewall»
- **Межсетевой экран**: межсетевого экрана, межсетевому экрану

### DDoS / DoS

**Не склоняются.** «DDoS-атака», «защита от DDoS», «после DoS». Не «ДДоСа», «ДоСом».

### Балансировщик

«Балансировщик», «балансировщика», «балансировщику», «балансировщиком». Мн.ч.: «балансировщики», «балансировщиков».

### Туннель

«Туннель», «туннеля», «туннелю», «туннелем». Мн.ч.: «туннели», «туннелей». **Не** «тунель» — две `н`.

### Пинг / Ping

- **Пинг** (м.р., разг.): пинга, пингу, пингом. «Сделать пинг»
- **Ping** (команда): не склоняется, строчная. «Выполнить `ping`», «команда `ping`»

### Подсеть

Женский род: «подсеть», «подсети», «подсетью». Мн.ч.: «подсети», «подсетей».

### CIDR

Не склоняется: «нотация CIDR», «в формате CIDR».

## Раздел 18. Типовые ошибки переводчика

### 1. Смешение «маршрутизатор» и «роутер» в одном тексте

```
✗ «Маршрутизатор пересылает пакет. Роутер также проверяет TTL.»
✓ «Маршрутизатор пересылает пакет. Маршрутизатор также проверяет TTL.»
```

В одном тексте — один вариант термина.

### 2. Перевод аббревиатур протоколов

```
✗ «протокол ВРГП», «протокол ОПФ»
✓ «протокол BGP», «протокол OSPF»
```

Аббревиатуры протоколов **не переводятся** — это международные стандарты.

### 3. «Сеть» как перевод для всего подряд

```
✗ «облачная сеть» (для VPC)
✓ «VPC» / «виртуальная частная сеть VPC»

✗ «частная сеть AWS» (для PrivateLink)
✓ «AWS PrivateLink»
```

В облаке VPC ≠ просто «сеть». Сохраняй технический термин.

### 4. Калька «является»

```
✗ «BGP является основным протоколом маршрутизации в интернете»
✓ «BGP — основной протокол маршрутизации в интернете»
```

### 5. «Switch» как «переключатель»

```
✗ «Сетевой переключатель пересылает кадры»
✓ «Коммутатор пересылает кадры»
```

`switch` в сетевом контексте — всегда «коммутатор» (или «свитч»), не «переключатель».

### 6. «Gateway» как «вход»

```
✗ «Сетевой вход» (для default gateway)
✓ «Шлюз по умолчанию»
```

### 7. Перевод имён облачных сервисов

```
✗ «Виртуальное частное облако» (для VPC в коде)
✓ «VPC» — имя сервиса AWS/GCP/Azure
```

В нарративе расшифровка допустима при первом упоминании, но имя сервиса остаётся `VPC`.

### 8. «Pipeline» сети vs CI/CD pipeline

В сетевых статьях встречается `data pipeline`, `processing pipeline` — это «конвейер обработки данных», не путать с DevOps-pipeline.

### 9. «Latency» как «отставание»

```
✗ «Сетевое отставание»
✓ «Сетевая задержка» / «латентность»
```

### 10. «Throughput» = «bandwidth»

Разные понятия:
- **Bandwidth** — теоретическая пропускная способность канала (например, 1 Гбит/с)
- **Throughput** — фактическая, измеренная пропускная способность

Перевод одинаковый — «пропускная способность», но в контексте сравнения теории и факта нужно уточнять: «теоретическая пропускная способность канала (bandwidth) 1 Гбит/с, фактическая (throughput) — 800 Мбит/с».

### 11. Перевод флагов TCP

```
✗ «Пакет с флагом ПОДТВЕРЖДЕНИЕ»
✓ «Пакет с флагом ACK»
```

TCP-флаги (SYN, ACK, FIN, RST, PSH, URG) не переводятся.

### 12. Перевод команд CLI

```
✗ «Запустить команду пинг»
✓ «Запустить `ping`» / «выполнить команду `ping`»
```

Команды (`ping`, `traceroute`, `tcpdump`, `dig`, `ip route`) — оригинал, строчная буква.

## Раздел 19. Чек-лист переводчика сетевой статьи

Перед сдачей литерального перевода пройди:

- [ ] **Аббревиатуры протоколов** (IP, TCP, UDP, BGP, OSPF, DNS, DHCP, VXLAN, MPLS, IPSec, TLS, ACL, NAT, CIDR, WAF, DDoS) — не переведены
- [ ] **Имена облачных сервисов** (VPC, VNet, NAT Gateway, Internet Gateway, Transit Gateway, Direct Connect, ExpressRoute) — не переведены и не транслитерированы
- [ ] **Команды CLI** (`ping`, `traceroute`, `tcpdump`, `dig`, `nslookup`, `ip route`, `iptables`) — оригинал, строчная буква
- [ ] **Согласованность транслитерации** — «маршрутизатор» ИЛИ «роутер» во всём тексте, не смесь
- [ ] **TCP-флаги** (SYN, ACK, FIN, RST, PSH, URG) — оригинал
- [ ] **Имена производителей и сервисов** (Cisco, Juniper, Cloudflare, Akamai, Fastly, Cilium, Envoy, Istio, NGINX, HAProxy) — оригинал
- [ ] **DNS-типы записей** (A, AAAA, CNAME, MX, TXT, NS, SOA, PTR, SRV) — оригинал
- [ ] **Bandwidth ≠ Throughput** — разница сохранена, при необходимости — уточнение в скобках
- [ ] **Latency** переведено как «задержка» или «латентность», не «отставание»
- [ ] **Адреса с дефисами** — «IP-адрес», «MAC-адрес», «AS-номер»
- [ ] **Cloudflare/Cisco/Juniper не склоняются** — «от Cloudflare», не «Циской»
- [ ] **«Туннель» — две `н`** — «туннель», «туннеля»
- [ ] **Калек избегли** — нет «является», «позволяет»
- [ ] **Кавычки** — «ёлочки»
- [ ] **Атрибуция оригинала** — блок в конце

## Что делать с новыми терминами

1. Проверь IETF RFC и официальную документацию протокола (https://www.rfc-editor.org/) — английская эталонная терминология.
2. Проверь переводы Хабра по тегу `сетевые технологии` и публикации Cisco-курсов.
3. Проверь документацию Selectel, Yandex Cloud, VK Cloud на русском — особенно для cloud networking.
4. Если нигде нет — оставь **в оригинале** + пометь `[прим. перев.: устоявшегося перевода нет, оставлен оригинал]`.

## Источники

| Источник | Назначение |
|----------|-----------|
| RFC Editor — https://www.rfc-editor.org/ | Эталонная английская терминология протоколов |
| Хабр, тег «сетевые технологии» — https://habr.com/ru/hubs/network_technologies/ | Переводы и оригинальные статьи русскоязычного сетевого сообщества |
| Cloudflare Learning Center (RU) — https://www.cloudflare.com/learning/ | Глоссарий сетевой безопасности и SASE |
| Selectel Docs — https://docs.selectel.ru/ | Cloud networking на русском |
| Yandex Cloud Docs — https://yandex.cloud/ru/docs/ | VPC, NAT, балансировщики на русском |
| OSP.ru — https://www.osp.ru/ | Журнал «Сети/Network World», классическая русская сетевая терминология |
| bitworks.software — EVPN/VXLAN | Глубокие технические статьи |
| Cisco Networking Academy (RU) | Канонические переводы Cisco-терминологии |
| Альянс ПРО (tran.su) | Методология «русский [англ.]» для составных понятий |

Версия словаря: **2026-05-16 v1.0**.

## Связь с другими словарями

Сетевой словарь часто активируется параллельно с другими:

- **K8s + Networking** — статья про CNI (Calico, Cilium), Service Mesh (Istio, Linkerd), Ingress, Network Policy. Подключаются оба словаря.
- **DevOps + Networking** — статья про cloud networking в Terraform (VPC, subnet, security group), про балансировщики в CI/CD pipeline. Подключаются оба.
- **Все три (K8s + DevOps + Networking)** — статья «GitOps для multi-cluster Kubernetes с Cilium и BGP». Активируются все три словаря.

При конфликте терминов — приоритет за словарём, более релевантным теме статьи. Полные правила приоритизации — в `references/translation-standards.md`, секция «Приоритеты при множественной активации».
