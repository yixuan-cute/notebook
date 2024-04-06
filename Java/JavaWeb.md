# 一、JDBC

&emsp;&emsp;JDBC(Java DataBase Connectivity) 就是使用 Java 语言操作关系型数据库的一套 API。

```java
//0.将驱动 jar 包导入工程

//1.注册驱动（MySQL5 之后，这一句可以不写）
Class.forName(“com.mysql.jdbc.Driver”);//旧版本
Class.forName(“com.mysql.cj.jdbc.Driver”);//新版本

//2.获取连接对象
String url = “jdbc:mysql://127.0.0.1:3306/db_1?useSSL=false”;
String username = “root”;
String password = “1234”;
Connection conn = DriverManager.getConnection(url,username,password);

//3.定义 SQL 语句
String sql = “update account set money = 2000 where id= 1”;

//4.获取 SQL 的执行对象
Statement stmt = conn.createStatement();

//5.执行 SQL 语句
int count = stmt.executeUpdate(sql);

//6.处理结果
......

//7.释放资源（顺序不能变）
stmt.close();
conn.close();
```

JDBC 的本质：

* Sun 公司定义的一套标准（接口），是用于操作所有关系型数据库的规则。
* 各数据库厂商分别去实现这套接口，提供各自数据库的驱动 jar 包。

JDBC 的好处：不同的数据库厂商使用相同的接口。

## 1.DriverManager（驱动管理类）

> 注册驱动

```java
Class.forName(“com.mysql.jdbc.Driver”);

//上面 Driver 的源码
static {
	try{
		DriverManager.registerDriver(new Driver());
	}catch(SQLException var1){
		throw new RuntimeException(“Can’t register diver!”);
	}
}
```

> 获取连接

```java
//getConnection() 函数
Connection DriverManager.getConnection(Sring url,String username,String password);
/*参数
url（连接路径）
	jdbc:mysql://ip地址:端口号/数据库名称？参数键值对1&参数键值对2&...
	①可简化为jdbc:mysq:///数据库名称。
	②配置useSSL=false（等号两侧不能有空格）参数，禁用安全连接方式。
username 用户名
password 密码
*/
```

## 2.Connection

> 获取执行 SQL 的对象

```java
//普通执行 SQL 的对象
Statement createStatement(String sql)

//预编译 SQL 的执行 SQL 对象（防止 SQL 注入）
PreparedStatement prepareStatement(String sql)

//执行存储过程的对象
CallableStatement perpareCall(Sting sql)
```

> 管理事务

```java
//开启事务
setAutoCommit(boolean autoCommit)
/*
	true 为自动提交事务
	false 为手动提交事务，即为开启事务
*/

//提交事务
commit()

//回滚事务
rollback()
```

## 3.Statement

```java
//执行 DML、DDL 语句
int executeUpdate(String sql)
/*
	对于 DML 语句，返回受影响的行数，返回 0 代表执行失败
	对于 DDL 语句，执行成功也可能返回 0
*/

//执行 DQL 语句，返回 ResultSet 结果集对象
ResultSet executeQuery(String sql)
```

## 4.ResultSet

> 封装了 DQL 语句的查询结果

```java
//将光标从当前位置向前移动一行，并判断（移动后的）当前行是否为有效行
boolean next()
/*
	true：有效行
	false：无效行
*/

//获取数据
xxx resultSet.getXxx(参数)
/*
	“get”什么类型，就返回什么类型。
	参数可以是 int 或 String：
		int 时，参数为列的编号，从 1 开始
		String 时，参数为列的名称
*/
```

> ResultSet 的数据结构

![[ResultSet数据结构.png]]

> 一贯用法

```java
while(resultSet.next()){
	result.getXxx(参数);
	......
}
```

## 5.PreparedStatement

&emsp;&emsp;预编译，提高执行效率；转义敏感字符，防止 SQL 注入。

```java
//开启预编译功能
String url = "jdbc:mysql:///atguigudb?useSSL=false&useServerPrepStmts=true";

//获取 PreparedStatement 对象
String sql = “select * from user where usename = ? and password = ?”;
PerparedStatement pstmt = conn.prepareStatement(sql);

//设置参数值
pstmt.getXxx(参数1,参数2);
/*
	Xxx：数据类型
	参数1：?的位置编号，从左向右，从 1 开始
	参数2：?的值
*/

//执行 SQL，不需要再传递 sql 语句
pstmt.executeUpdate();
pstmt.executeQuery();
```

## 6.数据库连接池

# 二、Servlet

# 三、JSP
