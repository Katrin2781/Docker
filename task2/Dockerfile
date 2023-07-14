FROM python:3.9

# рабочая директория внутри проекта
WORKDIR /django_cicd

# переменные окружения
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# устанавливаем зависимости
COPY /django_cicd/requirements.txt .
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# копируем содержимое текущей папки в контейнер
COPY . .
# выполняем миграции в БД
RUN python django_cicd/manage.py migrate


# выполнение команды
CMD ["python", "./django_cicd/manage.py", "runserver"]
