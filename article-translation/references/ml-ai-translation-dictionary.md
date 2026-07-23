---
name: ml-ai-translation-dictionary
delivery: reference
description: |
  Словарь терминологии машинного обучения и ИИ для перевода технических статей
  с английского и немецкого на русский. Покрывает классическое ML, deep learning,
  LLM (GPT, Claude, Gemini), эмбеддинги, RAG, fine-tuning, prompt engineering,
  AI-агенты, MLOps, frameworks (PyTorch, HuggingFace, LangChain), evaluation.

  Источники: переводы Хабра (Yandex, Sber, OTUS), документация OpenAI/Anthropic,
  Hugging Face docs, статьи DeepSchool, vc.ru/ai, методология «Альянса ПРО».
activation:
  - "ml"
  - "machine learning"
  - "машинное обучение"
  - "ии"
  - "ai"
  - "искусственный интеллект"
  - "llm"
  - "large language model"
  - "большая языковая модель"
  - "gpt"
  - "claude"
  - "gemini"
  - "anthropic"
  - "openai"
  - "deep learning"
  - "глубокое обучение"
  - "нейросеть"
  - "neural network"
  - "transformer"
  - "embeddings"
  - "эмбеддинги"
  - "fine-tuning"
  - "файнтюнинг"
  - "дообучение"
  - "rag"
  - "retrieval"
  - "retrieval augmented generation"
  - "prompt engineering"
  - "промпт"
  - "промпт-инжиниринг"
  - "tokenization"
  - "токенизация"
  - "attention"
  - "self-attention"
  - "rlhf"
  - "lora"
  - "qlora"
  - "peft"
  - "hugging face"
  - "huggingface"
  - "pytorch"
  - "tensorflow"
  - "langchain"
  - "llamaindex"
  - "mlops"
  - "model serving"
  - "inference"
  - "инференс"
  - "ai agent"
  - "ai-агент"
  - "mcp"
  - "model context protocol"
  - "diffusion"
  - "diffusion model"
  - "stable diffusion"
  - "midjourney"
  - "gan"
  - "cuda"
---

# ML / AI Translation Dictionary

Словарь для переводчиков статей по машинному обучению, deep learning и большим языковым моделям (LLM). Может активироваться параллельно с другими словарями: например, статья про MLOps на Kubernetes — `ml-ai` + `k8s`; LLM в продакшене с Terraform — `ml-ai` + `devops`; векторная БД для RAG — `ml-ai` + `databases`.

**Не догма.** Отражает консенсус русскоязычного ML/AI-сообщества (Яндекс, Сбер, OpenAI/Anthropic переводы Хабра, DeepSchool, vc.ru/ai) на 2026 год. Терминология этого домена активно меняется — словарь будет обновляться.

## Принципы

1. **Имена моделей — оригинал.** GPT-4, Claude 4.7, Gemini 2.5, Llama 3.3, Mistral, DeepSeek, Qwen. Не «ГПТ-4».
2. **Имена компаний-разработчиков моделей — оригинал.** OpenAI, Anthropic, Google DeepMind, Meta AI, Mistral AI, Sber AI, Yandex.
3. **Имена фреймворков и библиотек — оригинал.** PyTorch, TensorFlow, JAX, Hugging Face, LangChain, LlamaIndex, scikit-learn, pandas, NumPy.
4. **Базовые ML-концепции — переводятся.** «Машинное обучение», «нейросеть», «обучающая выборка», «градиентный спуск», «функция потерь».
5. **LLM-специфические термины — гибрид.** «Эмбеддинги» (устоялось), «токен» (склоняется), «промпт» (склоняется), «инференс» (склоняется), но `attention`, `fine-tuning`, `RAG`, `RLHF` — оригинал.
6. **Аббревиатуры — оригинал.** AI, ML, DL, NLP, CV, RL, GAN, RNN, CNN, LSTM, GRU, LLM, RAG, RLHF, DPO, LoRA, PEFT, MLOps, MCP. При первом упоминании — расшифровка.
7. **В русском тексте — `ИИ`, не `AI`** (правило `brand-terminology`). Исключение: имена продуктов (AI Ассистент), составные технические термины (AI-агент — допустимо).
8. **В одном тексте — один вариант для каждого термина.** Не смешивай «модель» и `model`, «обучение» и `training`.

## Раздел 1. Базовые понятия

| English | Русский (рекомендуемый) | Альтернативы | Комментарий |
|---------|-------------------------|--------------|-------------|
| Artificial Intelligence (AI) | искусственный интеллект / ИИ | — | В русском — «ИИ». «AI» — только в названиях продуктов (AI Ассистент, AI-агент) |
| Machine Learning (ML) | машинное обучение / ML | — | «ML» — допустимо при повторном упоминании |
| Deep Learning (DL) | глубокое обучение / DL | — | — |
| Artificial General Intelligence (AGI) | AGI / общий ИИ | — | — |
| Artificial Superintelligence (ASI) | ASI | — | — |
| Generative AI / GenAI | генеративный ИИ / GenAI | — | — |
| Multimodal AI | мультимодальный ИИ | — | — |
| Supervised learning | обучение с учителем | — | — |
| Unsupervised learning | обучение без учителя | — | — |
| Semi-supervised learning | полуконтролируемое обучение | — | — |
| Reinforcement Learning (RL) | обучение с подкреплением / RL | — | — |
| Self-supervised learning | self-supervised обучение / самообучение | — | — |
| Transfer learning | трансферное обучение / transfer learning | — | — |
| Few-shot learning | few-shot обучение | — | — |
| Zero-shot learning | zero-shot обучение | — | — |
| Online learning | онлайн-обучение | — | — |
| Federated learning | федеративное обучение | — | — |
| Active learning | активное обучение | — | — |
| Model | модель | — | «Модель ИИ», «нейросетевая модель» |
| Algorithm | алгоритм | — | — |
| Data | данные | — | — |
| Dataset | датасет / набор данных | — | «Датасет» устоялось |
| Feature | признак / фича | — | «Фича» — разговорно |
| Label | метка / лейбл | — | «Лейбл» — разговорно |
| Class | класс | — | В задачах классификации |
| Inference | инференс / вывод | — | «Инференс» устоялось |
| Training | обучение | — | «Тренировка» — допустимо |
| Pretraining | предобучение / pretraining | — | — |
| Fine-tuning | дообучение / файнтюнинг / fine-tuning | — | «Файнтюнинг» устоялось |

