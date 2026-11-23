# LLM Experimentation Setup (LES)

Система для проведення експериментів над локальними мовними моделями, моделями  (Qwen 3.5, Gemma 4, LFM 2.5, OLMo 3.1, Apertus 1.5) та іншими моделями нейронних мереж для задач Обробки природної мови на основі трансформерної архітектури (моделі вбудовування (Qwen3-Embedding-0.6B), моделі реранжування (zerank-2, Qwen3-Reranker-0.6B), моделі прийняття рішень (Laya, Kev)).

# Розгортання на пристрої (Docker Compose)

```cmd
git clone https://github.com/tovsmax/llm-exp-setup.git
cd llm-exp-setup
docker compose up -d
```

# Структура проекту

- Сервіси для моніторингу
    - Glances - збирання даних використання ресурсів обладнання
    - Prometheus - база даних метрик, де зберігаються дані
    - Grafana - візуалізація метрик збережених у Prometheus
        - Grafana Image Renderer - експорт дашбордів у png-файли

- Сервіси для ШІ
    - llama-server - сервер для надання OpenAI-сумісного API до llama.cpp
    - SearXNG - мета-пошуковий рушій для надання функції веб-пошуку мовним моделям
    - Hermes Agent - агентський LLM-клієнт
