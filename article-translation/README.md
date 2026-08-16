# article-translation

Личный скилл для [claude.ai/customize/skills](https://claude.ai/customize/skills).
Папка производная — собрана `make skills-export` из репозитория content-agents,
вручную не редактируется (правки — в источниках, см. ниже).

## Описание

Перевод технической статьи EN/DE → RU в чате: блок-к-блоку с сохранением структуры, лида, картинок и сносок; политика терминов «три исхода» (русское слово / оригинал / сноска-определение «Прим. перев.»), тест распространённости, системная чистка калек по 9 категориям. Внутри: стандарты перевода, глоссарий с Общей таблицей терминов и 8 доменных словарей (K8s, DevOps, сети, БД, ML/AI, безопасность, фронтенд, мобильная разработка). Использовать при запросе перевести техническую статью, блог-пост или доклад с английского или немецкого.

## Установка

1. Возьмите готовый архив `dist/skill-zips/article-translation.zip` из репозитория
   (или пересоберите: `make skills-zip`). `SKILL.md` — в корне архива,
   этот README в архив не входит.
2. Загрузите `.zip` на [claude.ai/customize/skills](https://claude.ai/customize/skills).
3. Обновление — повторная загрузка свежего архива.

## Источники (source of truth)

- `skills/translation/article-translation/SKILL.md` — рукописный маршрутизатор (source of truth)
- `rules/translation/translation-standards.md` → `references/translation-standards.md`
- `rules/translation/translation-glossary.md` → `references/translation-glossary.md`
- `rules/translation/translation-calques.md` → `references/translation-calques.md`
- `rules/common/technical-punctuation.md` → `references/technical-punctuation.md`
- `rules/common/final-trust-editing.md` → `references/final-trust-editing.md`
- `skills/translation/k8s-translation-dictionary.md` → `references/k8s-translation-dictionary.md`
- `skills/translation/devops-translation-dictionary.md` → `references/devops-translation-dictionary.md`
- `skills/translation/networking-translation-dictionary.md` → `references/networking-translation-dictionary.md`
- `skills/translation/databases-translation-dictionary.md` → `references/databases-translation-dictionary.md`
- `skills/translation/ml-ai-translation-dictionary.md` → `references/ml-ai-translation-dictionary.md`
- `skills/translation/security-translation-dictionary.md` → `references/security-translation-dictionary.md`
- `skills/translation/frontend-translation-dictionary.md` → `references/frontend-translation-dictionary.md`
- `skills/translation/mobile-translation-dictionary.md` → `references/mobile-translation-dictionary.md`

Справочники `references/` — дословные копии источников, собираются автоматически при выгрузке (манифест `COMPOSITE_REFERENCES` в `scripts/export_skills.py`); ручных копий и их дрейфа нет.

Версия для ChatGPT (Custom GPT) — `dist/gpt-packs/article-translation/`: тот же маршрутизатор в формате Instructions + справочники под Knowledge, инструкция сборки в README пака. Версия для любого чат-бота без механики скиллов — сокращённые standalone-промты: `dist/prompts/article-translation.md` (шаблон — `_PROMPT.md` рядом с маршрутизатором; вставляется первым сообщением).

## Состав

- `SKILL.md`
- `references/databases-translation-dictionary.md`
- `references/devops-translation-dictionary.md`
- `references/final-trust-editing.md`
- `references/frontend-translation-dictionary.md`
- `references/k8s-translation-dictionary.md`
- `references/ml-ai-translation-dictionary.md`
- `references/mobile-translation-dictionary.md`
- `references/networking-translation-dictionary.md`
- `references/security-translation-dictionary.md`
- `references/technical-punctuation.md`
- `references/translation-calques.md`
- `references/translation-glossary.md`
- `references/translation-standards.md`
