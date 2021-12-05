# 河南工业大学

# 《JAVA程序设计》实验报告

专业班级： 物联网1902班   学号： 201916070216   姓名： 王源    

**实验单元一**  **Java****基本语法**

**实验一** **JDK****安装、配置及****Java****程序的编译和运行**

实验时间：    2021/9/9      

**【实验目的】**

1、熟悉JDK的安装、配置。

2、学会如何编辑、编译、运行Java程序。

**【实验环境】**

JDK1.8  IntelliJ IDEA

**【实验内容】**

\1. 在自己电脑d盘某目录下创建自己的工作空间及名称为“demo”的项目，并创建名称为ex01的包

\2. 在ex01包中，创建名称为“HelloWorld”的类，并实现输出“Welcome to java world”的功能。

\3. 编写程序，分别定义int、double、char类型数据，并输出它们的值。

\4. 编写程序，计算长宽分别为2.0、3.0的长方形的面积及周长。

\5. 编程找出100——999以内的水仙花数，并输出。（“水仙花数”是指一个3位数，其各位数字立方和等于该数。）

\6. 一个数如果恰好等于它的因子之和，这个数就称为"完数"。例如6=1＋2＋3。编程找出1000以内的所有完数。（选做）

 

 

 

**【详细分析】**

（此项由学生自己完成）

\1.   在自己电脑d盘某目录下创建自己的工作空间及名称为“demo”的项目，并创建名称为ex01的包

找到自己的d盘，在自己的常用代码路径下创建一个工作空间，我的常用代码路径是D:\Users\NingHai，于是我便在此右键鼠标，创建一个文件夹并命名为JavaWorkSpace，随后在IDEA里面打开此工作空间，在其下创建一个demo的项目，并创建了ex01包。

 

\2.  在ex01包中，创建名称为“HelloWorld”的类，并实现输出“Welcome to java world”的功能。

在ex01包下创建好HelloWord.java文件后，在名为HelloWorld的类中找到main方法，在main方法中输入一个System.out.println("Welcome to java world!");即为结果。

\3.  编写程序，分别定义int、double、char类型数据，并输出它们的值。

在main方法里分别定义int、double、char类型的变量，并初始化，进而打印出相应的值。

\4.  编写程序，计算长宽分别为2.0、3.0的长方形的面积及周长。

分别定义长跟宽两个变量并初始化，然后再分别定义面积变量和周长变量来接受长乘以宽 和 长加宽的和乘以2。

\5.   编程找出100——999以内的水仙花数，并输出。（“水仙花数”是指一个3位数，其各位数字立方和等于该数。）

三位数的水仙花数思路很简单，就是判断这个三位数的每一位的立方和是不是等于这个数本身。我们可以用一个for loop从100遍历到999，循环里再对每一个数模10除10，得到这个数的每一位，最后把每一位数的立方相加判断是不是等于原数就ok了。

多位数的水仙花数（自幂数）思路较为复杂一点，在三位水仙花数的基础上需要将每一位数依次除10，定义一个count变量依次++，进而得到每个数的位数。得到每个数的位数之后，重复三位数水仙花的操作，模10除10，然后将其每一位的count次方相加之和与原数比较即可。

\6.   一个数如果恰好等于它的因子之和，这个数就称为"完数"。例如6=1＋2＋3。编程找出1000以内的所有完数。（选做）

首先定义一个sum变量初始化为0，让其作为累加的结果。完数的概念就是一个数等于其因子之和（不包括本身）。思路很简单，我们可以类比为求素数。一个外层i for loop从2（因为由题意得1不是完数）到1000,遍历，内层j for loop从1到i / 2,因为因子除自身外都小于等于自身的一半。最后把筛选出来的结果累加即可，判断一下如果sum与原数相等，即为完数。

 

**【实验源码】**

实验内容1不需要代码实现，这里直接贴上结果的截图：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image002.jpg)

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image004.jpg)

