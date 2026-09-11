# vk-tech-press-release

Личный скилл для [claude.ai/customize/skills](https://claude.ai/customize/skills).
Папка производная — собрана `make skills-export` из репозитория content-agents,
вручную не редактируется (правки — в источниках, см. ниже).

## Описание

Пресс-релизы VK Tech в чате по фирменной структуре 2026: курсивный лид с главной цифрой, тело сплошным текстом, цитата спикера с сильнейшим тезисом, заключительный факт-абзац, бойлерплейт. Внутри: эталонные релизы, формулы заголовков/лидов/цитат, стандарты качества и терминологии VK Tech, атрибуция цитат, чистка ИИ-паттернов. Использовать при запросе написать пресс-релиз, анонс продукта, партнёрства или мероприятия VK Tech.

## Установка

1. Возьмите готовый архив `dist/skill-zips/vk-tech-press-release.zip` из репозитория
   (или пересоберите: `make skills-zip`). `SKILL.md` — в корне архива,
   этот README в архив не входит.
2. Загрузите `.zip` на [claude.ai/customize/skills](https://claude.ai/customize/skills).
3. Обновление — повторная загрузка свежего архива.

## Источники (source of truth)

- `company/content-knowledge/press-release/vk-tech-press-release/SKILL.md` — рукописный маршрутизатор (source of truth)
- `company/content-knowledge/press-release/press-release-knowledge.md` → `references/press-release-knowledge.md`
- `rules/press-release/press-release-standards.md` → `references/press-release-standards.md`
- `rules/press-release/content-quality.md` → `references/press-release-content-quality.md`
- `rules/press-release/brand-terminology.md` → `references/press-release-brand-terminology.md`
- `rules/common/content-quality.md` → `references/content-quality.md`
- `rules/common/brand-terminology.md` → `references/brand-terminology.md`
- `rules/common/source-attribution.md` → `references/source-attribution.md`
- `rules/common/ai-pattern-cleanup.md` → `references/ai-pattern-cleanup.md`
- `company/style/vk-tech-redstandards.md` → `references/vk-tech-redstandards.md`

Справочники `references/` — дословные копии источников, собираются автоматически при выгрузке (манифест `COMPOSITE_REFERENCES` в `scripts/export_skills.py`); ручных копий и их дрейфа нет.

Версия для ChatGPT (Custom GPT) — `dist/gpt-packs/vk-tech-press-release/`: тот же маршрутизатор в формате Instructions + справочники под Knowledge, инструкция сборки в README пака. Версия для любого чат-бота без механики скиллов — сокращённые standalone-промты: `dist/prompts/vk-tech-press-release.md` (шаблон — `_PROMPT.md` рядом с маршрутизатором; вставляется первым сообщением).

## Состав

- `SKILL.md`
- `references/ai-pattern-cleanup.md`
- `references/brand-terminology.md`
- `references/content-quality.md`
- `references/press-release-brand-terminology.md`
- `references/press-release-content-quality.md`
- `references/press-release-knowledge.md`
- `references/press-release-standards.md`
- `references/source-attribution.md`
- `references/vk-tech-redstandards.md`
