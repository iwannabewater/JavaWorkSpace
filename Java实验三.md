# 河南工业大学

# 《JAVA程序设计》实验报告

专业班级： 物联网1902班   学号： 201916070216    姓名： 王源     

**实验单元三**  **Java****多态、集合与泛型**

**实验五** **Java****集合的应用**

实验时间：   2021/11/9  

**【实验目的】**

（1）理解List的应用场合。

（2）掌握Comparable和Comparator接口的使用方法。

（3）掌握迭代器接口Iterator和ListIterator遍历集合的方法

**【实验环境】**

JDK、Eclipse

**【实验内容】**

1.处理扑克牌

每张扑克牌有点数和花色，定义Poker类，要求如下：

（1）成员变量包括点数（point）和花色（color）；

（2）定义构造方法初始化所有成员变量；

（3）省略setter，定义getter（）方法；

（4）重写toString（）方法返回扑克牌的信息。

定义PokerComparator类实现Comparator接口，重写compare（Object obj1，Object obj2）方法，首先按照花色排序，如果花色相同则按照点数从大到小排序。

定义游戏类Game，要求如下：

（1）  定义变量ArrayLIst类型保持Poker对象，并定义空参构造；

（2）  省略setter和getter方法；

（3）  定义showAll（）方法显示成员变量ArrayList对象的所有内容；

（4）  定义成员方法sort（）对成员变量ArrayList元素按照花色点数排序。

定义测试类，完成以下任务：

（1）  创建ArrayList对象al，有若干个不容的Poker对象；

（2）  创建Game对象，参数是al；

（3）  调用Game中的showAll（）方法显示所有牌；

（4）  调用Game中的sort（）方法对al进行排序

2.学生成绩管理

定义学生类（可以直接用之前定义过的）实现Comparable接口，要求：

（1）  成员变量包括学号id，姓名name，年龄age，课程成绩ArrayList（至少三门课的成绩）；

（2）  定义构造方法初始化所有成员变量

（3）  省略getter和setter；

（4）  功能方法：重写Comparable接口中的compareTo（）方法按照总分从大到小的顺序排序，重写toString方法返回学生的所有成员变量。

定义学生管理类Manager，要求：

（1）  成员变量包括TreeSet ts；

（2）  定义构造方法初始化成员变量

（3）  定义功能方法：show()显示集合ts中的学生的学号、姓名、年龄、每门课程的成绩、总成绩，定义add（Student stu）方法把一个学生信息添加到ts中，利用remove（Student stu）方法删除一个学生，search（String id）方法根据学号查找学生。



定义测试类Demo，调用add（）方法添加至少10个学生信息，调用show（）方法显示学生信息，调用remove（String std）方法删除学生信息，调用search（String id）查找某学生信息。

**【详细分析】**

（此项由学生自己完成）

\1.   处理扑克牌

Poker类：

按照要求定义成员变量点数(point)跟花色(color)，定义构造方法初始化所有成员变量省略setter，定义getter方法；重写toString方法返回扑克牌的信息。toString方法主要是让信息输出的更为直观。同时为了方便比较花色(color)，我额外定义了enum枚举类来表示四个花色。

PokerComparator类：

实现Comparator接口，重写compare(Object obj1，Object obj2)方法，首先按照花色排序，如果花色相同则按照点数从大到小排序。

逻辑完全按照题目所要求的。

  Game类：

定义变量ArrayLIst类型保持Poker对象，并定义空参构造；

省略setter和getter方法；定义showAll方法显示成员变量ArrayList对象的所有内容；自定义成员方法sort对成员变量ArrayList元素按照花色点数排序。

TestDemo类：

创建ArrayList对象al，有若干个不容的Poker对象；创建Game对象，参数是al；调用Game中的showAll方法显示所有牌；调用Game中的sort方法对al进行排序

 

 

 

 

\2.   学生成绩管理

Student类：

