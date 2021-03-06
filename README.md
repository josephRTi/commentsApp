## ТЗ:
Функциональные требования:
У системы должны быть методы API, которые обеспечивают
- Добавление статьи (Можно чисто номинально, как сущность, к которой крепятся комментарии).
- Добавление комментария к статье.
- Добавление комментария в ответ на другой комментарий (возможна любая вложенность).
- Получение всех комментариев к статье вплоть до 3 уровня вложенности.
- Получение всех вложенных комментариев для комментария 3 уровня.
- По ответу API комментариев можно воссоздать древовидную структуру.


## Окружение проекта:
  * Django~=3.2.4
  * djangorestframework~=3.13.1
  * django-mptt~=0.13.4
  * django-rest-swagger==2.2.0
  * psycopg2-binary==2.8.5

Склонируйте репозиторий с помощью git
```bash
git clone https://github.com/josephRTi/commentsApp
```
Сборка и запуск Docker
```bash
cd commentsApp
docker-compose build 
docker-compose up -d  
```
Миграции
```bash
docker-compose exec web python manage.py makemigrations --noinput
docker-compose exec web python manage.py migrate --noinput
```
Создание суперпользователя для доступа к админ панели:
```bash
docker-compose exec web python manage.py createsuperuser
```

* Приложение будет доступно по адресу: http://0.0.0.0:8000/

Просмотр логов
```bash
docker-compose logs -f 
```

### Документация

(автодокументирование на swagger по адресу http://0.0.0.0:8000/api/docs )

### Admin панель
* URL: http://0.0.0.0:8000/admin/

### Запросы
