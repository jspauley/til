# Insert Values Into Postgres Table

If you have an existing table with data, and you want to add rows to the table, you can run the following command with as many column / value pairs as needed:

```sql
INSERT INTO table_name(column1, column2, …)
VALUES (value1, value2, …);
```