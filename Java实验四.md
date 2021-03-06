# 河南工业大学

# 《JAVA程序设计》实验报告

专业班级： 物联网1902班   学号： 201916070216   姓名： 王源      

**实验单元四**  **综合性程序设计**

**实验七** **简单学生信息管理系统**

实验时间：  2021/11/23    

**【实验目的】**

1、了解JDBC的作用，中我通过JDBC访问数据库的方法。

2、能够实现对数据库中数据的添加、删除、修改和查询。

**【实验环境】**

JDK、Eclipse

**【实验内容】**

完成教材P316实验内容

(综合性程序设计---简单学生信息管理系统---序列化版)

**【详细分析】**

本实验是用Java实现一个简单学生信息管理系统。只要是考察到序列化对象和反序列化对象的知识。我们必须要知道，要实现数据的序列化，前提是让其实现Serializable接口，所以我们必须在Student类中实现Serializable接口。这是本实验的关键。在Student类中按照要求重写一个toString方法，在StuList类中主要用到ObjectOutputStream处理流写入文件，实现序列化，用到ObjectInputStream

处理流实现反序列化，将对象数据读入到内存中，我们需要保存在数组中打印出来，以便于验证我们的操作是正确的。最后再加一个showUI方法实现控制台操作，便于使用。

**【实验源码】**

**Student.java:**

```java
package com.test;

import java.io.Serializable;

/**
 * @Author: 宁海
 * @Date: 2021/11/24
 * @Time: 15:09
 * @Version: 1.0
 */
@SuppressWarnings({"all"})
public class Student implements Serializable {
    //序列版本号，可以提高序列化的兼容性
    private static final long serialVersionUID = 1L;
    //成员变量
    private String name; //姓名
    private long id; //学号
    private double math; //数学成绩
    private double os; //操作系统成绩
    private double java; //java成绩

    //基本的set跟get方法
    public void setName(String name) {
        this.name = name;
    }

    public void setId(long id) {
        this.id = id;
    }

    public void setMath(double math) {
        this.math = math;
    }

    public void setOs(double os) {
        this.os = os;
    }

    public void setJava(double java) {
        this.java = java;
    }

    public String getName() {
        return name;
    }

    public long getId() {
        return id;
    }

    public double getMath() {
        return math;
    }

    public double getOs() {
        return os;
    }

    public double getJava() {
        return java;
    }

    //习惯性的定义一个空参构造
    public Student() {//空参构造
    }
    //构造方法，初始化成员属性
    public Student(String name, long id, double math, double os, double java) {
        this.name = name;
        this.id = id;
        this.math = math;
        this.os = os;
        this.java = java;
    }

    //按照要求重写toString方法
    @Override
    public String toString() {
        return name + " " + id + " " + "os:" + os
                + " java:" + java + " math:" + math;
    }
}
```



**StuList.java:**

