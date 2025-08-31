# Git-Settings

1. Основы Git

```bash
git init                     # инициализация репозитория в текущей папке
git clone URL                # клонировать проект с GitHub
git status                   # показать изменения
git add FILE                 # добавить конкретный файл в коммит
git add .                    # добавить все изменения
git commit -m "Сообщение"    # зафиксировать изменения
git log                      # история коммитов
git diff                     # показать, что изменилось
```

# 3. Работа с удалённым репозиторием

```bash
git remote add origin URL     # привязать локальный репозиторий к GitHub
git remote -v                 # проверить связь с удалённым репо
git push -u origin main       # отправить локальные изменения на GitHub
git pull origin main          # подтянуть изменения с GitHub
git fetch                     # загрузить новые данные (без слияния)
```

# 5. Ветки (branch)
```bash
git branch                    # показать все ветки
git branch NAME               # создать ветку
git checkout NAME             # переключиться на ветку
git checkout -b NAME          # создать и сразу перейти
git merge NAME                # объединить ветку NAME в текущую
git branch -d NAME            # удалить ветку (если уже слита)
git branch -D NAME            # удалить ветку принудительно
```

# 6. Командная работа

-Лучший рабочий процесс (Git Flow или Feature Branch):

-main/master — стабильный код

-dev — для интеграции

-feature/* — для новых задач

```bash
git checkout dev                 # перейти в dev
git pull origin dev              # обновить dev
git checkout -b feature-login    # создать ветку для задачи
# ... работа ...
git add . && git commit -m "add login feature"
git push origin feature-login    # отправить ветку на GitHub
```

-После ревью:

-На GitHub создаётся Pull Request (PR)

-После слияния ветки можно удалить:

```bash
git branch -d feature-login
git push origin --delete feature-login
```

# 5. Откаты и исправления

```bash
git reset --hard HASH          # откатиться на конкретный коммит (история теряется)
git reset --soft HASH          # откатиться, но оставить изменения в файлах
git checkout HASH FILE         # вернуть файл к определённому коммиту
git revert HASH                # создать коммит, отменяющий изменения HASH
git restore FILE               # отменить изменения в файле (новая команда)
git clean -fd                  # удалить все неотслеживаемые файлы
```
# 6. Полезные команды

```bash
git stash                      # временно спрятать изменения
git stash pop                  # вернуть спрятанные изменения
git tag v1.0                   # создать тег (например, релиз)
git show HASH                  # показать изменения конкретного коммита
git blame FILE                 # кто и когда менял строки в файле
```

# 7. Базовый README.md пример
# Git Шпаргалка

## Основные команды
\`\`\`bash
git init
git add .
git commit -m "first commit"
git push origin main
\`\`\`

## Ветки
\`\`\`bash
git checkout -b feature-name
git push origin feature-name
git merge feature-name
\`\`\`

## Откаты
\`\`\`bash
git reset --hard <hash>
git revert <hash>
\`\`\`

## Командная работа
1. Создавай ветки для задач (`feature/*`)
2. Делаем Pull Request (PR) в `dev` или `main`
3. После слияния — удаляем ветки
