# Update Values In Postgres Table

If you have an existing table with data, and you want to update a value in the table,
you can run the following (with the `WHERE` clause required to select the particular row
and column that you'd like to update):

```sql
UPDATE table_name
SET first_name = 'New First Name', last_name = 'New Last Name'
WHERE id = 1;
```