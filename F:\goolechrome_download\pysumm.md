

 # coding=utf-8
 # 如何定义一个函数：

    def function_name ([arguments]):
        "optional documentation string"
        function_suite
    def foo(debug=True):
    	     "determine if in debug mode with default argument"
    	     if debug:
    	        print "In debug mode"
    	    print "done"
     foo(0)

类：
  定义类：

     class ClassName (base_class[es]):
       "option"
        static_member+declaratons
        method_declarations
 所有名字开始和结束都有两个下划线的方法都是特殊方法
    一个类实例被创建时，`__init__()`方法会自动执行，他的目的是执行
    一些搞对象的必要的初始化工作

    class FooClass(object):
        """my very first class: FooClass"""
    version = 0.1  # class (data) attribute    
    def __init__(self, nm='John Doe'):
        """constructor"""
        self.name = nm  # class instance (data) attribute
        print 'Created a class instance for', nm
    def showname(self):
        """display instance attribute and class name"""
        print 'Your name is', self.name
        print 'My name is', self.`__class__.__name__`
    def showver(self):
        """display class(static) attribute"""
        print self.version  # references FooClass.version
    def addMe2Me(self, x):  # does not
        # use 'self'
        """apply + operation to argument"""
        return x + x
在该例子中，我们初始化了一个名为Name的类实例属性或成员，该变量只在类实例中存在，他并不是实际类中的一部分 
  `__init__()`需要一个默认参数
	self:是一个类实例自身的引用
模块
模块是一种组织形式，他将彼此有关系的Python代码阻止道一个个独立的文件当中，模块可以包含可执行代码，函数和类这些东西的组合
导入模块
  

      import module_name 

如何访问一个模块函数或访问一个模块变量可以通过  “.”

    module.function
    import sys
    sys.stdout.write("Hello.world!\n")
    print sys.platform
    print sys.version

raw_input(str) 等待用户输入一个字符串，可用提供一个可选参数
str用作提示信息
open(fn,mode)以mode('r' ,'w')方式打开一个文件名为fn的文件。
range([start],stop,[,step])起始值为start 结束值为stop-1.start
默认值为0，if step默认值为1:

    # for i in range(11):
    #     print i
    # i=0
    # while(i<11):
    #     print i
    #     i=i+1
    # ----
    # i=int(raw_input("please Input :"))
    #
    # if (i>0):
    #     print "正数"
    # elif (i<0):
    #     print "负数"
    # else:
    #     print "0"
    # str1=str(raw_input("Please input a str:"))
    # for  i in ls:
    #     print i
    # i=0

    # while i<str1.count(str1):
    #     print str1[i]
    #     i=i+1
    # print str

count(...)
 |      S.count(sub[, start[, end]]) -> int
 |      
 |      Return the number of non-overlapping occurrences of substring sub in
 |      string S[start:end].  Optional arguments start and end are interpreted
 |      as in slice notation.

    # print str1
    # li = list(str1)
    # for i in li:
    #     print i
    # ---
    # li = [1,3,4,5,3]
    # summ=0
    # aver=0
    # for i in li:
    #     summ=summ+i
    #     aver=float(summ/len(li))
    # print aver
    # ---
    # def num():
    #     num1 = int(raw_input("Please input a number between 1-100:"))
    #     return num1
    # num2=num()
    # if num2 <100 and  num2>1:
    #     print num2
    #     exit (0)
    # else:
    #     while num2>100 or num2<1:
    #         print "error"
    #         num()
    # ---
 带循环和条件判断的用户输入，使用raw_input()函数来提示用户输入一个1和100之间的数，如果用户输入的数满足这个条件，显示成功并退出，否则显示一个错误信息然后再次提示用户输入数值，知道满足条件为止。

    while 1:
    a=int(raw_input(“please input a number:”))
    if 1<=a<=100:
    print”success!”
    break
    else:
    print”input error!plese input again!”
    continue

