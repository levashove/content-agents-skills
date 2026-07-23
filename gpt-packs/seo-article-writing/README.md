# seo-article-writing — версия для ChatGPT (Custom GPT)

Тот же скилл, что `dist/claude-skills/seo-article-writing/`, переупакованный под механику
ChatGPT: маршрутизатор — в поле Instructions, справочники — файлами в
Knowledge (retrieval). Папка производная, собрана `make skills-export`;
источники правды те же, что у скилла claude.ai (см. README скилла).

## Как собрать Custom GPT

1. [chatgpt.com](https://chatgpt.com) → My GPTs → **Create a GPT** →
   вкладка **Configure**.
2. **Name** — например, «seo-article-writing». **Description** — можно взять первое
   предложение описания ниже.
3. **Instructions** — вставьте содержимое `instructions.txt` целиком
   (6135 символов из ~8000 лимита).
4. **Knowledge** — загрузите все файлы из `knowledge/`:
- `knowledge/seo-baseline.md`
- `knowledge/content-quality.md`
- `knowledge/expert-writing.md`
- `knowledge/brand-terminology.md`
- `knowledge/source-standards.md`
- `knowledge/cybersecurity-claims.md`
- `knowledge/ai-ecosystem-claims.md`
- `knowledge/yandex-specifics.md`
- `knowledge/ai-crawler-access.md`
- `knowledge/source-attribution.md`
- `knowledge/freshness-check.md`
- `knowledge/ai-pattern-cleanup.md`
- `knowledge/editorial-angle.md`
- `knowledge/final-trust-editing.md`
- `knowledge/seo-trust-optimization.md`
5. Сохраните (Only me — для личного использования).

Альтернатива без Custom GPT: Project в ChatGPT — те же instructions + файлы.

## Отличия от claude.ai-версии

- GPT не подхватывается автоматически по теме запроса — его нужно открыть.
- Knowledge работает через поиск по фрагментам (retrieval), а не чтение файла
  целиком: критичный минимум продублирован в Instructions, но детали
  справочников могут подтягиваться выборочно — при сомнении попросите GPT
  свериться с конкретным файлом.

## Описание скилла

Полный процесс написания SEO-статьи по редполитике репозитория в чате, без агентного рантайма: от фактуры и выбора угла до самопроверки и trust-блоков для AI-выдачи. Внутри: базовые SEO-требования (ключи, структура, мета), стандарты источников и свежести цифр, доменные белые списки (ИБ, AI-экосистема), чистка ИИ-паттернов, специфика Яндекса и доступ AI-краулеров. Использовать при запросе написать SEO-статью, лонгрид для блога или поисковый текст. Для аудита готового текста есть отдельный скилл seo-trust-optimization.
