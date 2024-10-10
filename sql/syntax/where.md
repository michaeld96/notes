# `WHERE`

`WHERE` will return all the records where a specific condition
is true.

## `WHERE IN (<values>)` 

`IN` returns records that have multiple values that are true. It 
acts like a multiple OR statement.

### Example
```sql
SELECT Id FROM People
WHERE IN (1, 30, 60)
```
This query will the records that have the `Id` of `1`, `30`, and `60`
if they exist.