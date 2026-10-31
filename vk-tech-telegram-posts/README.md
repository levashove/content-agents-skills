# vk-tech-telegram-posts

Личный скилл для [claude.ai/customize/skills](https://claude.ai/customize/skills).
Папка производная — собрана `make skills-export` из репозитория content-agents,
вручную не редактируется (правки — в источниках, см. ниже).

## Описание

Посты для 11 каналов VK Tech: @vk_cloud_news, @k8s_vk, @sterodata, @tarantool_news, @vk_digital_tech, @vk_workspace_official, @vkhrtek, @vkfinop, @sandyq_orda «Цифровая Орда» (Казахстан, с поиском новостей), закрытый канал Стятюгина о корпоративном ИИ, LinkedIn VK WorkSpace Казахстан. Рубрики, голос, эмодзи и CTA каналов, контроль дрейфа, чистка ИИ-паттернов, редстандарт.

## Установка

1. Возьмите готовый архив `dist/skill-zips/vk-tech-telegram-posts.zip` из репозитория
   (или пересоберите: `make skills-zip`). `SKILL.md` — в корне архива,
   этот README в архив не входит.
2. Загрузите `.zip` на [claude.ai/customize/skills](https://claude.ai/customize/skills).
3. Обновление — повторная загрузка свежего архива.

## Источники (source of truth)

- `company/channels/vk-tech-telegram-posts/SKILL.md` — рукописный маршрутизатор (source of truth)
- `company/channels/vk-cloud-news-channel.md` → `references/vk-cloud-news-channel.md`
- `company/channels/kubernetes-channel.md` → `references/kubernetes-channel.md`
- `company/channels/data-channel.md` → `references/data-channel.md`
- `company/channels/tarantool-news-channel.md` → `references/tarantool-news-channel.md`
- `company/channels/vk-tech-channel.md` → `references/vk-tech-channel.md`
- `company/channels/vk-workspace-channel.md` → `references/vk-workspace-channel.md`
- `company/channels/vk-hr-tek-channel.md` → `references/vk-hr-tek-channel.md`
- `company/channels/vk-finop-channel.md` → `references/vk-finop-channel.md`
- `company/channels/sandyq-orda-channel.md` → `references/sandyq-orda-channel.md`
- `company/channels/styatyugin-ai-channel.md` → `references/styatyugin-ai-channel.md`
- `company/channels/vk-workspace-kz-linkedin-channel.md` → `references/vk-workspace-kz-linkedin-channel.md`
- `company/content-knowledge/digest/sources-catalog-kz.md` → `references/sources-catalog-kz.md`
- `company/style/vk-tech-voice-packs.md` → `references/vk-tech-voice-packs.md`
- `company/style/vk-tech-redstandards.md` → `references/vk-tech-redstandards.md`
- `rules/common/channel-style-drift.md` → `references/channel-style-drift.md`
- `rules/common/ai-pattern-cleanup.md` → `references/ai-pattern-cleanup.md`
- `rules/communications/telegram-post-standards.md` → `references/telegram-post-standards.md`
- `rules/common/brand-terminology.md` → `references/brand-terminology.md`
- `rules/common/technical-punctuation.md` → `references/technical-punctuation.md`
- `rules/common/content-quality.md` → `references/content-quality.md`
- `rules/common/russian-grammar.md` → `references/russian-grammar.md`

Справочники `references/` — дословные копии источников, собираются автоматически при выгрузке (манифест `COMPOSITE_REFERENCES` в `scripts/export_skills.py`); ручных копий и их дрейфа нет.

Версия для ChatGPT (Custom GPT) — `dist/gpt-packs/vk-tech-telegram-posts/`: тот же маршрутизатор в формате Instructions + справочники под Knowledge, инструкция сборки в README пака. Версия для любого чат-бота без механики скиллов — сокращённые standalone-промты: `dist/prompts/telegram-post-vk-cloud-news.md`, `dist/prompts/telegram-post-k8s.md`, `dist/prompts/telegram-post-data.md`, `dist/prompts/telegram-post-tarantool.md`, `dist/prompts/telegram-post-vk-tech.md`, `dist/prompts/telegram-post-vk-workspace.md`, `dist/prompts/telegram-post-vk-hr-tek.md`, `dist/prompts/telegram-post-vk-finop.md`, `dist/prompts/telegram-post-sandyq-orda.md`, `dist/prompts/telegram-post-styatyugin-ai.md`, `dist/prompts/linkedin-post-vk-workspace-kz.md` (шаблон — `_PROMPT.md` рядом с маршрутизатором; вставляется первым сообщением).

## Состав

- `SKILL.md`
- `references/ai-pattern-cleanup.md`
- `references/brand-terminology.md`
- `references/channel-style-drift.md`
- `references/content-quality.md`
- `references/data-channel.md`
- `references/kubernetes-channel.md`
- `references/russian-grammar.md`
- `references/sandyq-orda-channel.md`
- `references/sources-catalog-kz.md`
- `references/styatyugin-ai-channel.md`
- `references/tarantool-news-channel.md`
- `references/technical-punctuation.md`
- `references/telegram-post-standards.md`
- `references/vk-cloud-news-channel.md`
- `references/vk-finop-channel.md`
- `references/vk-hr-tek-channel.md`
- `references/vk-tech-channel.md`
- `references/vk-tech-redstandards.md`
- `references/vk-tech-voice-packs.md`
- `references/vk-workspace-channel.md`
- `references/vk-workspace-kz-linkedin-channel.md`
