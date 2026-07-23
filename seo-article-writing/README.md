# seo-article-writing

Личный скилл для [claude.ai/customize/skills](https://claude.ai/customize/skills).
Папка производная — собрана `make skills-export` из репозитория content-agents,
вручную не редактируется (правки — в источниках, см. ниже).

## Описание

Полный процесс написания SEO-статьи по редполитике репозитория в чате, без агентного рантайма: от фактуры и выбора угла до самопроверки и trust-блоков для AI-выдачи. Внутри: базовые SEO-требования (ключи, структура, мета), стандарты источников и свежести цифр, доменные белые списки (ИБ, AI-экосистема), чистка ИИ-паттернов, специфика Яндекса и доступ AI-краулеров. Использовать при запросе написать SEO-статью, лонгрид для блога или поисковый текст. Для аудита готового текста есть отдельный скилл seo-trust-optimization.

## Установка

1. Возьмите готовый архив `dist/skill-zips/seo-article-writing.zip` из репозитория
   (или пересоберите: `make skills-zip`). `SKILL.md` — в корне архива,
   этот README в архив не входит.
2. Загрузите `.zip` на [claude.ai/customize/skills](https://claude.ai/customize/skills).
3. Обновление — повторная загрузка свежего архива.

## Источники (source of truth)

- `skills/seo/seo-article-writing/SKILL.md` — рукописный маршрутизатор (source of truth)
- `rules/seo/seo-baseline.md` → `references/seo-baseline.md`
- `rules/seo/content-quality.md` → `references/content-quality.md`
- `rules/seo/expert-writing.md` → `references/expert-writing.md`
- `rules/seo/brand-terminology.md` → `references/brand-terminology.md`
- `rules/seo/source-standards.md` → `references/source-standards.md`
- `rules/seo/cybersecurity-claims.md` → `references/cybersecurity-claims.md`
- `rules/seo/ai-ecosystem-claims.md` → `references/ai-ecosystem-claims.md`
- `rules/seo/yandex-specifics.md` → `references/yandex-specifics.md`
- `rules/seo/ai-crawler-access.md` → `references/ai-crawler-access.md`
- `rules/common/source-attribution.md` → `references/source-attribution.md`
- `rules/common/freshness-check.md` → `references/freshness-check.md`
- `rules/common/ai-pattern-cleanup.md` → `references/ai-pattern-cleanup.md`
- `rules/common/editorial-angle.md` → `references/editorial-angle.md`
- `rules/common/final-trust-editing.md` → `references/final-trust-editing.md`
- `skills/optimization/seo-trust-optimization.md` → `references/seo-trust-optimization.md`

Справочники `references/` — дословные копии источников, собираются автоматически при выгрузке (манифест `COMPOSITE_REFERENCES` в `scripts/export_skills.py`); ручных копий и их дрейфа нет.

Версия для ChatGPT (Custom GPT) — `dist/gpt-packs/seo-article-writing/`: тот же маршрутизатор в формате Instructions + справочники под Knowledge, инструкция сборки в README пака. Версия для любого чат-бота без механики скиллов — сокращённые standalone-промты: `dist/prompts/seo-article-writing.md` (шаблон — `_PROMPT.md` рядом с маршрутизатором; вставляется первым сообщением).

## Состав

- `SKILL.md`
- `references/ai-crawler-access.md`
- `references/ai-ecosystem-claims.md`
- `references/ai-pattern-cleanup.md`
- `references/brand-terminology.md`
- `references/content-quality.md`
- `references/cybersecurity-claims.md`
- `references/editorial-angle.md`
- `references/expert-writing.md`
- `references/final-trust-editing.md`
- `references/freshness-check.md`
- `references/seo-baseline.md`
- `references/seo-trust-optimization.md`
- `references/source-attribution.md`
- `references/source-standards.md`
- `references/yandex-specifics.md`
