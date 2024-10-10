# `WHERE`

`WHERE` will return all the records where a specific condition
is true.

## `IN` 

`IN` returns records that have multiple values that are true. It 
acts like a multiple OR statement.

### Example
```sql
SELECT Id FROM People
WHERE IN (1, 30, 60)
```
This query will the records that have the `Id` of `1`, `30`, and `60`
if they exist.

## `LIKE`

`LIKE` operator is used to return a specific pattern in a column.

### Example
The query below will return all of the records where the `FirstName`
column has `Mike` in it. `%` is a wildcard, meaning that it will search
a string for anything before and after the string `Mike`, so, a string
`aaaMikeaaa` will be returned.

```sql
SELECT * 
FROM People
WHERE FirstName LIKE '%Mike%';
```