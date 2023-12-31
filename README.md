## Условие:

С работой ядра Спринг мы разобрались, теперь самое время подключить к нему пару модулей для комфортной работы. <br />
Начнем с ORM. <br />
Для работы с hibernate нам понадобится зависимость hibernate-core, корректным взаимодействием со Спрингом озаботится зависимость spring-orm. <br />
Как вы можете видеть, зависимость spring-core пропала, это произошло из-за того, что она является транзитной для всех модулей Спринга и дублировать ее смысла нет. <br />
У нас появились пакеты model, service, теперь сервисы и DAO объявлены бинами с помощью аннотаций @Repository и @Service. <br />
В методе main будет происходить тестирование работоспособности нашего приложения. Класс Car аннотирован как стандартная сущность hibernate. В AppConfig теперь присутствует базовая настройка hibernate, берущая данные из файла db.properties. Обратите внимание, что для ее работы используется аннотация @PropertySource("classpath:db.properties"), обращающаяся к папке ресурсов. <br />
На этом настройка приложения окончена. <br />

## Задание:

1. Создайте соединение к своей базе данных и схему. Запустите приложение. Проверьте, что оно полностью работает. <br />
2. Создайте сущность Car с полями String model и int series, на которую будет ссылаться User с помощью связи one-to-one. <br />
3. Добавьте этот класс в настройки hibernate. <br />
4. Создайте несколько пользователей с машинами, добавьте их в базу данных, вытащите обратно. <br />
5. В сервис добавьте метод, который с помощью hql-запроса будет доставать юзера, владеющего машиной по её модели и серии. <br />
