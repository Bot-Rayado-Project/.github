<div align="center">
  <a href="https://github.com/3xiced/vkbot/">
    <img src="https://sun9-2.userapi.com/impf/rk2ygDyEHBqBLbBUPpWGRKfP4n-envluGtF3Vg/T5XaeQtts3E.jpg?size=1024x1024&quality=95&sign=f48c68a1368be545efd1e88ad36d4ca1&type=album" height="512">
  </a>
  <h1><a href="https://github.com/Rayado-Development">Bot Rayado Project</a> - Python</h1>
  <h3>Bot Rayado - Проект, содержащий все компоненты для функционирования ботов Rayado, написанный на Python и других языках.</h3>
</div>

# Bot Rayado

Bot Rayado - это проект, созданный двумя разработчками, чтобы облегчить жизнь студентов МТУСИ.

Bot Rayado вдохновлен многими другими проектами и был создан благодаря энтузиазму разработчиков.

**Текущий мейнтейнер** проекта: [@3xiced](https://github.com/3xiced)
# Почему именно мы?

- Есть шаблоны для быстрого получения расписания
- Всегда новое расписание, полученное с сайта в момент запроса
- Большое количество потоков
- Быстрая работа бота
- Регулярные обновления
- Микросервисная архитектура
- Уникальный алгоритм парсинга

# Установка
Клонируем репозиторий:
(https)
```
git clone https://github.com/Rayado-Development/compose-services & cd compose-services
```
(ssh)
```
git clone git@github.com:Rayado-Development/compose-services.git & cd compose-services
```
(gh cli)
```
gh repo clone Rayado-Development/compose-services & cd compose-services
```
Важно! Перед запуском не забудьте внести конфиденциальные данные в .env файлы.

Запускаем только postgres:
```
docker-compose up --build --no-deps pgadmin postgres
```

Создаем базу данных schedules

Создаем таблицы в ней
```
CREATE TABLE IF NOT EXISTS shared_schedules(stream_group TEXT NOT NULL, day TEXT NOT NULL, parity TEXT NOT NULL, schedule TEXT NOT NULL);
CREATE TABLE IF NOT EXISTS headman_schedules(stream_group TEXT NOT NULL, day TEXT NOT NULL, parity TEXT NOT NULL, schedule TEXT NOT NULL);
CREATE TABLE IF NOT EXISTS personal_schedules(id INT NOT NULL, stream_group TEXT NOT NULL, day TEXT NOT NULL, parity TEXT NOT NULL, schedule TEXT NOT NULL);
CREATE TABLE IF NOT EXISTS headman_annotations(stream_group TEXT NOT NULL, day TEXT NOT NULL, parity TEXT NOT NULL, annotation TEXT NOT NULL);
CREATE TABLE IF NOT EXISTS personal_annotations(id INT NOT NULL, stream_group TEXT NOT NULL, day TEXT NOT NULL, parity TEXT NOT NULL, annotation TEXT NOT NULL);
CREATE TABLE IF NOT EXISTS headman_changes(stream_group TEXT NOT NULL, day TEXT NOT NULL, parity TEXT NOT NULL, pair_number INT NOT NULL, changes TEXT NOT NULL);
CREATE TABLE IF NOT EXISTS personal_changes(id INT NOT NULL, stream_group TEXT NOT NULL, day TEXT NOT NULL, parity TEXT NOT NULL, pair_number INT NOT NULL, changes TEXT NOT NULL);
```

Создаем базу данных tgbot и vkbot

Создаем таблицы в них
```
CREATE TABLE users(user_id integer NOT NULL, date timestamp NOT NULL, command text NOT NULL);
CREATE TABLE config(user_id integer NOT NULL, keyboard_buttons text NOT NULL);
```

Запускаем проект
```
docker-compose up --build
```

# Производительность

Bot Rayado не самый легковесный, но довольно оптимизированный проект.

# Сообщество

Bot rayado - очень молодой проект.

[Группа ВКонтакте](https://vk.com/botrayado)
[Телеграм](t.me/rayadobot)

# Разработчики

[Александр Разумов](https://vk.com/lamabot2000)

[Иван Чепиков](https://vk.com/crymother)
