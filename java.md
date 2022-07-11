### java

#### 1.判断对象是否相等的思路

1.判断是否引用一个对象

2.判断显示变量是否为null

3.判断other 和this是否在同一类

4.如果在子类中语义变化，则用getclass，反之使用instanceof

5.转为同类，比较对象域

#### 2.hashcode

字符串的散列码是通过根据内容导出的，hashcode（）

#### 3.ArrayList

采用类型参数的泛型类

ArrayList <> list=new ArrayList<>()\

数组列表管理内存空间，不够时会自动给你生成更大的空间

enshCapacity（） 可以分配空间

确定数组大小后，trimtosize 存储容量削减到当前尺寸

#### 4.根据字符串创建对象

Class.forname(s).newInstance

#### 5.检查类的结构

getField 获取public域，getMethod 获取方法 getConstructor 获取构造器。可以获取超类的公共成员

#### 6.Tomcat容器

Service：Tomcat 封装的、对外提 供完整的、基于组件的 web 服务， 包含 Connectors、Container 两个 核心组件，以及多个功能组件，各 个 Service 之间是独立的，但是共享 同一 JVM 的资源 ；
Connector：Tomcat 与外部世界的连接器，监听固定端口接收外部请求，传递给 Container，并 将 Container 处理的结果返回给外部；
Container：Catalina，Servlet 容器，内部有多层容器组成，用于管理 Servlet 生命周期，调用 servlet 相关方法。

![img](https://img2018.cnblogs.com/blog/1484390/201903/1484390-20190305164340383-764300376.png)

1.请求被发送到本机端口8080，被在那里侦听的CoyoteHTTP/1.1 Connector获得
2.Connector把请求交给他所在的Service的Engine来处理，并等待Engine的回应
3.Engine获取请求localhost:8080/test/index.jsp,匹配它所有虚拟主机Host
4.Engine匹配到名为localhost的Host（即使匹配不到也把请求交给该host处理，因为该Host被定为Engine默认主机）
5.localhost Host获得请求/test/index.jsp，匹配它所拥有的Context
6.Host匹配到路径为/test的Context（如果匹配不到就把请求交给默认的Context去处理）
7.path="test"的Context获取请求/index.jsp,在他的mapping table中寻找对应的servlet
8.Context匹配到URL PATTERN为*。jsp的servlet,对应与JspServlet类
9.构造HttpServletRequest对象和HttpServletResponse对象，作为参数调用JspServlet的doGet或doPost方法。
10.Context把执行完了之后的HttpServletResponse对象返回给Host
11.Host把HttpServletResponse对象返回给Engine
12.Engine把HttpServletResponse对象返回给Connector
13.Connector把HttpServletResponse对象返回给客户browser



#### 7.递归遍历树返回给前端

1.在entity里构造list子节点

2.for循环遍历列表，找到根节点加入父列表

3.加入时寻找递归遍历，找到最末尾的构造一个list节点

```java
findchirdren（item,list）
for
{
	判断是否为子节点
        追加在父节点后面，进行findchildren
}
//当没有子节点时返回，追加上溯。
返回item
```







