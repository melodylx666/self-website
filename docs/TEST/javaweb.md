# javaweb

## 考试范围

1-6章，10章

## 第1章 网页开发基础

### HTML

例子：

```apache
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>here for title</title>
</head>
<body>

</body>
</html>
```

1. 定义：超文本标记语言
2. 后缀名: html或者htm
3. 元素：
   1. doctype: 一条指令，用于向浏览器说明html文件使用哪种HTML规范
   2. html标签: 根标签
   3. head标签: 头部标签
   4. body标签：主体标签
4. 标签类型
   1. 单标签：<标签名 />。 不需要选择的时候就直接使用单标签进行描述
   2. 双标签： <标签名> </ 标签名>
   3. 注释标签 <!-- 注释语句 -->
5. 常见的HTML标签
   1. 段落，行内，换行标签
   2. 文本样式标签
   3. 表格标签
   4. 表单标签：网页上允许输入信息的区域

      1. 表单域：action=url, method=post/get,name="xxx"
      2. 表单:
         1. 使用**input**单标签
         2. 文本：text; 单选ratio; 多选：checkbox; 文件上传：file; 提交: submit；重置： reset
   5. 多文本标签：textarea cols= rows=
   6. 列表标签：

      1. 无序列表：ul + li
      2. 有序列表：ol + li
   7. 超链接标签
   8. 图像标签

### CSS

1. 定义：层叠样式表
2. 引用方式：
   1. 行内式(内联式)：标签 + style
   2. 内嵌式：将css代码集中写在head部分，并用style标签定义
   3. 外链式：**常用**，将css文件的链接标签(link)写在head标签中。需要定义：href，type，relation
   4. 导入式：了解即可
3. 选择器和常用属性
   1. 类型：范围从大到小
      1. 通配符选择器：能匹配所有元素
      2. 标签选择器：通过标签名称来选择
      3. 类选择器：通过标签的class属性选择，可以不唯一
      4. id选择器：唯一标识某个标签

### JS

1. 定义：一种脚本语言，不需要进行编译，直接嵌入HTML页面中，把静态的页面转换为和用户交互的动态效果页面
2. 组成
   1. ES：语法标准
   2. DOM：文档对象模型，可对页面的各种元素交互
   3. BOM：浏览器对象模型，可以通过BOM对浏览器进行交互
3. 引入方式
   1. 行内式：比如在input控件中引入
   2. 内嵌式：通过script标签
   3. 外链式：同样通过script标签 + src 标签部分引入JS文件
4. 数据类型
   1. Number
   2. String
   3. Boolean
   4. Object
   5. Null
   6. Undefined：指变量被创建，但是没有被赋值的时候所拥有的值
5. 变量：用var声明
6. DOM
   1. 例如一个HTML文件可以做出一个DOM树(P22)
   2. head和body是两个分支
7. BOM
   1. 组成
      1. Document
      2. Location
      3. Navigator
      4. Screen
      5. History
   2. 核心是Window，其他是Window的子对象

## 第二章 JAVA WEB概述

### XML

1. 定义：可扩展标记语言
2. 与HTML区别
   1. HTML用于显示数据，XML用于传输数据
   2. HTML不区分大小写，XML区分大小写
   3. XML不会过滤空格
   4. XML可以扩展标签
3. 语法
   1. 文档声明：version,encoding,standlone,其中version是强制性声明。standlone默认值是no
   2. 元素定义：使用标签定义，树形结构。只有一个顶层元素，为**根元素**或者文档元素
   3. 属性定义：同样使用标签定义
   4. 注释
