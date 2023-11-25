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