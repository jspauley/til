# Create Table In Postgres

Creating a new table in Postgress is very straightforward. Once connected to the database, it's as simple as running the following command, swapping in your column names, types, and restrictions as needed:

```sql
CREATE TABLE table_name (
	id serial PRIMARY KEY,
	table_id INTEGER NOT NULL,
	table_value VARCHAR(50) NOT NULL,
    created_at TIMESTAMP NOT NULL,
);
```