\2. 在ex01包中，创建名称为“HelloWorld”的类，并实现输出“Welcome to java world”的功能。

 

package com.ex01;

/*

Author: wang yuan

Time: 2021/9/9

Test: 2.在ex01包中，创建名称为“HelloWorld”的类，并实现输出“Welcome to java world”的功能。

*/

public class HelloWorld {

  public static void main(String[] args) {

​    System.*out*.println("Welcome to java world!");

  }

}

 

\3. 编写程序，分别定义int、double、char类型数据，并输出它们的值。

package com.assassin;

 

 

/*

 Author: wang yuan

 Time: 2021/9/9

 Test: 编写程序，分别定义int、double、char类型数据，并输出它们的值。

 */

public class TestDemo {

  public static void main(String[] args) {

​    int integer = 1; //定义int值为1

​    double aDouble = 2.0; //定义double值为2.0

​    char character = 'a'; //定义char值为’a’

​    System.*out*.println("integer = " + integer);

​    System.*out*.println("aDouble = " + aDouble);

​    System.*out*.println("character = " + character);

  }

}

 

4．编写程序，计算长宽分别为2.0、3.0的长方形的面积及周长。

package com.ex01;

 

/**

 \* Author: wang yuan

 \* Time: 2021/9/9

 \* Test: 编写程序，计算长宽分别为2.0、3.0的长方形的面积及周长。

 */

 

public class HelloWorld {

  public static void main(String[] args) {

​    double lenth = 3.0; //长

​    double width = 2.0; //宽

​    double area = lenth * width; //面积

​    double perimeter = 2 * (lenth + width); //周长

 

​    System.out.println("长方形的面积为:"+area);

​    System.out.println("长方形的周长为:"+perimeter);

 

  }

}

 

 

\5. 编程找出100——999以内的水仙花数，并输出。（“水仙花数”是指一个3位数，其各位数字立方和等于该数。）

package com.ex01;

 

/**

 \* Author: wang yuan

 \* Time: 2021/9/9

 \* Test: 编程找出100——999以内的水仙花数，并输出。（“水仙花数”是指一个3位数，其各位数字立方和等于该数。）

 */

 

public class HelloWorld {

  public static void main(String[] args) {

​    System.out.println("the result is:");

​    test();

  }

  public static void test() {

​    for (int i = 100; i <= 999; i++) {

​      int sum = 0;

​      int temp = i;

​      while (temp != 0) {

​        sum += Math.pow(temp % 10, 3);

​        temp /= 10;

​      }

​      if (sum == i) {

​        System.out.print(i + " ");

​      }

​    }

  }

}

 

水仙花升级版：水仙花数其实是三位的自幂数，详细定义摘自百度百科

