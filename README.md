<div align="center">
  <img src="assets/banner.svg" alt="Эдуард — AI Engineer" width="100%" />
</div>

## Обо мне

Меня зовут **Эдуард**. Я развиваюсь как AI Engineer и создаю портфолио прикладных
ИИ-систем — от обработки данных и оценки качества до API, тестирования и развёртывания.

Мне интересны задачи на стыке **LLM, обработки документов, RAG и production-разработки**.
В проектах уделяю внимание не только демонстрации модели, но и воспроизводимости,
измеримому качеству, ограничениям и удобному интерфейсу.

## Проекты

### [Document Intelligence Platform](https://github.com/RegarZ/document-intelligence-platform)

Главный интеграционный проект: пользователь загружает PDF, получает извлечённую
структуру, задаёт вопрос по документу и видит ответ с цитатами до страницы-источника.

**Версия 0.2.0:** FastAPI gateway, два независимых downstream-сервиса, Docker
Compose, dependency-aware health checks, OCR fallback для сканированных PDF
(Tesseract, `rus+eng`), 17 тестов, CI для Python 3.11–3.13 и проверка Docker-сборки.

**Инженерный акцент:** валидация файла до отправки downstream, таймауты,
нормализация ошибок сервисов и явная обработка сканов без текстового слоя.

[`Открыть Live Demo →`](https://document-intelligence-demo.dnhnin303661239.chatgpt.site) ·
[`Код и документация →`](https://github.com/RegarZ/document-intelligence-platform)

### [LLM Evaluation & Prompt Regression Platform](https://github.com/RegarZ/llm-evaluation-platform)

Сервис для воспроизводимого сравнения baseline и candidate версий промпта по
качеству, валидности JSON, стоимости и p95 latency с автоматическим решением
`PASS/FAIL` для CI.

**Версия 0.1.0:** FastAPI, CLI, versioned evaluation dataset, Exact Match,
Token F1, content requirements, quality gates, срезы по тегам, Docker,
22 теста и покрытие 99%.

**Демонстрационный результат:** качество candidate выросло с 0.842 до 1.000,
стоимость — на 6.12%, p95 latency — на 2.68%; все бюджеты соблюдены.

[`Код и воспроизводимый эксперимент →`](https://github.com/RegarZ/llm-evaluation-platform)

### [Сервис структурированного извлечения данных из PDF](https://github.com/RegarZ/pdf-data-extraction-service)

REST API, преобразующий PDF-документы в типизированный JSON: текст по страницам,
метаданные, таблицы и пользовательские поля с указанием страницы-источника.

**Версия 0.2.0:** FastAPI, PyMuPDF, Pydantic, безопасные regex-шаблоны,
11 тестов, покрытие 88%, Dockerfile и CI для Python 3.11–3.13.

**Следующие этапы:** OCR для сканов, LLM fallback, bounding box для evidence
и evaluation-набор с метриками качества.

[`Код и документация →`](https://github.com/RegarZ/pdf-data-extraction-service)

### [RAG Retrieval & Evaluation Service](https://github.com/RegarZ/rag-evaluation-service)

API для гибридного retrieval: deterministic embeddings + BM25, настраиваемый
reranking, extractive-ответы и цитаты до исходных чанков.

**Версия 0.1.0:** FastAPI, Pydantic, Recall@K, MRR, nDCG@K, Hit Rate,
12 тестов, покрытие 98%, Dockerfile и успешный CI для Python 3.11–3.13.

**Инженерный акцент:** метрики считаются по уникальным документам, поэтому
повторные чанки одного источника не завышают качество retrieval.

[`Код и документация →`](https://github.com/RegarZ/rag-evaluation-service)

## Технологии

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI" />
  <img src="https://img.shields.io/badge/Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white" alt="Pydantic" />
  <img src="https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white" alt="pytest" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker" />
  <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" alt="GitHub Actions" />
</p>

## Направления развития

- Document AI и мультимодальная обработка документов
- RAG-системы с измеримым качеством поиска и ответов
- LLM evaluation, prompt regression и наблюдаемость
- Надёжные API и сервисы для запуска моделей в production

## Контакты

- GitHub: [@RegarZ](https://github.com/RegarZ)

---

<div align="center">
  <sub>Профиль и проекты обновляются по мере разработки.</sub>
</div>
