# vk-tech-press-release — версия для ChatGPT (Custom GPT)

Тот же скилл, что `dist/claude-skills/vk-tech-press-release/`, переупакованный под механику
ChatGPT: маршрутизатор — в поле Instructions, справочники — файлами в
Knowledge (retrieval). Папка производная, собрана `make skills-export`;
источники правды те же, что у скилла claude.ai (см. README скилла).

## Как собрать Custom GPT

1. [chatgpt.com](https://chatgpt.com) → My GPTs → **Create a GPT** →
   вкладка **Configure**.
2. **Name** — например, «vk-tech-press-release». **Description** — можно взять первое
   предложение описания ниже.
3. **Instructions** — вставьте содержимое `instructions.txt` целиком
   (5381 символов из ~8000 лимита).
4. **Knowledge** — загрузите все файлы из `knowledge/`:
- `knowledge/press-release-knowledge.md`
- `knowledge/press-release-standards.md`
- `knowledge/press-release-content-quality.md`
- `knowledge/press-release-brand-terminology.md`
- `knowledge/content-quality.md`
- `knowledge/brand-terminology.md`
- `knowledge/source-attribution.md`
- `knowledge/ai-pattern-cleanup.md`
- `knowledge/vk-tech-redstandards.md`
5. Сохраните (Only me — для личного использования).

Альтернатива без Custom GPT: Project в ChatGPT — те же instructions + файлы.

## Отличия от claude.ai-версии

- GPT не подхватывается автоматически по теме запроса — его нужно открыть.
- Knowledge работает через поиск по фрагментам (retrieval), а не чтение файла
  целиком: критичный минимум продублирован в Instructions, но детали
  справочников могут подтягиваться выборочно — при сомнении попросите GPT
  свериться с конкретным файлом.

## Описание скилла

Пресс-релизы VK Tech в чате по фирменной структуре 2026: курсивный лид с главной цифрой, тело сплошным текстом, цитата спикера с сильнейшим тезисом, заключительный факт-абзац, бойлерплейт. Внутри: эталонные релизы, формулы заголовков/лидов/цитат, стандарты качества и терминологии VK Tech, атрибуция цитат, чистка ИИ-паттернов. Использовать при запросе написать пресс-релиз, анонс продукта, партнёрства или мероприятия VK Tech.