水仙花数只是[自幂数](https://baike.baidu.com/item/自幂数)的一种，严格来说3位数的3次幂数才称为水仙花数。

附：其他位数的自幂数名字

一位自幂数：[独身数](https://baike.baidu.com/item/独身数/13019786)

三位自幂数：水仙花数

四位自幂数：[四叶玫瑰数](https://baike.baidu.com/item/四叶玫瑰数/13019609)

五位自幂数：[五角星数](https://baike.baidu.com/item/五角星数/13019763)

六位自幂数：[六合数](https://baike.baidu.com/item/六合数/13019768)

七位自幂数：[北斗七星数](https://baike.baidu.com/item/北斗七星数/13019769)

八位自幂数：[八仙数](https://baike.baidu.com/item/八仙数/13019781)

九位自幂数：[九九重阳数](https://baike.baidu.com/item/九九重阳数/13019774)

十位自幂数：[十全十美数](https://baike.baidu.com/item/十全十美数/13019780)

 

package com.ex01;

 

/**

 \* Author: wang yuan

 \* Time: 2021/9/9

 \* Test: 升级版水仙花数，

 */

 

public class HelloWorld {

  public static void main(String[] args) {

//    System.out.println("the result is:");

​    test();

  }

 

  public static void test() {

​    for (int i = 1; i <=999999 ; i++) {

 

​      int count = 0;

​      int temp = i;

​      while(temp != 0) {

​        count++;

​        temp /= 10;

​      }

 

​      temp = i;

​      int sum = 0;

​      while(temp != 0) {

​        sum += Math.pow(temp%10,count);

​        temp /= 10;

​      }

​      if(sum == i) {

​        System.out.println(sum+" is my result");

​      }

​    }

  }

 

}

\6. 一个数如果恰好等于它的因子之和，这个数就称为"完数"。例如6=1＋2＋3。编程找出1000以内的所有完数。（选做）

package com.ex01;

 

/**

 \* Author: wang yuan

 \* Time: 2021/9/9

 \* Test: 一个数如果恰好等于它的因子之和，这个数就称为"完数"。例如6=1＋2＋3。编程找出1000以内的所有完数。（选做）

 */

 

public class HelloWorld {

  public static void main(String[] args) {

​    test();

  }

 

  // 思想类似于求素数

  public static void test() {

​    //依题意得，1不是完数，因为1的因子为本身，而例子中给的6是除本身以外的因子之和

​    //所以这里直接从2开始

​    for (int i = 2; i <= 1000 ; i++) {

​      int sum = 0;

​      for (int j = 1; j <= i / 2; j++) { 

​        if(i % j == 0) {

​          sum += j;

​        }

 

​      }

​      if(sum == i) {

​        System.out.println("the result is:" + i);

​      }

​    }

  }

}

 

**【实验结果】**

（截图给出实验结果）

\1. 在自己电脑d盘某目录下创建自己的工作空间及名称为“demo”的项目，并创建名称为ex01的包

 

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image005.jpg)

 

\2. 在ex01包中，创建名称为“HelloWorld”的类，并实现输出“Welcome to java world”的功能。

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image006.jpg)

\3. 编写程序，分别定义int、double、char类型数据，并输出它们的值。

 

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image008.jpg)

\4. 编写程序，计算长宽分别为2.0、3.0的长方形的面积及周长。

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image010.jpg)

 

\5. 编程找出100——999以内的水仙花数，并输出。（“水仙花数”是指一个3位数，其各位数字立方和等于该数。）

 

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image012.jpg)

升级版水仙花数（自幂数）：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image014.jpg)

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image016.jpg)

\6. 一个数如果恰好等于它的因子之和，这个数就称为"完数"。例如6=1＋2＋3。编程找出1000以内的所有完数。（选做）

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image018.jpg)

**【实验体会】**

**实验一较为简单，主要是考察一些基本的编译环境的操作和一些非面向对象题的解法。这里简单谈一下对每道题的一些体会。**

**第一题纯粹就是看我们会不会新建文件夹。我们写的一些小项目需要一个文件夹也就是专门的工作空间来存储，在日常的开发中，难免会写到很多的****java****文件，这时包****package****的概念就出来了，这是为了解决的多文件编写和重名的问题，功能类似于****C++****里的****namespace****。**

​    **第二题就是在自己的建好的包下再新建一个****java****文件，值得注意的是，自己建的****java****文件有且只有一个****public****的类，随后就是在****main****方法中输出****Welcome to java world** **了，这个没啥好说的。**

​    **第三题只需要注意定义局部变量时，需要进行初始化的操作即可。局部变量不初始化直接使用会报错。**

​    **第四题也是很常规的，不过好歹有了用****java****解决问题的影子。其实也就是定义长和宽两个变量，再用面积变量和周长变量来接受并输出。具体周长跟面积跟长，宽什么关系这里就不说了。**

​    **第五题三位数的水仙花数思路很简单，就是判断这个三位数的每一位的立方和是不是等于这个数本身。我们可以用一个****for loop****从****100****遍历到****999****，循环里再对每一个数模****10****除****10****，得到这个数的每一位，最后把每一位数的立方相加判断是不是等于原数就****ok****了。推广多位数的次方和的具体思路可以看前面的详解。**

​    **第六题熟悉的同学就会发现其实就是求素数的方法，两层****for****循环，外层控制要求的数，内层来判断是否满足条件，最后把满足条件的数加和比较就行了。**

 

 

 

 

 

**实验二** **Java****基本语法**

实验时间： 2021/9/9  

**【实验目的】**

1、熟悉Java语言中的数据类型、变量声明、数组、运算符号、流程控制语句。

2、学会定义类和方法，利用方法传递参数，得到方法的返回值。

**【实验环境】**

JDK1.8  IntelliJ IDEA

**【实验内容】**

1.求1+2!+3!+...+20!的和。

2.输入三个整数x、y、z，请把这三个数由小到大输出。

3.利用条件运算符的嵌套来完成此题：学习成绩>=90分的同学用A表示，60-89分之间的用B表示，60分以下的用C表示。

4.一球从100米高度自由落下，每次落地后反跳回原高度的一半；再落下……，求它在第10次落地时，共经过多少米？第10次反弹多高？（选做）

5.计算两个3*3矩阵相乘，矩阵为int[][]或者double[][]都可以。声明一个方法，该方法接受参数，并返回计算的结果。

6.企业发放的奖金根据利润提成。利润低于或等于10万元时，奖金可提10%；利润高于10万元，低于20万元时，低于10万元的部分按10%提成，高于10万元的部分，可可提成7.5%；20万到40万之间时，高于20万元的部分，可提成5%；40万到60万之间时高于40万元的部分，可提成3%；60万到100万之间时，高于60万元的部分，可提成1.5%，高于100万元时，超过100万元的部分按1%提成，从键盘输入当月利润，求应发放奖金总数？

**【详细分析】**

（此项由学生自己完成）

\1.   求1+2!+3!+...+20!的和。

此题思路很简单，就是无脑直接遍历加和。这里提供两种解法。

第一种用两层for loop，外层控制循环的次数，从1到20也就是20次。内层循环求出每一次的阶乘。最后定义一个sum把每一次的阶乘相加便是结果。

第二种其实思路跟第一种没啥区别，不过用一层for loop便可以搞定。我们仔细观察规律，每一次的阶乘都是上一次的阶乘再乘以这个数，所以我们每一次可以在上一次的基础上再乘以本身就ok了，不过也不要忘了把每一次的结果累加到sum上。

这里必须要提一点的是，很多同学发现用int存储会溢出之后，改用long进行存储，然后他们发现还是溢出。我发现他们只是把sum定义成了long，而没有把存储每一次的变量temp定义为long，这便是导致犯错的关键。

\2.   输入三个整数x、y、z，请把这三个数由小到大输出。

这种题可以无脑if，因为只有三个数，作业量不多的情况下直接用三个if就搞定了，如果x大于y，交换二者的值，如果x大于z，交换二者的值，如果y大于z，交换二者的值。此时便达到了x最小，y次之，z最大的目的，依次输出就好了。

\3.   利用条件运算符的嵌套来完成此题：学习成绩>=90分的同学用A表示，60-89分之间的用B表示，60分以下的用C表示。

题目明确提出了要用条件运算符的嵌套来解决问题。条件运算符有if else if和switch case，这里选用最为直观的if else if。根本不需要思考，if成绩大于等于90，输出a，60-89输出b，小于60输出c，都不带拐弯的，如实描述就好了。

\4.   一球从100米高度自由落下，每次落地后反跳回原高度的一半；再落下……，求它在第10次落地时，共经过多少米？第10次反弹多高？（选做）

此题也是按照题意如实描述即可。定义一个sum来累加路程。不过需要判断一下是否为第一次下落，如果是第一次下落，经过的路程直接就是高度，如果不是第一次下落，经过的路程就要是高度的2倍(一上一下的路程之和)，然后就是注意每次下落后高度除以2就行了。

\5.   计算两个3*3矩阵相乘，矩阵为int[][]或者double[][]都可以。声明一个方法，该方法接受参数，并返回计算的结果。

此题是让我们计算两个3*3的矩阵，我们可以把它推广为由我们控制的矩阵相乘，也就是不一定是3*3，可以两个矩阵能相乘，任意两个都能计算。

首先在main方法里new三个对象指向null，一个用来表示矩阵A，一个用来表示矩阵B，另一个用来表示相乘过后的矩阵。自己实现矩阵构造的方法，将构造初始化过后的对象地址返回给main方法的两个引用类型的变量。自己还需实现一个矩阵乘法的方法，将结果的地址返回给表示相乘的矩阵，这里需要注意的是，两个矩阵必须是可以相乘的，如果不满足条件直接return null；具体的矩阵乘法步骤可以看代码里的注释，这里不再展开。最后就是实现打印方法进行结果的打印就行了。

\6.   企业发放的奖金根据利润提成。利润低于或等于10万元时，奖金可提10%；利润高于10万元，低于20万元时，低于10万元的部分按10%提成，高于10万元的部分，可可提成7.5%；20万到40万之间时，高于20万元的部分，可提成5%；40万到60万之间时高于40万元的部分，可提成3%；60万到100万之间时，高于60万元的部分，可提成1.5%，高于100万元时，超过100万元的部分按1%提成，从键盘输入当月利润，求应发放奖金总数？

此题是典型的多分支判断语句，也就是利用if else if进行多次如实描述，没有什么技术含量，跟前面有道题是一模一样的，具体操作看代码实现。

**【实验源码】**

（此项由学生自己完成）

\1. 求1+2!+3!+...+20!的和。

package com.ex01;

/**

 \* Author: wang yuan

 \* Time: 2021/9/9

 \* Test: 1.求1!+2!+3!+...+20!的和

 */

 

public class TestDemo {

  public static void main(String[] args) {

​    long factorial = fac();

​    System.out.println("the result is: "+factorial);

 

  }

  //求阶乘 阶乘值太大，用long定义变量

  public static long fac() {

​    long ret = 0L; //各个阶乘结果之和

​    for (int i = 1; i <= 20; i++) { //两层for循环，外层是阶乘的个数，内层是具体某个阶乘值

​      long temp = 1L;       //因为是乘法，所以初始化为1

​      for (int j = 1; j <= i; j++) {

​        temp *= j;

​      }

​      ret += temp; 

​    }

​    return ret;

  }

}

 

 

\2. 输入三个整数x、y、z，请把这三个数由小到大输出。

package com.ex01;

 

import java.util.Scanner;

 

/**

 \* Author: wang yuan

 \* Time: 2021/9/9

 \* Test: 2.输入三个整数x、y、z，请把这三个数由小到大输出

 */

 

public class TestDemo {

  public static void main(String[] args) {

​    Scanner scan = new Scanner(System.in);

​    int x = scan.nextInt();

​    int y = scan.nextInt();

​    int z = scan.nextInt();

 

​    if(x > y) {

​      int temp = x;

​      x = y;

​      y = temp;

​    }

​    if(x > z) {

​      int temp = x;

​      x = z;

​      z = temp;

​    }

​    if(y > z) {

​      int temp =y;

​      y = z;

​      z = temp;

​    }

​    System.out.print("这三个数从小到大分别为：");

​    System.out.print(x+" ");

​    System.out.print(y+" ");

​    System.out.print(z+" ");

 

  }

}

 

 

\3. 利用条件运算符的嵌套来完成此题：学习成绩>=90分的同学用A表示，60-89分之间的用B表示，60分以下的用C表示。

 

package com.ex01;

 

import java.util.Scanner;

 

/**

 \* Author: wang yuan

 \* Time: 2021/9/9

 \* Test: 3.利用条件运算符的嵌套来完成此题：学习成绩>=90分的同学用A表示 +

 \* Test: 60-89分之间的用B表示，60分以下的用C表示。

 */

 

public class TestDemo {

  public static void main(String[] args) {

​    Scanner scan = new Scanner(System.in);

​    System.out.println("Please enter your score>");

​    int score = scan.nextInt();

​    if(score >= 90) {  // 大于90输出A

​      System.out.println("yeah you got a A");

​    }else if(score >= 60){ //60到90之间输出B

​      System.out.println("oh you got a B");

​    }else{ //低于60输出C

​      System.out.println("I'm sorry,you just goy a C");

​    }

 

  }

}

 

\4. 一球从100米高度自由落下，每次落地后反跳回原高度的一半；再落下……，求它在第10次落地时，共经过多少米？第10次反弹多高？（选做）

package com.ex01;

 

/*

Author: wang yuan

Time: 2021/9/9

Test: 4.一球从100米高度自由落下，每次落地后反跳回原高度的一半；再落下…… 求它在第10次落地时，共经过多少米？第10次反弹多高？（选做）

*/

public class TestDemo {

  public static void main(String[] args) {

​    double retDistance = *totalDistance*();

​    System.*out*.println("第10次下落时共经过的距离：" + retDistance); //输出第10次下落时共经过的距离

​    double retRebound = *rebound*();

​    System.*out*.println("第10次反弹的高度：" + retRebound); //输出第10次反弹的高度

  }

   public static double totalDistance() {

​    double height = 100.0;

​    double sum = 0.0;

​    for (int i = 0; i < 10; i++) {

​      if (i == 0) {

​        sum += height; //如果是第一次下落直接加上高度即可

​      } else {

​        sum += (height * 2); //如果不是第一次下落，需要加上高度的两倍（一上一下）

​      }

​      height /= 2; //每次下落后，高度变为原来的一半

​      //rebound()

​    }

​    return sum;

  }

 

  public static double rebound() {

​    double height = 100.0;

​    for (int j = 0; j < 10; j++) {

​       height /= 2; //每次下落后，高度变为原来的一半

​    }

​    return height;

  }

}

 

\5. 计算两个3*3矩阵相乘，矩阵为int[][]或者double[][]都可以。声明一个方法，该方法接受参数，并返回计算的结果。

package com.ex01;

 

//import java.util.Arrays; //配合Arrays.deepToString

import java.util.Scanner;

 

/**

 \* Author: wang yuan

 \* Time: 2021/9/9

 \* Test: 计算两个3*3矩阵相乘，矩阵为int[][]或者double[][]都可以 +

 \* Test: 声明一个方法，该方法接受参数，并返回计算的结果。

 */

 

public class TestDemo {

  //main

  public static void main(String[] args) {

 

​    //boolean count = false; //判断一下是创建矩阵A还是矩阵B

​    int[][] matrixA; //new一个矩阵A对象

​    int[][] matrixB; //new一个矩阵B对象

​    int[][] matrixRet; //new一个矩阵result对象

 

​    matrixA = createMatrix();  //让matrixA指向创建好的对象

​    matrixB = createMatrix();  //让matrixB指向创建好的对象

​    matrixRet = multiplyMatrix(matrixA,matrixB); // //让matrixRet指向相乘结果的对象

 

​    System.out.println("The value of the matrix multiplied> ");

​    //System.out.println(Arrays.deepToString(matrixRet));

​    //可以直接调用Arrays类的deepToString函数直接打印

​    assert matrixRet != null; //断言 如果是空对象直接抛空指针异常

​    printMatrix(matrixRet);

 

  }

  //构造函数，构造矩阵

  public static int[][] createMatrix() {

 

​    Scanner scan =new Scanner(System.in);

​    System.out.println("please enter the row of the matrix> "); //输入行数

​    int row = scan.nextInt(); //行

​    System.out.println("please enter the column of the matrix> "); //输入列数

​    int col = scan.nextInt(); //列

​    int[][] matrixTemp = new int[row][col];

​    System.out.println("please enter the values of the matrix> "); //输入矩阵的值

 

​    for (int i = 0; i < row; i++) { //给矩阵赋值

​      for (int j = 0; j < col; j++) {

​        matrixTemp[i][j] = scan.nextInt();

​      }

​    }

​    return matrixTemp;

  }

  //乘法函数，矩阵相乘

  public static int[][] multiplyMatrix(int[][] matrixA,int[][] matrixB) {

​    if(matrixA[0].length != matrixB.length) {

​      System.out.println("Your input is wrong> "); //输入的矩阵A的行不等于矩阵B的列，无法进行乘法计算

​      return null; //返回null对象

​    }else{

​      int[][] matrixRet =new int[matrixA.length][matrixB[0].length];

​      //矩阵A的第i行与矩阵B的每一列相乘，最外层矩阵A总共走的次数，也就是矩阵A的行数

​      for(int i = 0; i < matrixA.length; i++) {

​        //矩阵A的每一行都要依次跟矩阵B的每一列相乘，走矩阵B的列数次

​        for(int j = 0; j < matrixB[0].length; j++) {

​          for (int k = 0; k < matrixA[0].length; k++) { //每次相乘完都要把结果相加

​            // 矩阵A有多少行（矩阵B有多少列）就加多少次

​            matrixRet[i][j] += matrixA[i][k] * matrixB[k][j];

​          }

​        }

​      }

​      return matrixRet;

​    }

  }

  //打印函数,范围for/for each

  public static void printMatrix(int[][] matrix) { //增强for循环 打印出ret矩阵结果

​    for (int[] ints : matrix) {

​      for (int anInt : ints) {

​        System.out.print(anInt + "\t");

​      }

​      System.out.println();

​    }

  }

}

 

\6. 企业发放的奖金根据利润提成。利润低于或等于10万元时，奖金可提10%；利润高于10万元，低于20万元时，低于10万元的部分按10%提成，高于10万元的部分，可可提成7.5%；20万到40万之间时，高于20万元的部分，可提成5%；40万到60万之间时高于40万元的部分，可提成3%；60万到100万之间时，高于60万元的部分，可提成1.5%，高于100万元时，超过100万元的部分按1%提成，从键盘输入当月利润，求应发放奖金总数？

 

package com.ex01;

 

import java.util.Scanner;

 

/**

 \* Author: wang yuan

 \* Time: 2021/9/9

 \* Test:

 \* 6.企业发放的奖金根据利润提成。利润低于或等于10万元时，奖金可提10%；

 \* 利润高于10万元，低于20万元时，低于10万元的部分按10%提成，高于10万元的部分，

 \* 可提成7.5%；20万到40万之间时，高于20万元的部分，可提成5%；40万到60万之间时高于40万元的部分，

 \* 可提成3%；60万到100万之间时，高于60万元的部分，可提成1.5%，高于100万元时，

 \* 超过100万元的部分按1%提成，从键盘输入当月利润，求应发放奖金总数？

 */

 

public class TestDemo {

 

  public static void main(String[] args) {

 

​    Scanner scan = new Scanner(System.in);

 

​    System.out.println("please enter your profit> ");

​    double profit = scan.nextDouble();

 

​    double salaryRet = 0;

 

​    double salary1 = 100000 * 0.1;//10万的奖金

​    double salary2 = (200000 - 100000) * 0.075 + salary1;//20万的奖金

​    double salary3 = (400000 - 200000) * 0.05 + salary2;//40万的奖金

​    double salary4 = (600000 - 400000) * 0.03 + salary3;//60万的奖金

​    double salary5 = (1000000 - 600000) * 0.015 + salary4;//100万的奖金

 

​    if(profit <= 100000) {

​      salaryRet = profit * 0.1;//小于100000按10%提成

​    }else if(profit <= 200000) {

​      salaryRet = salary1 + (profit - 100000) * 0.075;//多出10万的按比例计算，加上10w应得的的奖金

​    }else if(profit <= 400000) {

​      salaryRet = salary2 + (profit - 200000) * 0.05;//多出20万的按比例计算，加上20w应得的的奖金

​    }else if(profit <= 600000) {

​      salaryRet = salary3 + (profit - 400000) * 0.03;//多出40万的按比例计算，加上40w应得的的奖金

​    }else if(profit <= 1000000) {

​      salaryRet = salary4 + (profit - 600000) * 0.015;//多出60万的按比例计算，加上60w应得的的奖金

​    }else{

​      salaryRet = salary5 + (profit - 1000000) * 0.01;//多出100万的按比例计算，加上100w应得的的奖金

​    }

​    System.out.println(salaryRet);

  }

}

 

**【实验结果】**

（截图给出实验结果）

\1.   求1+2!+3!+...+20!的和。

代码概览：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image020.jpg)

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image022.jpg)

 

