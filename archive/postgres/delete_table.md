# Delete Table In Postgres

If you've previously created a table in Postgres that now needs to be deleted, it's as simple as running:

```sql
DROP TABLE table_name;
```

This is irresversible, so make sure you have the correct table name!

If you want to check first if the table exists and then delete it if it does (which
helps prevent the entire query from erroring out), you can run:

```sql
DROP TABLE IF EXISTS table_name;
```
