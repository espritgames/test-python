# Тестовое задание

## Условие

Есть игровой сервер с 10 000 пользователями, которые постоянно играют и повышают свой уровень. Мы хотим иметь актуальную информацию об уровнях всех игроков и хотим ее получать как можно быстрее.

Игровой сервер не умеет сам отсылать оповещения о левелапах, но у него есть API, через которое можно получить текущий уровень игрока по его ID. Время ответа сервера - 100-1000 мс.

Демонстрационный сервер, эмулирующий игровую активность: https://github.com/espritgames/demo_game. Его можно использовать при разработке и тестировании.

Пример запроса и ответа API:
```
curl http://127.0.0.1:8080/user/1234
{"id": 1234, "level": 2}
```

ID игроков известны заранее - это все целые числа от 1 до 10000.

Нужно написать программу на Python, которая постоянно получает текущие уровни всех игроков и на каждом цикле сохраняет их в CSV-файле:
- формат названия файла: `levels-%Y-%m-%d_%H_%M_%S.csv` (например, `levels-2020-04-03_11_12_56.csv`)
- формат содержимого: `<user_id>;<level>` без заголовков;
- порядок строк в CSV произвольный, то есть сортировать по ID игрока необязательно.

В качестве решения нужно прислать ссылку на репозиторий в GitHub.

## Пожелания

Было бы классно, если бы при текущих условиях обновленные данные по всем игрокам появлялись каждую минуту.

Оформление в виде демона (через Docker, supervisord, systemd, etc) - по желанию.

С тестами будет совсем круто. Фреймворк (unittest, pytest) значения не имеет.
