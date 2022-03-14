# ISO 8601 YYY-MM-DD Date Format

There are many times when it would be nice for a date to appear formatted to
the standard YYYY-MM-DD format for easy visualization in reports. With Presto
/ Trino SQL, this can be accomplished with the `to_isd8601` date function.

```sql
SELECT
  -- Remove the time and conform to ISO standard YYYY-MM-DD string
  to_iso8601(DATE(timestamp)) AS formatted_date
FROM
  table_of_timestamps
```