## Раздел 2. Архитектуры моделей

| English | Русский | Комментарий |
|---------|---------|-------------|
| Neural Network (NN) | нейросеть / нейронная сеть | — |
| Artificial Neural Network (ANN) | ANN / искусственная нейросеть | — |
| Multilayer Perceptron (MLP) | MLP / многослойный перцептрон | — |
| Convolutional Neural Network (CNN) | CNN / свёрточная нейросеть | — |
| Recurrent Neural Network (RNN) | RNN / рекуррентная нейросеть | — |
| LSTM (Long Short-Term Memory) | LSTM | — |
| GRU (Gated Recurrent Unit) | GRU | — |
| Transformer | трансформер / Transformer | «Трансформер» устоялось. С заглавной — название архитектуры |
| Attention mechanism | механизм внимания / attention | — |
| Self-attention | self-attention | Не переводить |
| Cross-attention | cross-attention | — |
| Multi-head attention | multi-head attention | — |
| Encoder / Decoder | энкодер / декодер | — |
| Encoder-Decoder | encoder-decoder архитектура | — |
| Autoencoder | автоэнкодер | — |
| Variational Autoencoder (VAE) | VAE / вариационный автоэнкодер | — |
| Generative Adversarial Network (GAN) | GAN | — |
| Diffusion model | диффузионная модель / diffusion model | — |
| Stable Diffusion / SDXL | Stable Diffusion / SDXL | Имена продуктов |
| Mixture of Experts (MoE) | MoE / смесь экспертов | — |
| Graph Neural Network (GNN) | GNN / графовая нейросеть | — |
| Vision Transformer (ViT) | ViT / Vision Transformer | — |
| BERT, RoBERTa, ALBERT | BERT, RoBERTa, ALBERT | — |
| GPT (Generative Pretrained Transformer) | GPT | — |
| T5 (Text-to-Text Transfer Transformer) | T5 | — |
| Llama, Mistral, Qwen, DeepSeek | Llama, Mistral, Qwen, DeepSeek | Имена моделей |
| YOLO | YOLO | Object detection |
| CLIP | CLIP | Multimodal |
| Whisper | Whisper | Speech recognition |
| SAM (Segment Anything Model) | SAM | Image segmentation |

## Раздел 3. LLM-специфика

| English | Русский | Комментарий |
|---------|---------|-------------|
| Large Language Model (LLM) | большая языковая модель / LLM | При первом упоминании — расшифровка |
| Small Language Model (SLM) | SLM / малая языковая модель | — |
| Foundation model | foundation model / базовая модель | — |
| Frontier model | frontier model / передовая модель | — |
| Parameters (model size) | параметры | «Модель на 70B параметров», «175 млрд параметров» |
| Context window | контекстное окно / context window | — |
| Token | токен | Склоняется: токена, токену, токенов |
| Tokens per second (TPS) | токенов в секунду / TPS | — |
| Time to first token (TTFT) | TTFT / время до первого токена | — |
| Sampling | сэмплирование | — |
| Temperature | температура | «Параметр температуры» |
| Top-p / Top-k sampling | top-p / top-k сэмплирование | — |
| Greedy decoding | жадное декодирование / greedy | — |
| Beam search | beam search / лучевой поиск | — |
| Nucleus sampling | nucleus sampling | — |
| Generation | генерация | — |
| Completion | completion / завершение | — |
| Chat completion | chat completion | — |
| Streaming | streaming / потоковая генерация | — |
| Hallucination | галлюцинация | Склоняется: галлюцинации, галлюцинацию |
| Reasoning | reasoning / рассуждения | — |
| Chain-of-Thought (CoT) | Chain-of-Thought / CoT / цепочка рассуждений | — |
| Tree-of-Thought (ToT) | Tree-of-Thought / ToT | — |
| Thinking model / Reasoning model | thinking-модель / reasoning-модель | Claude Extended Thinking, GPT-o1 |
| Extended thinking | расширенное мышление / extended thinking | — |
| Prompt | промпт | Склоняется: промпта, промпту |
| System prompt | системный промпт | — |
| User prompt | пользовательский промпт | — |
| Few-shot prompting | few-shot промптинг | — |
| Zero-shot prompting | zero-shot промптинг | — |
| In-context learning (ICL) | in-context learning / обучение в контексте | — |
| Prompt engineering | промпт-инжиниринг / prompt engineering | — |
| Prompt injection | prompt injection / инъекция в промпт | — |
| Jailbreak | jailbreak / джейлбрейк | — |
| Prompt caching | кэширование промптов / prompt caching | — |
| Function calling / Tool use | function calling / tool use / вызов инструментов | — |
| JSON mode | JSON-режим / JSON mode | — |
| Structured output | структурированный вывод | — |
| Multimodal model | мультимодальная модель | Vision + text + audio |
| Vision model | vision-модель | — |

