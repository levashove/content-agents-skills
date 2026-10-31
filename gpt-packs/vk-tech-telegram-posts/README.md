# vk-tech-telegram-posts — версия для ChatGPT (Custom GPT)

Тот же скилл, что `dist/claude-skills/vk-tech-telegram-posts/`, переупакованный под механику
ChatGPT: маршрутизатор — в поле Instructions, справочники — файлами в
Knowledge (retrieval). Папка производная, собрана `make skills-export`;
источники правды те же, что у скилла claude.ai (см. README скилла).

## Как собрать Custom GPT

1. [chatgpt.com](https://chatgpt.com) → My GPTs → **Create a GPT** →
   вкладка **Configure**.
2. **Name** — например, «vk-tech-telegram-posts». **Description** — можно взять первое
   предложение описания ниже.
3. **Instructions** — вставьте содержимое `instructions.txt` целиком
   (7954 символов из ~8000 лимита).
4. **Knowledge** — загрузите все файлы из `knowledge/`:
- `knowledge/vk-cloud-news-channel.md`
- `knowledge/kubernetes-channel.md`
- `knowledge/data-channel.md`
- `knowledge/tarantool-news-channel.md`
- `knowledge/vk-tech-channel.md`
- `knowledge/vk-workspace-channel.md`
- `knowledge/vk-hr-tek-channel.md`
- `knowledge/vk-finop-channel.md`
- `knowledge/sandyq-orda-channel.md`
- `knowledge/styatyugin-ai-channel.md`
- `knowledge/vk-workspace-kz-linkedin-channel.md`
- `knowledge/sources-catalog-kz.md`
- `knowledge/vk-tech-voice-packs.md`
- `knowledge/vk-tech-redstandards.md`
- `knowledge/channel-style-drift.md`
- `knowledge/ai-pattern-cleanup.md`
- `knowledge/telegram-post-standards.md`
- `knowledge/brand-terminology.md`
- `knowledge/technical-punctuation.md`
- `knowledge/content-quality.md`
- `knowledge/russian-grammar.md`
5. Сохраните (Only me — для личного использования).

Альтернатива без Custom GPT: Project в ChatGPT — те же instructions + файлы.

## Отличия от claude.ai-версии

- GPT не подхватывается автоматически по теме запроса — его нужно открыть.
- Knowledge работает через поиск по фрагментам (retrieval), а не чтение файла
  целиком: критичный минимум продублирован в Instructions, но детали
  справочников могут подтягиваться выборочно — при сомнении попросите GPT
  свериться с конкретным файлом.

## Описание скилла

Посты для 11 каналов VK Tech: @vk_cloud_news, @k8s_vk, @sterodata, @tarantool_news, @vk_digital_tech, @vk_workspace_official, @vkhrtek, @vkfinop, @sandyq_orda «Цифровая Орда» (Казахстан, с поиском новостей), закрытый канал Стятюгина о корпоративном ИИ, LinkedIn VK WorkSpace Казахстан. Рубрики, голос, эмодзи и CTA каналов, контроль дрейфа, чистка ИИ-паттернов, редстандарт.
