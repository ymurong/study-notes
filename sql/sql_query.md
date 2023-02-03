- [Difference between **NOT EXISTS** and **NOT IN**](#difference-between-not-exists-and-not-in)


# Difference between **NOT EXISTS** and **NOT IN**


1. **NOT EXISTS** use correlated sub-query while **NOT IN** use sub-query in default.

    Different reaction to NULL value, if **NOT EXISTS** return one null record then the query would not return any records

2. Performance is crucial 

```sql
-- A is smaller than B

select * from A where cc in(select cc from B)　　
--> worse perf as using the index cc on A

select * from A where exists(select cc from B where cc=A.cc)　　
--> better perf as using the index cc on B
```