```java
package com.test;


import java.io.*;
import java.util.Arrays;
import java.util.Scanner;

/**
 * @Author: 宁海
 * @Date: 2021/11/24
 * @Time: 15:20
 * @Version: 1.0
 */
@SuppressWarnings({"all"})
public class StuList {
    private Student[] students = new Student[10];//初始化能保存的stu数
    private int count = 0;//记录add stu的次数

    public static void main(String[] args) {
        StuList stuList = new StuList();
        System.out.println("The deserialized data is as follows:>");
        stuList.load(); //一开始就恢复数据
        stuList.showUI();//控制台操作
        stuList.save();//序列化到文件中

//        Student wy = new Student("wy", 201916070216L, 90, 90, 90);
//        Student cdc = new Student("cdc", 201916070201L, 100, 100, 100);
//        Student lzh = new Student("lzh", 201916070202L, 95, 100, 100);
//        Student hw = new Student("hw", 201916070203L, 100, 95, 100);
//        Student yt = new Student("yt", 201916070204L, 99, 95, 100);
//        Student zh = new Student("zh", 201916070205L, 99, 99, 99);
//
//        stuList.add(zh);
//        stuList.add(wy);
//        stuList.add(cdc);
//        stuList.add(lzh);
//        stuList.add(hw);
//        stuList.add(yt);
//        stuList.save();
//        System.out.println("============我是分割线===============");

//        System.out.println("============我是分割线===============");
//        //展示所有信息
//        stuList.dispAll();
//
//        System.out.println("============我是分割线===============");
//        //按id查找
//        stuList.findById(201916070216L);
//
//        System.out.println("============我是分割线===============");
//        //按名字查找
//        stuList.findByName("wy");
//
//        System.out.println("============我是分割线===============");
//        //按id删除信息
//        stuList.delById(201916070204L);
//        //退出时保存数据
//        System.out.println("============我是分割线===============");

    }

    public void add(Student stu) {
        //判断是否扩容，count大于10就开始扩容机制
        if (count >= 10) {
            System.out.println("Start to expand....");
            //按二倍进行扩容
            Student[] students1 = Arrays.copyOf(students, count * 2);
            //将原数组指向新开辟的堆空间
            students = students1;
            //销毁多余的引用
            students1 = null;
        }
        //add stu进入数组
        students[count] = stu;
        System.out.println("Data added successfully!");
        //更新count
        count++;
    }

    public void dispAll() {
        System.out.println("All information is as follows:>");
        //遍历数组，如果元素不为null则输出
        for (int i = 0; i < count; i++) {
            if (students[i] != null) {
                System.out.println(students[i]);
            }
        }
    }

    public void findById(long id) {
        int flag = 0; //记录次数
        for (int i = 0; i < count; i++) {
            //遍历数组，匹配到合适的元素则输出
            if (students[i] != null && id == students[i].getId()) {
                System.out.println("Information found successfully by Id!");
                System.out.println(students[i]);
                break;
            } else {
                //没有匹配到则将标志位flag++，当flag==count时，
                //也就是遍历完了还没找到合适的元素，此时提示找不到
                flag++;
                if (flag == count) {
                    System.out.println("Sorry, no student information that " +
                            "meets the conditions is found!");
                }
            }
        }
    }

    public void findByName(String name) {
        int flag = 0; //标志位，记录没找到的次数
        for (int i = 0; i < count; i++) {
            //遍历匹配，匹配到合适的元素则退出
            if (students[i] != null && name.equalsIgnoreCase(students[i].getName())) {
                System.out.println("Information found successfully by name!");
                System.out.println(students[i]);
                break;
            } else {
                //每次没有匹配到都将flag++，当flag==count时
                //也就是遍历完了还没找到合适的元素，此时提示找不到
                flag++;
                if (flag == count) {
                    System.out.println("Sorry, no student information that " +
                            "meets the conditions is found!");
                }
            }
        }
    }

    public void delById(long id) {
        int flag = 0; // 记录没有找到的次数
        for (int i = 0; i < count; i++) {
            //跟前面的功能同理，不再展开
            if (students[i] != null && id == students[i].getId()
) {
                System.out.println("Successfully found the student information!");
                System.out.println(students[i]);
                students[i] = null;
                //count--;
                System.out.println("The student information has been successfully deleted!");
                break;
            } else {
                //跟上述方法同理
                flag++;
                if (flag == count) {
                    System.out.println("Sorry, no student information that " +
                            "meets the conditions is found!");
                }
            }
        }
    }

    //序列化
    public void save() {

        String filePath = "D:\\Users\\NingHai\\result.dat";

        ObjectOutputStream oos = null;
        try {
            oos = new ObjectOutputStream(new FileOutputStream(filePath));
            //写入文件
            oos.writeObject(students);
            System.out.println("Data serialization is saved!");

        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            try {
                //关闭外层处理流
                oos.close();
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }

    //反序列化
    public void load() {
        String filePath = "D:\\Users\\NingHai\\result.dat";
        ObjectInputStream ois = null;
        try {
            ois = new ObjectInputStream(new FileInputStream(filePath));
            //反序列化
            try {
                //转型
                Object[] objArr = (Object[]) ois.readObject();
                for (Object obj : objArr) {
                    //扩容
                    if (count >= 10) {
                        Student[] students1 = Arrays.copyOf(students, count * 2);
                        students = students1;
                        students1 = null;
                    }
                    //当元素不为null进行保存及输出
                    if (obj != null) {
                        students[count++] = (Student) obj;//每次读到一个就保存到数组中
                        System.out.println(obj);
                    }
                }
//                while (new FileInputStream(filePath).available() > 0) {
//                    Object obj = ois.readObject();
//                    System.out.println(obj);
//                }
//           //捕获异常
            } catch (ClassNotFoundException e) {
                e.printStackTrace();
            }
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            try {
                //关闭外层流
                ois.close();
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }

    public void showUI() {

        System.out.println("please input you choice:>");
        Scanner scanner = new Scanner(System.in); //扫描器
        do {
            System.out.println("==============================");
            System.out.println("1.显示所有学生信息     2.按学号查找");
            System.out.println("3.按姓名查找          4.按学号删除");
            System.out.println("5.保存信息            6.读入信息");
            System.out.println("7.添加学生            8.退出");
            System.out.println("==============================");

            int input = scanner.nextInt(); //读入一个值

            switch (input) {
                case 1:
                    dispAll(); //显示所有信息
                    break;
                case 2:
                    System.out.println("Please input your id:>");
                    long id = scanner.nextLong();
                    findById(id); //按id查找
                    break;
                case 3:
                    System.out.println("Please input your name:>");
                    String name = scanner.next();
                    findByName(name); //按name查找
                    break;
                case 4:
                    System.out.println("Please input your id:>");
                    long id1 = scanner.nextLong();
                    delById(id1); //按id删除
                    break;
                case 5:
                    save(); //序列化在文件中
                    break;
                case 6:
                    load(); //反序列化并保存在数组中
                    break;
                case 7:
                    Student student = new Student();//实例化一个学生
                    System.out.println("please input your name");
                    student.setName(scanner.next());
                    System.out.println("please input your id");
                    student.setId(scanner.nextLong());
                    System.out.println("please input your math score");
                    student.setMath(scanner.nextDouble());
                    System.out.println("please input your os score");
                    student.setOs(scanner.nextDouble());
                    System.out.println("please input your java score");
                    student.setJava(scanner.nextDouble());
                    add(student); //add stu
                    break;
                case 8:
                    //System.exit(1); //退出程序
                    return; //退出程序
            }
        } while (true);
    }
}

```

 

