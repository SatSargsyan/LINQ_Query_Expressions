# LINQ  Query Expressions


<a href=https://msdn.microsoft.com/en-us/library/bb397676.aspx> LINQ  Query Expressions</a>

### Filtering
#### Probably the most common query operation is to apply a filter in the form of a Boolean expression. The filter causes the query to return only those elements for which the expression is true. The result is produced by using the where clause. The filter in effect specifies which elements to exclude from the source sequence. In the following example, only those customers who have an address in Երևան are returned.

```C#
var queryLondonCustomers = from cust in customers
                                         where cust.City == "Երևան"
                                         select cust;
```

#### You can use the familiar C# logical AND and OR operators to apply as many filter expressions as necessary in the where clause. For example, to return only customers from "Երևան" AND whose name is "Գագիկ" you would write the following code:

```C#
where cust.City=="Երևան" && cust.Name == "Գագիկ"
```
#### To return customers from Երևան or Paris, you would write the following code:
```C#
 where cust.City == "Երևան" || cust.City == "Paris"
```
Labbda-ov tipavorvats enq talis
Groupby
Select
where
#### <a href=https://msdn.microsoft.com/en-us/library/bb348436(v=vs.110).aspx> Distinct</a>
#### <a href=https://msdn.microsoft.com/en-us/library/bb534972(v=vs.110).aspx> Any</a>

