# Create A Table From Values In Trino

To create a table from a manually generated set of data, run a query with the following format:

```sql
SELECT
  *
FROM (
  VALUES
  -- Manually Generated List
  (1,     'Name One',     100,    'Thing One'),
  (2,     'Name Two',     200,    'Thing Two'),
  (3,     'Name Three',   300,    'Thing Three')
) AS t (id, name, value_id, value_name)

```

This can also be wrapped in a CTE so that it's queryable in additional SQL.