## Раздел 4. Токенизация и эмбеддинги

| English | Русский | Комментарий |
|---------|---------|-------------|
| Tokenization | токенизация | — |
| Tokenizer | токенизатор | — |
| BPE (Byte-Pair Encoding) | BPE | — |
| WordPiece | WordPiece | — |
| SentencePiece | SentencePiece | — |
| Subword tokenization | subword токенизация | — |
| Vocabulary / Vocab | словарь / vocab | — |
| Token ID | ID токена / token ID | — |
| Special token | специальный токен | `<bos>`, `<eos>`, `<pad>` |
| BOS / EOS / PAD / UNK | BOS / EOS / PAD / UNK | Не переводить |
| Embedding | эмбеддинг | Устоявшаяся транслитерация. «Вложение» — официальный перевод, реже встречается |
| Word embedding | словарный эмбеддинг / word embedding | — |
| Sentence embedding | sentence embedding | — |
| Document embedding | document embedding | — |
| Embedding model | эмбеддинг-модель / модель эмбеддингов | — |
| Vector | вектор | — |
| Dimension | размерность | «Размерность эмбеддинга 1536» |
| Vector space | векторное пространство | — |
| Dense vector | плотный вектор / dense vector | — |
| Sparse vector | разреженный вектор / sparse vector | — |
| Cosine similarity | косинусное сходство / cosine similarity | — |
| Dot product | скалярное произведение / dot product | — |
| Euclidean distance | евклидово расстояние | — |
| Nearest neighbor search | поиск ближайших соседей / nearest neighbor search | — |
| K-nearest neighbors (kNN) | kNN / k ближайших соседей | — |
| Approximate Nearest Neighbor (ANN) | ANN / приближённый поиск | Не путать с ANN-сетью |
| HNSW (Hierarchical Navigable Small World) | HNSW | — |
| IVF (Inverted File Index) | IVF | — |
| FAISS | FAISS | Library от Meta |
| Vector database | векторная БД | См. также `databases-translation-dictionary` |

## Раздел 5. Обучение моделей

| English | Русский | Комментарий |
|---------|---------|-------------|
| Training | обучение | — |
| Training data / Training set | обучающая выборка / training set | — |
| Validation set | валидационная выборка / validation set | — |
| Test set | тестовая выборка / test set | — |
| Train/Val/Test split | разделение train/val/test | — |
| Epoch | эпоха | — |
| Iteration | итерация | — |
| Batch | батч / пакет | «Батч» устоялось |
| Batch size | размер батча | — |
| Mini-batch | мини-батч | — |
| Gradient descent | градиентный спуск | — |
| Stochastic Gradient Descent (SGD) | SGD / стохастический градиентный спуск | — |
| Adam, AdamW, Adagrad | Adam, AdamW, Adagrad | Оптимизаторы — оригинал |
| Learning rate | learning rate / скорость обучения | — |
| Learning rate schedule | расписание learning rate | — |
| Warmup | warmup / прогрев | — |
| Loss function | функция потерь / loss | — |
| Cross-entropy loss | cross-entropy loss / кросс-энтропия | — |
| MSE (Mean Squared Error) | MSE / среднеквадратичная ошибка | — |
| Backpropagation | обратное распространение / backpropagation | — |
| Gradient | градиент | — |
| Gradient clipping | обрезка градиентов / gradient clipping | — |
| Gradient accumulation | накопление градиентов / gradient accumulation | — |
| Weight decay | weight decay / регуляризация весов | — |
| Regularization | регуляризация | — |
| Overfitting | переобучение / overfitting | — |
| Underfitting | недообучение / underfitting | — |
| Bias-variance tradeoff | tradeoff смещения и дисперсии | — |
| Pretraining | предобучение | — |
| Fine-tuning | дообучение / файнтюнинг | — |
| Instruction tuning | instruction tuning / обучение на инструкциях | — |
| RLHF (Reinforcement Learning from Human Feedback) | RLHF | При первом упоминании — расшифровка |
| DPO (Direct Preference Optimization) | DPO | — |
| RLAIF (RL from AI Feedback) | RLAIF | — |
| Constitutional AI | Constitutional AI | Anthropic-метод |
| LoRA (Low-Rank Adaptation) | LoRA | — |
| QLoRA | QLoRA | — |
| PEFT (Parameter-Efficient Fine-Tuning) | PEFT | — |
| Adapter | адаптер | — |
| Prefix tuning | prefix tuning | — |
| Prompt tuning | prompt tuning | — |
| Knowledge distillation | дистилляция знаний / knowledge distillation | — |
| Teacher / Student model | учитель / ученик | — |
| Quantization | квантизация | INT8, INT4, FP8, GGUF |
| GGUF, GGML | GGUF, GGML | Форматы квантизации |
| Pruning | прунинг / сокращение | — |
| Mixed-precision training | mixed-precision обучение | FP16, BF16 |
| Curriculum learning | curriculum learning | — |
| Catastrophic forgetting | catastrophic forgetting / катастрофическое забывание | — |

## Раздел 6. RAG (Retrieval-Augmented Generation)

