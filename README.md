## Упражнения по SQL
*(https://www.sql-ex.ru/learn_exercises.php)*


#### Задание: 10
> Найдите модели принтеров, имеющих самую высокую цену. Вывести: model, price.

``` 
SELECT model, price
FROM Printer
WHERE price = (SELECT MAX(price) 
 FROM Printer
 )
```

#### Результат выполнения запроса:

model | price
----- |-----
1288 | 400.0000
1276 | 400.0000


#### Задание: 11
> Найдите среднюю скорость ПК.

``` 
SELECT AVG(speed)
FROM PC
```

#### Результат выполнения запроса:

Avg_speed |
----- |
608 | 

#### Задание: 12
> Найдите среднюю скорость ПК-блокнотов, цена которых превышает 1000 дол.

``` 
SELECT AVG(speed)
FROM Laptop
WHERE price > 1000

```

#### Результат выполнения запроса:

Avg_speed |
----- |
700 | 

#### Задание: 13
> Найдите среднюю скорость ПК, выпущенных производителем A.

``` 
SELECT AVG(speed)
FROM Product, PC
WHERE PC.model= Product.model and maker = 'A'

```

#### Результат выполнения запроса:

Avg_speed |
----- |
600 | 

#### Задание: 14
> Найдите класс, имя и страну для кораблей из таблицы Ships, имеющих не менее 10 орудий.

``` 
SELECT s.class, s.name, c.country
FROM ships s
INNER JOIN classes c ON s.class = c.class
WHERE c.numGuns >= 10
```

#### Результат выполнения запроса:

class|name|country
----- |-----|-----
Tennessee|California|USA
North Carolina|North Carolina|USA
North Carolina|South Dakota|USA
Tennessee|Tennessee|USA
North Carolina|Washington|USA

#### Задание: 15
> Найдите размеры жестких дисков, совпадающих у двух и более PC. Вывести: HD.

``` 
SELECT hd
FROM PC
GROUP BY (hd) 
HAVING COUNT(model) >= 2
```

#### Результат выполнения запроса:

hd |
-----|
5.0|
8.0|
10.0|
14.0|
20.0| 