4. DTD约束
   1. 定义：对XML语法进行约束
   2. 内容：可以包含元素的定义，元素之间的关系，元素属性的定义，以及实体符号之间的关系
   3. 引入DTD约束：
      1. SYSTEM
      2. PUBLIC 公司 + 版本 + 语言
   4. 语法
      1. #PCDATA：表示元素使普通文本字符串
      2. 子元素
      3. 混合内容：包含子元素，也包含字符串
      4. EMPTY：空元素
      5. ANY
   5. 属性定义
      1. 这里是为元素定义属性
      2. 设置说明
         1. REQUIRED:必须的
         2. IMPLIED:可以包含可以1不包含
         3. FIXED：固定的默认值
         4. 默认值
      3. 属性类型
         1. **CDATA**：和#PCDATA一样，都是文本字符串
         2. Enumbered:枚举类型
         3. ID：唯一标识某个元素
         4. IDREF 和IDREFS：元素 + 联系
   6. schema约束
      1. 后缀：xsd约束
      2. 名称空间：元素名 xmlns：prefixname="URL"
      3. 作用：**将某一个前缀绑定到某个URL上，然后将该前缀添加到元素名称前面，说明该元素属于哪个模式文档**

### 程序开发体系结构

1. 体系结构
   1. C/S模式：直接客户端到数据库
   2. B/S模式：浏览器 +WEB浏览器 + 数据库服务器。全面取代了C/S模式
2. Tomcat
   1. 安装：在另一个idea中进行的创建

## 第三章 HTTP协议

### 内容

1. 定义：超文本传输协议
2. 特点
   1. 支持C/S模式
   2. 简单快速
   3. 灵活
   4. **无状态**
3. HTTP1.1对HTTP1.0的改进：HTTP1.1的支持持久连接，减少了建立和关闭连接的耗时
4. 请求消息
   1. 请求行
      1. 格式：GET /index.html HTTP1.1
      2. 请求方式 资源路径 使用的HTTP版本
      3. 只有一种使用post，就是**提交表单**的时候，其余都使用get（比如超链接）
   2. 请求头
      1. k-v对形式
      2. 常见请求头
         1. Accept
         2. Accpet-Encoding：是**压缩方式**。用于指定**客户端能够解码的数据编码方式** .有gzip和compress方式
         3. HOST：用于指定资源所在的路径和端口号
         4. If-Modifed-Since：与本地缓存有关，如果没有缓存则返回304状态码
         5. Referer：浏览器对服务器发起请求，对于单机超链接的情况会有Referer，可以用于区别不同访问方式，制作防盗链。
         6. User-Agent：有Mozilla系列
   3. 消息实体
5. 相应消息
   1. 响应行
      1. 格式：HTTP1.1 200 OK
      2. 版本号 状态码 描述
      3. 常见状态码
         1. 1xx：请求已经接受，可继续处理
         2. 2xx: 请求已被服务器成功接收，理解
         3. 3xx: 为完成请求，客户端需要进一步细化请求。比如**302，请求重定向**
         4. 4xx: 客户端的请求有错误，比如**404，服务器找不到资源**
         5. 5xx：服务器出现错误，比**500，服务器发生错误**
   2. 响应头：
      1. k-v格式
      2. 常见相应头
         1. Location：通知客户端请求文档的新地址，多配合**3xx**状态码使用。不能同时出现Location和Content-Type两个字段
         2. Server：指定服务器软件产品
         3. Refresh：页面刷新，可以刷新到新的地址： refresh ; 3 ; url=
         4. Content-Disposition: 没有在HTTP的标准规范中定义，让用户选择把响应实体保存到一个文件中
         5. COntent-Encoding：相应消息的压缩方式
   3. 相应消息体

## 第四章 Servlet

见代码

## 第五章 会话与会话技术

1. 会话技术
   1. 定义：浏览器和服务器进行一系列请求和响应的过程
   2. 类别：Cookie和Session
2. Cookie对象
   1. **只有它是用户new的**
   2. 定义：类似会员卡，当用户访问服务器的时候，服务器给客户发送的一些信息，都保存到Cookie中。当浏览器再次使用Cookie访问服务器的时候，可以作出正确的相应。也就是服务器给浏览器打标，然后浏览器访问每次都需要带上这个标签
   3. 方式：**服务器设置，浏览器保存**
   4. 方法
      1. 构造方法，只有一个，名称不能修改，值可以