定义学生类（可以直接用之前定义过的）实现Comparable接口， 成员变量包括学号id，姓名name，年龄age，课程成绩ArrayList（至少三门课的成绩）；定义构造方法初始化所有成员变量。省略getter和setter；重写Comparable接口中的compareTo方法按照总分从大到小的顺序排序，重写toString方法返回学生的所有成员变量。

Manager类：

成员变量包括TreeSet ts；定义构造方法初始化成员变量。定义功能方法：show()显示集合ts中的学生的学号、姓名、年龄、每门课程的成绩、总成绩，定义add（Student stu）方法把一个学生信息添加到ts中，利用remove（Student stu）方法删除一个学生，search（String id）方法根据学号查找学生。

TestDemo类：

调用add方法添加至少10个学生信息，调用show方法显示学生信息，调用remove（String std）方法删除学生信息，调用search（String id）查找某学生信息。

 

**【实验源码】**

（此项由学生自己完成）

\1.   处理扑克牌

Poker.java

```java
package com.haut.iot.ninghai;

/**
 * @Author: 宁海
 * @Date: 2021/11/9
 * @Time: 20:35
 * @Version: 1.0
 */


@SuppressWarnings({"all"}) //忽略警告

enum Color {
    DIAMOND, //方块
    CLUB,   //梅花
    HEART,  //红桃
    SPADE;  //黑桃
    private String[] colors = {"方块", "梅花", "红桃", "黑桃"};

    @Override
    public String toString() {
        //返回对象的字符串信息
        return colors[this.ordinal()];
    }
}

@SuppressWarnings({"all"}) //忽略警告
public class Poker {
    private int point; //点数
    private Color color; //颜色

    //构造方法初始化成员属性
    public Poker(int point, Color color) {
        this.point = point;
        this.color = color;
    }

    //getter方法
    public int getPoint() { //get point
        return point;
    }

    public Color getColor() { //get color
        return color;
    }

    @Override  //重写toString方法
    public String toString() {
        return "Poker{" +
                "point=" + point +
                ", color='" + color.toString() + '\'' +
                '}';
    }
}

```



PokerComparator.java:

```java
package com.haut.iot.ninghai;

import java.util.Comparator;
import java.util.Objects;

/**
 * @Author: 宁海
 * @Date: 2021/11/9
 * @Time: 20:37
 * @Version: 1.0
 */


//泛型
public class PokerComparator implements Comparator<Poker> {
    @Override //指定比较规则
    public int compare(Poker obj1, Poker obj2) {//重写compare方法
        //调用Objects的equals方法进行判断，若花色不相同，就进行花色的比较
        //按照黑桃>红桃>梅花>方块的规则进行排序
        if (!Objects.equals(obj1.getColor(), obj2.getColor())) {
            //调用Integer的compare方法
            return Integer.compare(obj2.getColor().ordinal(), obj1.getColor().ordinal());
        } else { //当花色相同时，按照点数进行排序，按照从大到小的规则进行排序
            return Integer.compare(obj2.getPoint(), obj1.getPoint());
        }
    }
}

```

Game.java:

```java
package com.haut.iot.ninghai;

import java.util.ArrayList;
import java.util.Collections;

/**
 * @Author: 宁海
 * @Date: 2021/11/9
 * @Time: 20:36
 * @Version: 1.0
 */


public class Game {
    //定义变量ArrayList类型变量来保存Poker对象
    private ArrayList<Poker> al;
    //构造方法初始化成员属性
    public Game(ArrayList<Poker> al) {
        this.al = al;
    }
    //定义空参构造
    public Game() {
    }

    @Override
    //重写toString方法
    public String toString() {
        return "Game{" +
                "al=" + al.toString() +
                '}';
    }

    //调用重写后的toString方法进行信息的打印
    public void showAll() {
        String ret = toString();
        System.out.println(ret);
    }
    //sort方法自动调用compareTo方法进行自定义排序
    //冒泡排序
    public void sort() {
        PokerComparator pokerComparator = new PokerComparator();
        for (int bound = 0; bound < al.size(); bound++) {
            for (int cur = 0; cur < al.size() - 1 - bound; cur++) {
                if (pokerComparator.compare(al.get(cur), al.get(cur + 1)) >= 1) {
                    //swap方法
                    Collections.swap(al, cur, cur + 1);
                }
            }
        }
    }


}
```

