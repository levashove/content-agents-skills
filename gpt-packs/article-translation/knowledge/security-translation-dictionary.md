---
name: security-translation-dictionary
delivery: reference
description: |
  Словарь терминологии информационной безопасности для перевода технических статей
  с английского и немецкого на русский. Покрывает CIA triad, типы атак (phishing,
  malware, ransomware, DDoS, OWASP Top 10), уязвимости (CVE, CWE, CVSS), threat
  modeling (STRIDE, MITRE ATT&CK), криптографию, IAM, application/cloud/container
  security, supply chain, SOC/SIEM/SOAR/EDR/XDR, compliance (152-ФЗ, ФСТЭК, ГОСТ).

  Источники: переводы Хабра (Positive Technologies, Solar, Kaspersky, BI.ZONE,
  Group-IB), документация регуляторов РФ (ФСТЭК, ФСБ, Роскомнадзор), глоссарий
  Kaspersky, NIST Glossary, методология «Альянса ПРО».
activation:
  - "security"
  - "ib"
  - "иб"
  - "информационная безопасность"
  - "кибербезопасность"
  - "cybersecurity"
  - "infosec"
  - "appsec"
  - "devsecops"
  - "уязвимость"
  - "vulnerability"
  - "cve"
  - "cwe"
  - "cvss"
  - "owasp"
  - "mitre att&ck"
  - "attack"
  - "атака"
  - "exploit"
  - "эксплойт"
  - "phishing"
  - "фишинг"
  - "malware"
  - "вредоносное по"
  - "ransomware"
  - "вымогатель"
  - "sql injection"
  - "xss"
  - "csrf"
  - "rce"
  - "threat model"
  - "threat modeling"
  - "моделирование угроз"
  - "stride"
  - "kill chain"
  - "rbac"
  - "iam"
  - "oauth"
  - "oidc"
  - "saml"
  - "jwt"
  - "mfa"
  - "sso"
  - "encryption"
  - "шифрование"
  - "криптография"
  - "cryptography"
  - "pki"
  - "sast"
  - "dast"
  - "sca"
  - "siem"
  - "soc"
  - "soar"
  - "edr"
  - "xdr"
  - "mdr"
  - "ndr"
  - "sbom"
  - "slsa"
  - "sigstore"
  - "incident response"
  - "152-фз"
  - "фстэк"
  - "фсб"
  - "кии"
  - "госсопка"
  - "gdpr"
  - "pci dss"
  - "hipaa"
  - "iso 27001"
  - "soc 2"
---

# Security Translation Dictionary

Словарь для переводчиков статей по информационной безопасности (ИБ) и кибербезопасности. Покрывает международную и российскую специфику. Может активироваться параллельно с другими словарями: `security` + `k8s` (Pod Security, network policies), `security` + `networking` (firewall, IDS, Zero Trust), `security` + `databases` (SQL injection, шифрование), `security` + `ml-ai` (prompt injection, model poisoning), `security` + `devops` (DevSecOps, SAST/DAST).

**Не догма.** Отражает консенсус русскоязычного ИБ-сообщества (Positive Technologies, Solar, Kaspersky, BI.ZONE, Group-IB, переводы Хабра, документация ФСТЭК) на 2026 год.

## Принципы

1. **Аббревиатуры — оригинал.** CVE, CWE, CVSS, OWASP, RBAC, IAM, MFA, SSO, SAST, DAST, SCA, SIEM, SOC, SOAR, EDR, XDR, MDR, NDR, SBOM, SLSA, TLS, SSL, PKI, JWT, OAuth, OIDC, SAML, MITRE ATT&CK. При первом упоминании — расшифровка.
2. **Базовые понятия — переводятся.** «Уязвимость», «угроза», «риск», «атака», «инцидент», «шифрование», «фишинг», «вредоносное ПО».
3. **Имена групп атакующих (APT) — оригинал.** APT28, APT29, Lazarus, BlackBasta, LockBit. Не переводить.
4. **Имена CVE/CWE — оригинал.** `CVE-2024-12345`, `CWE-79`. Формат стандартный.
5. **Российская регуляторика — точные русские названия.** 152-ФЗ, 187-ФЗ, ФСТЭК, ФСБ, КИИ, ГосСОПКА, БДУ, ОРД. Не переводить английскими аналогами.
6. **ИБ vs ИТ-безопасность.** В русском чаще «ИБ» (информационная безопасность) или «кибербезопасность». «Cybersecurity» = «кибербезопасность», «security» в общем контексте = «безопасность» или «ИБ».
7. **«Хакер» vs «злоумышленник» vs «атакующий».** В техническом тексте — «атакующий» или «злоумышленник». «Хакер» — общий термин (включая этичных хакеров).

## Раздел 1. Базовые понятия

| English | Русский (рекомендуемый) | Альтернативы | Комментарий |
|---------|-------------------------|--------------|-------------|
| Information Security (InfoSec) | информационная безопасность / ИБ | — | «ИБ» — стандартная аббревиатура |
| Cybersecurity | кибербезопасность | — | — |
| IT Security | ИТ-безопасность | — | — |
| Threat | угроза | — | — |
| Vulnerability | уязвимость | — | Склоняется: уязвимости, уязвимостью |
| Risk | риск | — | — |
| Attack | атака | — | — |
| Attack vector | вектор атаки | — | — |
| Attack surface | поверхность атаки / attack surface | — | — |
| Threat actor | злоумышленник / атакующий / threat actor | — | — |
| Adversary | противник / злоумышленник | — | — |
| Hacker | хакер | — | Нейтральный термин. White hat / black hat — этичный / неэтичный |
| Insider threat | внутренняя угроза / insider threat | — | — |
| Incident | инцидент | — | «Инцидент ИБ», «инцидент безопасности» |
| Breach (data breach) | утечка (данных) / breach | — | — |
| Compromise | компрометация | — | «Компрометация системы» |
| Exposure | экспозиция / раскрытие | — | — |
| Asset | актив | — | «Информационный актив» |
| Defense in Depth | эшелонированная защита | — | См. Раздел 2 — канонический вариант. Не «оборона» |
| Security posture | состояние защищённости / security posture | — | — |
| Hardening | хардненинг / усиление защиты | — | — |
| Mitigation | mitigation / снижение риска / нейтрализация | — | — |
| Remediation | remediation / устранение | — | — |
| Patch | патч / исправление | — | Склоняется: патча, патчу |
| Patching | патчинг / установка патчей | — | — |
| Zero-day | zero-day / уязвимость нулевого дня | — | — |
| Exploit | эксплойт | — | Склоняется: эксплойта, эксплойту |
| Exploitation | эксплуатация (уязвимости) | — | — |
| Payload | payload / полезная нагрузка | — | В контексте атаки |
| Reconnaissance | разведка / reconnaissance | — | — |

