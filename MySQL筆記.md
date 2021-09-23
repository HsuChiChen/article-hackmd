# MySQL筆記
###### tags: `code` `database`
###### 撰寫時間 : 2021/09/20 - 09/21

## 教學影片
- [MySQL_基础+高级篇- 数据库 -sql -mysql教程_mysql视频_mysql入门_尚硅谷](https://www.bilibili.com/video/BV12b411K7Zu?p=1)
- [SQL Tutorial - Full Database Course for Beginners](https://www.youtube.com/watch?v=HXV3zeQKqGY)
- [W3Schools SQL Tutorial](https://www.w3schools.com/sql/default.asp)
- [【資料庫】SQL 3小時初學者教學](https://www.youtube.com/watch?v=gvRXjsrpCHw)

## 下載後配置
1. 關閉自動開機後自動啟動，減少資源
![](https://i.imgur.com/HtNcfGg.png)

2. 配置環境變數`mysql.exe`在`C:\Program Files\MySQL\MySQL Server 8.0\bin`
![](https://i.imgur.com/d2PnuQ0.png)


## 命令行開啟程式
1. 在`cmd`鍵入，開啟程式
```
net start mysql80(視名稱而定)
```
關閉則為`net start mysql80`

2. 開啟數據庫服務主機
```
mysql -h localhost -P 3306 -u root -p
```
`-h` host(數據庫服務主機) `-P` port(端口號) `-u` user(用戶)

## 表格與鍵值
|代碼|功能|
|:-|:-:|
|`primary key`|設定這個屬性可以區分每一筆資料|
|`foreign key`|可以對應到自己或是其他表格的`primary key`|

## 創建資料庫與表格
- `SQL`語法規範
    - 不區分大小寫，但建議關鍵字大寫、表名列名小寫
    - 命令結束用`;`隔開
    - 表名列名習慣上用\`\`避免被判定為關鍵字

|代碼|功能|
|:-|:-:|
|`show databases;`|查看當前數據庫|
|`use {database_name};`|打開指定的數據庫|
|`show tables;`|顯示表單訊息|
|`show tables {other_database_name};`|查看其他數據庫|
|`select database();`|顯示當前數據庫|
|`create table {table_name}`<br> `name1 type1`, <br>`name2 type2);`|創建表|
|`drop database {database_name}`|刪除資料庫|
|`select version();`|登入mysql時查看版本|
|`mysql --version`<br>`mysql -V`|非登入mysql時查看版本|
|`#單行註釋`、`-- 單行註釋`、`/*多行註釋*/`|註釋|

## 數據類型
|型態|解釋|
|:-|:-:|
|`INT`|整數|
|`DECIMAL(m, n)`|浮點數(m位數，小數點占n位)|
|`VARCHAR(m)`|最多能存放m個字元|
|`BLOB`|Binary Large Object，存放二進制的資料，影片、圖片...|
|`DATE`|日期，'YYYY-MM-DD'|
|`TIMESTAMP`|時間，'YYYY-MM-DD HH:MM:SS'|

## 新增資料
|代碼|功能|
|:-|:-:|
|`insert into {table_name} values(value1, value2)`|插入資料|
|`insert into {table_name} ({name1}. {name2})values(value1, value2)`|自定義順序插入資料|

## 約束(constraints)

|代碼|功能|
|:-|:-:|
|`not null`|不可空白|
|`unique`|不可重複|
|`dafault {name}`|默認值|
|`auto_increment`|每加一筆數據時自動累加1|

## 修改與刪除
- 先把預更新模式關閉`set sql_safe_updates = 0;`
- 修改
```sql
update `student`
set `name` = "stella", `major` = "english"
where `student_id` = 2 OR `student_id` = 3;
```
變動表格，當id是2或3時，把該row的`name`更新為"sella"、`major`更新為"english"。
- 刪除
```sql
delete from `student`
where `score` < 60;
```
成績低於60分刪除資料。`>`大於、`<`小於、`=`等於、`<>`不等於。

## 取得資料
|代碼|功能|
|:-|:-:|
|`select * from {table_name}`|回傳表格所有資料|
|`select {name1}, {name2} from {table_name}`|回傳符合該屬性的資料|

- 後面再加上參數

|代碼|功能|
|:-|:-:|
|`order by {name1}, {name1} asc`|預設由低到高排序|
|`order by {name} desc`|由高到低排序|
|`limit 3`|回傳前3筆資料|
|`where {name1} <> 60`|回傳不等於60分資料|
|`where in({name1}, {name2}, {name3})`|等於三筆`OR`的條件|

## 公司資料案例
### 創建
![](https://i.imgur.com/ZlxzwpB.png)
```sql
-- 創建員工資料庫表格
create table `employee`(
	`emp_id` int primary key,
    `name` varchar(20),
    `birth_date` date,
    `sex` varchar(1),
    `salary` int,
    `branch_id` int,
    `sub_id` int
);

create table `branch`(
	`branch_id` int primary key,
    `branch_name` varchar(20),
    `manager_id` int,
    foreign key (`manager_id`) references `employee`(`emp_id`) on delete set null
);
-- 當參照的數被刪掉，就設為NULL

alter table `employee` add foreign key(`branch_id`) references `branch`(`branch_id`)  on delete set null;
alter table `employee` add foreign key(`sub_id`) references `employee`(`emp_id`)  on delete set null;

create table `client`(
	`client_id` int primary key,
	`client_name` varchar(20),
    `phone` varchar(20)
);

create table `works_with`(
	`emp_id` int,
    `client_id` int,
    `total_sales` int,
    primary key(`emp_id`, `client_id`),
    foreign key(`emp_id`) references `employee`(`emp_id`) on delete cascade,
    -- 當參照的數被刪掉，就把該筆資料刪掉
    foreign key(`client_id`) references`client`(`client_id`) on delete cascade
);
```

### 新增
```sql
-- 新增資料
INSERT INTO `branch` VALUES(1, '研發', NULL);
INSERT INTO `branch` VALUES(2, '行政', NULL);
INSERT INTO `branch` VALUES(3, '資訊', NULL);

INSERT INTO `employee` VALUES(206, '小黃', '1998-10-08', 'F', 50000, 1, NULL);
INSERT INTO `employee` VALUES(207, '小綠', '1985-09-16', 'M', 29000, 2, 206);
INSERT INTO `employee` VALUES(208, '小黑', '2000-12-19', 'M', 35000, 3, 206);
INSERT INTO `employee` VALUES(209, '小白', '1997-01-22', 'F', 39000, 3, 207);
INSERT INTO `employee` VALUES(210, '小蘭', '1925-11-10', 'F', 84000, 1, 207);

UPDATE `branch`
SET `manager_id` = 206
WHERE `branch_id` = 1;

UPDATE `branch`
SET `manager_id` = 207
WHERE `branch_id` = 2;

UPDATE `branch`
SET `manager_id` = 208
WHERE `branch_id` = 3;

INSERT INTO `client` VALUES(400, '阿狗', '254354335');
INSERT INTO `client` VALUES(401, '阿貓', '25633899');
INSERT INTO `client` VALUES(402, '旺來', '45354345');
INSERT INTO `client` VALUES(403, '露西', '54354365');
INSERT INTO `client` VALUES(404, '艾瑞克', '18783783');

INSERT INTO `works_with` VALUES(206, 400, 70000);
INSERT INTO `works_with` VALUES(207, 401, 24000);
INSERT INTO `works_with` VALUES(208, 402, 9800);
INSERT INTO `works_with` VALUES(208, 403, 24000);
INSERT INTO `works_with` VALUES(210, 404, 87940);
```

### 取得
```sql
-- 薪水前3高的資料
select * from `employee` order by `salary` desc limit  3;

-- 不重複的部門id
select distinct `branch_id` from `employee`;
```

### 聚合函數(aggregate function)
```sql
-- 取得有幾個不為空的sub_id
select count(`sub_id`) from `employee`;

-- 1970後的女性員工個數
select count(*) from `employee` 
where `birth_date` > "1970-01-01" and `sex` = "F";

select avg(`salary`) from `employee`; -- 平均
select sum(`salary`) from `employee`; -- 總和
select max(`salary`) from `employee`; -- 最高
select min(`salary`) from `employee`; -- 最低
```

### 萬用字元(wildcards)
```sql
-- 取得電話結尾是354的客戶
select * from `client` where `phone` like "%354";
-- %代表0到多個字符

-- 取得12月份的員工
select * from `employee` where `birth_date` like "_____12%";
-- _代表單個字符
```

| Symbol |                      Description                      |                 Example                 |
|:------:|:-----------------------------------------------------:|:---------------------------------------:|
|    %   |          Represents   zero or more characters         |  bl% finds   bl, black, blue, and blob  |
|    _   |             Represents a single character             |       h_t finds hot, hat, and hit       |
|   []   | Represents   any single character within the brackets | h[oa]t   finds hot and hat, but not hit |
|    ^   |      Represents any character not in the brackets     |  h[^oa]t finds hit, but not hot and hat |
|    -   |           Represents a   range of characters          |       c[a-b]t finds   cat and cbt       |

### 聯集(union)
- 員工id、名字 union 客戶id、名字，並重新命名表格
```sql
select `emp_id` as `totoal_id`, `name` as `total_name`
from `employee`
union
select `client_id`, `client_name`
from `client`;
```

### 交集(join)
- 合併表格
```sql
select `emp_id`, `name`, `branch_name`
from `employee` left join `branch` 
-- 加上左邊不管條件有無成立，都會回傳表格資料；右邊則一樣條件成立才會回傳表格
on `employee`.`emp_id` = `branch`.`manager_id`;
```

### 子查詢(subquery)
- 研發部門經理的名字
```sql
select `name`
from `employee`
where `emp_id` = ( -- 嵌套另一個查詢
    select `manager_id`
    from `branch`
    where `branch_name` = "研發"
);
```
- 找出對單一客戶銷售金額超過50000的員工姓名
```sql
select `name`
from `employee`
where `emp_id` in(
	select `emp_id` 
	from `works_with`
	where `total_sales` > 50000
);
```

## python連線MySQL

- 下載模組
```
python -m pip install mysql-connector
```

- 創建表格
```python
import mysql.connector

connection = mysql.connector.connect(host='localhost',
                                    port='3306',
                                    user='root',
                                    password='passworld')

cursor = connection.cursor(buffered=True)
# 創建資料庫
#cursor.execute("CREATE DATABASE `hello_db`;")


# 取得所有資料庫名稱
cursor.execute("SHOW DATABASES;")
records = cursor.fetchall()
for r in records:
    print(r)


# 選擇資料庫
cursor.execute("USE `hello`;")


# 創建表格
# cursor.execute('CREATE TABLE `qq`(qq INT);')

cursor.close()
connection.close()
```

- 取得資料
```python
import mysql.connector

connection = mysql.connector.connect(host='localhost',
                                    port='3306',
                                    user='root',
                                    password='password',
                                    database='hello')

cursor = connection.cursor(buffered=True)

# 取的部門表格所有資料
cursor.execute('SELECT * FROM `branch`;')

records = cursor.fetchall()
for r in records:
    print(r)

cursor.close()
connection.close()
```

- 更新表格
```python
import mysql.connector

connection = mysql.connector.connect(host='localhost',
                                    port='3306',
                                    user='root',
                                    password='password',
                                    database='hello')

cursor = connection.cursor(buffered=True)

# 新增
# cursor.execute("INSERT INTO `branch` VALUES(10, 'qq', NULL)")


# 修改
# cursor.execute('UPDATE `branch` SET `manager_id` = 206 WHERE `branch_id` = 4;')


# 刪除
cursor.execute("DELETE FROM `branch` WHERE `branch_id` = 5;")


cursor.close()
connection.commit()
connection.close()
```
- `commit()`意義<br>
`MySQLConnection.commit()` method sends a COMMIT statement to the MySQL server, committing the current transaction. After the successful execution of a query make changes persistent into a database using the commit() of a connection class.
![](https://i.imgur.com/Zw8dAeE.jpg)
<br><br>
ref : [Use Commit and Rollback to Manage MySQL Transactions in Python](https://pynative.com/python-mysql-transaction-management-using-commit-rollback/)