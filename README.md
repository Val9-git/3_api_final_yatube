# Yatube_REST_API
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white)
![DjangoREST](https://img.shields.io/badge/DJANGO-REST-ff1709?style=for-the-badge&logo=django&logoColor=white&color=ff1709&labelColor=gray)
![JWT](https://img.shields.io/badge/JWT-black?style=for-the-badge&logo=JSON%20web%20tokens)

### Описание проекта

Многофункциональный API для социальной сети Yatube.
Yatube - социальная сеть для авторов и подписчиков. Пользователи могут подписываться на избранных авторов, оставлять и удалять комментари к постам, оставлять новые посты на главной странице и в тематических группах, прикреплять изображения к публикуемым постам.

### Описание возможностей
```
Аутентификация по JWT-токену
Получение, cоздание, обновление и удаление публикаций и комментариев;
Получение информации о сообществах;
Получение информации о существующих подписках автора;
Возможность подписываться на пользователей.
```

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/<your_git_account/api_final_yatube.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv venv
```

```
source venv/bin/activate
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
python3 manage.py migrate
```


Запустить проект:

```
python3 manage.py runserver
```

### Технологии:
```
Python 3.9
Django 3.2.16
djangorestframework 3.12.4
djangorestframework-simplejwt 4.7.2
djoser 2.2.0
```

### Примеры:

Пример POST-запроса с токеном Антона Чехова: добавление нового поста.

```
[POST] .../api/v1/posts/
{
    "text": "Вечером собрались в редакции «Русской мысли», чтобы поговорить о народном театре. Проект Шехтеля всем нравится."
}
```

Пример ответа:

```
{
    "id": 14,
    "text": "Вечером собрались в редакции «Русской мысли», чтобы поговорить о народном театре. Проект Шехтеля всем нравится.",
    "author": "anton",
    "image": null,
    "group": 1,
    "pub_date": "2021-06-01T08:47:11.084589Z"
}
```

Пример POST-запроса с токеном Антона Чехова: отправляем новый комментарий к посту с id=14.

```
[POST] .../api/v1/posts/14/comments/
{
    "text": "тест тест",
}
```

Пример ответа:

```
{
    "id": 4,
    "author": "anton",
    "post": 14,
    "text": "тест тест",
    "created": "2021-06-01T10:14:51.388932Z"
}
```

Пример GET-запроса с токеном Антона Чехова: получаем информацию о группе.

```
[GET] .../api/v1/groups/2/
```

Пример ответа:

```
{
    "id": 2,
    "title": "Математика",
    "slug": "math",
    "description": "Посты на тему математики"
}
```

### Авторы:

Valeriy Lozitskiy