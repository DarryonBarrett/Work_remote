# Инструкция по работе в Git
## 1. Инициализация репозитория
Для **инициализации** репозитория следует использовать команду `git init`.
## 2. Добавление файлу версионности
Чтобы добавить файлу версионности необходимо использовать команду `git add`
## 3. Просмотр данных в папке
Для просмотра данных о файлах в папке нужно использовать команду `git status`.
## 4. Сохранение изменений в файле и создание коммита
Для подготовки файла к записи коммита следует сначала сохранить его сочетанием клавиш `ctrl+s`, затем использовать команду `git add`, после чего должна быть использована команда `git commit` для записи коммита.
## 5. Отображение коммитов в истории ветки
Для того чтобы отобразить список коммитов в терминале, необходимо использовать команду `git log`. Перелистывание списка осуществляется перемещением курсора вниз и вверх.
## 6. Отображение разницы измененного файла
Чтобы увидеть разницу между сохраненным и измененным файлом используется команда `git diff`.
## 7. Перемещение между коммитами в ветке
Для того чтобы перейти на созданный ранее коммит, следует использовать команду `git checkot` и ввести хэш-код коммита (достаточно первые четыре его цифры).
## 8. Создание веток
Для создания новой ветки необходимо ввести команду `git branch <branch_name>`
Чтобы перейти на другую ветку необходимо ввести команду `git checkout <branch_name>`
## 9. Слияниие веток
Чтобы слить две ветки, необходимо перейти в ветку, **в которую** будет слита другая ветка, посредством команды `git checkout <master_branch_name>`, и ввести команду `git merge <slave_branch_name>`. 
## 9.1.
Если при слиянии двух веток возник конфликт, необходимо в редакторе конфликтов выбрать, что нужно сохранить, затем закоммитить изменения, чтобы завершить слияние. 
## 10. Удаление веток
`git branch -d <branch_name>` - удаление уже слитой ветки; производится из другой ветки.

`git branch -D <branch_name>` - принудительное удаление ветки, даже если там есть неслитая информация. 

## 11. Клонирование удаленного репозитория
Для того, чтобы клонировать удаленный репозиторий с GitHub, необходимо копировать URL-адрес этого репозитория, ввести в терминале команду `git clone <скопированный_URL>`. Авторизоваться на платформе GitHub для этого не обязательно.

После этого желательно выполнить команду `cd <Имя_склонированного_репозитория>`, чтобы начать работу в склонированном репозитории. 
## 12. Создание удаленного репозитория
Для того, чтобы создать удаленный репозиторй, необходимо зарегистрироваться на платформе GitHub. 

После регистрации и настройки профиля в меню профиля выбрать пункт "Мои репозитории", затем на открывшемся окне нажать кнопку "New". После чего будет дана быстрая найстройка и советы по привязке локального и созданного удаленного репозиториев. 

## 13. Привязка удаленного репозитория к локальному. 
Для привязки локального репозитория к удаленному необходимо выполнить следующую команду:
`git remote add origin https://github.com/<имя_пользователя_GitHub>/<имя_удаленного_репозитория>.git`.
## 13.1. Переименование текущей ветки

После привязки репозиториев желательно выполнить переименование ветки "master" в "main" посредством командый `git branch -M main`.

## 14. Выгрузка контента из удаленного репозитория в локальный

Чтобы выгрузить контент из удаленного репозитория в связанный с ним локальный, следует воспользоваться командой `git pull`. При этом контент будет выполнять мёрж с контентом локального репозитория.

Для того чтобы выгрузить контент без выполнения мёржа, следует использовать команду `git fetch`.

## 15. Загрузка контента из локального репозитория в удаленный

Для того, чтобы "залить" контент из локального репозитория в удаленный, нужно использовать команду `git push --set-upstream origin <branch_name>`.

## 16. Копирование чужого репозитория

Скопировать чужой репозиторий на свой аккаунт можно через клавишу `Fork` (при условии что он доступен к копированию) на странице чужого репозитория. 

## 17. Pull Request

Если нужно предложить автору чужого репозитория изменения, необходимо:

1. Сделать Fork желаемого репозитория
2. Клонировать его в локальный репозиторий 
3. Создать новую ветку и вносить изменения в ней, фиксируя их коммитами
4. Залить через команду `git push --set-upstream origin <branch_name>` изменения в удаленный копированный репозиторий
5. На странице репозитория нажать кнопку "Compare & Pull request", подтвердить отправку запроса.