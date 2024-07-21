# Теория баз данных

## Тема: Запросы SELECT, INSERT, UPDATE, DELETE.

Запросы:

1. Вывести таблицу кафедр, провеси сортировку в обратном порядке.
SELECT * FROM Departments ORDER BY ID DESC;

![текст](https://sun9-74.userapi.com/impg/4QtkV9ZEZPVrQ7dXhuXr3z8XRaiFifNHGHTaMQ/OlE4p-HK31M.jpg?size=1920x1080&quality=95&sign=75300eb6466b45269d08ffef9f0e7390&type=album)

Вывести таблицу кафедр, но расположить ее поля в обратном порядке.
SELECT Name, Financing, Id FROM Departments;

![текст](https://sun9-34.userapi.com/impg/TEaVCcAf337DYpTzNiG_0OVS_cOB7C4qKe4feQ/wqcz3ynIsh8.jpg?size=1920x1080&quality=95&sign=77da14de5f880f281a1af72e160ca837&type=album)

2. Вывести названия групп и их рейтинги с уточнением имен полей именем таблицы.
SELECT `Groups`.Name AS Groups_Name, `Groups`.Rating AS Groups_Rating FROM `Groups`;

![текст](https://sun9-12.userapi.com/impg/6xK-Do9Ieex0Iv_jDua3JwfqPxxQfoBBIERRmw/tU1iHgAC7v0.jpg?size=1920x1080&quality=95&sign=5fb8e0a69aec80a95f6e642b0e48a69e&type=album)

3. Вывести для преподавателей их фамилию, процент ставки по отношению к надбавке и процент ставки по отношению к зарплате (сумма ставки и надбавки).
SELECT Surname, Salary * 100 / Premium, Salary * 100 / (Salary + Premium) FROM Teachers;

![текст](https://sun9-10.userapi.com/impg/qjjtKLGQsYoKaFX2E3HtXoMlm2vPc6m4JzpEJg/FwHFlRPDYbA.jpg?size=1920x1080&quality=95&sign=d1cde58036e19331887520956360d69a&type=album)

4. Вывести таблицу факультетов в виде одного поля в следующем формате: “The dean of faculty [faculty] is [dean].”.
SELECT CONCAT("The dean of faculty ", Name, " is ", Dean) FROM Faculties;
5. Вывести фамилии преподавателей, которые являются профессорами и ставка которых превышает 1050.
SELECT Surname FROM Teachers WHERE isProfessor = 1 AND Salary > 1050;

![текст](https://sun9-4.userapi.com/impg/aWAFQ_DdoeZIAcG1aJxrG9mtfL7HBbYNx-09gg/DFox6ucwRO8.jpg?size=1920x1080&quality=95&sign=9ddc3419fab07f854fb43963a5091049&type=album)

6. Вывести названия кафедр, фонд финансирования которых меньше 11000 или больше 25000. 
SELECT Name FROM Departments WHERE Financing < 11000 OR Financing > 25000;
7. Вывести названия факультетов кроме факультета “Computer Science”.
SELECT Name FROM Faculties WHERE Name != "Computer Science";
8. Вывести фамилии и должности преподавателей, которые не являются профессорами. 
SELECT Surname, Position FROM Teachers WHERE isProfessor != 1;
9. Вывести фамилии, должности, ставки и надбавки ассистентов, у которых надбавка в диапазоне от 160 до 550.
SELECT Surname, Position, Salary, Premium FROM Teachers WHERE isAssistant = 1 AND Premium BETWEEN 160 AND 550;

![текст](https://sun3-24.userapi.com/impg/Vanuic5y_id1cyxcR5iJEFx_wxCI9MZwOhUejw/UaU7zwiSstg.jpg?size=1920x1080&quality=95&sign=6d453cf260441aa66b052d8bde3f2c90&type=album)

10. Вывести фамилии и ставки ассистентов.
SELECT Surname, Salary FROM Teachers WHERE isAssistant = 1;

![текст](https://sun9-69.userapi.com/impg/Pv-inM673QPllI7-kRLtJlPhPD0LRj2L_aeaEA/L4yMNilT-oA.jpg?size=1920x1080&quality=95&sign=54f9cc44b80e44b4d050a6138bceed95&type=album)

11. Вывести фамилии и должности преподавателей, которые были приняты на работу до 01.01.2000.
SELECT Surname, Position FROM Teachers WHERE EmploymentDate < "2000-01-01";
12. Вывести названия кафедр, которые в алфавитном порядке располагаются до кафедры “Software Development”. Выводимое поле должно иметь название “Name of De­part­ment”.
SELECT Name AS `Name of Department` FROM Departments WHERE Name < "Software Development";

![текст](https://sun9-16.userapi.com/impg/Jq9c3G7gkGh1VAavy3rsfP0y1WZkfOKdpFrOuQ/dk1Sj_fiTJQ.jpg?size=1920x1080&quality=95&sign=dfba3338a02c21c2661eec39cb498787&type=album)

13. Вывести фамилии ассистентов, имеющих зарплату (сумма ставки и надбавки) не более 1200.
SELECT Surname FROM Teachers WHERE isAssistant = 1 AND (Salary + Premium) <= 1200;

![текст](https://sun9-2.userapi.com/impg/E-Dqrv_n3cLkzmWo7_A3nR2ChZvcW2zjUAeqNw/AUpE4ZpsZXw.jpg?size=1920x1080&quality=95&sign=8d4f3b7e8d89eb5a4f2f1b0d769c3d67&type=album)

14. Вывести названия групп 5-го курса, имеющих рейтинг в диапазоне от 2 до 4.
SELECT Name FROM `Groups` WHERE Year = 5 AND Rating BETWEEN 2 AND 4;

![текст](https://sun9-52.userapi.com/impg/0_1RThHS6pqWOYaVRU8wc4Rm4WxYScQYdlyxEw/l_ofq0fUzBU.jpg?size=1920x1080&quality=95&sign=f4ecf05a0d38dd3c0b99411236334567&type=album)


15. Вывести фамилии ассистентов со ставкой меньше 550 или надбавкой меньше 200. 
SELECT Surname FROM Teachers WHERE isAssistant = 1 AND (Salary < 550 OR Premium < 200); 

![текст](https://sun9-62.userapi.com/impg/GcjMLfQCaIxOhaWktvGVpqaslWQnfzfBUqoXxA/eplYIuXWFqA.jpg?size=1920x1080&quality=95&sign=4745fcad664d3747617a2afd205a6d2c&type=album)