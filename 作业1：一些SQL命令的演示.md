学号：17061902
姓名：童言


## 一.对数据库操作的相关命令
### 1.创建一个新的数据库
```sql
 create database task1;
 ```
 #### 执行结果
 
 
 ### 2.查看和选择数据库
 ```sql
 show databases;
 use task1;
 ```
 
 #### 执行结果
 
 
 ### 3.删除数据库
 ```sql
 drop database task1;
 ```
 
#### 执行结果


## 二.如何查看MySQL数据库中的存储引擎
### 1.查看所支持的存储引擎
```sql
show engines;
```

#### 执行结果

### 2.查看默认的存储引擎
```sql
SHOW VARIABLES LIKE '%storage_engine%';
```

#### 执行结果

## 三.介绍对表操作的相关命令
### 1.在数据库中创建一个新的表
```sql
create table t_dept(
     depton int,
     dname varchar(20),
     loc varchar(40)
    );
 ```
 
 #### 执行结果
 
 ### 2.查看表的定义信息
 ```sql
  describe t_dept;
 show create table t_dept;
 ```
 
 #### 执行结果
 
 ### 3.删除表
 ```sql
 drop table t_dept;
 ```
 
 #### 执行结果
 
 ### 4.修改表名
 ```sql
  alter table t_dept RENAME t_dept1;
  ```
  
  #### 执行结果
 
 
 ### 5.增加字段和删除字段
 #### （1）在表的最后增加字段
 ```sql
 ALTER TABLE t_dept1
  ADD Tel VARCHAR(20); 
  ```
  
  ##### 执行结果
  
  #### （2）在表的最前面增加字段
  ```sql
   ALTER TABLE t_dept1
    ADD Aname VARCHAR(10) FIRST;
   ```
   
   
   ##### 
  
 