带文本菜单的程序 写一个带文本菜单的程序，菜单项如下（1）取五个数的和 (2) 取五个
数的平均值....（X）退出。由用户做一个选择，然后执行相应的功能。 当用户选择退出时程序
结束。 这个程序的有用之处在于用户在功能之间切换不需要一遍一遍的重新启 你 动 的脚本。（ 这
对 发 开 人员测试自己的程序也会大有用处)


    si = list()
    summ = 0
    aver = 0
    
    
    def cx():
        str1 = raw_input("please input your wanna:")
        if str1 == "sum":
            si[i] = raw_input(
                "please input your number and end with .:")
            while si[i] == ".":
                break
            summ = summ + si[i]
            print summ
        if str1 == "aver":
            si[i] = raw_input(
                "please input your number and end with .:")
            while si[i] == ".":
                break
            summ = summ + si[i]
            aver = float(summ) / len(si)
            print aver
            
-------------

    print dir()
    ['FooClass', '__builtins__', '__doc__', '__file__', '__init__',
     '__name__', '__package__', 'addMe2Me', 'aver', 'cx', 'showname', 
     'showver', 'si', 'summ', 'version']
python中用下划线作为变量前缀和后缀指定特殊变量。

> _xxx 不用'from  module import *　'导入
> `__xxx__`系统定义名字
> __xxx 类中的私有变量名 一般来说，变量名__xxx被看作是"私有的"，在模块或类外不可以使用.

文档：Python还提供了一个机制：可以通过__doc__特别变量，动态获得文档字符串，
在模块，类，声明，或者函数声明中第一个没有赋值的字符串可以用obj.__doc__来访问。
其中，obj是一个模块，类或函数的名字。

 # import  this
 
模块结构和布局：
(1)起始行
(2)模块文档
(3)模块导入
(4)变量定义
(5)类定义
(6)函数定义
(7)主程序
(1) 起始行
通常只有在类 Unix 环境下才使用起始行，有起始行就能够仅输入脚本名字来执行脚本，无
需直接调用解释器。
(2)模块文档
简要介绍模块的功能及重要全局变量的含义，模块外可通过 module.__doc__ 访问这些内
容。
(3)模块导入
导入当前模块的代码需要的所有模块；每个模块仅导入一次（当前模块被加载时）；函数
内部的模块导入代码不会被执行， 除非该函数正在执行。
(4)变量定义
这里定义的变量为全局变量， 本模块中的所有函数都可直接使用。从好的编程风格角度说，
除非必须，否则就要尽量使用局部变量代替全局变量，如果坚持这样做，你的代码就不但容易
维护，而且还可以提高性能并节省内存。
(5)类定义语句
所有的类都需要在这里定义。当模块被导入时 class 语句会被执行, 类也就会被定义。类
的文档变量是 `class.__doc__`。
(6)函数定义语句
此处定义的函数可以通过 module.function()在外部被访问到，当模块被导入时 def 语句
会被执行， 函数也就都会定义好，函数的文档变量是 `function.__doc__`。
(7) 主程序
无论这个模块是被别的模块导入还是作为脚本直接执行，都会执行这部分代码。通常这里
不会有太多功能性代码，而是根据执行的模式调用不同的函数。

时刻记住：所有的模块都有能力来执行代码，最高级别的python语句(没有缩进的代码行)
在模块导入时就会执行，不管是不是真的需要。
由于这个特性，比较安全的写代码的方式是除了那些真正需要执行的代码行以外，几乎
所有的功能代码都在函数当中。
通常只有主程序模块中有大量的顶级可执行代码，所有其他被导入的模块只应该有很少的
顶级执行代码。

> `__name__`来判断模块是被导入还是被直接执行。 
> 如果是导入：`__name__`的值为该模块的名字 
> 如果模块是被直接执行，`__name__`的值为'`__main__`'
