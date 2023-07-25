# Update Table In Postgres

If you have an existing table that you need to add a column to, you can run, swapping in your column names, types, and restrictions as needed:

```sql
ALTER TABLE table_name
ADD COLUMN column_name VARCHAR(255) NOT NULL;
```

Sometimes you might need to update a column type. This can be done by running:

```sql
ALTER TABLE table_name
ALTER COLUMN column_name TYPE new_data_type;
```

If you want to make a previously nullable column non-nullable then run:

```sql
ALTER TABLE table_name ALTER COLUMN column_name SET NOT NULL;
```

Or if you want to remove the nullable restriction, run:

```sql
ALTER TABLE table_name ALTER COLUMN column_name DROP NOT NULL;
```