## Раздел 2. CIA triad и принципы

| English | Русский | Комментарий |
|---------|---------|-------------|
| CIA triad | триада CIA | Confidentiality, Integrity, Availability |
| Confidentiality | конфиденциальность | — |
| Integrity | целостность | — |
| Availability | доступность | — |
| Non-repudiation | неотказуемость / non-repudiation | — |
| Authenticity | аутентичность / подлинность | — |
| Accountability | подотчётность / accountability | — |
| Least privilege | принцип минимальных привилегий | — |
| Need-to-know | принцип «нужно знать» | — |
| Separation of duties | разделение обязанностей | — |
| Fail-safe defaults | fail-safe defaults / безопасные значения по умолчанию | — |
| Security by design | security by design / безопасность по умолчанию | — |
| Privacy by design | privacy by design | — |
| Defense in depth | эшелонированная защита | — |

## Раздел 3. Типы атак

| English | Русский | Комментарий |
|---------|---------|-------------|
| Phishing | фишинг | Склоняется: фишинга, фишингу |
| Spear phishing | целевой фишинг / spear phishing | — |
| Whaling | whaling / атака на топ-менеджеров | — |
| Smishing (SMS phishing) | смишинг | — |
| Vishing (voice phishing) | вишинг | — |
| Social engineering | социальная инженерия | — |
| Pretexting | pretexting / претекстинг | — |
| Baiting | baiting | — |
| Malware | вредоносное ПО / malware / вредонос | — |
| Virus | вирус | — |
| Worm | червь | — |
| Trojan | троян / троянец | — |
| Rootkit | руткит | — |
| Spyware | шпионское ПО / spyware | — |
| Adware | adware / рекламное ПО | — |
| Keylogger | кейлоггер | — |
| Backdoor | бэкдор | — |
| Ransomware | программа-вымогатель / шифровальщик / ransomware | «Вымогатель» — устоявшийся термин в РФ |
| Cryptolocker / Cryptominer | криптолокер / криптомайнер | — |
| Botnet | ботнет | — |
| C2 / C&C (Command and Control) | C2 / C&C / командный сервер | — |
| Drive-by download | drive-by download | — |
| Watering hole attack | watering hole атака | — |
| Supply chain attack | атака на цепочку поставок | — |
| SQL injection (SQLi) | SQL-инъекция | — |
| NoSQL injection | NoSQL-инъекция | — |
| Cross-Site Scripting (XSS) | XSS / межсайтовый скриптинг | — |
| Reflected XSS | reflected XSS / отражённый XSS | — |
| Stored XSS | stored XSS / хранимый XSS | — |
| DOM-based XSS | DOM-based XSS | — |
| Cross-Site Request Forgery (CSRF) | CSRF / межсайтовая подделка запроса | — |
| Server-Side Request Forgery (SSRF) | SSRF | — |
| Remote Code Execution (RCE) | RCE / удалённое выполнение кода | — |
| Local File Inclusion (LFI) | LFI | — |
| Remote File Inclusion (RFI) | RFI | — |
| Path traversal | path traversal / обход каталога | — |
| Directory traversal | directory traversal | — |
| Command injection | command injection / инъекция команд | — |
| XML External Entity (XXE) | XXE | — |
| Buffer overflow | переполнение буфера / buffer overflow | — |
| Stack overflow / Heap overflow | stack overflow / heap overflow | — |
| Use-after-free | use-after-free | — |
| Race condition | состояние гонки / race condition | — |
| TOCTOU (Time-of-check to time-of-use) | TOCTOU | — |
| Man-in-the-Middle (MITM) | MITM / атака «человек посередине» | — |
| Replay attack | replay-атака / атака повтора | — |
| Session hijacking | session hijacking / перехват сессии | — |
| Brute force | брутфорс / перебор | — |
| Dictionary attack | словарная атака | — |
| Credential stuffing | credential stuffing | — |
| Password spraying | password spraying | — |
| Rainbow table | радужная таблица / rainbow table | — |
| DDoS / DoS | DDoS / DoS | См. также `networking-translation-dictionary` |
| Privilege escalation | повышение привилегий / privilege escalation | — |
| Lateral movement | lateral movement / горизонтальное перемещение | — |
| Persistence | persistence / закрепление в системе | — |
| Exfiltration | exfiltration / эксфильтрация / вывод данных | — |
| Living off the land (LOTL) | LOTL | — |
| Fileless attack | бесфайловая атака / fileless attack | — |

## Раздел 4. Уязвимости и каталоги

