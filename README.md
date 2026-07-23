# Скиллы content-agents для claude.ai

Готовые личные скиллы для [claude.ai/customize/skills](https://claude.ai/customize/skills):
папка на скилл (внутри `SKILL.md`, справочники и README с описанием и
источниками) + готовый к загрузке архив в `zips/`.

**Репозиторий — производная витрина.** Собирается автоматически из основного
репозитория `content-agents` (выборочно, по манифесту `config/skills-mirror.yaml`);
руками не редактируется — правки перетираются следующим синком. Править скилл —
значит править его источники в основном репозитории.

## Установка

1. Скачайте архив скилла из [`zips/`](zips/) (один скилл = один `.zip`,
   `SKILL.md` — в корне архива).
2. Загрузите на [claude.ai/customize/skills](https://claude.ai/customize/skills).
3. Обновление — повторная загрузка свежего архива после очередного синка.

## Состав (4 скилла)

| Скилл | О чём | Архив |
|-------|-------|-------|
| [`vk-tech-telegram-posts`](vk-tech-telegram-posts/) | Посты для Telegram-каналов VK Tech в чате — по профилям четырёх каналов: VK Cloud (@vk_cloud_news, зонтичный новостной), Kubernetes (@k8s_vk, инженерный), Данные и данные (@sterod… | [`zips/vk-tech-telegram-posts.zip`](zips/vk-tech-telegram-posts.zip) |
| [`seo-article-writing`](seo-article-writing/) | Полный процесс написания SEO-статьи по редполитике репозитория в чате, без агентного рантайма: от фактуры и выбора угла до самопроверки и trust-блоков для AI-выдачи. | [`zips/seo-article-writing.zip`](zips/seo-article-writing.zip) |
| [`vk-tech-press-release`](vk-tech-press-release/) | Пресс-релизы VK Tech в чате по фирменной структуре 2026: курсивный лид с главной цифрой, тело сплошным текстом, цитата спикера с сильнейшим тезисом, заключительный факт-абзац, бой… | [`zips/vk-tech-press-release.zip`](zips/vk-tech-press-release.zip) |
| [`article-translation`](article-translation/) | Перевод технической статьи EN/DE → RU в чате: блок-к-блоку с сохранением структуры, лида, картинок и сносок; политика терминов «три исхода» (русское слово / оригинал / сноска-опре… | [`zips/article-translation.zip`](zips/article-translation.zip) |

Полное описание, источники правды и состав каждого скилла — в README его папки.

## Версия для ChatGPT

Для части скиллов есть GPT-пак в [`gpt-packs/`](gpt-packs/): [`vk-tech-telegram-posts`](gpt-packs/vk-tech-telegram-posts/), [`seo-article-writing`](gpt-packs/seo-article-writing/), [`vk-tech-press-release`](gpt-packs/vk-tech-press-release/), [`article-translation`](gpt-packs/article-translation/) — маршрутизатор под поле Instructions кастомного GPT + справочники файлами под Knowledge; инструкция сборки — в README пака.

## Standalone-промты (любой чат-бот)

Версия без механики скиллов и Knowledge — [`prompts/`](prompts/): [`telegram-post-vk-cloud-news.md`](prompts/telegram-post-vk-cloud-news.md), [`telegram-post-k8s.md`](prompts/telegram-post-k8s.md), [`telegram-post-data.md`](prompts/telegram-post-data.md), [`telegram-post-tarantool.md`](prompts/telegram-post-tarantool.md), [`seo-article-writing.md`](prompts/seo-article-writing.md), [`vk-tech-press-release.md`](prompts/vk-tech-press-release.md), [`article-translation.md`](prompts/article-translation.md). Сокращённый промт (правила + процесс + нужный справочник инлайном): скопируйте файл целиком первым сообщением в чат и следом напишите задачу. Для Telegram — по промту на каждый канал.
