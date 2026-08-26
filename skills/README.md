# Каждый skill отвечает за один законченный QA workflow.
## analyze-task
### Вход: Jira issue key.
Алгоритм:
1. Read issue.
2. Read parent.
3. Read subtasks.
4. Read comments.
5. Read links.
6. Search Confluence.
7. Search Testy.
8. Search GitLab.
9. Build context.
10. Identify requirements.
11. Identify risks.
12. Identify gaps.
13. Generate questions.
14. Return evidence and confidence.

## find-existing-tests
### Цель — не допустить создания дублей.
Поиск выполняется по:
1. ID задачи;
2. ключевым словам;
3. компоненту;
4. функциональности;
5. существующим связям;
6. похожему коду.

## generate-test-cases
```text
### Перед генерацией:
requirements
      ↓
existing tests
      ↓
gaps
      ↓
test design
```
### AI должен учитывать подходящие для функциональности:
1. positive;
2. negative;
3. boundary;
4. validation;
5. permissions;
6. error handling;
7. integration;
8. regression impact.

## analyze-coverage
### Строит временный граф:
```text
Requirement
   |
   +-- Manual Test
   |
   +-- Automated Test
```
### Для каждой связи:
```text
type: explicit | inferred | imported
confidence: high | medium | low
source:
  system: jira | testy | gitlab | confluence
  id: ...
```

## generate-autotest
### Перед генерацией AI должен найти:
1. аналогичные тесты;
2. fixtures;
3. Page Objects;
4. API clients;
5. factories;
6. utilities;
7. markers;
8. project conventions.
Принцип:
```text
Existing project conventions over generic best practices.
```

## review-autotest
### Проверяет:
1. корректность сценария;
2. соответствие требованиям;
3. отсутствие дублей;
4. читаемость;
5. локаторы;
6. ожидания;
7. fixtures;
8. тестовые данные;
9. независимость;
10. flaky behavior;
11. метаданные.

## MCP и интеграции
### Общий принцип:
```text
AI
 ↓
MCP
 ↓
Tool
 ↓
External system
```

MCP предпочтителен, если существует официальный или согласованный MCP.
### REST API остается допустимым:
1. если MCP отсутствует;
2. если MCP не предоставляет необходимые возможности;
3. если собственный адаптер проще и безопаснее.