| English | Русский | Комментарий |
|---------|---------|-------------|
| CVE (Common Vulnerabilities and Exposures) | CVE | Формат: `CVE-2024-12345` |
| CWE (Common Weakness Enumeration) | CWE | Формат: `CWE-79` (XSS) |
| CVSS (Common Vulnerability Scoring System) | CVSS | CVSS 3.1, CVSS 4.0 |
| CVSS score | CVSS-оценка / оценка CVSS | 0.0-10.0 |
| NVD (National Vulnerability Database) | NVD | — |
| MITRE | MITRE | Имя организации |
| OWASP (Open Worldwide Application Security Project) | OWASP | — |
| OWASP Top 10 | OWASP Top 10 | — |
| OWASP ASVS | OWASP ASVS | Application Security Verification Standard |
| OWASP SAMM | OWASP SAMM | Software Assurance Maturity Model |
| OWASP ZAP | OWASP ZAP | Zed Attack Proxy |
| CAPEC (Common Attack Pattern Enumeration and Classification) | CAPEC | — |
| EPSS (Exploit Prediction Scoring System) | EPSS | — |
| KEV (Known Exploited Vulnerabilities) | KEV | CISA каталог |
| Patch Tuesday | Patch Tuesday | Microsoft |
| Bug bounty | bug bounty / программа поощрения за уязвимости | — |
| Responsible disclosure | responsible disclosure / ответственное раскрытие | — |
| Full disclosure | full disclosure / полное раскрытие | — |
| Coordinated disclosure | coordinated disclosure | — |
| Vulnerability management | управление уязвимостями | — |
| Scanner / Vulnerability scanner | сканер / сканер уязвимостей | Nessus, OpenVAS, Qualys |
| **БДУ ФСТЭК** | БДУ ФСТЭК / Банк данных угроз | Российский аналог |
| **ОРД ФСТЭК** | ОРД | Отраслевой реестр данных |

## Раздел 5. Threat Modeling

| English | Русский | Комментарий |
|---------|---------|-------------|
| Threat modeling | моделирование угроз / threat modeling | — |
| STRIDE | STRIDE | Microsoft framework |
| PASTA (Process for Attack Simulation and Threat Analysis) | PASTA | — |
| DREAD | DREAD | Microsoft framework |
| OCTAVE | OCTAVE | — |
| Trike | Trike | — |
| LINDDUN | LINDDUN | Privacy threat modeling |
| Attack tree | дерево атак / attack tree | — |
| Data flow diagram (DFD) | DFD / диаграмма потоков данных | — |
| Trust boundary | граница доверия / trust boundary | — |
| Threat actor / Adversary | актор угроз / противник | — |
| Threat intelligence (TI) | threat intelligence / TI / разведка угроз | — |
| TTPs (Tactics, Techniques, Procedures) | TTPs / тактики, техники, процедуры | — |
| IoC (Indicator of Compromise) | IoC / индикатор компрометации | — |
| IoA (Indicator of Attack) | IoA / индикатор атаки | — |
| Kill chain | kill chain / цепочка атаки | Lockheed Martin Cyber Kill Chain |
| Cyber Kill Chain | Cyber Kill Chain | 7 этапов |
| Unified Kill Chain | Unified Kill Chain | — |
| MITRE ATT&CK | MITRE ATT&CK | — |
| ATT&CK tactic | тактика ATT&CK | — |
| ATT&CK technique | техника ATT&CK | — |
| ATT&CK sub-technique | подтехника ATT&CK | — |
| ATT&CK matrix | матрица ATT&CK | Enterprise, Mobile, ICS |
| Adversary emulation | эмуляция противника / adversary emulation | — |
| Red team | red team / красная команда | — |
| Blue team | blue team / синяя команда | — |
| Purple team | purple team / фиолетовая команда | — |
| Tabletop exercise | tabletop exercise / штабные учения | — |
| Penetration testing (pentest) | пентест / тестирование на проникновение | — |
| Pentester | пентестер | — |
| Vulnerability assessment | оценка уязвимостей | — |
| Security audit | аудит безопасности | — |
| Compliance audit | комплаенс-аудит | — |

## Раздел 6. Криптография

| English | Русский | Комментарий |
|---------|---------|-------------|
| Cryptography | криптография | — |
| Encryption | шифрование | — |
| Decryption | расшифрование / дешифрование | «Расшифрование» — официальный термин ГОСТ, «дешифрование» — общепринятый |
| Cipher | шифр | — |
| Plaintext | открытый текст / plaintext | — |
| Ciphertext | шифротекст / ciphertext | — |
| Symmetric encryption | симметричное шифрование | — |
| Asymmetric encryption | асимметричное шифрование | — |
| Public-key cryptography | криптография с открытым ключом | — |
| Key | ключ | — |
| Public key | открытый ключ | — |
| Private key | закрытый ключ | — |
| Key pair | пара ключей | — |
| Key exchange | обмен ключами | — |
| Key derivation | производство ключа / key derivation | — |
| KDF (Key Derivation Function) | KDF | PBKDF2, scrypt, Argon2 |
| AES (Advanced Encryption Standard) | AES | AES-128, AES-256 |
| RSA | RSA | — |
| ECC (Elliptic Curve Cryptography) | ECC / эллиптическая криптография | — |
| ECDSA, EdDSA, Ed25519 | ECDSA, EdDSA, Ed25519 | — |
| Diffie-Hellman (DH) | Диффи-Хеллман / DH | — |
| ECDH | ECDH | — |
| Hash function | хеш-функция | — |
| Hash | хеш | — |
| MD5, SHA-1, SHA-256, SHA-3 | MD5, SHA-1, SHA-256, SHA-3 | — |
| HMAC | HMAC | — |
| Digital signature | электронная подпись / цифровая подпись | В РФ — «электронная подпись» (ЭП) |
| Salt | соль (для хешей) | — |
| Pepper | pepper | — |
| Rainbow table | радужная таблица | — |
| Nonce | nonce / одноразовое число | — |
| IV (Initialization Vector) | IV / вектор инициализации | — |
| Mode of operation (ECB, CBC, GCM, CTR) | режим работы (ECB, CBC, GCM, CTR) | — |
| Authenticated Encryption (AEAD) | AEAD / аутентифицированное шифрование | — |
| TLS (Transport Layer Security) | TLS | См. `networking-translation-dictionary` |
| SSL | SSL | Устар. |
| Certificate | сертификат | — |
| X.509 | X.509 | — |
| PKI (Public Key Infrastructure) | PKI / инфраструктура открытых ключей | — |
| CA (Certificate Authority) | удостоверяющий центр (УЦ) / CA | — |
| CRL (Certificate Revocation List) | CRL / список отзыва сертификатов | — |
| OCSP (Online Certificate Status Protocol) | OCSP | — |
| Quantum cryptography | квантовая криптография | — |
| Post-quantum cryptography (PQC) | постквантовая криптография / PQC | — |
| Homomorphic encryption | гомоморфное шифрование | — |
| Zero-knowledge proof (ZKP) | zero-knowledge proof / ZKP / доказательство с нулевым разглашением | — |
| **ГОСТ Р 34.10 / ГОСТ Р 34.11 / ГОСТ 28147** | ГОСТ Р 34.10 / ГОСТ Р 34.11 / ГОСТ 28147 | Российские криптостандарты |
| **«Кузнечик», «Стрибог», «Магма»** | Кузнечик / Стрибог / Магма | Российские шифры |

