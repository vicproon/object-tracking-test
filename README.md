Описание задачи
=================================================

Данные
-------------------------------------------------

Данные лежат в папке `det_data`, представляют собой таблицы с результатами сырых детекций объектов (машин, пешеходов, светофоров).
Поля таблицы разделены символом '\t', и представляют собой

* `msec` --- `int64_t` миллисекунды события с начала работы системы
* `type` --- `string`  тип объекта: Pedestrian, Vehicle, TrafficLight
* `x_gm` --- `float64` x-координата объекта на виде "сверху", измеряется в метрах
* `y_gm` --- `float64` y-координата объекта на виде "сверху", измеряется в метрах

оси X, Y направлены на восток и север, соответсвенно, и представляют собой плоскую развертку некоторого участка испытаний


Задача
-------------------------------------------------

Необходимо написать программу на языке С++, которая бы выполняла фильтрацию детекций и трекинг уникальных объектов.
Результатом должны быть аналогичные файлы ответов-таблиц, в которых для каждой строчки иходного файла должны добавиться дополнительные три столбца:

* `id`   --- уникальный идентификатор объекта или `-1` если объект был отфильтрован
* `yaw`  --- направление движения объекта в радианах. Положительное направление - против часовой, 0 считать направление на север.
* `v`    --- оценка мгновенной скорости вдоль направления yaw, в м\с

Выбор алгоритмов фильтрации и трекинга остается за кандидатом.
В качестве baseline можем предложить использовать фильтр калана и фильтровать результаты треков со временем жизни менее 5 сек.


Отчет
-------------------------------------------------

Необходимо приготовить мини отчет и по скайпу или вживую защитить его перед сотрудникми когнитив-роботикс. 
В отчете следует указать использованные инструменты, возникшие проблемы, способы которыми их удалось решить или анализ возможных путей их решения в будущем.
Так же важным результатом работы является сам код решения задачи.