**【实验结果】**

第一次序列化保存到文件中的数据如下：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image002.jpg)

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image004.jpg)

第二次反序列化恢复到内存中的数据：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image006.jpg)

演示显示所有学生信息：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image008.jpg)

演示按学号查找：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image010.jpg)

演示按姓名查找：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image012.jpg)

演示按学号删除：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image014.jpg)

此时验证是否删除成功：

可以很明显的看到，201916070203同学已经被删除

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image016.jpg)

演示保存信息：

如图，已序列化保存

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image018.jpg)

演示读入信息：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image020.jpg)

演示添加学生：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image022.jpg)

可以看到已经添加成功：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image024.jpg)

演示退出：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image026.jpg)

 

**【实验体会】**

（至少150字）

本实验是实验一个简单的学生信息管理系统，较为基础，我们从大一到大三写过很多诸如此类的管理系统。实验的亮点是数据保存的序列化，要实现Serializable接口来让其对象能够被序列化。实现对象的序列化需要在StuList类中主要用到ObjectOutputStream处理流写入文件，实现序列化，用到ObjectInputStream处理流实现反序列化，将对象数据读入到内存中。

其他增删查改的小细节个人觉得没有什么难点，主要是注意细节，比如在删除操作时题目要求是删除对象，并置为null，并不是我们常用的尾删法。此外，我们还需主要到save跟load的时期，我们想要恢复上次的数据就必须在文件头load，在文件尾save，load操作时，为了保证数据能够可视化，我的解决方法时将数据保存在对象数组中，这样就能遍历查看。在add操作时，当数据达到上限时，主要需要适当扩容来实现更多数据的保存。基本的心得体会就是这样。