## Раздел 7. IAM (Identity & Access Management)

| English | Русский | Комментарий |
|---------|---------|-------------|
| IAM (Identity and Access Management) | IAM / управление доступом и идентификацией | — |
| Identity | идентичность / identity | — |
| Authentication (AuthN) | аутентификация | «Аутентификация пользователя» |
| Authorization (AuthZ) | авторизация | Не путать с аутентификацией |
| Identification | идентификация | — |
| Accounting | учёт / accounting | AAA-модель |
| AAA (Authentication, Authorization, Accounting) | AAA | — |
| Credentials | учётные данные / credentials | — |
| Password | пароль | — |
| Passphrase | passphrase / парольная фраза | — |
| Token (auth token) | токен (аутентификации) | — |
| Bearer token | bearer token | — |
| Refresh token | refresh-токен / токен обновления | — |
| API key | API-ключ | — |
| MFA (Multi-Factor Authentication) | MFA / многофакторная аутентификация | — |
| 2FA (Two-Factor Authentication) | 2FA / двухфакторная аутентификация | — |
| TOTP (Time-based One-Time Password) | TOTP | — |
| HOTP (HMAC-based One-Time Password) | HOTP | — |
| FIDO2 / WebAuthn | FIDO2 / WebAuthn | — |
| Passkey | passkey / пасскей | — |
| Biometric authentication | биометрическая аутентификация | — |
| SSO (Single Sign-On) | SSO / единый вход | — |
| Federated identity | федеративная идентификация | — |
| IdP (Identity Provider) | IdP / провайдер идентификации | — |
| SP (Service Provider) | SP / поставщик услуг | — |
| SAML (Security Assertion Markup Language) | SAML | — |
| OAuth 2.0 / OAuth | OAuth 2.0 | — |
| OIDC (OpenID Connect) | OIDC / OpenID Connect | — |
| JWT (JSON Web Token) | JWT | — |
| OpenID | OpenID | — |
| RBAC (Role-Based Access Control) | RBAC / ролевая модель доступа | — |
| ABAC (Attribute-Based Access Control) | ABAC / атрибутная модель доступа | — |
| PBAC (Policy-Based Access Control) | PBAC | — |
| ReBAC (Relationship-Based Access Control) | ReBAC | — |
| MAC (Mandatory Access Control) | MAC / мандатное управление доступом | Не путать с MAC-адресом |
| DAC (Discretionary Access Control) | DAC / дискреционное управление доступом | — |
| Role | роль | — |
| Permission | разрешение / permission | — |
| Policy | политика | — |
| Principle of least privilege | принцип минимальных привилегий | — |
| Privileged access | привилегированный доступ | — |
| PAM (Privileged Access Management) | PAM | — |
| Service account | сервисная учётная запись / service account | — |
| Human user / Machine identity | человек-пользователь / машинная идентичность | — |

## Раздел 8. Application Security (AppSec) и DevSecOps

| English | Русский | Комментарий |
|---------|---------|-------------|
| Application Security (AppSec) | AppSec / безопасность приложений | — |
| DevSecOps | DevSecOps | — |
| Shift Left (security) | shift left | См. `devops-translation-dictionary` |
| SAST (Static Application Security Testing) | SAST / статический анализ безопасности | — |
| DAST (Dynamic Application Security Testing) | DAST | — |
| IAST (Interactive Application Security Testing) | IAST | — |
| RASP (Runtime Application Self-Protection) | RASP | — |
| SCA (Software Composition Analysis) | SCA / анализ состава ПО | — |
| Secret scanning | сканирование секретов | — |
| Container scanning | сканирование контейнеров | — |
| IaC scanning | сканирование IaC | — |
| Fuzz testing / Fuzzing | фаззинг / fuzzing | — |
| Symbolic execution | символическое выполнение | — |
| Code review (security) | security code review / ревью кода с точки зрения ИБ | — |
| Threat hunting | threat hunting / охота за угрозами | — |
| WAF (Web Application Firewall) | WAF | См. `networking-translation-dictionary` |
| Bot management | bot management / защита от ботов | — |
| Captcha | капча / CAPTCHA | — |
| Rate limiting | rate limiting / ограничение скорости запросов | — |
| CORS (Cross-Origin Resource Sharing) | CORS | — |
| CSP (Content Security Policy) | CSP | — |
| HSTS (HTTP Strict Transport Security) | HSTS | — |
| Subresource Integrity (SRI) | SRI | — |
| Tools: SonarQube, Snyk, Checkmarx, Veracode, Semgrep, CodeQL | оригинал | Имена сканеров |

## Раздел 9. Cloud Security