3. Session对象
   1. 定义：将数据保存到服务器，每次用户登录，使用cookie存储id，则可以判断是哪个session的范围
   2. 4个域对象的大小：从小到大
      1. pageContext(JSP)
      2. HttpServletRequest
      3. HttpSession
      4. ServletContext
   3. 生命周期
      1. 生效：第一次访问JSP页面的时候生效
      2. 失效
         1. 超时。如果在web.xml中设置为0或者负数，就代表永不超时，默认30分钟
         2. invalidate
         3. 关闭浏览器
   4. 编码
4. 实例：购书示例
   一共使用三个Servlet，第一个listBookServlet用于和数据库交互，获取数据，并通过点击超链接转到第二个PurchaseServlet(
   用于对session的存储的k-v进行更新)。最后转到BookServlet，用于对购物车数据进行展示。

```apache

//第1个
@WebServlet(name = "listBookServlet", value = "/listBookServlet")
public class ListBookServlet extends HttpServlet {
    private static final long serialVersionUID = 1L;

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        resp.setContentType("text/html;charset=UTF-8");
        PrintWriter writer = resp.getWriter();
        Collection<Book> books = BookDB.getAll();
        writer.println("books are");
        books.forEach(book -> {
            String url = "purchaseServlet?id=" + book.getId();
            writer.write(book.getName() + "<a href='" + url
                    + "'>get it</a><br>");
        });

    }
    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        doGet(req, resp);
    }
}

//第2个
@WebServlet(name = "purchaseServlet", value = "/purchaseServlet")
public class PurchaseServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        String id = req.getParameter("id");
        if(id == null){
            String url = "/listBookServlet";
            resp.sendRedirect(url);
            return;
        }
        Book book = BookDB.getBook(id);
        HttpSession session = req.getSession();
        List<Book> cart = (List<Book>) session.getAttribute("cart");
        if(cart == null){
            cart = new ArrayList<>();
            session.setAttribute("cart", cart);
        }
        cart.add(book);
        Cookie cookie = new Cookie("JSESSEIONID", session.getId());
        cookie.setMaxAge(60*30);
        cookie.setPath("/");
        resp.addCookie(cookie);

        String url = "bookServlet";
        resp.sendRedirect(url);
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        doGet(req, resp);
    }
}

//第3个
@WebServlet(name = "bookServlet", urlPatterns= "/bookServlet")
public class BookServlet extends HttpServlet {
    public BookServlet() {
        super();
    }

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        resp.setContentType("text/html;charset=UTF-8");
        final PrintWriter writer = resp.getWriter();
        HttpSession session = req.getSession(false);
        var flag = true;
        List<Book> cart = null;
        if(session == null){
            flag = false;
        }else{
            cart = (List<Book>) session.getAttribute("cart");
            if(cart == null){
                flag = false;
            }
        }

        if(!flag){
            writer.println("cart is empty");
        }else{
            cart.forEach(book -> {
                writer.write(book.getName() + "<br>");
            });
        }
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        doGet(req, resp);
    }
}

```

## 第六章 JSP技术

1. JSP
   1.定义：是Servlet更高级别的扩展，在JSP文件中，HTML代码和Java代码共同存在，其中HTML代码用于实现网页的静态功能，而Java代码实现动态内容的展示。最终，JSP文件会在Web服务器上的Web容器中编译成为Servlet
   1. 特点
      1. 跨平台
      2. 业务代码分离
      3. 组件重用
      4. 预编译
   2. 使用：在web文件夹下和创建html一样，创建jsp文件并使用
