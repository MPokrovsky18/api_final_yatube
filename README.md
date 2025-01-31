# api_final
api final

## Описание
API для проекта "Yatube" - блог, где можно размещать посты с картинками и подписываться на любимых авторов.
___
**Проект реализован с использованием следующих технологий:**
- Django
- Django REST Framework
- Django REST Framework Simple JWT
- Djoser
- PyJWT
- SQLite (используется по умолчанию в Django)

***Остальные зависимости указаны в файле requirements.txt***
## Установка
Клонировать репозиторий и перейти в него в командной строке:
```
git clone git@github.com:MPokrovsky18/api_final_yatube.git
```
```
cd api_final_yatube
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
Перейти в папку `yatube_api`
```
cd yatube_api
```
Выполнить миграции:
```
python3 manage.py migrate
```
Запустить проект:
```
python3 manage.py runserver
```
## Примеры запросов
Когда вы запустите проект, по адресу
```
http://127.0.0.1:8000/redoc/
```
будет доступна документация для `API Yatube`. Документация представлена в формате Redoc.
### Получение публикаций
При указании параметров limit и offset выдача работает с пагинацией. По умолчанию, пагинация выставленна также в файле `settings.py`
- GET `/api/v1/posts/`

**Response 200**
  ```
  {
    "count": 123,
    "next": "http://api.example.org/accounts/?offset=400&limit=100",
    "previous": "http://api.example.org/accounts/?offset=200&limit=100",
    "results": [
      {
        "id": 0,
        "author": "string",
        "text": "string",
        "pub_date": "2021-10-14T20:41:29.648Z",
        "image": "string",
        "group": 0
      }
    ]
  }
  ```
___
### Создание публикации
- POST `/api/v1/posts/`

**Payload**
  ```
  {
    "text": "string",
    "image": "string",
    "group": 0
  }
  ```

**Response 201**
  ```
  {
    "id": 0,
    "author": "string",
    "text": "string",
    "pub_date": "2019-08-24T14:15:22Z",
    "image": "string",
    "group": 0
  }
  ```
___
> Автор проекта [Maxim Pokrovsky](https://github.com/MPokrovsky18)
