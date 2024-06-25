# API TEAMS

## Цей API сервіс призначений для створення запитів для створення нових команд та людей, зміни їх відповідних полів та розподілення людей серед команд.

## Технології, які використані в проекті

- Django
- Django REST Framework
- SQLite
- Docker

## Інструкція по розгортанню

### Клонування репозиторію

1. Клонувати репозиторій
    ```sh
    git clone https://github.com/SafonovVladimir/api_teams.git
    cd teams_config
    ```

### Налаштування середовища

2. Створити віртуальне середовище та активувати його
    ```sh
    python -m venv venv
    source venv/bin/activate  # На Windows використовуйте venv\Scripts\activate
    ```

3. Встановити залежності
    ```sh
    pip install -r requirements.txt
    ```

4. Налаштування змінних середовища:
    - Створіть файл `.env` у директорії, в якій знаходиться файл `manage.py`.
    - Додайте до нього ваш секретний ключ та інші необхідні змінні середовища:
        ```
        SECRET_KEY=your_secret_key
        DEBUG=True  # або False в залежності від середовища
        ```

### Міграції бази даних

5. Застосувати міграції бази даних
    ```sh
    python manage.py makemigrations
    python manage.py migrate
    ```

### Запуск проекту

6. Запустити сервер розробки
    ```sh
    python manage.py runserver
    ```

API буде доступне за адресою `http://127.0.0.1:8000/`

### Використання Docker

7. Якщо ви віддаєте перевагу використанню Docker, можна скористатися Docker Compose для запуску проекту:
    ```sh
    docker-compose up --build
    ```

API буде доступне за адресою `http://0.0.0.0:8081/`.

## Використання

### Головний екран API

![screenshot](/teams_config/readme_images/main_screen.jpg)

### Додавання нової команди

- Метод: POST
- URL: `/teams/`
- Приклад запиту:
    ```json
    {
        "name": "Ferrari"
    }
    ```
![screenshot](/teams_config/readme_images/add_new_team.jpg)

### Додавання нової людини

- Метод: POST
- URL: `/persons/`
- Приклад запиту:
    ```json
    {
        "first_name": "Michael",
        "last_name": "Schumacher",
        "email": "m.schumacher@ferrari.it",
        "team": "Ferrari"
    }
    ```
![screenshot](/teams_config/readme_images/add_new_person.jpg)

Цей README.md файл містить інформацію про налаштування змінних середовища,
використання `load_dotenv()` для завантаження секретних ключів та інструкції по встановленню,
використанню та тестуванню проекту.
