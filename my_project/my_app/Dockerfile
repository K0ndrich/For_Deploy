# ↓ В етом файле команды выполняються сверху вниз
# ↓ Если изменяет какуюто команду, то все команды которые идиту ниже ее будут пересоздаваться
# ↓

# берем другой docker образ, который будет основой нашего docker образа
FROM python:3.11-slim

# создаем рабочую директори, где будет храниться наш проект
WORKDIR /my_app

# переносим весь проект в рабочую директори текущего контейнера
COPY . /my_app/

# устанавливаем зависимости для нашего проекта внутри docker образа
# req.txt должен храниться внутри локальной папки с проектом
RUN pip install -r req.txt

CMD python manage.py makemigrations \
    && python manage.py migrate \
    && python manage.py runserver 0.0.0.0:8000
    



# CMD запускает команды каждый раз при запуске в docker контейнере
# CMD gunicorn config.wsgi:application -b 0.0.0.0:8000