# Joins
Joins are used to connect and gain information from multiple tables at the same time. Tables are connect to each other using what is known as a join predicate.
There are different types of joins:
* `(INNER) JOIN`
    * Used to return the values that only exist in both tables queried

* `LEFT JOIN`
    * Returns ALL the values in the first/left table and only the matching values in the second/right table

* `RIGHT JOIN`
    * The opposite of a left join
    * Returns ALL the values in the right/second table and only the matching values in the first/left table

* `FULL (OUTER) JOIN`
    * Combination of a left join and a right join
    * Returns all of the results in both tables regardless of whether or not they have a matching value in the other table

* General syntax:

```sql
SELECT [columns]
FROM [left table]
LEFT/RIGHT/FULL JOIN [right table]
ON [join predicate];
```

* `NATURAL`
    * Natural is a keyword used in addition to a join declaration.
    * Natural removes the need for a join predicate and simply joins the tables by the same column names

* Natural Join Syntax:

```sql
SELECT [columns]
FROM [left table]
NATURAL LEFT/RIGHT/FULL JOIN [right table]
```

Helpful Graphic:

<img src="https://www.dofactory.com/img/sql/sql-joins.png" />

# Subqueries
Subqueries are essentially queries held within another query
* Useful for combining queries together to minimize change required by developer or analyst
* Can go anywhere in the `SELECT`, `FROM`, or `WHERE` clauses
* Must be contained entirely within parantheses
* If used with a `WHERE` clause it must be aliased
* Can be used with DML commands (`INSERT`, `SELECT`, `UPDATE`, `DELETE`)

# Set Operations
Set operations aggregate data together in ways different than joins
* Used to combine multiple columns worth of data together at once for comparison
* Sets being operated on need to have the same number of columns selected and those columns must contain similar data types
* Set operations are done using the `UNION`, `UNION ALL`, `INTERSECT`, and `EXCEPT` commands
    * `UNION` 
        * Combines columns of data vertically. Takes all the data from the first select and combines it with all the data from the second select without duplicates
    * `UNION ALL`
        * Very similar to `UNION`. The only difference is that `UNION ALL` includes duplicates.
    * `INTERSECT`
        * Contains the intersection of the two selects. It will only return a column with values that both selects share.
    * `EXCEPT`
        * Sometimes called `MINUS` in other versions of SQL
        * Returns the data from the first select and removes any columns that are also in the other selection
        * Another way to this about this is the first select minus the intersection it has with the second selection

Helpful Graphic:

<img src="https://www.codeproject.com/KB/database/1223175/SET-Operations-Visual-Guide-r-700.png" />

# Difference between JOIN and UNION
Joins and Unions may seem very similar but they are different in one cardinal way
* Joins combine data "horizontally". When two tables are joined together the data is compiled so that columns are placed next to each other in a horizontal fashion
* Unions combine data "vertically". When you union two selections the result sets are stacked vertically into the same number of columns as the selects. If you have one column for the selects it'll take the results from the first query and "stack" them on top of the results from the second query.
