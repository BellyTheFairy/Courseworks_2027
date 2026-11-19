# Правила работы в репозитории

## Ветки
- `main` — шаблон и документация. Запись запрещена (protected).
- `team-XX` — рабочая ветка команды XX. Пушить может только эта команда.
- Внутри своей ветки можно создавать подветки: `team-01/feature-auth`, `team-01/fix-db`.

## Первый запуск (один раз на компьютер)
```bash
git config --global user.name "Имя Фамилия"
git config --global user.email "почта@пример.com"
git config --global push.default current   # пушится только текущая ветка
```

## Клонирование своей ветки
```bash
git clone --branch team-01 --single-branch https://github.com/Kordebalet67/coursework-2026.git
cd coursework-2026
git switch team-01
```

## Ежедневный цикл
```bash
git pull                      # забрать изменения однокомандников
# ...работаем в teams/team-01/...
git add .
git commit -m "feat: описание того, что сделали"
git pull --rebase             # ещё раз подтянуть, чтобы не было конфликтов
git push                      # уходит ТОЛЬКО в team-01
```

## Подтянуть обновления методички из main
```bash
git fetch origin
git merge origin/main
```

## Запрещено
- пушить в `main` и в чужие ветки `team-YY`;
- `git push --force`, `git push --all`, удаление веток;
- коммитить `.env`, пароли, токены, `node_modules`, `venv`, бинарники сборок.

## Сдача работы
Pull Request `team-XX` → `main`, ревьюер — преподаватель. Шаблон PR заполняется автоматически.
