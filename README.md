# devops-netology
**Клонирование репозитория**
```
git clone https://github.com/Aleksandr-afk-22/devops-netology.git

aleks@aleks-nb:~/project/devops-netology/devops-netology$ ls -la
total 16
drwxrwxr-x 3 aleks aleks 4096 Jun  1 21:27 .
drwxrwxr-x 3 aleks aleks 4096 Jun  1 21:27 ..
drwxrwxr-x 7 aleks aleks 4096 Jun  1 21:27 .git
-rw-rw-r-- 1 aleks aleks   17 Jun  1 21:27 README.md
aleks@aleks-nb:~/project/devops-netology/devops-netology$ git remote -v
origin	https://github.com/Aleksandr-afk-22/devops-netology.git (fetch)
origin	https://github.com/Aleksandr-afk-22/devops-netology.git (push)
aleks@aleks-nb:~/project/devops-netology/devops-netology$ 

```
**Первоначальная настройка Git**
```
git config --global user.name "Aleksandr"
git config --global user.email "asimaev@gmail.com"
 git config --global --list
user.name=Aleksandr
user.email=asimaev@gmail.com

```
**Проверка Статуса**
```
git status
Текущая ветка: main
Эта ветка соответствует «origin/main».

нечего коммитить, нет изменений в рабочем каталоге

```
**Внесение изменений команды git diff, git diff --staged, первый коммит**
```
aleks@aleks-nb:~/project/devops-netology/devops-netology$ git diff
diff --git a/README.md b/README.md
index 647b370..56e3025 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,3 @@
-# devops-netology
\ No newline at end of file
+# devops-netology
+**Клонирование репозитория**
+
aleks@aleks-nb:~/project/devops-netology/devops-netology$ git diff --staged 
aleks@aleks-nb:~/project/devops-netology/devops-netology$ git add README.md 
aleks@aleks-nb:~/project/devops-netology/devops-netology$ git diff
aleks@aleks-nb:~/project/devops-netology/devops-netology$ git diff --staged 
diff --git a/README.md b/README.md
index 647b370..56e3025 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,3 @@
-# devops-netology
\ No newline at end of file
+# devops-netology
+**Клонирование репозитория**
+
aleks@aleks-nb:~/project/devops-netology/devops-netology$ git commit -m 'First commit'
[main 7d61e79] First commit
 1 file changed, 3 insertions(+), 1 deletion(-)
aleks@aleks-nb:~/project/devops-netology/devops-netology$ git status
Текущая ветка: main
Ваша ветка опережает «origin/main» на 1 коммит.
  (используйте «git push», чтобы опубликовать ваши локальные коммиты)

нечего коммитить, нет изменений в рабочем каталоге
aleks@aleks-nb:~/project/devops-netology/devops-netology$ git diff
aleks@aleks-nb:~/project/devops-netology/devops-netology$ git diff --staged 
aleks@aleks-nb:~/project/devops-netology/devops-netology$ 
```
**Создание файлов .gitignore и второго коммита**
```
git status
Текущая ветка: main
Ваша ветка опережает «origin/main» на 1 коммит.
  (используйте «git push», чтобы опубликовать ваши локальные коммиты)

Неотслеживаемые файлы:
  (используйте «git add <файл>...», чтобы добавить в то, что будет включено в коммит)
        .gitignore

индекс пуст, но есть неотслеживаемые файлы
(используйте «git add», чтобы проиндексировать их)
git add ./.gitignore 
git status
Текущая ветка: main
Ваша ветка опережает «origin/main» на 1 коммит.
  (используйте «git push», чтобы опубликовать ваши локальные коммиты)

Изменения, которые будут включены в коммит:
  (используйте «git restore --staged <файл>...», чтобы убрать из индекса)
        новый файл:    .gitignore
```
**создание директории terraform и внутри этой директории — файл .gitignore по примеру: https://github.com/github/gitignore/blob/master/Terraform.gitignore.**
```
aleks@aleks-nb:~/project/devops-netology/devops-netology$ tree -a terraform/
terraform/
└── .gitignore

1 directory, 1 file
```
**Игнорируемые файлы (.gitignore)**
- **Состояния Terraform** (`*.tfstate`, `.terraform/`) — содержат инфраструктурные данные и потенциальные секреты.
- **Переменные с секретами** (`*.tfvars`, `*.tfvars.json`) — пароли, ключи доступа, приватные данные.
- **Логи и временные файлы** (`crash.log`, `.terraform.tfstate.lock.info`) — служебная информация.
- **Локальные переопределения** (`override.tf`) — файлы для локального тестирования, не предназначенные для общего репозитория.
- **Конфигурации CLI** (`.terraformrc`) — локальные настройки пользователя.
