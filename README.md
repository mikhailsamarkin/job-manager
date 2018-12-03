Job-manager
======================

Структура проекта
-------------------

```
common
    builders/               содержит классы построители для других классов
    dto/                    содержит классы Data Transfer Object
    entities/               содержит классы объектов используемых в приложении
    migrations              содержит миграции базы данных
    services/               содержит сервисы, используемые контроллерами
config/                     содержит настройки приложения
console/                    содержит контроллеры консольных комманд
environments/               содержит файлы для начальной инициализации приложения
modules
    api/                    модуль содержит end-point'ы HTTP API
tests/                      набор юнит тестов
web/                        содержит публичные файлы приложения
```

Консольные команды
-------------------

Первоначальная инициализация приложения
```
php yii environment/init [environment] [overwrite]
    environment             не обязательное поле с значением "dev" по умолчанию
    overwrite               не обязательное поле с значением "y" по умолчанию
```

Генерирование случайных вакансий в количестве от 10 до 100
```
php yii vacancy/generate
```

Доступные API
-------------------

```
/api/vacancy/index          получить список всех вакансий в формате JSON
```

Запуск Docker
-------------------

Для запуска контейнера используете команду
```
make install
```
Помимо установки вебсервера и СУБД будет выполнена установка миграций и генерация тестовых данных

Инструкция по ручному разворачиванию
-------------------

```
1. Выполнить команду php yii environment/init
2. Заполнить файл config/serv.env данными о БД
3. Выполнить команду php yii migrate
```