| English | Русский | Комментарий |
|---------|---------|-------------|
| Cloud security | облачная безопасность | — |
| Shared responsibility model | модель разделённой ответственности | — |
| CSPM (Cloud Security Posture Management) | CSPM | — |
| CIEM (Cloud Infrastructure Entitlement Management) | CIEM | — |
| CWPP (Cloud Workload Protection Platform) | CWPP | — |
| CNAPP (Cloud-Native Application Protection Platform) | CNAPP | — |
| CASB (Cloud Access Security Broker) | CASB | — |
| SASE (Secure Access Service Edge) | SASE | См. `networking-translation-dictionary` |
| SSE (Security Service Edge) | SSE | — |
| ZTNA (Zero Trust Network Access) | ZTNA | — |
| Zero Trust | Zero Trust / нулевое доверие | — |
| BeyondCorp | BeyondCorp | Google Zero Trust |
| Cloud misconfiguration | неправильная конфигурация облака | — |
| Public S3 bucket | публичный S3-бакет | Типовая ошибка |
| IAM policy | IAM-политика | — |
| Privilege escalation (cloud) | повышение привилегий в облаке | — |
| Cross-tenant attack | cross-tenant атака | — |
| Cloud-native security | cloud-native безопасность | — |
| Confidential computing | confidential computing / конфиденциальные вычисления | — |
| TEE (Trusted Execution Environment) | TEE | Intel SGX, AMD SEV |

## Раздел 10. Container / Kubernetes Security

| English | Русский | Комментарий |
|---------|---------|-------------|
| Container security | безопасность контейнеров | — |
| Image scanning | сканирование образов | Trivy, Clair, Snyk, Grype, Anchore |
| Image signing | подпись образов | Cosign, Notary |
| Pod Security Standards (PSS) | Pod Security Standards / PSS | См. `k8s-translation-dictionary` |
| Pod Security Admission (PSA) | Pod Security Admission / PSA | — |
| PSP (PodSecurityPolicy) | PSP | Устар. |
| Admission controller | контроллер допуска / admission controller | — |
| OPA (Open Policy Agent) | OPA | — |
| Gatekeeper | Gatekeeper | OPA на K8s |
| Kyverno | Kyverno | Policy engine |
| Network policy | Network Policy / сетевая политика | — |
| RBAC (K8s) | RBAC | См. `k8s-translation-dictionary` |
| Service account (K8s) | ServiceAccount | — |
| Secrets management | управление секретами | HashiCorp Vault, External Secrets |
| HashiCorp Vault | HashiCorp Vault | — |
| External Secrets Operator | External Secrets Operator | — |
| Runtime security | runtime-безопасность | Falco, Tetragon |
| Falco, Tetragon, Sysdig | Falco, Tetragon, Sysdig | — |
| eBPF security | eBPF security | См. `networking-translation-dictionary` |
| Container escape | container escape / выход из контейнера | — |
| Distroless image | distroless-образ | — |
| Minimal base image | минимальный базовый образ | Alpine, distroless |
| Image vulnerability | уязвимость образа | — |

## Раздел 11. Supply Chain Security

| English | Русский | Комментарий |
|---------|---------|-------------|
| Software supply chain | цепочка поставок ПО | — |
| Supply chain attack | атака на цепочку поставок | — |
| SBOM (Software Bill of Materials) | SBOM / спецификация ПО | — |
| CycloneDX, SPDX | CycloneDX, SPDX | Форматы SBOM |
| SLSA (Supply-chain Levels for Software Artifacts) | SLSA | — |
| Sigstore | Sigstore | — |
| Cosign | cosign | — |
| Rekor | Rekor | Прозрачный журнал Sigstore |
| Fulcio | Fulcio | Sigstore CA |
| in-toto | in-toto | — |
| Provenance | provenance / происхождение | — |
| Reproducible build | воспроизводимая сборка | — |
| Dependency confusion | путаница зависимостей (dependency confusion) | Устоявшийся ru-вариант на Хабре. Первое упоминание — с англ. в скобках |
| Typosquatting | тайпсквоттинг (typosquatting) | **ВНИМАНИЕ**: правильно «тайпсквоттинг» — НЕ «тайпосквоттинг». Источник: ru.wikipedia, encyclopedia.kaspersky.ru |
| Malicious package | вредоносный пакет | npm, PyPI, RubyGems |
| Build attestation | build attestation / аттестация сборки | — |
| SBOM attestation | аттестация SBOM | Подписанное удостоверение состава ПО |
| SLSA provenance | SLSA-провенанс / SLSA-аттестация происхождения | — |
| GUAC | GUAC | Graph for Understanding Artifact Composition |
| Allowlist / Blocklist | allow-list / deny-list (или: список разрешённых / запрещённых) | Современный гайд OSSF — «allow/deny». «Белый/чёрный» — допустимо, но менее точно |
| SHA pinning / pin by digest | закрепление по SHA / SHA-пиннинг | Первое упоминание: «закрепление action по полному SHA коммита (SHA pinning)». «Pin by digest» в OCI — оставлять «пин по digest» |
| Expression injection (GitHub Actions) | инъекция выражений | По аналогии с «SQL-инъекция». Контекст — синтаксис `${{ }}` в YAML workflow |
| Mutable tags | изменяемые теги | Контекст контейнерных реестров и Git-тегов |
| Yanked (package) | отозван (npm) / помечен как yanked (PyPI) | Контекст важен: yank в PyPI ≠ unpublish в npm |
| Scoped secrets | секреты с ограниченной областью действия / scoped-секреты | Первое упоминание — оба варианта; далее «scoped-секреты» |
| Egress firewall | egress-файрвол | «Egress» в Хабре чаще латиницей: «egress-трафик», «egress-политики» |
| Vendoring (Go) | вендоринг | Калька, кириллицей. Папка остаётся `vendor`. См. devops-словарь |

## Раздел 12. SOC, мониторинг, реагирование

