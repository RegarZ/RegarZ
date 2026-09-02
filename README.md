<div align="center">
  <img src="assets/banner.svg" alt="Эдуард — AI Engineer: Document AI, RAG, LLM Evaluation" width="100%" />

  <br />

  <b>Создаю прикладные AI-системы, результат которых можно проверить:</b><br />
  Document Intelligence · RAG с цитатами · LLM Evaluation · Production-oriented API

  <br /><br />

  <a href="https://document-intelligence-demo.dnhnin303661239.chatgpt.site">
    <img src="https://img.shields.io/badge/Открыть_Live_Demo-111827?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Открыть Live Demo" />
  </a>
  <a href="https://github.com/RegarZ/document-intelligence-platform">
    <img src="https://img.shields.io/badge/Главный_проект-0F766E?style=for-the-badge&logo=github&logoColor=white" alt="Document Intelligence Platform" />
  </a>
  <a href="https://github.com/RegarZ/llm-evaluation-platform">
    <img src="https://img.shields.io/badge/LLM_Evaluation-B45309?style=for-the-badge&logo=githubactions&logoColor=white" alt="LLM Evaluation Platform" />
  </a>
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Публичные_проекты-4-2563EB?style=flat-square" alt="4 публичных проекта" />
  <img src="https://img.shields.io/badge/Автотесты-62-16A34A?style=flat-square" alt="62 автотеста" />
  <img src="https://img.shields.io/badge/Покрытие-87–99%25-7C3AED?style=flat-square" alt="Покрытие проектов от 87 до 99 процентов" />
  <img src="https://img.shields.io/badge/CI-Python_3.11–3.13-0EA5E9?style=flat-square&logo=githubactions&logoColor=white" alt="CI на Python 3.11–3.13" />
  <img src="https://img.shields.io/badge/Public_Live_Demo-online-059669?style=flat-square" alt="Публичное интерактивное демо" />
</p>

## Обо мне

Меня зовут **Эдуард**. Я развиваюсь как AI Engineer и собираю портфолио вокруг
полного жизненного цикла AI-функции: данные и документы → retrieval → проверяемый
ответ → измерение качества → API, тесты, контейнеризация и CI.

В проектах мне важны **воспроизводимость, типизированные контракты, evidence до
источника, явные ограничения и измеримые release gates**. Поэтому репозитории
содержат не только демонстрационный код, но и тестовые наборы, метрики, Docker и
автоматические проверки.

## Главный проект — Document Intelligence Platform

<a href="https://document-intelligence-demo.dnhnin303661239.chatgpt.site">
  <img src="assets/document-intelligence-showcase.png" alt="Document Intelligence: скан счёта, OCR rus+eng, извлечённые поля и ответ с подтверждением на странице 1" width="100%" />
</a>

<p align="center">
  <i>Сканированный PDF → OCR → извлечённые поля → hybrid retrieval → ответ с цитатой до страницы</i>
</p>

- FastAPI gateway объединяет PDF Extraction API и RAG API в один workflow;
- проверяет MIME-тип, размер и PDF-заголовок до отправки downstream;
- запускает Tesseract OCR fallback (`rus+eng`) для документов без текстового слоя;
- возвращает ответ с фрагментом и номером страницы-источника;
- нормализует ошибки сервисов, применяет таймауты и dependency-aware health checks;
- запускается через Docker Compose; CI проверяет Python 3.11–3.13 и Docker build;
- orchestration и OCR fallback покрыты 17 автоматическими тестами.

> Live Demo — интерактивная витрина со встроенным обезличенным счётом. Полный
> backend, OCR-адаптер и Docker Compose находятся в исходном репозитории.