\2. 输入三个整数x、y、z，请把这三个数由小到大输出。

 

代码概览：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image024.jpg)

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image026.jpg)

\3. 利用条件运算符的嵌套来完成此题：学习成绩>=90分的同学用A表示，60-89分之间的用B表示，60分以下的用C表示。

 

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image028.jpg)

 

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image030.jpg)

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image032.jpg)

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image034.jpg)

 

\4. 一球从100米高度自由落下，每次落地后反跳回原高度的一半；再落下……，求它在第10次落地时，共经过多少米？第10次反弹多高？（选做）

 

 

 

 

代码概览：

 

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image036.jpg)

 

 

 

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image038.jpg)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

\5. 计算两个3*3矩阵相乘，矩阵为int[][]或者double[][]都可以。声明一个方法，该方法接受参数，并返回计算的结果。

代码概览：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image040.jpg)

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image042.jpg)

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image044.jpg)

\6. 企业发放的奖金根据利润提成。利润低于或等于10万元时，奖金可提10%；利润高于10万元，低于20万元时，低于10万元的部分按10%提成，高于10万元的部分，可可提成7.5%；20万到40万之间时，高于20万元的部分，可提成5%；40万到60万之间时高于40万元的部分，可提成3%；60万到100万之间时，高于60万元的部分，可提成1.5%，高于100万元时，超过100万元的部分按1%提成，从键盘输入当月利润，求应发放奖金总数？

 

 

 

 

 

 

 

 

