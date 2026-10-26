# 3LR
 настройка (один раз)
git config --global user.name "kristinarei888"
git config --global user.email "krisqwq44@gmail.com"

# создание проекта
mkdir my-git-project
cd my-git-project
git init

# первый файл
echo "<h1>Мой проект</h1>" > index.html
git status
git add index.html
git commit -m "Initial commit"

# README
echo "# My Git Project" > README.md
git add README.md
git commit -m "Add README"

# изменения
echo "<p>Описание проекта</p>" » index.html
echo "body {font-family: Arial;}" > style.css
git add index.html
git add style.css
git commit -m "Add paragraph and CSS"

# отмена изменений
echo "ошибка" » index.html
git checkout – index.html

# удаление и восстановление файла
rm style.css
git checkout HEAD – style.css

# работа с индексом
echo "h1 {color:red;}" » style.css
git add .
git reset HEAD style.css

# создание ветки
git branch feature/contact-form
git checkout feature/contact-form

# новая страница
echo "<h2>Контакты</h2>" > contact.html
echo "<a href='contact.html'>Контакты</a>" » index.html
git add .
git commit -m "Add contact page"

# возврат в main
git checkout main

# изменение заголовка
nano index.html
# поменять на <h1>Главная страница</h1>

git add index.html
git commit -m "Change header in main"

# снова в feature
git checkout feature/contact-form
nano index.html
# поменять на <h1>Добро пожаловать!</h1>

git add index.html
git commit -m "Change header in feature"

# merge (будет конфликт)
git checkout main
git merge feature/contact-form

# вручную исправить index.html
git add index.html
git commit

# просмотр различий
git diff
git diff HEAD
git diff HEAD~1 HEAD

# финальная проверка
git log --oneline --graph --all