| English | Русский | Комментарий |
|---------|---------|-------------|
| SOC (Security Operations Center) | SOC / центр мониторинга ИБ / центр кибербезопасности | — |
| SIEM (Security Information and Event Management) | SIEM | — |
| SOAR (Security Orchestration, Automation and Response) | SOAR | — |
| EDR (Endpoint Detection and Response) | EDR | — |
| XDR (Extended Detection and Response) | XDR | — |
| MDR (Managed Detection and Response) | MDR | — |
| NDR (Network Detection and Response) | NDR | — |
| MSSP (Managed Security Service Provider) | MSSP | — |
| Incident response (IR) | реагирование на инциденты / IR | — |
| Incident response plan (IRP) | план реагирования на инциденты / IRP | — |
| Playbook (SOC) | playbook / плейбук | — |
| Runbook | runbook | — |
| Digital forensics | цифровая криминалистика / форензика | — |
| Forensics | форензика | — |
| Chain of custody | цепочка хранения доказательств | — |
| Evidence preservation | сохранение доказательств | — |
| Memory dump | дамп памяти | — |
| Disk image | образ диска | — |
| Log analysis | анализ логов | — |
| Threat hunting | threat hunting / охота за угрозами | — |
| UEBA (User and Entity Behavior Analytics) | UEBA | — |
| Anomaly detection | обнаружение аномалий | — |
| Honeypot | ханипот / приманка | — |
| Honeynet | ханинет | — |
| Deception technology | deception-технологии | — |
| Detection engineering | detection engineering | — |
| Sigma rule | Sigma-правило | — |
| YARA rule | YARA-правило | — |
| Snort / Suricata rule | Snort / Suricata правило | — |
| Splunk, QRadar, ArcSight, ELK, Wazuh | оригинал | Имена SIEM |
| **MaxPatrol SIEM / R-Vision / KOMRAD** | MaxPatrol SIEM / R-Vision / KOMRAD | Российские SIEM |
| **PT NAD / Solar JSOC / BI.ZONE TDR** | PT NAD / Solar JSOC / BI.ZONE TDR | Российские NDR/MDR |

## Раздел 13. Compliance и стандарты

| English | Русский | Комментарий |
|---------|---------|-------------|
| Compliance | комплаенс / соответствие требованиям | — |
| ISO 27001 | ISO 27001 | Стандарт СУИБ |
| ISO 27002 | ISO 27002 | — |
| NIST CSF (Cybersecurity Framework) | NIST CSF | — |
| NIST 800-53 | NIST 800-53 | — |
| NIST 800-171 | NIST 800-171 | — |
| SOC 2 (Type I/II) | SOC 2 (Type I/II) | Не путать с SOC = Security Operations Center |
| PCI DSS | PCI DSS | Платёжные карты |
| HIPAA | HIPAA | США, медицина |
| GDPR (General Data Protection Regulation) | GDPR | ЕС, защита персональных данных |
| CCPA (California Consumer Privacy Act) | CCPA | США |
| FedRAMP | FedRAMP | США, облака |
| FISMA | FISMA | — |
| Common Criteria (CC) | Common Criteria / Общие критерии | — |
| EAL (Evaluation Assurance Level) | EAL | CC уровень |
| FIPS 140-2 / 140-3 | FIPS 140-2 / FIPS 140-3 | — |
| СУИБ (ISMS — Information Security Management System) | СУИБ / система управления информационной безопасностью | — |

## Раздел 14. Российская специфика

| English / контекст | Русский | Комментарий |
|--------------------|---------|-------------|
| Russian PII regulation | **152-ФЗ** | «О персональных данных» |
| Critical Information Infrastructure | **187-ФЗ / КИИ** | Критическая информационная инфраструктура |
| Federal Service for Technical and Export Control | **ФСТЭК** | Не «ФСТЭК России» — официально «ФСТЭК России», но в тексте достаточно «ФСТЭК» |
| Federal Security Service | **ФСБ** | — |
| Roskomnadzor | **Роскомнадзор / РКН** | — |
| Russian SOC center | **ГосСОПКА** | Государственная система обнаружения, предупреждения и ликвидации последствий компьютерных атак |
| FSTEK Threat Database | **БДУ ФСТЭК** | Банк данных угроз |
| Operational and search activities | **ОРД** | Оперативно-розыскная деятельность |
| Russian crypto standards | **ГОСТ Р** | ГОСТ Р 34.10, ГОСТ Р 34.11, ГОСТ 28147 |
| Russian ciphers | **Кузнечик, Стрибог, Магма** | — |
| Personal data | **персональные данные / ПДн** | — |
| Operator of personal data | **оператор персональных данных** | — |
| Subject of personal data | **субъект персональных данных** | — |
| Consent | **согласие** (на обработку ПДн) | — |
| Localization | **локализация (ПДн)** | Хранение в РФ |
| Certified protection means | **сертифицированные СЗИ** | Средства защиты информации |
| Class K1/K2/K3/K4 (СЗИ) | **класс защиты К1/К2/К3/К4** | — |
| Security class (data) | **уровень защищённости УЗ-1...УЗ-4** | — |
| Domestic software registry | **Реестр отечественного ПО** | Минцифры |
| Import substitution | **импортозамещение** | — |

## Раздел 15. AI Security (для пересечения с ml-ai-словарём)

| English | Русский | Комментарий |
|---------|---------|-------------|
| Prompt injection | prompt injection / инъекция в промпт | — |
| Jailbreak | jailbreak / джейлбрейк | — |
| Model poisoning | отравление модели | — |
| Data poisoning | отравление данных | — |
| Adversarial attack | adversarial attack / атака с противоборством | — |
| Adversarial example | adversarial example | — |
| Model extraction | model extraction / извлечение модели | — |
| Membership inference | membership inference атака | — |
| Model inversion | инверсия модели | — |
| AI red teaming | red teaming ИИ-моделей | — |
| LLM Top 10 (OWASP) | OWASP LLM Top 10 | — |
| Indirect prompt injection | непрямая prompt injection | — |
| Sensitive information disclosure | раскрытие чувствительной информации | — |
| AI safety | AI safety / безопасность ИИ | — |

## Раздел 16. Глаголы и действия

