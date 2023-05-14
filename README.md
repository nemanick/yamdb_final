# API YaMDB
### Описание проекта.
Проект представляет собой сервис для любителей различных произведений.
Проект YaMDb собирает отзывы пользователей на произведения. Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.
Произведения делятся на категории, такие как «Книги», «Фильмы», «Музыка». Например, в категории «Книги» могут быть произведения «Винни-Пух и все-все-все» и «Марсианские хроники», а в категории «Музыка» — песня «Давеча» группы «Жуки» и вторая сюита Баха. Список категорий может быть расширен (например, можно добавить категорию «Изобразительное искусство» или «Ювелирка»).
Произведению может быть присвоен жанр из списка предустановленных (например, «Сказка», «Рок» или «Артхаус»).
Добавлять произведения, категории и жанры может только администратор.
Благодарные или возмущённые пользователи оставляют к произведениям текстовые отзывы и ставят произведению оценку в диапазоне от одного до десяти (целое число); из пользовательских оценок формируется усреднённая оценка произведения — рейтинг (целое число). На одно произведение пользователь может оставить только один отзыв.
Пользователи могут оставлять комментарии к отзывам.
Добавлять отзывы, комментарии и ставить оценки могут только аутентифицированные пользователи.
Настоящий репозиторий - API для данного проекта.

##### Технологии.
В проекте использованы следующие технологии:
Python 3.7, Django 3.2, Django REST Framework, Simple JWT.

### Об авторах:
Над проектом работали:

**Костров Михаил (тимлид)**
[GitHub](https://github.com/mdkostrov/)

**Александр Морозов**
[GitHub](https://github.com/notebad)

**Иван Наливайко**
[GitHub](https://github.com/nemanick)

Студенты курса "Разработчик Python" (47 когорта).

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
https://github.com/nemanick/infra_sp2.git
```

```
cd infra_sp2
```

Создать .env файл внутри директории infra (на одном уровне с docker-compose.yaml). Пример .env файла:
```
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
DB_HOST=db
DB_PORT=5432
SECRET_KEY=ch9r$dgbry1k@62srg=(=n+a%lq%t^v&(-is*ejb9&e4#6@$4!
```

Для запуска docker-compose необходимо перейти в папку, где он располагается, и выполнить команду:
```
docker-compose up -d --build
```
##### Для работы с базой данных необходимо создать суперюзера:

```
docker-compose exec web python manage.py createsuperuser
```
После чего можно проверить работу проекта и войти в админку:
```
http://localhost/admin
```

Команда для загрузки в БД данных из фикстур:
````
docker-compose exec web python manage.py loaddata fixtures.json 
```` 

Все необходимое для работы с api описано в документации:
```
http://localhost/redoc/
```

![example workflow](https://github.com/nemanick/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)