TestDemo.java:

```java
package com.haut.iot.ninghai;

import java.util.ArrayList;

/**
 * @Author: 宁海
 * @Date: 2021/11/9
 * @Time: 20:37
 * @Version: 1.0
 */


public class TestDemo {
    public static void main(String[] args) {
        ArrayList<Poker> al = new ArrayList<>();  //new一个泛型的ArrayList对象
        //添加Poker对象
        al.add(new Poker(2, Color.SPADE));
        al.add(new Poker(3, Color.HEART));
        al.add(new Poker(4, Color.CLUB));
        al.add(new Poker(5, Color.DIAMOND));
        al.add(new Poker(7, Color.DIAMOND));
        al.add(new Poker(6, Color.SPADE));
        //new一个game对象进行测试
        Game game = new Game(al);
        game.showAll();
        //排序
        game.sort();
        game.showAll();
    }
}
```



\2.   学生成绩管理：

Student.java:

```java
package com.haut.iot._ninghai;

import java.util.List;

/**
 * @Author: 宁海
 * @Date: 2021/11/10
 * @Time: 14:11
 * @Version: 1.0
 */

public class Student implements Comparable<Student> {
    public String id; //学号
    public String name; //姓名
    public List<Integer> scoreList; //分数集合

    @Override
    //重写compareTo方法
    public int compareTo(Student o) {
        int scoreRet1 = 0; //计分器
        int scoreRet2 = 0; //计分器
        //增强for循环
        for (Integer next : scoreList) {
            scoreRet1 += next;
        }

        for (Integer next : o.scoreList) {
            scoreRet2 += next;
        }
        //按照总分从大到小排序
        return Integer.compare(scoreRet2, scoreRet1);

    }
    //默认的无参构造
    public Student() {
    }
    //构造方法初始化成员属性
    public Student(String id, String name, List<Integer> scoreList) {
        this.id = id;
        this.name = name;
        this.scoreList = scoreList;
    }

    @Override
    //重写toString
    public String toString() {
        return "Student{" +
                "id='" + id + '\'' +
                ", name='" + name + '\'' +
                ", scoreList=" + scoreList +
                '}';
    }
}

```

Manager.java:

```java
package com.haut.iot._ninghai;

import java.util.TreeSet;

/**
 * @Author: 宁海
 * @Date: 2021/11/10
 * @Time: 14:11
 * @Version: 1.0
 */


public class Manager {
    private TreeSet<Student> ts;//TreeSet集合，用来存放Student对象

    //默认的无参构造
    public Manager() {
    }
    //构造方法初始化成员属性
    public Manager(TreeSet<Student> ts) {
        this.ts = ts;
    }
    //show方法打印出各类信息
    public void show() {
        for (Student student : ts) {
            int total = 0;
            for (int i = 0; i < student.scoreList.size(); i++) {
                total = total + student.scoreList.get(i);
            }
            System.out.println("学生的学号为:" + student.id + ",姓名为:" + student.name +
                    ",成绩分别是" + student.scoreList + ",总成绩为:" + total);
        }
    }
    //调用TreeSet的add方法
    public void add(Student student) {
        this.ts.add(student);
    }
    //调用TreeSet的remove方法
    public void remove(Student student) {
        this.ts.remove(student);
    }
    //search方法
    public void search(String id) {
        for (Student student : ts) {
            if (student.id.equals(id)) {
                System.out.println(student);
            }
        }
    }
}

```

 

TestDemo.java

