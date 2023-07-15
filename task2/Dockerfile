FROM python:3.9

# рабочая директория внутри проекта
WORKDIR /orm_migrations

# переменные окружения
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# устанавливаем зависимости
COPY ./orm_migrations/requirements.txt .
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# копируем содержимое текущей папки в контейнер
COPY . .
# выполняем миграции в БД
RUN python ./orm_migrations/manage.py migrate


# выполнение команды
CMD [ "python", "./orm_migrations/manage.py", "runserver", "0.0.0.0:8000" ]
