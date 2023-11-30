SQL можно использовать для:
1) Получения данных
2) Обновления данных
3) Удаление данных
4) Создание новых таблиц и БД
5) Добавить/удалить пользователей
6) Управление разрешениями пользователей базы данных
Для установки mysql/mariadb используем команды 
1) установка - sudo apt instal mysql
2) активация - chkconfig mysqld on
3) service mysqld start
4) mysql -u root
5)  Затем в консоли mysql вводим - ALTER USER 'root'@'localhost' IDENTIFIED BY 'you_own_pass';
6) Запуск - mysql -u root -p, следом вводи пароль.

Команды баз данных не чувствительны к регистру, писать можно и в верхнем и в нижнем, но при этом названия баз данных ТОЛЬКО в нижнем регистре, поэтому рекомендуется писать 

Создание базы данных

CREATE DATABASE <name>;     // создание базы данных
SHOW DATABASES;                   // Показывает кол-во и название баз 
USE <name>;                            // Переключение на эту базу данных
DESCRIBE <name>;                  // Описание таблицы в виде колонка - тип 

Пример создания таблицы:

CREATE TABLE logins (
    id INT,
    username VARCHAR(100),
    password VARCHAR(100),
    date_of_joining DATETIME
    );

Вставить записи в таблицу без пропуска даты и id
INSERT INTO table_name VALUES (column1_value, column2_value, column3_value, ...); 

Запись конкретных значений в конкретные колонки (пропуск столбцов с  NOT NULL приведет к ошибке)
INSERT INTO table_name(column2, column3, ...) VALUES (column2_value, column3_value, ...);

Получить значения из таблицы
SELECT column1, column2 FROM table_name;

удаление таблиц и данных с сервера
DROP TABLE <name>

Произвести изменения с таблицей, колонной:

1) ALTER TABLE logins ADD newColumn INT;       // Добавление новой таблицы
2) ALTER TABLE logins RENAME COLUMN newColumn TO oldColumn;  //Переименовать столбец 
3) ALTER TABLE logins MODIFY oldColumn DATE;   // Изменение типа данных столбца
4) ALTER TABLE logins DROP oldColumn;   // Удаление столбца

Обновление данных в таблице 
1) UPDATE table_name SET column1=newvalue1, column2=newvalue2, ... WHERE <условие>; 

Сортировка результатов
1) SELECT * FROM logins ORDER BY password;    // Сортирует таблицу logins по паролю
2) SELECT * FROM logins ORDER BY password DESC;   //Сортировка по убыванию 
3) LIMIT <value>   //Ограничение выдаваемых запросов


Условия
1) WHERE <условие>      //Возвращает все значения, подходящие под условия
2) LIKE 'шаблон'    // Работает вместе с WHERE и ищет совпадения по шаблону, где % после шаблона означает наличие любых символов дальше, _ используется для соответствию 1 символу, соответственно '___' это поиск всех значений с 3мя символовами

Логические операторы 
1) AND (он же &&) - оба выражения должны быть TRUE
2) OR (он же ||) - одно из должно быть TRUE
3) NOT (он же !=) - переворачивает значение 

Приоритет операций: 

    Разделение ( /), Умножение ( *) и модуль ( %)
    Добавление ( +) и вычитание ( -)
    Сравнение ( =, >, <, <=, >=, !=, LIKE)
    НЕТ ( !)
    И ( &&)
    ИЛИ ( ||)
