# Занятие 28.09.2026 "24. Пользователи и группы. Авторизация и аутентификация"

Для запуска проекта используются команды:

```
git clone https://github.com/kosogoroff/users_rights.git
cd users_rights
vagrant up
```

Для создания репозитория были использованы команды:

```
[admin_insta11@mv334 users_rights]$ echo "# users_rights" >> README.md
[admin_insta11@mv334 users_rights]$ git init
hint: Using 'master' as the name for the initial branch. This default branch name
hint: will change to "main" in Git 3.0. To configure the initial branch name
hint: to use in all of your new repositories, which will suppress this warning,
hint: call:
hint:
hint: 	git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint: 	git branch -m <name>
hint:
hint: Disable this message with "git config set advice.defaultBranchName false"
Инициализирован пустой репозиторий Git в /home/admin_insta11/users_rights/.git/
[admin_insta11@mv334 users_rights]$ git add 
Ничего не проиндексировано.
hint: Maybe you wanted to say 'git add .'?
hint: Disable this message with "git config set advice.addEmptyPathspec false"
[admin_insta11@mv334 users_rights]$ git add .
[admin_insta11@mv334 users_rights]$ git status
Текущая ветка: master

Еще нет коммитов

Изменения, которые будут включены в коммит:
  (используйте «git rm --cached <файл>...», чтобы убрать из индекса)
	новый файл:    README.md
	новый файл:    Vagrantfile

[admin_insta11@mv334 users_rights]$ git commit -m "first commit"
[master (корневой коммит) 58a606f] first commit
 2 files changed, 57 insertions(+)
 create mode 100644 README.md
 create mode 100644 Vagrantfile
[admin_insta11@mv334 users_rights]$ 
[admin_insta11@mv334 users_rights]$ git branch -M main
[admin_insta11@mv334 users_rights]$ 
[admin_insta11@mv334 users_rights]$ git remote add origin https://github.com/kosogoroff/users_rights.git
[admin_insta11@mv334 users_rights]$ 
[admin_insta11@mv334 users_rights]$ git push -u origin main
Перечисление объектов: 4, готово.
Подсчет объектов: 100% (4/4), готово.
При сжатии изменений используется до 4 потоков
Сжатие объектов: 100% (3/3), готово.
Запись объектов: 100% (4/4), 1.20 KiB | 1.21 MiB/s, готово.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/kosogoroff/users_rights.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
[admin_insta11@mv334 users_rights]$
```