| English | Русский | Комментарий |
|---------|---------|-------------|
| RAG (Retrieval-Augmented Generation) | RAG / генерация с дополнительным поиском | При первом упоминании — расшифровка |
| Retrieval | retrieval / извлечение | — |
| Retriever | retriever / извлекатель | — |
| Reranker | reranker / переранжировщик | — |
| Chunking | чанкинг / разбиение на чанки | — |
| Chunk | чанк / фрагмент | — |
| Chunk size | размер чанка | — |
| Overlap | overlap / перекрытие | — |
| Hybrid search | гибридный поиск / hybrid search | Dense + sparse |
| Semantic search | семантический поиск | — |
| Lexical search / BM25 | лексический поиск / BM25 | — |
| Indexing | индексация | — |
| Knowledge base | база знаний | — |
| Context retrieval | извлечение контекста | — |
| Contextual retrieval | контекстный retrieval | Anthropic-метод |
| Multi-hop retrieval | multi-hop retrieval | — |
| Self-RAG | Self-RAG | Не переводить |
| GraphRAG | GraphRAG | Microsoft-метод |
| Vector store | vector store / векторное хранилище | — |
| Vector database | векторная БД | Pinecone, Weaviate, Qdrant, Milvus, Chroma, pgvector |
| Query expansion | расширение запроса / query expansion | — |
| Query rewriting | переписывание запроса | — |
| RAG evaluation | оценка RAG | Метрики: faithfulness, answer relevancy, context precision/recall |

## Раздел 7. AI-агенты и оркестрация

| English | Русский | Комментарий |
|---------|---------|-------------|
| AI Agent | AI-агент / ИИ-агент | Через дефис |
| Multi-agent system | мультиагентная система | — |
| Agent orchestration | оркестрация агентов | — |
| Tool use | tool use / использование инструментов | — |
| Function calling | function calling / вызов функций | — |
| Tool definition | определение инструмента / tool definition | — |
| MCP (Model Context Protocol) | MCP / Model Context Protocol | Стандарт Anthropic для подключения инструментов к LLM |
| MCP server | MCP-сервер | — |
| Agent SDK | Agent SDK | Anthropic Agent SDK, OpenAI Agents SDK |
| Subagent | субагент | — |
| Orchestrator | оркестратор | — |
| ReAct (Reasoning + Acting) | ReAct | — |
| Plan-and-Execute | plan-and-execute | — |
| Memory (agent) | память (агента) | Short-term, long-term, episodic |
| Context compaction | компакция контекста | — |
| Subagent context | контекст субагента | — |
| Computer use | computer use / использование компьютера | Claude Computer Use |
| Browser use | browser use | — |
| Code execution | code execution / выполнение кода | — |
| Sandboxing | sandboxing / песочница | — |
| Guardrails | guardrails / ограничения | — |
| Safety filter | safety-фильтр / фильтр безопасности | — |
| Tool result | tool result / результат инструмента | — |
| Tool offload | tool offload / офлоад tool-результатов | — |

## Раздел 8. Prompt Engineering

| English | Русский | Комментарий |
|---------|---------|-------------|
| Prompt engineering | промпт-инжиниринг / prompt engineering | — |
| Prompt template | шаблон промпта / prompt template | — |
| Chain-of-Thought (CoT) prompting | CoT-промптинг | — |
| Few-shot prompting | few-shot промптинг | — |
| Zero-shot prompting | zero-shot промптинг | — |
| One-shot prompting | one-shot промптинг | — |
| Role prompting | role prompting | — |
| Persona | персона | «Промпт-персона» |
| Self-consistency | self-consistency | — |
| Self-refine | self-refine | — |
| Self-critique | self-critique | — |
| Tree-of-Thoughts (ToT) | Tree-of-Thoughts | — |
| Graph-of-Thoughts (GoT) | Graph-of-Thoughts | — |
| Skeleton-of-Thought | Skeleton-of-Thought | — |
| Prompt chaining | prompt chaining / цепочка промптов | — |
| Prompt injection attack | атака prompt injection | — |
| System prompt | системный промпт | — |
| Examples / Demonstrations | примеры / демонстрации | В few-shot |
| Output format | формат вывода | — |
| Output parser | парсер вывода / output parser | — |

## Раздел 9. Evaluation и метрики

| English | Русский | Комментарий |
|---------|---------|-------------|
| Evaluation | оценка / evaluation | — |
| Benchmark | бенчмарк | Склоняется: бенчмарка, бенчмарку |
| Eval | eval / оценка | — |
| Accuracy | точность / accuracy | — |
| Precision | precision / точность | Различать с accuracy |
| Recall | recall / полнота | — |
| F1 score | F1-метрика / F1 score | — |
| AUC / ROC | AUC / ROC | — |
| Confusion matrix | матрица ошибок / confusion matrix | — |
| Perplexity | перплексия / perplexity | LLM-метрика |
| BLEU | BLEU | Machine translation |
| ROUGE | ROUGE | Summarization |
| METEOR | METEOR | — |
| BERTScore | BERTScore | — |
| Loss curve | кривая потерь | — |
| Learning curve | кривая обучения | — |
| MMLU | MMLU | LLM-бенчмарк |
| HumanEval | HumanEval | Code-бенчмарк |
| MATH, GSM8K | MATH, GSM8K | Reasoning-бенчмарки |
| MT-Bench / Arena | MT-Bench / Chatbot Arena | LLM-бенчмарк |
| Hallucination | галлюцинация | — |
| Factuality | фактологичность | — |
| Faithfulness (RAG) | faithfulness / достоверность | — |
| Toxicity | токсичность | — |
| Bias (model) | предвзятость / смещение | — |
| Robustness | устойчивость / robustness | — |
| Calibration | калибровка | — |
| LLM-as-a-judge | LLM-as-a-judge / LLM-судья | — |

