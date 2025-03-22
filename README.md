# Telegram File Manager Bot

Этот бот позволяет управлять файлами на сервере через Telegram. Вы можете создавать, редактировать, просматривать, перемещать, копировать и удалять файлы и папки, а также выполнять поиск по содержимому.
## ПРЕДУПРЕЖДЕНИЕ: Не все команды работают правильно, или работают вообще.

## Установка

1. Клонируйте репозиторий:
   ```bash
   git clone https://github.com/yourusername/telegram-file-manager-bot.git
   cd telegram-file-manager-bot
   ```

2. Установите зависимости:
   ```bash
   pip install -r requirements.txt
   ```

3. Создайте файл `.env` в корне проекта и добавьте в него следующие переменные:
   ```plaintext
   TOKEN=your_telegram_bot_token
   LOG_FILE=path_to_log_file
   SETTINGS_DB_FILE=path_to_settings_db_file
   AUTHORIZED_USER_ID=your_user_id
   ```
   - `TOKEN`: Токен вашего Telegram-бота.
   - `LOG_FILE`: Путь к файлу для логирования действий.
   - `SETTINGS_DB_FILE`: Путь к файлу для хранения настроек.
   - `AUTHORIZED_USER_ID`: Ваш ID в Telegram (можно узнать у бота [@userinfobot](https://t.me/userinfobot)).

4. Запустите бота:
   ```bash
   python bot.py
   ```

## Использование

После запуска бота вы можете использовать следующие команды:

### Основные команды
- `/start` - Начать работу с ботом.
- `/help` - Показать список доступных команд.
- `/pwd` - Показать текущую директорию.
- `/ls` - Показать содержимое текущей директории.
- `/cd <путь>` - Сменить директорию.
- `/back` - Вернуться на уровень выше.
- `/download <имя_файла>` - Скачать файл.
- `/search <текст или маска>` - Поиск файлов.
- `/view <имя_файла>` - Просмотреть содержимое файла.
- `/create <имя_файла> "текст"` - Создать файл.
- `/edit <имя_файла> "новый_текст"` - Редактировать файл.

### Управление файлами и папками
- `/mv <источник> <назначение>` - Переместить или переименовать файл/папку.
- `/cp <источник> <назначение>` - Скопировать файл/папку.
- `/rm <путь>` - Удалить файл/папку.
- `/mkdir <имя_папки>` - Создать папку.
- `/rmdir <имя_папки>` - Удалить пустую папку.

### Настройки
- `/settings` - Показать текущие настройки.
- `/settings default_path <путь>` - Установить дефолтный путь для команды `/cd`.
- `/settings filtering <name/date/off>` - Установить режим фильтрации.
- `/settings grouping <date/off>` - Установить режим группировки.

### Примеры использования
- Перейти в папку `Documents`:
  ```
  /cd Documents
  ```
- Просмотреть содержимое текущей директории:
  ```
  /ls
  ```
- Создать файл `test.txt` с текстом:
  ```
  /create test.txt "Это тестовый файл"
  ```
- Поиск файлов с расширением `.txt`:
  ```
  /search --type=txt
  ```

## Логирование
Все действия пользователя логируются в файл, указанный в переменной окружения `LOG_FILE`.

## Лицензия
Этот проект распространяется под лицензией GNU GPL. Подробнее см. в файле [LICENSE](LICENSE).

---

**Примечание:** Бот предназначен для использования только авторизованным пользователем. Убедитесь, что вы указали правильный `AUTHORIZED_USER_ID` в файле `.env`.