<div align="center">

# 🔎 Service Checker
**IT Support Lab · HTTP / TCP · Python**

![Python](https://img.shields.io/badge/Python-CLI-152a3b?style=flat-square&logo=python&logoColor=white)
![Checks](https://img.shields.io/badge/HTTP%20%26%20TCP-diagnostics-147d86?style=flat-square)
![Tests](https://img.shields.io/badge/unittest-included-152a3b?style=flat-square)
![Status](https://img.shields.io/badge/status-learning%20project-53677b?style=flat-square)

[← GitHub-профиль](https://github.com/smadie228) · [Linux Incident Lab](https://github.com/smadie228/linux-incident-lab)

</div>

---

## `01 / Назначение`

Учебная утилита на Python для проверки HTTP-сервисов и TCP-портов. Практика диагностики для первой линии поддержки: проверить доступность, определить тип ошибки и записать результаты. **Не является production-мониторингом.** Основная утилита работает без внешних библиотек.

## `02 / Возможности`

| Инструмент | Что проверяет |
|---|---|
| HTTP | код ответа, ожидаемый статус, задержку, ошибку |
| TCP | возможность установить соединение с указанным портом |
| JSON / JSONL | вывод структурированных результатов и локальный журнал |
| CLI | код завершения 0 при успехе, 2 при неудаче |
| Тесты | `unittest` для основных сценариев |

## `03 / Быстрый запуск`

Нужен **Python 3.10+**.

**Терминал 1:** локальный демо-сервис.

```bash
python demo_app.py
```

**Терминал 2:** проверки.

```bash
python service_check.py http http://127.0.0.1:8000/health
python service_check.py http http://127.0.0.1:8000/fail
python service_check.py tcp 127.0.0.1 8000
python service_check.py --json --log results.jsonl http http://127.0.0.1:8000/health
```

В демо `/health` возвращает HTTP 200, а `/fail` — намеренный HTTP 503. Проверяйте только собственные ресурсы или ресурсы, на проверку которых есть разрешение.

**Тесты:**

```bash
python -m unittest discover -s tests -v
```

## `04 / Документация`

- [Алгоритм L1-диагностики](docs/L1_RUNBOOK.md) — что проверять при недоступности сервиса.
- [QA-чеклист и шаблон баг-репорта](docs/QA_CHECKLIST.md) — план тестирования, не отчёт о прохождении.
- [Учебный Jira-тикет](docs/JIRA_SAMPLE.md) — симуляция, не реальный дефект.
- [Read-only пример Jira Cloud API](docs/JIRA_API.md) — mock-тесты; реальное подключение не заявляется.
- [План самостоятельной практики](docs/PRACTICE.md).

## `05 / В планах`

CSV-экспорт, несколько проверок по конфигурации и тестирование на собственной Linux-VM. Для реального Jira API и реальной инфраструктуры нужны отдельные разрешения и проверки.

**Статус:** учебный проект. Сценарии Jira и инцидентов являются примерами, не опытом эксплуатации production.

---

<div align="center"><sub>Learning by doing · <a href="https://github.com/smadie228">@smadie228</a></sub></div>