| English | Русский | Комментарий |
|---------|---------|-------------|
| to attack | атаковать | — |
| to exploit | эксплуатировать (уязвимость) | — |
| to compromise | скомпрометировать | — |
| to breach | взломать / получить доступ | — |
| to encrypt / decrypt | зашифровать / расшифровать | — |
| to hash | хешировать | — |
| to sign | подписать | — |
| to verify | проверить (подпись) | — |
| to authenticate | аутентифицировать | — |
| to authorize | авторизовать | — |
| to grant / revoke (access) | предоставить / отозвать (доступ) | — |
| to patch | пропатчить / установить патч | — |
| to mitigate | нейтрализовать / снизить риск | — |
| to harden | хардненить / усилить защиту | — |
| to scan | просканировать | — |
| to monitor | мониторить | — |
| to detect | обнаружить | — |
| to respond (incident) | реагировать (на инцидент) | — |
| to contain | сдержать (инцидент) | — |
| to eradicate | искоренить (угрозу) | — |
| to recover | восстановиться (после инцидента) | — |
| to phish | фишить (разг.) | — |
| to social-engineer | применить социальную инженерию | — |
| to escalate (privileges) | повысить (привилегии) | — |
| to pivot | сделать pivot / переключиться (на другой хост) | — |
| to exfiltrate | эксфильтровать / вывести (данные) | — |

## Раздел 17. Падежные формы

### Атака / Уязвимость / Угроза / Инцидент

- **Атака** (ж.р.): атаки, атаку, атакой; мн.ч. атаки, атак
- **Уязвимость** (ж.р.): уязвимости, уязвимостью; мн.ч. уязвимости, уязвимостей
- **Угроза** (ж.р.): угрозы, угрозу, угрозой
- **Инцидент** (м.р.): инцидента, инциденту, инцидентом

### Эксплойт / Патч / Хеш / Бэкдор / Фишинг

- **Эксплойт** (м.р.): эксплойта, эксплойту, эксплойтом
- **Патч** (м.р.): патча, патчу, патчем; мн.ч. патчи, патчей
- **Хеш** (м.р.): хеша, хешу, хешем
- **Бэкдор** (м.р.): бэкдора, бэкдору
- **Фишинг** (м.р.): фишинга, фишингу, фишингом

### CVE / CWE / CVSS / OWASP / RBAC / IAM / MFA / SSO / SAST / DAST / SIEM / SOC / EDR / XDR / SBOM / SLSA / TLS / JWT

**Не склоняются.** «В CVE», «по CVSS», «через OWASP», «в RBAC», «с MFA». В составных — через дефис: «CVE-2024-12345», «CVSS-оценка», «OWASP-стандарт», «RBAC-политика», «MFA-фактор», «SOC-команда», «SIEM-система», «JWT-токен».

### MITRE ATT&CK

Не склоняется. «В MITRE ATT&CK», «по MITRE ATT&CK», «техника ATT&CK», «матрица ATT&CK».

### Российские аббревиатуры — склоняются

- **ФСТЭК** (м.р.): ФСТЭКа, ФСТЭКу, ФСТЭКом. Также «при ФСТЭК», «по ФСТЭК»
- **ФСБ** (ж.р.): ФСБ. Не склоняется
- **РКН / Роскомнадзор** (м.р.): Роскомнадзора, Роскомнадзору
- **СУИБ** (ж.р.): не склоняется
- **КИИ** (ж.р.): не склоняется. «Субъекты КИИ», «объекты КИИ»
- **ГосСОПКА**: не склоняется. «Подключение к ГосСОПКА»
- **152-ФЗ, 187-ФЗ**: не склоняются. «По 152-ФЗ», «согласно 187-ФЗ»

### Имена групп APT и продуктов ИБ

- **APT28, APT29, Lazarus** — не склоняются
- **Kaspersky, Positive Technologies, Group-IB, Solar, BI.ZONE** — компании, не склоняются
- **Cobalt Strike, Metasploit, Burp Suite** — продукты, не склоняются

## Раздел 18. Типовые ошибки переводчика

### 1. AppSec/InfoSec/IT Security

```
✗ «Информационные технологии безопасности»
✓ «Информационная безопасность» / «ИБ»

✗ «Безопасность приложений как процесс»
✓ «Application Security (AppSec)» / «безопасность приложений»
```

### 2. Authentication vs Authorization

Не путать:
- **Authentication (AuthN)** — аутентификация (кто ты)
- **Authorization (AuthZ)** — авторизация (что можешь делать)

```
✗ «Авторизация пользователя через пароль»
✓ «Аутентификация пользователя через пароль»
```

### 3. Encryption vs Hashing vs Signing

- **Encryption** — шифрование (обратимое)
- **Hashing** — хеширование (необратимое)
- **Signing** — подпись (обеспечивает целостность и аутентичность)

```
✗ «Пароль зашифрован SHA-256» (SHA-256 — хеш-функция)
✓ «Пароль хеширован SHA-256»
```

### 4. Перевод имён групп APT и атак

```
✗ «АПТ28», «Лазарус»
✓ «APT28», «Lazarus»
```

Имена кибергрупп — оригинал.

### 5. Ransomware → «программа-вымогатель» или «шифровальщик»

Оба варианта допустимы. «Вымогатель» — точнее (не все шифруют, некоторые угрожают публикацией). «Шифровальщик» — более общеупотребимо.

### 6. Перевод OWASP Top 10 категорий

Названия пунктов OWASP Top 10 — оригинал: `A01:2021 - Broken Access Control`, `A03:2021 - Injection`. В нарративе можно переводить: «Категория A01 — нарушение контроля доступа».

### 7. «Атака на цепочку поставок» vs «supply chain attack»

Оба термина приняты. «Атака на цепочку поставок» — более понятно русскоязычному читателю.

### 8. Privilege escalation → «повышение привилегий»

```
✗ «эскалация привилегий» (калька)
✓ «повышение привилегий» / «privilege escalation»
```

### 9. «Хакер» в плохом смысле

