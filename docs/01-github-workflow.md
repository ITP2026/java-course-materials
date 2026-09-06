# Ветки и pull requests в GitHub

## Правило курса

Одна лабораторная — одна ветка — один pull request в `main` личного репозитория.

## Начало работы

```bash
git switch main
git pull --ff-only origin main
git switch -c lab/01-basics
```

## Содержательные коммиты

```bash
git status
git add lab01
git commit -m "Implement prime number check"
git push -u origin lab/01-basics
```

Хороший коммит описывает одно завершенное изменение. Не нужно создавать искусственные коммиты после каждой строки, но один коммит `final` за всю работу затрудняет проверку истории.

## Pull request

1. Откройте личный репозиторий на GitHub.
2. Перейдите в **Pull requests → New pull request**.
3. Выберите `base: main`, а в `compare` — ветку лабораторной.
4. Назовите PR по образцу `[READY] ЛР 01 — Фамилия Имя`.
5. Заполните появившийся шаблон и назначьте преподавателя reviewer.
6. Нажмите **Create pull request**.

Не создавайте PR в центральный репозиторий курса: решение принимается только в `main` личного репозитория.

## Исправления после review

Не закрывайте PR и не создавайте новый. Исправьте код в той же ветке:

```bash
git add lab01
git commit -m "Address review comments"
git push
```

Новый commit автоматически появится в открытом PR. Ответьте на комментарии преподавателя; не отмечайте обсуждение решенным, пока исправление не отправлено.

## После принятия

После комментария преподавателя `Принято` студент самостоятельно нажимает **Squash and merge**, удаляет ветку на GitHub и обновляет локальный `main`:

```bash
git switch main
git pull --ff-only origin main
git branch -d lab/01-basics
```
