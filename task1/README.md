**Замеры оптимизации**

1. В папке cacheble содержатся скрины замера времени до использования аннотации @Cacheble и после.

2. В папке localHash содержатся скрины несколько замеров скорости.

same_days: Если замер скорости до и после совпал по кол-ву дней.

different_days: Замеряем скорость до при 50 и 100 днях, а потом смотрим прирост скорости при 100, при прогретых 50 днях.

Тут кэширование происходит по первым дням, то есть от нашего нового запроса подтягиваем дни, которые мы уже запрашивали, остальное по запросам.



_P.S. Вообще можно было, конечно вставить сюда бд и расчитывать относительно сохраненных до, сопоставляя с текущей датой, но вряд ли надо было настолько сложно делать, там скорее в обычном случае добавится время на проверку бд, а время запроса на сервер схожих дней заменится на поход к локальной бд. В жизни же мы тоже бы обращались не к локальной, а по какой-то api до места, где бд, причем не факт, что это было бы быстрее для 1 даты, но было бы быстрее для группы дат_


Вывод в консоль не убирал, так как это типо логирования, не считается оптимизацией. Это нужно, хоть и отнимает время.