2. JSP运行原理
   1. 基于请求，响应模式
   2. 过程
      1. 首先，客户端发送请求文件，请求访问JSP文件
      2. JSP将JSP文件转换为Java源文件(Servlet源程序)
      3. JSP容器将Java源文件编译为字节码文件
      4. Servlet容器将该文件加载，创建Servlet实例(**常驻内存**)，并执行**jspInit**方法完成初始化(执行一次)
      5. JSP容器执行**jspService**方法来处理客户端请求，对每个请求，创建一个线程来处理它
      6. 处理完成，响应对象由JSP容器接受，将HTML格式的静态页面发送给客户端
   3. JSP脚本元素
      1. 定义：指嵌套进入的Java代码
      2. 分类
         1. JSP Scriptlets：<% %>，用于使用简单的语句，相当于方法内定义的局部变量
         2. 声明标识:<%！ %>,多了个冒号。用于定义整个页面需要的东西，比如成员变量，方法等。在当前界面有效。可以在head部分声明
         3. JSP表达式：<%= expression %>,，用于向页面输出信息
3. JSP指令
   1. page指令：<%@ page k1=v1,k2=v2 >
   2. include指令，用于包含另一个元素
4. JSP动作元素
   1. 定义：用于控制JSP动作的行为，执行一些JSP作用
   2. 元素
      1. 包含文件元素,jsp:include page=可以引入动态文件(比如可以是jsp)或者是静态文件，flush默认值是false
      2. 请求转发元素，jsp:forward page=
   3. 两种include的区别
      1. include指令通过file属性指定文件，file属性支持任何表达式，后者使用page指令，支持表达式
      2. 使用前者，会编译成一个字节码文件。后者会分别编译成多个
      3. 前者变量不能重复，后者可以
5. 隐式对象
   1. out：带缓存的PrintWriter
   2. request/response
   3. config
   4. session
   5. application
   6. page
   7. pageContext:4个作用范围：**page,request,session,application**
   8. exception:可以指定错误处理的jsp位置


## 大题 JDBC+Servlet+JSP

### 1.封装Connection工具类

这里省略

### 2.创建UserBean

对应字段进行封装的bean对象

### 3.创建login.jsp

```apache
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>login</title>
</head>
<body>
<form action="LoginServlet" method="post" name="loginForm">
    用户名:<input name="username" type="text" id="username" style="width: 200px"/><br><br>
    密码:<input name="password" type="password" id="password" style="width: 200px"/><br><br>
    input:<input type="submit" name="submit" value="登录">
</form>
</body>
</html>
```

### 4. 创建LoginServlet

```apache
/**
 * ClassName: LoginServlet
 * Package: org.example.userlogin
 * Description:
 *
 * @author lx
 * @version 1.0
 */
@WebServlet(name = "LoginServlet", urlPatterns = "/LoginServlet")
public class LoginServlet extends HttpServlet {

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        req.setCharacterEncoding("UTF-8");
        resp.setCharacterEncoding("UTF-8");
        resp.setContentType("text/html;charset=utf-8");
        PrintWriter out = resp.getWriter();
        String username = req.getParameter("username");
        String password = req.getParameter("password");
        if(userDao.checkuser(username, password)){
            out.println("success");
        }else{
            out.println("failure");
        }
    }
    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        doGet(req, resp);
    }
}
```

### 5. DAO层封装从表到bean对象的逻辑(ORM)

```apache
/**
 * ClassName: userDao
 * Package: org.example.userlogin.DAO
 * Description:
 *
 * @author lx
 * @version 1.0
 */
public class userDao {
    public static boolean checkuser(String username, String password){
        Connection conn = getConnection();
        if(conn==null){
            return false;
        }
        var sql = "select `passward` from userin.tb_user where username=" + "'" + username + "'";
        try(var statement = conn.createStatement()){
            ResultSet resultSet = statement.executeQuery(sql);
            while(resultSet.next()){
                String pwd = resultSet.getString("passward");
                if(pwd.equals(password)){
                    return true;
                }
            }
        }catch(Exception e){
            e.printStackTrace();
        }
        return false;
    }
}
```