```
✗ «Хакеры взломали систему» (общий термин)
✓ «Атакующие взломали систему» / «злоумышленники взломали систему»
```

В технических текстах — «атакующий» или «злоумышленник». «Хакер» — широкий термин (включая этичных).

### 10. Российская регуляторика — точные названия

```
✗ «федеральный закон о персональных данных»
✓ «152-ФЗ» / «ФЗ-152 «О персональных данных»»

✗ «российский CERT»
✓ «ГосСОПКА»
```

### 11. Personal data → «персональные данные» (ПДн)

```
✗ «личные данные»
✓ «персональные данные» / «ПДн»
```

Официальный термин в российском законодательстве — «персональные данные».

### 12. Перевод названий стандартов

```
✗ «ИСО 27001», «ПСИ ДСС»
✓ «ISO 27001», «PCI DSS»
```

Международные стандарты — оригинал.

### 13. «Защита периметра» vs «Zero Trust»

В современных статьях парадигма «защита периметра» (perimeter security) противопоставляется Zero Trust. Не смешивать в одном контексте без объяснения разницы.

## Раздел 19. Чек-лист переводчика + источники

### Чек-лист

- [ ] **Аббревиатуры** (CVE, CWE, CVSS, OWASP, RBAC, IAM, MFA, SSO, SAST, DAST, SCA, SIEM, SOC, SOAR, EDR, XDR, MDR, NDR, SBOM, SLSA, TLS, JWT, OAuth, OIDC, SAML, STRIDE, PASTA, MITRE ATT&CK) — оригинал, расшифровка при первом упоминании
- [ ] **CVE/CWE-номера** (`CVE-2024-12345`, `CWE-79`) — точный формат
- [ ] **Имена APT-групп** (APT28, APT29, Lazarus, BlackBasta, LockBit) — оригинал
- [ ] **Имена компаний ИБ** (Kaspersky, Positive Technologies, Group-IB, Solar, BI.ZONE, CrowdStrike, Mandiant, Palo Alto) — оригинал, не склоняются
- [ ] **Имена инструментов** (Burp Suite, Metasploit, Cobalt Strike, Nmap, Wireshark, OWASP ZAP) — оригинал
- [ ] **AuthN ≠ AuthZ** — аутентификация и авторизация различены
- [ ] **Encryption ≠ Hashing ≠ Signing** — шифрование, хеширование и подпись не смешаны
- [ ] **Российская регуляторика** (152-ФЗ, 187-ФЗ, ФСТЭК, ФСБ, КИИ, ГосСОПКА, БДУ, ПДн) — точные названия
- [ ] **Международные стандарты** (ISO 27001, NIST CSF, PCI DSS, GDPR, HIPAA, SOC 2) — оригинал
- [ ] **ИБ vs ИТ-безопасность** — выбран один термин
- [ ] **Атакующий / злоумышленник** вместо «хакер» в технических контекстах
- [ ] **Калек избегли** — нет «является», «эскалация привилегий», «личные данные»
- [ ] **Кавычки** — «ёлочки»
- [ ] **Атрибуция оригинала** — есть

### Что делать с новыми терминами

1. Проверь глоссарий Kaspersky — https://encyclopedia.kaspersky.ru/glossary/
2. Проверь публикации Positive Technologies на Хабре — https://habr.com/ru/companies/pt/
3. Проверь Solar/Ростелеком, BI.ZONE, Group-IB
4. Проверь NIST Glossary — https://csrc.nist.gov/glossary
5. Для российской регуляторики — нормативные документы ФСТЭК, ФСБ, Минцифры
6. Если нигде нет — оставь в оригинале + `[прим. перев.: устоявшегося перевода нет]`

### Источники

| Источник | Назначение |
|----------|-----------|
| Kaspersky Encyclopedia (RU) — https://encyclopedia.kaspersky.ru/glossary/ | Глоссарий ИБ на русском |
| Positive Technologies на Хабре — https://habr.com/ru/companies/pt/ | Технические статьи по ИБ |
| Solar / Ростелеком — https://rt-solar.ru/ | МДР, SIEM, киберразведка |
| BI.ZONE — https://bi.zone/ | TDR, MDR, threat intelligence |
| Group-IB — https://www.group-ib.ru/ | Threat intelligence, форензика |
| OWASP — https://owasp.org/ | Эталонная английская терминология |
| MITRE ATT&CK — https://attack.mitre.org/ | TTPs, тактики и техники |
| NIST Glossary — https://csrc.nist.gov/glossary | Эталонная терминология |
| **ФСТЭК России** — https://fstec.ru/ | Российская регуляторика, БДУ |
| **Российский ГОСТ Р по ИБ** | ГОСТ Р 34.10, 34.11, 27001 (адаптация) | — |
| Альянс ПРО (tran.su) | Методология |

Версия словаря: **2026-05-16 v1.0**.

## Связь с другими словарями

ИБ-словарь часто пересекается практически с любым доменом:

- **Security + K8s** — статья про Pod Security Standards, network policies, image signing, runtime security (Falco, Tetragon). Подключаются `security` + `k8s`.
- **Security + Networking** — статья про firewall, WAF, IDS/IPS, Zero Trust, SASE. Подключаются `security` + `networking`.
- **Security + Databases** — статья про SQL injection, шифрование данных в БД, защита PII. Подключаются `security` + `databases`.
- **Security + DevOps** — статья про DevSecOps, SAST/DAST в CI/CD, secret scanning, supply chain. Подключаются `security` + `devops`.
- **Security + ML/AI** — статья про prompt injection, model poisoning, AI red teaming, OWASP LLM Top 10. Подключаются `security` + `ml-ai`.
- **Все шесть** — статья «DevSecOps-платформа для AI-моделей на Kubernetes с PostgreSQL через Zero Trust сеть» — активируются все.

Приоритеты при конфликте — в `translation-standards.md`, секция «Приоритеты при множественной активации словарей».
