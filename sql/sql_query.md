- [Difference between **EXISTS** and **IN**](#difference-between-exists-and-in)
- [Difference between **NOT EXISTS** and **NOT IN**](#difference-between-not-exists-and-not-in)


# Difference between **EXISTS** and **IN**

1. **EXISTS** use correlated sub-query while **IN** use sub-query in default. EXISTS is used to check if a row exists based on a certain condition, while IN is used to check if a value exists in a specified set of values.

2. Performance is crucial  (executing order matters)

```sql
-- A is smaller than B

select * from A where cc in(select cc from B)　　
--> worse perf as using the index cc on A

select * from A where exists(select cc from B where cc=A.cc)　　
--> better perf as using the index cc on B 
```


# Difference between **NOT EXISTS** and **NOT IN**


1. **NOT EXISTS** use correlated sub-query while **NOT IN** use sub-query in default.
   
2. Different reaction to NULL value, if **NOT EXISTS** return one null record then the query would not return any records