## Раздел 10. Данные и датасеты

| English | Русский | Комментарий |
|---------|---------|-------------|
| Dataset | датасет / набор данных | — |
| Corpus | корпус | «Корпус текстов» |
| Annotation | разметка / аннотирование | — |
| Labeling | разметка / labeling | — |
| Data labeling | разметка данных | — |
| Annotator | разметчик / аннотатор | — |
| Crowdsourcing | краудсорсинг | — |
| Data augmentation | аугментация данных | — |
| Synthetic data | синтетические данные | — |
| Data leakage | утечка данных (между train/test) | Не путать с security leak |
| Data drift | data drift / дрейф данных | — |
| Concept drift | concept drift | — |
| Class imbalance | дисбаланс классов | — |
| Oversampling / Undersampling | oversampling / undersampling | — |
| SMOTE | SMOTE | Synthetic Minority Over-sampling |
| Train / Val / Test | train / val / test | — |
| Holdout set | holdout set / отложенная выборка | — |
| Cross-validation | кросс-валидация | — |
| K-fold | K-fold | — |
| Stratified sampling | стратифицированная выборка | — |
| Common Crawl | Common Crawl | — |
| The Pile | The Pile | Dataset |
| RedPajama | RedPajama | — |
| Hugging Face Datasets | Hugging Face Datasets | — |

## Раздел 11. MLOps

| English | Русский | Комментарий |
|---------|---------|-------------|
| MLOps | MLOps | Не переводится |
| LLMOps | LLMOps | — |
| Notebook (Jupyter и т. п.) | ноутбук / notebook | В ML-контексте «ноутбук» устоялся (Jupyter-ноутбук); при риске путаницы с laptop — «Jupyter-ноутбук» или «notebook-сервер». Склонение «notebook-и / notebook-ов» не использовать — либо русский «ноутбук», либо составное «notebook-сервер» (фидбек редакторов 2026-07-22) |
| Model serving | model serving / обслуживание модели | — |
| Model deployment | развёртывание модели | — |
| Model registry | реестр моделей / model registry | MLflow Model Registry |
| Feature store | feature store / хранилище признаков | Feast, Tecton |
| Feature engineering | feature engineering / разработка признаков | — |
| Model monitoring | мониторинг моделей | — |
| Model drift | дрейф модели / model drift | — |
| Prediction service | сервис предсказаний / prediction service | — |
| Online inference | онлайн-инференс | — |
| Batch inference | batch-инференс | — |
| Streaming inference | streaming-инференс | — |
| A/B testing (ML) | A/B-тестирование моделей | — |
| Shadow deployment | shadow deployment | — |
| Champion / Challenger | champion / challenger модели | — |
| Model versioning | версионирование моделей | — |
| Experiment tracking | трекинг экспериментов | MLflow, Weights & Biases |
| MLflow | MLflow | — |
| Weights & Biases (wandb) | Weights & Biases / wandb | — |
| Kubeflow | Kubeflow | — |
| Ray, Ray Serve | Ray, Ray Serve | — |
| BentoML | BentoML | — |
| Triton Inference Server | Triton Inference Server | NVIDIA |
| vLLM, TGI (Text Generation Inference) | vLLM, TGI | — |
| TensorRT, TensorRT-LLM | TensorRT, TensorRT-LLM | NVIDIA |
| ONNX | ONNX | Open Neural Network Exchange |
| Model card | model card / карточка модели | — |

## Раздел 12. Фреймворки и библиотеки

| English | Русский | Комментарий |
|---------|---------|-------------|
| PyTorch | PyTorch | Не переводится |
| TensorFlow | TensorFlow | — |
| JAX, Flax | JAX, Flax | — |
| Keras | Keras | — |
| Hugging Face | Hugging Face | Имя компании, без склонения |
| Transformers (library) | Transformers (библиотека HF) | Не путать с архитектурой Transformer |
| Diffusers | Diffusers | — |
| Datasets | Datasets | HF |
| Tokenizers | Tokenizers | HF |
| Accelerate, PEFT (library) | Accelerate, PEFT | HF |
| LangChain | LangChain | — |
| LangGraph | LangGraph | — |
| LlamaIndex | LlamaIndex | — |
| Haystack | Haystack | RAG framework |
| DSPy | DSPy | — |
| Instructor | Instructor | Structured output |
| Pydantic AI | Pydantic AI | — |
| scikit-learn | scikit-learn | — |
| pandas, NumPy | pandas, NumPy | — |
| XGBoost, LightGBM, CatBoost | XGBoost, LightGBM, CatBoost | Yandex CatBoost |
| spaCy, NLTK | spaCy, NLTK | NLP |
| OpenCV | OpenCV | CV |
| Ultralytics (YOLO) | Ultralytics | — |
| Stable Baselines3 | Stable Baselines3 | RL |
| Anthropic SDK | Anthropic SDK | — |
| OpenAI Python SDK | OpenAI Python SDK / `openai` | — |
| Anthropic Claude API | Anthropic API / Claude API | — |
| OpenAI API | OpenAI API | — |

## Раздел 13. Hardware и инфраструктура

