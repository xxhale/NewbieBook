Всё про разные СУБД, SQL, оптимизацию запросов.

Базовый синтаксис

Создание новых объектов базы данных, таких как таблицы, индексы, базы данных
CREATE

    CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    position VARCHAR(50),
    salary DECIMAL(10, 2)
    );

Изменение структуры существующих объектов базы данных, таких как таблицы.
ALTER

    ALTER TABLE employees
    ADD COLUMN hire_date DATE;

Удаление объектов базы данных, таких как таблицы или базы данных.
DROP

    DROP TABLE employees;

Удаление всех записей из таблицы без удаления самой таблицы.
TRUNCATE

    TRUNCATE TABLE employees;

Извлечение данных из одной или нескольких таблиц.
SELECT

    SELECT * FROM employees;
    
Вставка новых данных в таблицу.
INSERT

    INSERT INTO employees (id, name, position, salary)
    VALUES (1, 'John Doe', 'Manager', 75000.00);

Обновление существующих данных в таблице.
UPDATE

    UPDATE employees
    SET salary = 80000.00
    WHERE id = 1;

Удаление данных из таблицы.
DELETE

    DELETE FROM employees
    WHERE id = 1;

Предоставление привилегий пользователям или ролям.
GRANT

    GRANT SELECT, INSERT ON employees TO user1;

Примеры комбинирования команда:
Создание и наполнение таблицы:

    CREATE TABLE departments (
    id INT PRIMARY KEY,
    name VARCHAR(100)
    );

    INSERT INTO departments (id, name)
    VALUES (1, 'HR'), (2, 'Finance'), (3, 'Engineering');

Извлечение данных с фильтрацией и сортировкой:

    SELECT name, salary
    FROM employees
    WHERE salary > 50000
    ORDER BY salary DESC;

Объединение данных из нескольких таблиц:

    SELECT e.name, d.name AS department
    FROM employees e
    JOIN departments d ON e.department_id = d.id;


    

