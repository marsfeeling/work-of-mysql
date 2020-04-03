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
  
  ##### 执行结果
   
   ####  (3)在指定位置增加字段
   ```sql
   ALTER TABLE t_dept1 
	 	    ADD Bname VARCHAR(10)
		       	AFTER dname; # 在指定字段位置dname后增加字段
   ```
  
   ##### 执行结果
   
   #### （4）删除字段
   ```sql
   ALTER TABLE t_dept1
            DROP Bname;
 ```
 
 ##### 执行结果
 
 ### 6.修改字段
 
 #### （1）修改字段数据类型
 ```sql
 ALTER TABLE t_dept1 
		MODIFY Tel INT;
  ```
  
  ##### 执行结果
  
  
  #### （2）同时修改字段名字和数据类型
```sql
ALTER TABLE t_dept1 
		CHANGE dname Dname VARCHAR(10);
 ```
 
 ##### 执行结果
 
 
 #### （3）修改字段顺序
```sql
ALTER TABLE t_dept1 
		MODIFY  deptno INT(11) AFTER loc;
```

##### 执行结果


## 四.操作表的约束
```sql
deptno INT NOT NULL,  # 非空约束
	dname VARCHAR(20) DEFAULT 'Petter', 
	cname VARCHAR(20) UNIQUE,	#唯一性约束
	loc VARCHAR(40)， 
	number INT PRIMARY KEY AUTO_INCREMENT	#设置字段自动增加
	); 
 ```
 
 ### 执行结果
 
 
 
 ## 五.数据的操作
### 1.插入数据记录
```sql
INSERT INTO t_dept_1( deptno,dname,loc)
		values(10,'Xiaotong','Chongqing');
	INSERT INTO t_dept_1(deptno,Dname,loc)
		values(20,'Xiaotan','Chongqing');
```
#### 执行结果


### 2.同时插入多条数据记录
```sql
INSERT INTO t_dept_1( deptno,dname,loc)
values(10,'Xiaoyang','Chongqing'),
          (20,'Xiaomei','Hangzhou'),
          (10,'Xiaoxin','Chengdu');
```

#### 执行结果

### 3.将一个表的记录插入另一个表中
```sql
create table t_dept_2 (
    deptno INT,
	dname  VARCHAR(20),
	loc    VARCHAR(40)
);
INSERT INTO t_dept_2( deptno,dname,loc)
values(20,'Yanyang','Chongqing'),
          (20,'Xiye','Hangzhou');
INSERT INTO t_dept_1(deptno,dname,loc)
SELECT deptno,dname,loc		
 FROM t_dept_2;
SELECT * FROM t_dept_1;
```

#### 执行结果





