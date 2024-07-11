практика, советы и фишки по cockеру 

Как работает Docker:

Создание Dockerfile: Вы создаете Dockerfile с инструкциями для сборки образа. Пример простого Dockerfile:
    
    # Используем базовый образ Python
    FROM python:3.8-slim

    # Устанавливаем рабочую директорию
    WORKDIR /app

    # Копируем локальные файлы в контейнер
    COPY . /app

    # Устанавливаем зависимости
    RUN pip install --no-cache-dir -r requirements.txt

    # Определяем команду для запуска приложения
    CMD ["python", "app.py"]

Сборка образа: Используя команду docker build, вы создаете образ из Dockerfile:

    docker build -t my-python-app .

Запуск контейнера: С помощью команды docker run вы создаете и запускаете контейнер на основе образа:

    docker run -d -p 5000:5000 my-python-app
