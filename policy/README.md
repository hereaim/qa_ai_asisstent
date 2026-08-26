# Модель разрешений
## READ
1. Search, read, analyze, compare.
## PLAN
1. Планирование и подготовка diff/действий.
## LOCAL WRITE
### С подтверждением:
1. создание файла;
2. изменение файла;
3. локальная ветка.
## EXTERNAL WRITE
### С отдельным подтверждением:
1. Testy create/update;
2. Jira create/update;
3. GitLab push;
4. MR.
## CRITICAL
### Запрещено в MVP:
1. merge;
2. production;
3. secret management;
4. destructive operations.