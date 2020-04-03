学号：17061902
姓名：童言


## 一.对数据库操作的相关命令
### 1.创建一个新的数据库
```sql
 create database task1;
 ```
 #### 执行结果
  ![](https://github.com/ty0816/work/blob/master/images/create.png)
 
 ### 2.查看和选择数据库
 ```sql
 show databases;
 use task1;
 ```
 
 #### 执行结果
  ![](https://github.com/ty0816/work/blob/master/images/show%20and%20use.png)
 
 ### 3.删除数据库
 ```sql
 drop database task1;
 ```
 
#### 执行结果
 ![](https://github.com/ty0816/work/blob/master/images/%E5%88%A0%E9%99%A4%E6%95%B0%E6%8D%AE%E5%BA%93.png)

## 二.如何查看MySQL数据库中的存储引擎
### 1.查看所支持的存储引擎
```sql
show engines;
```

#### 执行结果
 ![](https://github.com/ty0816/work/blob/master/images/%E6%9F%A5%E7%9C%8B%E6%94%AF%E6%8C%81%E7%9A%84%E5%AD%98%E5%82%A8%E5%BC%95%E6%93%8E.png)

### 2.查看默认的存储引擎
```sql
SHOW VARIABLES LIKE '%storage_engine%';
```

#### 执行结果
![](https://github.com/ty0816/work/blob/master/images/%E6%9F%A5%E7%9C%8B%E9%BB%98%E8%AE%A4%E5%AD%98%E5%82%A8%E5%BC%95%E6%93%8E.png)

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
![](https://github.com/ty0816/work/blob/master/images/%E5%88%9B%E5%BB%BA%E6%96%B0%E7%9A%84%E8%A1%A8%E6%A0%BC.png)

 ### 2.查看表的定义信息
 ```sql
  describe t_dept;
 show create table t_dept;
 ```
 
 #### 执行结果
 ![](https://github.com/ty0816/work/blob/master/images/%E6%9F%A5%E7%9C%8B%E8%A1%A8%E7%9A%84%E5%AE%9A%E4%B9%89%E4%BF%A1%E6%81%AF.png)
 
 
 ### 3.删除表
 ```sql
 drop table t_dept;
 ```
 
 #### 执行结果
 ![](https://github.com/ty0816/work/blob/master/images/%E5%88%A0%E9%99%A4%E8%A1%A8.png)
 
 ### 4.修改表名
 ```sql
  alter table t_dept RENAME t_dept1;
  ```
  
  #### 执行结果
 ![](https://github.com/ty0816/work/blob/master/images/%E4%BF%AE%E6%94%B9%E8%A1%A8%E5%90%8D.png)
 
 ### 5.增加字段和删除字段
 #### （1）在表的最后增加字段
 ```sql
 ALTER TABLE t_dept1
  ADD Tel VARCHAR(20); 
  ```
  
  ##### 执行结果
   ![](https://github.com/ty0816/work/blob/master/images/%E5%9C%A8%E8%A1%A8%E7%9A%84%E6%9C%80%E5%90%8E%E6%B7%BB%E5%8A%A0%E5%AD%97%E6%AE%B5.png)
  
  #### （2）在表的最前面增加字段
  ```sql
   ALTER TABLE t_dept1
    ADD Aname VARCHAR(10) FIRST;
   ```
  
  ##### 执行结果
   ![](https://github.com/ty0816/work/blob/master/images/%E5%9C%A8%E8%A1%A8%E7%9A%84%E6%9C%80%E5%89%8D%E9%9D%A2%E6%B7%BB%E5%8A%A0%E5%AD%97%E6%AE%B5.png)
  
   ####  (3)在指定位置增加字段
   ```sql
   ALTER TABLE t_dept1 
	 	    ADD Bname VARCHAR(10)
		       	AFTER dname; # 在指定字段位置dname后增加字段
   ```
  
   ##### 执行结果
   ![](https://github.com/ty0816/work/blob/master/images/%E5%9C%A8%E8%A1%A8%E4%B8%AD%E6%8C%87%E5%AE%9A%E4%BD%8D%E7%BD%AE%E5%8A%A0%E5%85%A5%E5%AD%97%E6%AE%B5.png)
   
   #### （4）删除字段
   ```sql
   ALTER TABLE t_dept1
            DROP Bname;
 ```
 
 ##### 执行结果
  ![](https://github.com/ty0816/work/blob/master/images/%E5%88%A0%E9%99%A4%E5%AD%97%E6%AE%B5.png)
 
 ### 6.修改字段
 
 #### （1）修改字段数据类型
 ```sql
 ALTER TABLE t_dept1 
		MODIFY Tel INT;
  ```
  
  ##### 执行结果
  ![](https://github.com/ty0816/work/blob/master/images/%E5%90%8C%E6%97%B6%E4%BF%AE%E6%94%B9%E5%AD%97%E6%AE%B5%E5%90%8D%E5%AD%97%E5%92%8C%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B.png)
  
  #### （2）同时修改字段名字和数据类型
```sql
ALTER TABLE t_dept1 
		CHANGE dname Dname VARCHAR(10);
 ```
 
 ##### 执行结果
  ![](https://github.com/ty0816/work/blob/master/images/%E5%90%8C%E6%97%B6%E4%BF%AE%E6%94%B9%E5%AD%97%E6%AE%B5%E5%90%8D%E5%AD%97%E5%92%8C%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B.png)
 
 #### （3）修改字段顺序
```sql
ALTER TABLE t_dept1 
		MODIFY  deptno INT(11) AFTER loc;
```

##### 执行结果
 ![](https://github.com/ty0816/work/blob/master/images/%E4%BF%AE%E6%94%B9%E5%AD%97%E6%AE%B5%E9%A1%BA%E5%BA%8F.png)

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
 ![](https://github.com/ty0816/work/blob/master/images/%E6%93%8D%E4%BD%9C%E8%A1%A8%E7%9A%84%E7%BA%A6%E6%9D%9F.png)
 
 
 ## 五.数据的操作
### 1.插入数据记录
```sql
INSERT INTO t_dept_1( deptno,dname,loc)
		values(10,'Xiaotong','Chongqing');
	INSERT INTO t_dept_1(deptno,Dname,loc)
		values(20,'Xiaotan','Chongqing');
```
#### 执行结果
 ![](https://github.com/ty0816/work/blob/master/images/%E6%8F%92%E5%85%A5%E6%95%B0%E6%8D%AE%E8%AE%B0%E5%BD%95.png)

### 2.同时插入多条数据记录
```sql
INSERT INTO t_dept_1( deptno,dname,loc)
values(10,'Xiaoyang','Chongqing'),
          (20,'Xiaomei','Hangzhou'),
          (10,'Xiaoxin','Chengdu');
```

#### 执行结果
 ![](https://github.com/ty0816/work/blob/master/images/%E5%90%8C%E6%97%B6%E6%8F%92%E5%85%A5%E5%A4%9A%E6%9D%A1%E6%95%B0%E6%8D%AE%E8%AE%B0%E5%BD%95.png)

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
 ![](https://github.com/ty0816/work/blob/master/images/%E5%B0%86%E4%B8%80%E4%B8%AA%E8%A1%A8%E7%9A%84%E8%AE%B0%E5%BD%95%E6%8F%92%E5%85%A5%E5%8F%A6%E4%B8%80%E4%B8%AA%E8%A1%A8.png)




