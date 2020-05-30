
### Вывести названия категорий товаров, количество продуктов в которых
больше 20**

```SQL
SELECT
    [PC.Name],
    count(*)
FROM [Production].[Product] AS P
INNER JOIN [Production].[ProductSubcategory] AS PSC
    ON P.ProductSubcategoryID = PSC.ProductSubcategoryID
INNER JOIN [Production].[ProductCategory] AS PC
    ON PSC.ProductCategoryID=PC.ProductCategoryID
group by [PC.Name]
having count(*) > 20

select pc.name, count(*)
from Production.Product as p
INNER JOIN Production.ProductSubcategory as psc
    on p.ProductSubcategoryID=psc.ProductSubcategoryID
INNER JOIN Production.ProductCategory as pc
    on psc.ProductCategoryID=PC.ProductCategoryID
group by PC.Name
having count(*) > 20
```

### Получить названия первых двух категорий товаров из упорядоченного по возрастанию количества товаров в категории списка

> select top 2 [pc.name\
> ]from
> Production.ProductCategory as pc\
> join production.ProductSubcategory as psc\
> on psc.ProductCategoryID = pc.ProductCategoryID\
> join production.Product as p\
> on psc.ProductSubcategoryID = p.ProductSubcategoryID\
> group by [pc.name\
> ]order by
> count(*) asc
>
> Хз зачем 2 таски одинаковые

```SQL
select top 2
[pc.name]

from Production.ProductCategory as pc

join production.ProductSubcategory as psc

on psc.ProductCategoryID = pc.ProductCategoryID

join production.Product as p

on psc.ProductSubcategoryID = p.ProductSubcategoryID

group by
[pc.name]

order by count(*) asc
```

**3 Найти названия товаров, которые были проданы хотя бы один раз**\

```SQL
select [p.name\
]from
Production.Product as p\
join Sales.SalesOrderDetail as sod on p.ProductID=sod.ProductID\
group by [p.name\
]
```

**4 Найти названия товаров, которые не были проданы ни разу**

**(Ржомба работает. В сумме с предыдущим дают число товаров)**

```SQL
SELECT p.name

FROM Production.Product as p

LEFT JOIN Sales.SalesOrderDetail as sod

ON p.ProductID=sod.ProductID

WHERE sod.ProductID is NULL

GROUP BY p.name
```

**5 Вывести на экран список товаров, названия, упорядоченный по
количеству продаж, по возрастанию**

```SQL
SELECT [p.Name]

FROM Production.Product AS p

join Sales.SalesOrderDetail as sod

on p.ProductID=sod.ProductID

GROUP BY
[p.Name]

ORDER BY COUNT(*)
```

**6 Вывести на экран первых три товара с наибольшим количеством продаж**

```SQL
SELECT top 3
[p.Name]

FROM Production.Product as p

join Sales.SalesOrderDetail as sod

on p.ProductID=sod.ProductID

GROUP BY
[p.Name]

ORDER BY COUNT(*) desc
```

**7 Вывести на экран список категорий, названия, упорядоченный по
количеству продаж товаров этих категорий, по возрастанию**

```SQL
SELECT
[PC.Name]

FROM Production.Product AS P

INNER JOIN Production.ProductSubcategory AS PSC

ON P.ProductSubcategoryID = PSC.ProductSubcategoryID

INNER JOIN Production.ProductCategory AS PC

ON PC.ProductCategoryID = PSC.ProductCategoryID

GROUP BY
[PC.Name],
PC.ProductCategoryID

ORDER BY COUNT(*) asc
```

**8 Вывести список поставщиков, названия вендоров, упорядоченный по
количеству поставляемых товаров, по возрастанию**

```SQL
select [v.name]

from Purchasing.Vendor as v

join Purchasing.ProductVendor as pv

on pv.BusinessEntityID = v.BusinessEntityID

join Production.Product as p

on p.ProductID = pv.ProductID

group by
[v.name]

order by count(*) asc
```

**9 Получить названия первых двух категорий товаров из упорядоченного по
возрастанию количества товаров в категории списка**

```SQL
select top 2 [pc.name\
]from
Production.ProductCategory as pc\
join production.ProductSubcategory as psc\
on psc.ProductCategoryID = pc.ProductCategoryID\
join production.Product as p\
on psc.ProductSubcategoryID = p.ProductSubcategoryID\
group by [pc.name\
]order by
count(*) asc
```

**10 Найти сколько различных размеров товаров приходится на каждую
категорию товаров**

```SQL
select
[pc.Name],
count(distinct p.Size)

from Production.Product as p

join Production.ProductSubcategory as psc

on p.ProductSubcategoryID = psc.ProductSubcategoryID

join Production.ProductCategory as pc

on psc.ProductCategoryID = pc.ProductCategoryID

group by
[pc.Name]
```

**Найти название товаров, которые были куплены или три, или пять раз**

```SQL
select p.Name, count(*)

from Production.Product as p join

Sales.SalesOrderDetail as sod

on sod.ProductID = p.ProductID

group by p.Name

having count(*)=3 or count(*)=5
```

**11 Подкатегории, которые больше 5....**

```SQL
select
[p.Name],count(*)а

from Production.Product a join

Production.ProductSubcategory p

on a.ProductSubcategoryID = p.ProductSubcategoryID

group by
[p.Name]

having count(*) > 5
```

**12. Найти названия тех категорий товаров, где количество товаров более
20**

```SQL
SELECT [PC.Name],
count(*)

FROM [Production].[Product] AS P

INNER JOIN [Production].[ProductSubcategory] AS PSC

ON P.ProductSubcategoryID=PSC.ProductSubcategoryID

INNER JOIN [Production].[ProductCategory] AS PC

ON PSC.ProductCategoryID=PC.ProductCategoryID group by
[PC.Name] having
count(*)>20
```