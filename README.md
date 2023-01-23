# Описание
Проект представляет собой API для проекта yatube.

Ключевые моменты:

Применены вьюсеты.

Для аутентификации использованы JWT-токены.

У неаутентифицированных пользователей доступ к API только для чтения. Исключение — эндпоинт /follow/.

Аутентифицированным пользователям разрешено изменение и удаление своего контента; в остальных случаях доступ предоставляется только для чтения.

Клонировать репозиторий и перейти в него в командной строке:
```
git clone git@github.com:Epikhin/api_final_yatube.git
```
Cоздать и активировать виртуальное окружение:
```
python3 -m venv env
```
```
source env/bin/activate
```
Установить зависимости из файла requirements.txt:
```
python3 -m pip install --upgrade pip
```
```
pip install -r requirements.txt
```
Выполнить миграции:
```
python manage.py makemigrations
```
```
python3 manage.py migrate
```

Запустить проект:
```
python3 manage.py runserver
```
Пример использования API:

Для доступа к API необходимо получить токен: 

Нужно выполнить POST-запрос localhost:8000/api/v1/token/ передав поля username и password. API вернет JWT-токен

Дальше, передав токен можно будет обращаться к методам, например: 

/api/v1/posts/ (GET, POST, PUT, PATCH, DELETE)

При отправке запроса передавайте токен в заголовке Authorization: Bearer <токен>
