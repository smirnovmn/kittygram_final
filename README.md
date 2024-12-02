# Kittygram

**Kittygram** — это онлайн-платформа, где пользователи могут зарегистрироваться, загружать фотографии своих котиков и наслаждаться фото других котиков со всего мира.

## Статус проекта

[![Main Kittygram workflow](https://github.com/smirnovmn/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/smirnovmn/kittygram_final/actions/workflows/main.yml)

## Развернутый проект

Развернутый проект доступен по следующей ссылке: [kittygramsite.zapto.org](http://kittygramsite.zapto.org)

## Описание

- **Что такое продакшн-версия?**
  Продакшн-версия — это стабильная версия приложения, готовая для использования конечными пользователями. В продакшн-версии включены:
  - Оптимизированные настройки безопасности.
  - Минифицированные файлы фронтенда.
  - Отключение режима отладки (`DEBUG=False`).
  - Подключение к реальной базе данных.

- **Когда использовать продакшн-версию?**
  Продакшн-версия используется, когда приложение готово для работы в реальных условиях. Используйте ее на сервере, чтобы обеспечить стабильную работу вашего проекта для конечных пользователей.

- **Когда использовать обычную (локальную) версию?**
  Локальная версия используется для разработки и тестирования. В этой версии доступны отладочные сообщения, не оптимизированные файлы и другие инструменты для разработки.

## Инструкция по разворачиванию проекта

### Локальное развертывание

1. **Клонируйте репозиторий:**
   ```bash
   git clone https://github.com/ваш_пользователь/kittygram_final.git
   cd kittygram_final

2. **Создайте виртуальное окружение:**
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # Для Linux/macOS
   venv\Scripts\activate     # Для Windows 

3. **Установите зависимости:**
   ```bash
   pip install -r requirements.txt

4. **Настройте базу данных:**
   -Вам нужно настроить параметры для подключения к базе данных. Вы можете сделать это через файл .env или через переменные окружения. Вот необходимые параметры:

   -Создайте файл .env в корневой директории проекта (или настройте переменные окружения):

   ```bash
   POSTGRES_USER=your_user
   POSTGRES_PASSWORD=your_password
   POSTGRES_DB=your_db
   DB_HOST=localhost
   DB_PORT=5432
   SECRET_KEY=your_secret_key
   DEBUG=True

5. **Примените миграции и создайте суперпользователя**
   -Теперь примените миграции базы данных и создайте суперпользователя для доступа к админке:
   ```bash
   python manage.py migrate
   python manage.py createsuperuser

6. **Запустите сервер через Docker**
   ```bash
   docker-compose up --build
  
-После этого проект будет доступен по адресу http://localhost:9000/.

### Развертывание на сервере

1. **Клонируйте репозиторий на сервер:**
   ```bash
   git clone https://github.com/5mirnovvv/kittygram_final.git
   cd kittygram_final

2. **Запустите проект с помощью Docker Compose:**
   -В каталоге с проектом выполните:
   ```bash
   docker-compose up -d --build

3. **Проверьте что контейнеры запустились:**
   -В списке должны быть соотвествующие контейнеры
   ```bash
   docker-compose ps

4. **Для остановки и удаления контейнеров:**
   ```bash
   docker-compose down
  
## Автор проекта:

- **Автор**: [Misha Smirnov](https://github.com/smirnovmn)

## Технологии:

- **Backend**:
  - Django
  - PostgreSQL
  - Docker
  - Gunicorn
  - Nginx

- **Frontend**:
  - HTML
  - CSS
  - JavaScript
  - React