```java
package com.haut.iot._ninghai;

import java.util.ArrayList;
import java.util.List;
import java.util.TreeSet;

/**
 * @Author: 宁海
 * @Date: 2021/11/10
 * @Time: 14:12
 * @Version: 1.0
 */

public class TestDemo {
    public static void main(String[] args) {
        TreeSet<Student> ts = new TreeSet<>(); //new一个泛型的TreeSet对象
        Manager manager = new Manager(ts); //new一个Manager对象
        //添加10个Student对象，每个对象带有三个不同的成绩
        for (int i = 0; i < 10; i++) {
            List<Integer> list = new ArrayList<>(); //泛型list对象，用来存放Student对象
            //添加分数
            list.add(99 - i);
            list.add(98 - i);
            list.add(97 - i);
            //Student对象
            Student student = new Student("" + i, "boy0" + i, list);
            //添加到manager中
            manager.add(student);
        }
        //显示排序结果
        manager.show();
        //演示add方法
        System.out.println("\n==========我是分割线===========\n");
        List<Integer> list = new ArrayList<>();
        list.add(100);
        list.add(100);
        list.add(100);
        Student s1 = new Student("666", "王源", list);
        manager.add(s1);
        //演示show方法
        manager.show();
        //演示search方法+remove方法
        System.out.println("\n==========我是分割线===========\n");
        manager.search("666");
        manager.remove(s1);
        manager.show();

    }
}
```

 

**【实验结果】**

（截图给出实验结果）

\1.   处理扑克牌

Poker.java:

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image002.jpg)

PokerComparator.java:

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image004.jpg)

Game.java:

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image006.jpg)

TestDemo.java:

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image008.jpg)

 

 

 

 

 

 

 

 

 

 

 

 

 

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image010.jpg)

可以看出排序后首先严格按照花色排序，黑桃>红桃>梅花>方块。当花色相同时，按照点数从大到小进行排序。

 

\2.   学生成绩管理

Student.java:

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image012.jpg)

Manager.java:

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image014.jpg)

TestDemo.java:

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image016.jpg)

运行结果：

添加10个Student对象：

 

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image018.jpg)

添加王源对象：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image020.jpg)

 

 

 

 

 

 

 

 

 

演示查询删除对象：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image022.jpg)

很明显地看到能添加Student对象，并按总成绩进行排序。同时还能满足删除插座和查询操作。

 

 

 

**【实验体会】**

（至少150字）

总的来说，这两个题很有针对性，可以说是很全面的考查到了多态，集合与泛型的知识。

​     第一题处理扑克牌中主要考查到了Comparator接口的实现。要实现对类对象的排序，就必须实现Comparator接口，自然也必须重写compare方法。

这是第一题的关键所在。我注意到sort方法是需要自己实现，在实际应用中，我们可以直接调用Arrays.sort()方法进行排序，或者调用Collections.sort()底层也是一个道理。他们都会去调用重写过后的compare方法来实现自己想要的逻辑。我自实现的sort排序是冒泡排序套上compare的外壳。还有一点需要强调，由于需要对花色进行比较，而我们知道花色是黑桃>红桃>梅花>方块，而这种逻辑是字典序里的方法所判断不了的，于是我单独定义了一个Color的枚举类来表示四种花色，因为enum枚举类可以直接比较ordinal，也就是默认的大小。第一题大致的思路就是这样。

第二题学生成绩管理相对来说比较直观，实现Comparable接口，并重写compareTo方法。实现了Comparable接口的类存放在TreeSet中会自动按逻辑排序，而这个逻辑是按学生成绩总分从高到低进行排序，较为简单Manager类中的add，remove方法可以直接调用成员变量TreeSet的add跟remove实现，大大简化了代码量，而search方法可以使用String类的equals方法判断两字符串是否相同，若相同，则输出该信息，若不同提示找不到该信息。

大致的体会就是这样，此次实验收获很多，让我意识到了自己存在很严重的眼高手低的毛病，代码只是光能看懂，要真自己上手写就显得捉襟见肘，总的来说，受益匪浅。