代码概览：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image046.jpg)

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image048.jpg)

**【实验体会】**

实验二整体来说难度比实验一大了一些，基本都是运用java来解决一些生活中的小问题，不过面向对象的思想还是不能够很好地体现。这里简单谈谈我对每道题的看法。

​    第一题是求1到20各数的阶乘之和，唯一需要注意的一点就是需要考虑范围的问题。用int会直接溢出，这里必须提一下，有些同学虽然想到了用long来存储总和，但还是提示溢出。这说明根本不仔细认真，他们的记录每一个阶乘的临时值temp还是int类型，这相当于做事只做了一半，基本没用。

​    第二题把三个数按从小到大的顺序依次输出。无非就是三个if搞定，数据不是很多，这个时候就不要去考虑很高大上的解法，直截了当更来的快。

​    第三题需要用到分支结构对问题的每一种情况进行分析，对每一个if else if都如实地做出相应的对策就行了，毫无技术含量，重点是考察分支条件嵌套的使用。

​    第四题只需要对一个地方进行特殊考虑，当第一次下落的时候，路程直接加上高度即可，后面的都需要加上两次高度（一上一下）。

​    第五题的重点其实是考察对矩阵阶乘的掌握程度，当然还有对二维数组用法的考察，需要注意的是我们的main方法里一般是用来测试的，逻辑一般都要另外实现方法，用main方法来调用，这样结构清晰明了。

​    第六题跟第三题一个样，也是考察分支结构条件嵌套的使用，不要看文字量多了就害怕了，其实根本不需要思考，每一个分支按照给的条件来实现就行了。