| English | Русский | Комментарий |
|---------|---------|-------------|
| GPU | GPU / графический процессор | «GPU» в технических текстах |
| CUDA | CUDA | NVIDIA |
| TPU (Tensor Processing Unit) | TPU | Google |
| NPU (Neural Processing Unit) | NPU | — |
| AI accelerator | AI-ускоритель | — |
| NVIDIA H100 / H200 / B200 / A100 / L40S / L4 | H100 / H200 / B200 / A100 / L40S / L4 | Имена GPU |
| AMD MI300X | MI300X | — |
| VRAM | VRAM / видеопамять | — |
| HBM (High Bandwidth Memory) | HBM | HBM3, HBM3e |
| FLOPS / TFLOPS / PFLOPS | FLOPS / TFLOPS / PFLOPS | Производительность |
| FP32, FP16, BF16, FP8, INT8, INT4 | FP32, FP16, BF16, FP8, INT8, INT4 | Не переводить |
| Tensor cores | тензорные ядра / Tensor Cores | — |
| Multi-GPU | multi-GPU | — |
| Distributed training | распределённое обучение | — |
| Data parallelism | data parallelism / параллелизм по данным | — |
| Model parallelism | model parallelism / параллелизм по модели | — |
| Pipeline parallelism | pipeline parallelism | — |
| Tensor parallelism | tensor parallelism | — |
| FSDP (Fully Sharded Data Parallel) | FSDP | — |
| ZeRO | ZeRO | DeepSpeed optimization |
| NCCL | NCCL | NVIDIA Collective Communications |
| InfiniBand | InfiniBand | — |
| Spot instances | spot-инстансы | — |
| Reserved instances | reserved-инстансы | — |
| GPU memory | GPU-память / VRAM | — |
| KV cache | KV-кэш / KV cache | LLM-inference |
| Continuous batching | continuous batching | vLLM-оптимизация |
| Paged attention | paged attention | vLLM |
| Speculative decoding | speculative decoding / спекулятивное декодирование | — |
| Prefill (stage) | префилл / этап префилла | LLM-inference, устоявшаяся калька |
| Decode (stage) | декодирование / этап декодирования | LLM-inference, **НЕ «декод»** — см. раздел 18 |
| Prefill workers | префилл-воркеры | дезагрегированный инференс |
| Decode workers | воркеры декодирования | **не «декод-воркеры»** |
| Disaggregated serving | дезагрегированный инференс / disaggregated serving | NVIDIA Dynamo, llm-d |
| Aggregated serving | агрегированный инференс | антоним к disaggregated |
| Time to first token (TTFT) | время до первого токена (TTFT) | inference SLA-метрика |
| Inter-token latency (ITL) | задержка между токенами (ITL) | inference SLA-метрика |

## Раздел 14. AI-продукты и игроки рынка

| English | Русский | Комментарий |
|---------|---------|-------------|
| ChatGPT | ChatGPT | — |
| Claude | Claude | Имя продукта Anthropic |
| Gemini | Gemini | Google |
| Copilot | Copilot | GitHub, Microsoft |
| Cursor, Windsurf | Cursor, Windsurf | AI IDE |
| Perplexity | Perplexity | Search |
| Midjourney, DALL-E | Midjourney, DALL-E | Image generation |
| Sora, Veo | Sora, Veo | Video generation |
| ElevenLabs | ElevenLabs | Voice |
| Suno, Udio | Suno, Udio | Music |
| HuggingChat | HuggingChat | — |
| LM Studio, Ollama | LM Studio, Ollama | Local LLM |
| OpenAI | OpenAI | — |
| Anthropic | Anthropic | — |
| Google DeepMind | Google DeepMind | — |
| Meta AI | Meta AI | — |
| Mistral AI | Mistral AI | — |
| xAI | xAI | — |
| Cohere, AI21 Labs, Reka | Cohere, AI21 Labs, Reka | — |
| Sber AI / GigaChat | Sber AI / GigaChat | — |
| YandexGPT / Yandex | YandexGPT / Yandex | — |
| T-Bank ML | T-Bank ML | — |

## Раздел 15. Безопасность ИИ

| English | Русский | Комментарий |
|---------|---------|-------------|
| AI safety | AI safety / безопасность ИИ | — |
| Alignment | alignment / выравнивание | — |
| Misalignment | misalignment / рассогласование | — |
| Red teaming (AI) | red teaming | — |
| Adversarial attack | adversarial attack / атака с противоборством | — |
| Adversarial example | adversarial example | — |
| Model jailbreak | jailbreak модели | — |
| Prompt injection | prompt injection | — |
| Data poisoning | отравление данных / data poisoning | — |
| Model poisoning | отравление модели | — |
| Membership inference | membership inference атака | — |
| Model extraction | model extraction | — |
| Federated learning (security) | федеративное обучение | — |
| Differential privacy | дифференциальная приватность | — |
| Homomorphic encryption | гомоморфное шифрование | — |
| Watermarking (AI) | watermarking / водяные знаки для ИИ | — |
| Provenance | provenance / происхождение | — |
| AI content detection | детекция ИИ-контента | — |
| Deepfake | deepfake / дипфейк | — |

## Раздел 16. Глаголы и действия

