# vk-tech-telegram-posts

Личный скилл для [claude.ai/customize/skills](https://claude.ai/customize/skills).
Папка производная — собрана `make skills-export` из репозитория content-agents,
вручную не редактируется (правки — в источниках, см. ниже).

## Описание

Посты для Telegram-каналов VK Tech в чате — по профилям четырёх каналов: VK Cloud (@vk_cloud_news, зонтичный новостной), Kubernetes (@k8s_vk, инженерный), Данные и данные (@sterodata), Tarantool (@tarantool_news). Внутри: рубрикаторы, tone of voice, эмодзи-системы, структуры постов и CTA каждого канала + контроль дрейфа «не звучи как чужой канал», чистка ИИ-паттернов, редстандарт и эталоны голоса VK Tech. Использовать при запросе написать пост для Telegram-канала, анонс релиза, адаптацию статьи под телеграм VK Cloud / VK Tech / Tarantool.

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
- `company/style/vk-tech-voice-packs.md` → `references/vk-tech-voice-packs.md`
- `company/style/vk-tech-redstandards.md` → `references/vk-tech-redstandards.md`
- `rules/common/channel-style-drift.md` → `references/channel-style-drift.md`
- `rules/common/ai-pattern-cleanup.md` → `references/ai-pattern-cleanup.md`
- `rules/common/brand-terminology.md` → `references/brand-terminology.md`
- `rules/common/technical-punctuation.md` → `references/technical-punctuation.md`

Справочники `references/` — дословные копии источников, собираются автоматически при выгрузке (манифест `COMPOSITE_REFERENCES` в `scripts/export_skills.py`); ручных копий и их дрейфа нет.

Версия для ChatGPT (Custom GPT) — `dist/gpt-packs/vk-tech-telegram-posts/`: тот же маршрутизатор в формате Instructions + справочники под Knowledge, инструкция сборки в README пака. Версия для любого чат-бота без механики скиллов — сокращённые standalone-промты: `dist/prompts/telegram-post-vk-cloud-news.md`, `dist/prompts/telegram-post-k8s.md`, `dist/prompts/telegram-post-data.md`, `dist/prompts/telegram-post-tarantool.md` (шаблон — `_PROMPT.md` рядом с маршрутизатором; вставляется первым сообщением).

## Состав

- `SKILL.md`
- `references/ai-pattern-cleanup.md`
- `references/brand-terminology.md`
- `references/channel-style-drift.md`
- `references/data-channel.md`
- `references/kubernetes-channel.md`
- `references/tarantool-news-channel.md`
- `references/technical-punctuation.md`
- `references/vk-cloud-news-channel.md`
- `references/vk-tech-redstandards.md`
- `references/vk-tech-voice-packs.md`
