# Лабораторная работа #4
<ins>Задание.</ins>

По варианту, выданному преподавателем, составить и выполнить запросы к базе данных "Учебный процесс".

Команда для подключения к базе данных ucheb:

_psql -h pg -d ucheb_

<ins>Отчёт по лабораторной работе должен содержать:</ins>
1. Текст задания. 
2. Реализацию запросов на SQL. 
3. Планы выполнения запросов. 
4. Ответы на вопросы, представленные в задании. 
5. Выводы по работе.

<ins>Темы для подготовки к защите лабораторной работы:</ins>
1. Индексы 
2. Оптимизация запросов 
3. Выбор плана выполнения запросов

### Номер варианта: _9325_
## Внимание! У разных вариантов разный текст задания!
Составить запросы на языке SQL (пункты 1-2).

Для каждого запроса предложить индексы, добавление которых уменьшит время выполнения запроса (указать таблицы/атрибуты, для которых нужно добавить индексы, написать тип индекса; объяснить, почему добавление индекса будет полезным для данного запроса).

Для запросов 1-2 необходимо составить возможные планы выполнения запросов. Планы составляются на основании предположения, что в таблицах отсутствуют индексы. Из составленных планов необходимо выбрать оптимальный и объяснить свой выбор.
Изменятся ли планы при добавлении индекса и как?

Для запросов 1-2 необходимо добавить в отчет вывод команды EXPLAIN ANALYZE [запрос]

Подробные ответы на все вышеперечисленные вопросы должны присутствовать в отчете (планы выполнения запросов должны быть нарисованы, ответы на вопросы - представлены в текстовом виде).

1. Сделать запрос для получения атрибутов из указанных таблиц, применив фильтры по указанным условиям:
    - Таблицы: Н_ЛЮДИ, Н_СЕССИЯ.
    - Вывести атрибуты: Н_ЛЮДИ.ИД, Н_СЕССИЯ.УЧГОД.
    - Фильтры (AND):
       - Н_ЛЮДИ.ИМЯ = Александр.
       - Н_СЕССИЯ.ЧЛВК_ИД > 105948q.
       - Н_СЕССИЯ.ЧЛВК_ИД = 100012.
    - Вид соединения: RIGHT JOIN.

2. Сделать запрос для получения атрибутов из указанных таблиц, применив фильтры по указанным условиям:
    - Таблицы: Н_ЛЮДИ, Н_ОБУЧЕНИЯ, Н_УЧЕНИКИ.
    - Вывести атрибуты: Н_ЛЮДИ.ОТЧЕСТВО, Н_ОБУЧЕНИЯ.ЧЛВК_ИД, Н_УЧЕНИКИ.ГРУППА.
    - Фильтры: (AND)
      - Н_ЛЮДИ.ИД < 142095.
      - Н_ОБУЧЕНИЯ.ЧЛВК_ИД < 163276.
    - Вид соединения: INNER JOIN.
