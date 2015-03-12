JS 快速入门
===========

JavaScript（简称 JS） 脚本由 JS 语句构成。
处于 HTML 标记 ``<scipt> ... </scipt>`` 之间。
可以把 ``<scipt> ... </scipt>`` 放在任意位置，但是最好放在 <head> 标记范围内。

<script> 有两个重要属性：

* language
* type
  
language 指明脚本使用的语言。
一般其值为 `Javascript`。
type 表示推荐使用的脚本语言，必须为 `text/Javascript`。

所以 HTML 中的 JS 片段为：

.. code-block:: html

    <script language="javascript" type="text/javascript"> 
        JavaScript code 
    </script> 

"hello, world"
--------------

.. code-block:: html

    <html> 
    <body> 
    <script language="javascript" type="text/javascript"> 
    <!-- 
        document.write("Hello World!") 
    //--> 
    </script> 
    </body> 
    </html> 

空白符和换行
------------

Javascript 忽略空格，制表符以及换行符。
使用它们只是为了缩进，使代码更易于阅读

分号是可选的
------------

简单语句后面通常有一个分号，就像 C/C++, Java 那样。

.. note::
 每个语句单独一行，可以省略分号，多个语句放在一行，需要分号

.. code-block:: html

    <script language="javascript" type="text/javascript"> 
    <!-- 
        var1 = 10 
        var2 = 20
        var3 = 10; var4 = 20
    //--> 
    </script>

区分大小写
----------

注释
----

支持 ``//`` 和 ``/* */`` 两种风格。

支持 HTML 格式的注释 ``<!--``：

* 独占一行
* 以 ``//-->`` 结束，同样独占一行

JS 代码位置
-----------

推荐位置：

* ``<head> ... </head>``
* ``<body> ... </body>``
* both
* 外部文件，通过指令加载到 ``<head> ... </head>``

数据类型
--------

* Numbers: 80
* Strings: "string"
* Boolean: true or false
  
变量
----

JS 的变量必须先声明，再使用，有点类似于 C/C++， Java 等。
变量的声明使用 **var** 关键字。

变量的作用域
------------

* 全局变量
* 局部变量
  
定义在函数外的变量是全局变量；定义在函数中的变量是局部变量。

变量名
------

* 不可以使用保留关键字
* 由字母，数字，下划线等构成，只能以字母、下划线开头。
* 大小写敏感

保留关键字：

.. image:: images/reserved_keywords.png

运算符
------

``+, -, * , /, %, ++, --, ==, !=, >, <, >=, <=, &&, ||, !, &, |, ^,	~, <<, >>, >>>,
=, +=, -=, *=, /=, %=, ?:, typeof``

.. note:: >>> 逻辑右移， typeof 值为 **{"number", "string", "boolean"}** 之一

if, switch ,for, while
----------------------

用法和 C/C++ 一样。


for ... in
----------

for (varName in object)
{
	
}

break, continue
---------------

用法请参考 C/C++。

函数定义
--------

使用函数之前先要定义它。
函数格式：函数关键字， 函数名， 参数列表（空），以及大括号包围的语句模块。
例如：

.. code-block:: html

    <script type="text/javascript">  
    <!-- 
        function functionname(parameter-list) 
        { 
            statements 
        } 
    //--> 
    </script>

函数调用
--------

函数调用语句和 C 语言一样，通过函数名和实参列表实现。

.. note:: 函数定义和函数调用的位置顺序可以任意，不像 C，必须在调用前面预先声明 / 定义。

异常处理
--------

.. code-block:: html

    <script type="text/javascript">
    <!--
        try
        {
            statementsToTry
        }
        catch ( e ) 
        {
            catchStatements
        }
        finally
        {
            finallyStatements
        }
    //-->
    </script>

警告对话框
----------

``alert("<warning message>")``

确认对话框
----------

``value = confirm("<option message>")``

生成确认对话框，带有两个按钮 **OK** 和 **Cancel**

value(Boolean):

* true
* false
  
文本输入框
----------

``var input = prompt("<title message>", "<default input string>")``

生成一个文本输入框，有标题栏，有默认输入，以及 **OK** 和 **Cancel** 按钮。
返回输入的字符串或者 null 对象。

网页重定向
----------

在 ``<head>`` 标签中加上：

``window.location="<url>"``

**void**
--------

* 放在操作数前面，表示任意类型
* 放在表达式前面表示没有返回值
  
.. code-block:: html

    void func()
    javascript:void func()
    void (func())
    javascript:void(func())

以上写法等价。

**window.print()**
------------------

调出打印窗口

存储 Cookies
------------

``document.cookie = "key1=value1;key2=value2;expires=date";

读取 Cookies
------------

.. code-block:: html

    <script type="text/javascript"> 
    <!--
    // window.location = "http://www.baidu.com"
    window.cookie = "name=huwz;addr=beijing;";
    document.write(window.cookie);
    </script> 

语法错误或者运行异常
--------------------

