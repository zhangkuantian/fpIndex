# fpIndex

<p> 函数式编程基于一个简单而又蕴含深远的前提：只用纯函数来构造程序——换句话说，函数没有副作用。
<p> 带有副作用的函数：不仅只是简单地返回一个值，还干了一些其他的事情，比如：
<p> 1、修改一个变量
<p> 2、直接修改数据结构
<p> 3、设置一个对象的成员
<p> 4、抛出一个异常或者以一个错误停止
<p> 5、打印到终端或者读取用户的输入
<p> 6、读取或者写入一个文件
<p> 7、在屏幕上绘画

#函数也是值
<p>在scala中，函数也是值，就像其他类型的值，比如整型、字符串、列表；函数也可以赋值给一个变量、存储在一个数据结构里、像参数一样传递给另一个函数；
<p>把一个函数当作参数传递给另一个函数在纯函数式编程里很有作用，它被称为高阶函数

#例子：
<p>写一个递归函数，来获取第n个斐波那契数，前两个斐波那契数为0和1，第n个数总是等于它的前两个数之和——序列开始为0、1、1、2、3、5
<p>
package com.tianfei.collect

object ArrayUtils{
  
  def main(args:Array[String]):Unit = {
    
    val getMsg = (msg:String, time:Int) =>{
      for( i <- 0 until time){
        println("Receive Message: " + msg + " times: " + (i+1))
      }
    }
    
    getMsg("ERROR MSG ! ", 10)
    
    for(i <- 0 until 10){
      print(fib(i) + " ")
    }
    
    
  }
  
  private def fib(n:Int):Int = {
  
    if(0 == n )
      0 
    else if(1 == n)
      1
    else
      fib(n-1) + fib(n-2)
  }
  
}

#Scala多态函数
<p>通常，特别是在写高阶函数的时候，希望写出的这段代码能够适用于任何类型，他们被称为“多态函数”。
<p>例如在数组中查找元素的多态函数如下：

def p\[A,B\](str:A):Boolean = {
    str.equals(80)
  }
  
  
  def findFirst\[A,B\](ss:Array\[A\], p:A=>Boolean):Int ={
    
    def loop(n:Int):Int = {
      if(n>= ss.length) -1
      else if(p(ss(n))) n
      else loop(n + 1)
    }
    
    loop(0)
  }