[`Открыть Live Demo →`](https://document-intelligence-demo.dnhnin303661239.chatgpt.site) ·
[`Код и документация →`](https://github.com/RegarZ/document-intelligence-platform) ·
[`Успешный CI →`](https://github.com/RegarZ/document-intelligence-platform/actions)

## LLM Evaluation & Prompt Regression

<a href="https://github.com/RegarZ/llm-evaluation-platform">
  <img src="assets/llm-evaluation-report.png" alt="Отчёт LLM Evaluation с решением PASS, сравнением baseline и candidate и пройденными quality gates" width="100%" />
</a>

<p align="center">
  <i>Prompt regression gate: качество выросло до 1.000, бюджеты стоимости и задержки соблюдены</i>
</p>

Платформа сравнивает baseline и candidate на versioned dataset, считает Exact Match,
Token F1, JSON validity, content requirements, cost и p95 latency, находит регрессии
по кейсам и возвращает решение `PASS/FAIL` с exit code для CI.

Воспроизводимый recorded-mode эксперимент на 6 fixture-кейсах: **quality
0.842 → 1.000**, **cost +6.12%**, **p95 latency +2.68%**, 0 регрессий. Проект
содержит REST API, CLI, Docker, 22 теста и покрытие 99%.

[`Репозиторий →`](https://github.com/RegarZ/llm-evaluation-platform) ·
[`Релиз v0.1.0 →`](https://github.com/RegarZ/llm-evaluation-platform/releases/tag/v0.1.0) ·
[`Успешный CI →`](https://github.com/RegarZ/llm-evaluation-platform/actions/runs/33679736809)

## Другие проекты

| Проект | Что реализовано | Проверка качества |
|---|---|---|
| **[PDF Data Extraction Service](https://github.com/RegarZ/pdf-data-extraction-service)** | PDF → типизированный JSON: текст, metadata, таблицы, declarative field schema и page evidence | 11 тестов · 88% coverage · CI Python 3.11–3.13 |
| **[RAG Retrieval & Evaluation Service](https://github.com/RegarZ/rag-evaluation-service)** | BM25 + hashing embeddings, hybrid scoring, chunking, reranking, extractive QA и цитаты | 12 тестов · 98% coverage · Recall@K, MRR, nDCG, Hit Rate |

## Технологии

### Backend и API

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI" />
  <img src="https://img.shields.io/badge/Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white" alt="Pydantic" />
  <img src="https://img.shields.io/badge/Uvicorn-4051B5?style=flat-square" alt="Uvicorn" />
  <img src="https://img.shields.io/badge/HTTPX-1F2937?style=flat-square" alt="HTTPX" />
  <img src="https://img.shields.io/badge/REST_API-005571?style=flat-square" alt="REST API" />
  <img src="https://img.shields.io/badge/OpenAPI-6BA539?style=flat-square&logo=openapiinitiative&logoColor=white" alt="OpenAPI" />
  <img src="https://img.shields.io/badge/CLI-111827?style=flat-square&logo=windowsterminal&logoColor=white" alt="CLI" />
</p>

### Document AI, Retrieval и Evaluation

<p>
  <img src="https://img.shields.io/badge/PyMuPDF-ED8B00?style=flat-square" alt="PyMuPDF" />
  <img src="https://img.shields.io/badge/Tesseract_OCR-3F5D7D?style=flat-square" alt="Tesseract OCR" />
  <img src="https://img.shields.io/badge/Pillow-2563EB?style=flat-square" alt="Pillow" />
  <img src="https://img.shields.io/badge/Regex_Extraction-7C3AED?style=flat-square" alt="Regex extraction" />
  <img src="https://img.shields.io/badge/BM25-0F766E?style=flat-square" alt="BM25" />
  <img src="https://img.shields.io/badge/Hybrid_Retrieval-0369A1?style=flat-square" alt="Hybrid retrieval" />
  <img src="https://img.shields.io/badge/RAG_+_Citations-B45309?style=flat-square" alt="RAG with citations" />
  <img src="https://img.shields.io/badge/LLM_Evaluation-9333EA?style=flat-square" alt="LLM evaluation" />
  <img src="https://img.shields.io/badge/Ranking_Metrics-DC2626?style=flat-square" alt="Ranking metrics" />
</p>

### Frontend и Live Demo

<p>
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/React_19-20232A?style=flat-square&logo=react&logoColor=61DAFB" alt="React 19" />
  <img src="https://img.shields.io/badge/Tailwind_CSS_4-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind CSS 4" />
  <img src="https://img.shields.io/badge/shadcn/ui-000000?style=flat-square&logo=shadcnui&logoColor=white" alt="shadcn/ui" />
  <img src="https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white" alt="Vite" />
  <img src="https://img.shields.io/badge/Lucide-F56565?style=flat-square&logo=lucide&logoColor=white" alt="Lucide" />
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white" alt="HTML5" />
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white" alt="CSS3" />
</p>

### Качество и доставка

<p>
  <img src="https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white" alt="pytest" />
  <img src="https://img.shields.io/badge/pytest--cov-16A34A?style=flat-square" alt="pytest-cov" />
  <img src="https://img.shields.io/badge/Ruff-D7FF64?style=flat-square&logo=ruff&logoColor=111827" alt="Ruff" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker" />
  <img src="https://img.shields.io/badge/Docker_Compose-1D63ED?style=flat-square&logo=docker&logoColor=white" alt="Docker Compose" />
  <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" alt="GitHub Actions" />
  <img src="https://img.shields.io/badge/Hatchling-1F2937?style=flat-square" alt="Hatchling" />
  <img src="https://img.shields.io/badge/Cloudflare_compatible-F38020?style=flat-square&logo=cloudflare&logoColor=white" alt="Cloudflare-compatible hosting" />
</p>

## Как я проектирую AI-системы

| Принцип | Как проявляется в проектах |
|---|---|
| **Evidence first** | ответы и извлечённые поля привязаны к странице или исходному чанку |
| **Измеримость** | retrieval и LLM-пайплайны имеют воспроизводимые метрики и quality gates |
| **Контракты и валидация** | Pydantic-схемы, проверка входных файлов, структурированные ошибки |
| **Контролируемые отказы** | таймауты, health checks, нормализация downstream-ошибок, явные ограничения |
| **Воспроизводимость** | versioned fixtures, dataset hash, Docker, CI и фиксированные сценарии запуска |
| **Проверяемая доставка** | unit/API-тесты, coverage, Ruff, матрица Python и Docker build в GitHub Actions |

## Направления развития

- **Document AI:** layout-aware extraction, bounding boxes и координаты evidence,
  улучшение OCR preprocessing, golden datasets для измерения качества;
- **RAG:** semantic embeddings, vector database, сравнение retrieval-конфигураций,
  reranking и end-to-end метрики groundedness/faithfulness;
- **LLM Evaluation:** реальные provider adapters, JSON Schema и semantic metrics,
  парный bootstrap confidence interval, калиброванный LLM-as-a-judge;
- **Platform engineering:** PostgreSQL и object storage, асинхронные worker-задачи,
  progress API и обработка больших документов;
- **Наблюдаемость:** структурированные логи, distributed tracing, latency/cost/error
  dashboards и сквозные request IDs;
- **Безопасность:** авторизация, tenant isolation, rate limits, TTL и политики удаления;
- **Delivery:** cloud deployment backend-сервисов, preview environments и
  автоматический regression report в pull request.

> Этот блок описывает следующий этап развития. Технологии из roadmap не выдаются
> за уже реализованный production-стек.

## Контакты

<p>
  <a href="https://github.com/RegarZ">
    <img src="https://img.shields.io/badge/GitHub-@RegarZ-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub RegarZ" />
  </a>
</p>

---

<div align="center">
  <sub>Портфолио развивается итеративно: каждый новый этап сопровождается кодом, тестами и измеримым результатом.</sub>
</div>
