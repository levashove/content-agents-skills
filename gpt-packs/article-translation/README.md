# article-translation — версия для ChatGPT (Custom GPT)

Тот же скилл, что `dist/claude-skills/article-translation/`, переупакованный под механику
ChatGPT: маршрутизатор — в поле Instructions, справочники — файлами в
Knowledge (retrieval). Папка производная, собрана `make skills-export`;
источники правды те же, что у скилла claude.ai (см. README скилла).

## Как собрать Custom GPT

1. [chatgpt.com](https://chatgpt.com) → My GPTs → **Create a GPT** →
   вкладка **Configure**.
2. **Name** — например, «article-translation». **Description** — можно взять первое
   предложение описания ниже.
3. **Instructions** — вставьте содержимое `instructions.txt` целиком
   (5792 символов из ~8000 лимита).
4. **Knowledge** — загрузите все файлы из `knowledge/`:
- `knowledge/translation-standards.md`
- `knowledge/translation-glossary.md`
- `knowledge/translation-calques.md`
- `knowledge/technical-punctuation.md`
- `knowledge/final-trust-editing.md`
- `knowledge/k8s-translation-dictionary.md`
- `knowledge/devops-translation-dictionary.md`
- `knowledge/networking-translation-dictionary.md`
- `knowledge/databases-translation-dictionary.md`
- `knowledge/ml-ai-translation-dictionary.md`
- `knowledge/security-translation-dictionary.md`
- `knowledge/frontend-translation-dictionary.md`
- `knowledge/mobile-translation-dictionary.md`
5. Сохраните (Only me — для личного использования).

Альтернатива без Custom GPT: Project в ChatGPT — те же instructions + файлы.

## Отличия от claude.ai-версии

- GPT не подхватывается автоматически по теме запроса — его нужно открыть.
- Knowledge работает через поиск по фрагментам (retrieval), а не чтение файла
  целиком: критичный минимум продублирован в Instructions, но детали
  справочников могут подтягиваться выборочно — при сомнении попросите GPT
  свериться с конкретным файлом.

## Описание скилла

Перевод технической статьи EN/DE → RU в чате: блок-к-блоку с сохранением структуры, лида, картинок и сносок; политика терминов «три исхода» (русское слово / оригинал / сноска-определение «Прим. перев.»), тест распространённости, системная чистка калек по 9 категориям. Внутри: стандарты перевода, глоссарий с Общей таблицей терминов и 8 доменных словарей (K8s, DevOps, сети, БД, ML/AI, безопасность, фронтенд, мобильная разработка). Использовать при запросе перевести техническую статью, блог-пост или доклад с английского или немецкого.
