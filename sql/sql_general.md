- [Difference between subquery and correlated subquery](#difference-between-subquery-and-correlated-subquery)


# Difference between subquery and correlated subquery

1. order is different. 
   subquery >> external,
   external >> correlated subquery

2. subquery is independant while correlated subquery is dependent on external query

Example: find the employees that has the highest salary in their own department

```sql
-- subquery
select a.deptno,a.* 
from emp a
where (a.deptno, a.sal) in (
    select deptno, max(sal) 
    from emp 
    group by deptno
)
```

```sql
-- correlated subquery
select a.deptno, a.* 
from emp a
where a.sal = (
    select max(b.sal) 
    from emp b 
    where b.deptno = a.deptno
)
```