| English | Русский | Комментарий |
|---------|---------|-------------|
| to train (a model) | обучить / тренировать (модель) | — |
| to fine-tune | дообучить / зафайнтюнить | — |
| to pretrain | предобучить | — |
| to infer | сделать инференс | — |
| to generate | генерировать | — |
| to prompt | запромтить / спромптить | Разг. |
| to embed | сделать эмбеддинг / эмбеддить | — |
| to retrieve | извлечь / сделать retrieval | — |
| to rerank | переранжировать | — |
| to chunk | разбить на чанки / зачанкать | — |
| to quantize | квантизовать | — |
| to distill | дистиллировать | — |
| to align | выровнять / aligned | — |
| to evaluate | оценить / прогнать eval | — |
| to benchmark | сделать бенчмарк / прогнать на бенчмарке | — |
| to deploy (a model) | задеплоить модель | — |
| to serve (a model) | обслуживать модель / сделать model serving | — |

## Раздел 17. Падежные формы

### Модель / Промпт / Токен / Эмбеддинг / Датасет / Чанк

- **Модель** (ж.р.): модели, модель, моделью; мн.ч. модели, моделей
- **Промпт** (м.р.): промпта, промпту, промптом; мн.ч. промпты, промптов
- **Токен** (м.р.): токена, токену, токеном; мн.ч. токены, токенов
- **Эмбеддинг** (м.р.): эмбеддинга, эмбеддингу, эмбеддингом; мн.ч. эмбеддинги, эмбеддингов
- **Датасет** (м.р.): датасета, датасету, датасетом; мн.ч. датасеты, датасетов
- **Чанк** (м.р.): чанка, чанку, чанком; мн.ч. чанки, чанков
- **Бенчмарк** (м.р.): бенчмарка, бенчмарку, бенчмарком
- **Галлюцинация** (ж.р.): галлюцинации, галлюцинацию, галлюцинацией

### Инференс / Файнтюнинг / Промптинг

Мужской род: инференса, инференсу, инференсом. Файнтюнинга, файнтюнингу. Промптинга.

### LLM / GPT / Claude / Gemini / RAG / RLHF

**Не склоняются.** «В LLM», «у GPT-4», «через Claude», «для RAG». Род — мужской: «LLM ответил».

В составных словах через дефис: «LLM-агент», «GPT-промпт», «RAG-система», «RLHF-обучение».

### OpenAI / Anthropic / Google / Meta / Mistral / HuggingFace

**Не склоняются.** «От OpenAI», «в Anthropic», «у Meta». НЕ «ОпенЭйАем».

### PyTorch / TensorFlow / LangChain / Hugging Face

**Не склоняются.** «На PyTorch», «через LangChain», «с Hugging Face».

### CUDA, TPU, GPU

**Не склоняются.** «На CUDA», «через TPU», «GPU H100». В составных — через дефис: «GPU-память», «AI-ускоритель».

### Параметры модели — пишутся с английским суффиксом

- 7B (миллиардов): «модель Llama 3 8B», «70B параметров». «B» = billion
- 70K (тысяч): «контекст 200K токенов»
- В русском тексте — допустимо «70 млрд параметров»

## Раздел 18. Типовые ошибки переводчика

### 1. AI → ИИ в русском тексте

```
✗ «AI-модель», «AI-агент» (везде в статье)
✓ «ИИ-модель», «ИИ-агент» (правило brand-terminology)
```

Исключения: имена продуктов («AI Ассистент»), устоявшиеся составные («AI-агент» допустимо в технических статьях).

### 2. Перевод имён моделей

```
✗ «ГПТ-4», «Клод», «Лама»
✓ «GPT-4», «Claude», «Llama»
```

Имена моделей — оригинал.

### 3. «Машина» vs «модель»

```
✗ «Машинное обучение машины» (тавтология)
✗ «Машина сгенерировала текст»
✓ «Модель сгенерировала текст»
```

`Model` — переводится как «модель», не «машина».

### 4. Embedding → «вложение» vs «эмбеддинг»

«Эмбеддинг» — устоявшаяся транслитерация в практическом переводе. «Вложение» — официальный академический перевод, но в большинстве технических статей звучит чужеродно. В одном тексте — один вариант.

### 5. Перевод «training» vs «learning»

- **Training** — процесс обучения (`model training`)
- **Learning** — концепция/тип (`machine learning`, `deep learning`, `reinforcement learning`)

Оба переводятся как «обучение», но контекст разный. В переводе можно использовать «тренировка модели» для `training` и «обучение» для общих концепций.

### 6. Token как «токен» (правильно)

В контексте LLM `token` — это **токен** (единица текста после токенизации). Не путать с:
- **Token** в безопасности (auth token) — тоже «токен», но контекст другой
- **Token** в финтехе (NFT, blockchain) — тоже «токен», другой контекст

Контекст обычно ясен из статьи.

### 7. Hallucination → «галлюцинация» (правильно)

```
✗ «выдумывание»
✓ «галлюцинация»
```

Устоявшийся термин в ML-сообществе.

### 8. Calling vs invoking (function calling)

```
✗ «вызывание функции»
✓ «вызов функции / function calling»
```

### 9. Перевод параметров моделей

```
✗ «модель на 7 миллиардов»
✓ «модель на 7B параметров» / «модель с 7 млрд параметров»
```

Сохранять `B` (billion), `M` (million), `T` (trillion) — устоявшаяся нотация.

### 10. «Промпт» vs «подсказка»

`Prompt` в LLM — это **промпт**, не «подсказка». «Подсказка» — это в IDE (autocomplete suggestion).

### 11. Inference как «вывод» vs «инференс»

«Инференс» устоявшийся термин в ML-сообществе. «Вывод» — официальный перевод, но в практических статьях чаще «инференс».

