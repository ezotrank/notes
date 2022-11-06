# PostgreSQL

tags: #posgresql

## Patterns

**FOR UPDATE SKIP LOCKED**

```sql
UPDATE events SET status='running', updated_at=now()
WHERE id = (
  SELECT id
  FROM events
  WHERE status='new'
  ORDER BY id
  FOR UPDATE SKIP LOCKED
  LIMIT 1
)
RETURNING id;
```

Links:

[SKIP LOCKED: ONE OF MY FAVORITE 9.5 FEATURES](https://www.cybertec-postgresql.com/en/skip-locked-one-of-my-favorite-9-5-features/)
[Доводим распределённые действия до конца с использованием простейшего паттерна Saga](https://habr.com/ru/company/ozontech/blog/590709/)
[Most work queue implementations in SQL are wrong](https://www.2ndquadrant.com/en/blog/what-is-select-skip-locked-for-in-postgresql-9-5/)