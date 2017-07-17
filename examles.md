#
### [Inner Join](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/join-clause)
```C#
var innerJoinQuery =
    from category in categories
    join prod in products on category.ID equals prod.CategoryID
    select new { ProductName = prod.Name, Category = category.Name }; //produces flat sequence
```
    
    
### [Group Join](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/join-clause)
```C#
var innerGroupJoinQuery =
    from category in categories
    join prod in products on category.ID equals prod.CategoryID into prodGroup
    select new { CategoryName = category.Name, Products = prodGroup };
```    



```C#
var innerGroupJoinQuery2 =
    from category in categories
    join prod in products on category.ID equals prod.CategoryID into prodGroup
    from prod2 in prodGroup
    where prod2.UnitPrice > 2.50M
    select prod2;
```
    
### [Left Outer Join](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/join-clause)
```C#
var leftOuterJoinQuery =
    from category in categories
    join prod in products on category.ID equals prod.CategoryID into prodGroup
    from item in prodGroup.DefaultIfEmpty(new Product { Name = String.Empty, CategoryID = 0 })
    select new { CatName = category.Name, ProdName = item.Name };
```
### []()
