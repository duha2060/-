# Домашнее задание к занятию "`Базы Данных`" - `Максимов Андрей Дмитриевич`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1

Какие данные хранятся в этих таблицах :
фио - фамилия имя и отчество сотрудника
ОКЛАД - заработная плата сотрудника
должность - Занимаемая должность сотрудника
Тип подразделения - отдел в котором работает сотрудник
Дата - дата найма сотрудника
Адрес - местонахождение филиала
Проэкт - наименование проэкта для конкретного сотрудника.
Какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.
фио - строковый (varchar)
ОКЛАД - числовой (decimal/numeric)
должность - строковый (varchar)
Тип подразделения - строковый (varchar)
Дата - дата и время (tinyint)
Адрес - местонахождение филиала (varchar)
Проэкт - строковый (varchar)
Приведите решение к следующему виду:
```
employees (

id_employee, int, not null, auto_increment, primary_key
last_name, varchar(50), not null
first_name, varchar(50), not null
surname, varchar(50)
rank, foreign_key
salary, foreign_key
subdivision, foreign_key
office, foreign_key
project, foreign_key
hired_since, date, not null )
```
```
subdivisions (

id_subdivision, int, not null, auto_increment, primary_key
subdivision, varchar(100), not null
type_of_subdivision, foreign_key
office, foreign_key )
```

```
type_of_subdivision (

id_of_type, int, not null, auto_increment, primary_key
type )
```
```
offices (

id_office, int, not null, auto_increment, primary_key
office, varchar(200), not null )
```

```
projects (

id_project, int, not null, auto_increment, primary_key
project, varchar(100), not null )
```

```
ranks (

id_rank, int, not null, auto_increment, primary_key
rank, varchar(100), not null )
```
```
salary (

id_salary, int, not null, auto_increment, primary_key
salary, real, not null )
```
