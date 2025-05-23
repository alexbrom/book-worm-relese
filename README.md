# Book Store API

API для хранения и управления книгами и их PDF-файлами.

## Установка

1. Создайте виртуальное окружение Python:
```bash
python -m venv venv
source venv/bin/activate  # для Linux/Mac
venv\Scripts\activate     # для Windows
```

2. Установите зависимости:
```bash
pip install -r requirements.txt
```

3. Создайте базу данных PostgreSQL и настройте подключение:
   - Создайте новую базу данных
   - Отредактируйте `DATABASE_URL` в файле `main.py`
   - Выполните SQL-скрипт `schema.sql` для создания таблиц

## Запуск приложения

```bash
uvicorn main:app --reload
```

Приложение будет доступно по адресу: http://localhost:8000

## API Endpoints

### Книги

- `POST /books/` - Создать новую книгу
- `GET /books/` - Получить список всех книг
- `GET /books/{book_id}` - Получить информацию о конкретной книге

### Файлы

- `POST /books/{book_id}/upload_file/` - Загрузить файл для книги
- `GET /books/{book_id}/download/{file_id}` - Скачать файл книги

## Swagger документация

Документация API доступна по адресу: http://localhost:8000/docs

## Структура проекта

```
.
├── main.py           # Основной файл приложения
├── schema.sql        # SQL-скрипт создания таблиц
├── requirements.txt  # Зависимости проекта
├── uploads/          # Директория для хранения файлов
└── README.md         # Документация
``` 