Eng
---

Database - class for develop with database mysql, use adapter PHP mysqli and use placeholder, when each literal (argument) in string SQL query escaping without specific PHP function.

<code>
```sql
$db->query('SELECT * FROM `table` WHERE `field_1` = "?s" AND `field_2` = ?i', 'Basiel', 30);
```
</code>

Rus
---

Класс для простой работы с СУБД MySql с использованием расширения PHP mysqli.

Данный класс использует технологию placeholders - для формирования корректных SQL-запросов, в строке запроса вместо значений пишутся специальные типизированные маркеры - заполнители, а сами данные передаются "позже", в качестве последующих аргументов основного метода, выполняющего SQL-запрос:
<code>
```sql
$db->query('SELECT * FROM `table` WHERE `field_1` = "?s" AND `field_2` = ?i', 'вася', 30);
```
</code>

Данные, прошедшие через систему placeholders, экранируются специальными функциями экранирования, в зависимости от типа заполнителей. Т.е. вам нет необходимости заключать переменные в функции экранирования типа _mysqli_real_escape_string($value)_ или приводить их к числовому типу через _(int)$value_.

Подробное описание см. в файле <a href="https://github.com/Vasiliy-Makogon/Database/blob/master/Mysql.php">/Mysql.php</a>.
Тесты и различные вариации использования см. в файле <a href="https://github.com/Vasiliy-Makogon/Database/blob/master/Mysql/test.php">./Mysql/test.php</a>.