### 12. RAG как «РАГ»

```
✗ «РАГ-система»
✓ «RAG-система»
```

RAG — английская аббревиатура, не переводится.

### 13. Калька «является»

```
✗ «GPT-4 является мощной моделью»
✓ «GPT-4 — мощная модель»
```

### 14. «Декод» как существительное

```
✗ «этап декода», «декод-воркеры», «префилл и декод»
✓ «этап декодирования», «воркеры декодирования», «префилл и декодирование»
```

В английских статьях про LLM-инференс `decode` используется как существительное-обозначение этапа (по аналогии с `prefill`). По-русски «декод» — калька: в словаре нет такого существительного, есть только «декодирование» (процесс) и «декодер» (устройство). При этом «префилл» уже устоялся в русском LLM-сообществе как калька (Хабр, Yandex Research) — оставляем. Асимметрия сознательная: следуем фактическому узусу, а не формальной симметрии.

Латиница `decode`, `--role=decode`, `decode-workers`, имена подов `*-decode-*` в YAML и shell — **НЕ ТРОГАТЬ**, это идентификаторы.

Источник правила: ревью перевода NVIDIA Dynamo (v4, 2026-05-20), «2026-05-20-deploying-disaggregated-llm-inference-on-kubernetes-v4» (внутренний материал системы, в эту выгрузку не входит).

## Раздел 19. Чек-лист переводчика + источники

### Чек-лист

- [ ] **AI → ИИ** в русском тексте (кроме имён продуктов)
- [ ] **Имена моделей** (GPT-4, Claude, Gemini, Llama, Mistral) — оригинал, не транслитерированы
- [ ] **Имена компаний** (OpenAI, Anthropic, Google DeepMind, Meta AI) — оригинал, не склоняются
- [ ] **Имена фреймворков** (PyTorch, TensorFlow, JAX, Hugging Face, LangChain, LlamaIndex) — оригинал
- [ ] **Аббревиатуры** (LLM, RAG, RLHF, LoRA, PEFT, MoE, CoT, CNN, RNN, GAN, MCP, MLOps) — оригинал, расшифровка при первом упоминании
- [ ] **Параметры моделей** (`7B`, `70K`, `175B`) — сохранены в английской нотации или переведены как «млрд параметров»
- [ ] **`Token` как «токен»** — в LLM-контексте, склоняется
- [ ] **`Embedding` как «эмбеддинг»** или «вложение» — в одном тексте один вариант
- [ ] **`Inference` как «инференс»** или «вывод» — один вариант
- [ ] **`Prompt` как «промпт»** — не «подсказка»
- [ ] **`Hallucination` как «галлюцинация»** — не «выдумывание»
- [ ] **`Training` vs `learning`** — различены в переводе
- [ ] **Имена GPU** (H100, A100, L40S, MI300X), CUDA — оригинал
- [ ] **Числовые форматы** (FP16, BF16, INT8, FP8) — оригинал
- [ ] **Калек избегли** — нет «является», «позволяет»
- [ ] **Кавычки** — «ёлочки»
- [ ] **Атрибуция оригинала** — есть

### Что делать с новыми терминами

1. Проверь документацию OpenAI/Anthropic (часто на английском, но в Антропик-блогах терминология стабильна)
2. Проверь публикации на Хабре от Яндекса, Сбера, OTUS, T-Bank
3. Проверь vc.ru/ai и DeepSchool.ru
4. Если нигде нет — оставь в оригинале + `[прим. перев.: устоявшегося перевода нет]`

### Источники

| Источник | Назначение |
|----------|-----------|
| OpenAI Docs — https://platform.openai.com/docs | Эталонная английская терминология |
| Anthropic Docs — https://docs.anthropic.com/ | Claude API, Agent SDK, MCP |
| Hugging Face Docs — https://huggingface.co/docs | Transformers, Datasets, PEFT |
| Яндекс на Хабре — https://habr.com/ru/companies/yandex/ | Российская терминология ML |
| Сбер на Хабре — https://habr.com/ru/companies/sberbank/ | GigaChat, GigaEmbeddings |
| OTUS на Хабре — https://habr.com/ru/companies/otus/ | Серия статей по ML/LLM |
| DeepSchool — https://blog.deepschool.ru/ | Практические руководства |
| vc.ru/ai — https://vc.ru/ai | Российский AI-контент |
| Альянс ПРО (tran.su) | Методология для ИТ-переводчиков |

Версия словаря: **2026-05-16 v1.0**.

## Связь с другими словарями

ML/AI часто пересекается с другими доменами:

- **ML/AI + K8s** — статья про MLOps на Kubernetes, Kubeflow, Ray Serve, GPU-ноды в K8s. Подключаются `ml-ai` + `k8s`.
- **ML/AI + DevOps** — статья про CI/CD для ML-моделей, Terraform для GPU-инфраструктуры. Подключаются `ml-ai` + `devops`.
- **ML/AI + Databases** — статья про векторные БД (pgvector, Qdrant, Pinecone), feature store. Подключаются `ml-ai` + `databases`.
- **ML/AI + Networking** — статья про распределённое обучение через InfiniBand, NCCL. Подключаются `ml-ai` + `networking`.
- **Все пять** — статья «MLOps-платформа для LLM-инференса на Kubernetes с pgvector через CI/CD-пайплайн и InfiniBand-сеть» — активируются все.

Приоритеты при конфликте — в `references/translation-standards.md`, секция «Приоритеты при множественной активации словарей».
