# MESSENGER

1. `docker-compose up -d --build` запуск контейнера
2. `http://localhost:8000/` точка по генерации сообщений
3. нужно зайти в контейнер `web` - и запустить команду для вычитки сообщений `php bin/console messenger:consume -vv`
