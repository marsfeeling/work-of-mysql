## 需要用jion写的两个query
```sql
select * from t_employee2 WHERE sal > (
select sal from t_employee2 WHERE ename='SMITH');

select * from t_employee2 WHERE (sal, job) = (
select sal,job from t_employee2 where ename = 'smith');
```




### 1.第一个query用join写（第一个query据我分析就是选出工资比名叫SMITH的员工更高的员工的表格）
#### 代码
```sql
select t1.deptno,t1.empno,t1.ename,t1.job,t1.MGR,t1.Hiredate,t1.sal,t1.comm           
from t_employee2 t1 inner join t_employee2 t2 
on t1.sal>t2.sal and (t2.ename='SMITH');
```

##### 执行结果与原query对比
![](https://github.com/ty0816/work/blob/master/images/%E7%AC%AC%E4%B8%80%E4%B8%AAquery.png)


### 2.第二个query用join写（第二个query再据我分析就是选出工资和工作与名叫SMITH的员工的表格）
#### 代码
```sql
select t1.deptno,t1.empno,t1.ename,t1.job,t1.MGR,t1.Hiredate,t1.sal,t1.comm          
from t_employee2 t1 inner join t_employee2 t2 
on (t1.sal = t2.sal and (t2.ename='SMITH')) AND (t1.job = t2.job and (t2.ename='SMITH'));
```

##### 执行结果与原query对比
![](










