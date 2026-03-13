
# FastAPI Sellers & Books API

Этот проект демонстрирует создание REST API на FastAPI с использованием SQLAlchemy для работы с базой данных и JWT-аутентификации. Приложение позволяет управлять продавцами и книгами.

## Установка и запуск

### 1. Клонирование репозитория

git clone <ссылка-на-репозиторий>
cd mts-shad-fastapi-project

### 2. Создание виртуального окружения

**Windows (PowerShell)**

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

**Windows (CMD)**

```cmd
python -m venv .venv
.\.venv\Scripts\activate
```

**Linux / macOS**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Установка зависимостей

```bash
pip install -r requirements.txt
```

### 4. Запуск приложения

```bash
uvicorn main:app --reload
```

После запуска сервис будет доступен по адресу:
[http://127.0.0.1:8000](http://127.0.0.1:8000)

## Эндпоинты

### Продавцы

* `POST /api/v1/seller` — регистрация нового продавца
* `GET /api/v1/seller` — получение списка продавцов
* `GET /api/v1/seller/{seller_id}` — получение информации о продавце (требуется JWT)
* `PUT /api/v1/seller/{seller_id}` — обновление данных продавца (требуется JWT)
* `DELETE /api/v1/seller/{seller_id}` — удаление продавца (требуется JWT)

### Аутентификация

* `POST /api/v1/token` — получение JWT-токена

### Книги

* `POST /api/v1/books/` — создание книги (требуется JWT)
* `PUT /api/v1/books/{book_id}` — обновление книги (требуется JWT)

## Тестирование

Для запуска тестов выполните:

```bash
pytest test_main.py
```

Пример успешного результата:

```
collected 5 items
.....
5 passed in X.XXs
```

## Структура проекта

* `main.py` — основной файл приложения FastAPI
* `test_main.py` — тесты для API на pytest
* `test.db` — база данных SQLite, создаётся автоматически
* `.venv` — виртуальное окружение Python
* `requirements.txt` — список зависимостей проекта
