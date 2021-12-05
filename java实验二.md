# 河南工业大学

# 《JAVA程序设计》实验报告

专业班级： 物联网1902    学号： 201916070216   姓名： 王源   

**实验单元二**  **Java** **类的应用、继承**

**实验三** **Java****类的应用**

实验时间：  2021/10/12   

**【实验目的】**

1、定义自己的Java类。

2、能够应用类。

**【实验环境】**

JDK、IntelliJ IDEA

**【实验内容】**

1、输入两个矩阵，计算两个矩阵相乘，矩阵为int[][]或者double[][]都可以。声明一个方法，该方法接受参数，并返回计算的结果。

2、声明一个类，定义一个方法以计算一维数组中的最大值并返回该值，参数为int[]或double[]。在main方法中调用该方法，传递不同长度的数组，得到返回值并输出

3、声明一个Circle类有radius（double类型）属性，area方法返回圆面积。

4、设计一个人类Person，包含姓名，年龄，性别基本信息，修饰为私有的；定义构造方法，用来初始化基本信息；定义方法show，用来显示基本信息值。测试该类。（必做）

5、设计一个个人银行账号类，包含账户名、账户号码、所属银行属性，及存钱、取钱、查询余额方法，改写equals方法，当账户号码相等时返回TRUE。测试该类及其中的所有方法。（必做）

6、实现简单的计算器。定义名为Number的类其中有两个整型数据成员n1和n2应声明为私有。编写构造方法赋予n1和n2初始值再为该类定义加、减、乘、除等公有成员方法分别对两个成员变量执行加、减、乘、除的运算。在main方法中创建Number类的对象调用各个方法并显示计算结果。（选做）

7、定义一个Comment类，包括成员变量：int sex和int salary；方法void manOrWorman()：根据sex的值显示“man”(sex==1)或者“women”(sex==0)；方法void employeed()：根据salary的值显示“no job”(salary==0)或者“job”(salary!=0)。测试该类。（必做）

8、定义Book类，包括属性title（书名）、price（价格）及pub（出版社），pub的默认值是“在路上出版社”，并在该类中定义方法getInfo（），来显示三个属性的值。再定义一个公共类BookPress，其内包括主方法。在主方法中，定义3个Book类的实例b1，b2和b3，分别调用各个对象的getInfo（）方法，如果“在路上出版社”改为“天天向上出版社”，请在程序中实现b1，b2和b3的pub改名操作。完成功能后，思考:如果book类的实例众多，如何优化这样的批量改名操作？（选做）

9、定义一个交通工具(Vehicle)的类，有：属性速度(speed)体积(size)等等，方法移动(move())设置速度(setSpeed(int speed))加速speedUp(),减速speedDown()等等，并在测试类Vehicle中的main()中实例化一个交通工具对象并通过方法给它初始化speed，size的值并且通过打印出来。调用加速减速的方法改变其速度。（选做）

**【详细分析】**

（此项由学生自己完成）

\1.   输入两个矩阵，计算两个矩阵相乘，矩阵为int[][]或者double[][]都可以。声明一个方法，该方法接受参数，并返回计算的结果。

此题是让我们计算两个矩阵相乘的结果，我们可以把它推广为由我们控制的矩阵相乘，也就是不一定是3*3，可以两个矩阵能相乘，任意两个都能计算。

首先在main方法里new三个对象指向null，一个用来表示矩阵A，一个用来表示矩阵B，另一个用来表示相乘过后的矩阵。自己实现矩阵构造的方法，将构造初始化过后的对象地址返回给main方法的两个引用类型的变量。自己还需实现一个矩阵乘法的方法，将结果的地址返回给表示相乘的矩阵，这里需要注意的是，两个矩阵必须是可以相乘的，如果不满足条件直接return null；具体的矩阵乘法步骤可以看代码里的注释，这里不再展开。最后就是实现打印方法进行结果的打印就行了。

\2.   声明一个类，定义一个方法以计算一维数组中的最大值并返回该值，参数为int[]或double[]。在main方法中调用该方法，传递不同长度的数组，得到返回值并输出

此题让我们找出一个数组的最大值并返回，思路很简单，我们先定义一个

maxNum变量，让它等于数组的第一个元素，随后从第二个数开始遍历数组，如果有出现比maxNum大的元素，就把maxNum更新为此数，最终返回的就是数组的最大值。

可以考虑一下当数组的输入不规范，例如出现空数组时的情况，这时我们可以用一个if else来判断一下，提高代码的健壮性。

 

\3.   声明一个Circle类有radius（double类型）属性，area方法返回圆面积。

此题是让我们求圆面积，要求定义一个area方法，这是非常常规的，直接在area方法中return Math.PI * radius * radius就行了，在测试类中new一个对象来调用area方法即可。

 

\4.   设计一个人类Person，包含姓名，年龄，性别基本信息，修饰为私有的；定义构造方法，用来初始化基本信息；定义方法show，用来显示基本信息值。测试该类。（必做）

此题是考察基本的构造方法的定义，基本上没有什么值得分析的，就是如实描述出来，依据题意写一个构造方法来对属性进行初始化，随后在show方法中打印出属性，最后就是在测试类中new一个对象调用show方法打印信息。

\5.   设计一个个人银行账号类，包含账户名、账户号码、所属银行属性，及存钱、取钱、查询余额方法，改写equals方法，当账户号码相等时返回TRUE。测试该类及其中的所有方法。（必做）

本题主要考察equals方法的重写，equals方法时Object类的方法，当我们自己要使用时，通常是对其重写已达到我们自己想要的功能。需要注意的是，对equals方法重写的同时，需要重写hashCode方法，以满足hashCode的特性，此题较为基础。

 

\6.   实现简单的计算器。定义名为Number的类其中有两个整型数据成员n1和n2应声明为私有。编写构造方法赋予n1和n2初始值再为该类定义加、减、乘、除等公有成员方法分别对两个成员变量执行加、减、乘、除的运算。在main方法中创建Number类的对象调用各个方法并显示计算结果。（选做）

本题主要考察我们属性应该定义为私有，让外界调用公有的方法得到想要的结果，非常基础，无须赘述。

\7.   定义一个Comment类，包括成员变量：int sex和int salary；方法void manOrWorman()：根据sex的值显示“man”(sex==1)或者“women”(sex==0)；方法void employeed()：根据salary的值显示“no job”(salary==0)或者“job”(salary!=0)。测试该类。（必做）

本题考察分支语句，if else if，如实描述即可，完全按照要求做就行了。

\8.   定义Book类，包括属性title（书名）、price（价格）及pub（出版社），pub的默认值是“在路上出版社”，并在该类中定义方法getInfo（），来显示三个属性的值。再定义一个公共类BookPress，其内包括主方法。在主方法中，定义3个Book类的实例b1，b2和b3，分别调用各个对象的getInfo（）方法，如果“在路上出版社”改为“天天向上出版社”，请在程序中实现b1，b2和b3的pub改名操作。完成功能后，思考:如果book类的实例众多，如何优化这样的批量改名操作？（选做）

本题也是一样非常的基础，如实描述，跟着题目要求走，不需要额外的思考，实例化三个对象然后分别调用setPub改出版社，最后再逐个调用getInfo打印信息。

\9.   定义一个交通工具(Vehicle)的类，有：属性速度(speed)体积(size)等等，方法移动(move())设置速度(setSpeed(int speed))加速speedUp(),减速speedDown()等等，并在测试类Vehicle中的main()中实例化一个交通工具对象并通过方法给它初始化speed，size的值并且通过打印出来。调用加速减速的方法改变其速度。（选做）

本题依旧是面向过程的基础，考察我们对方法的定义和在另一个类里面实例化对象，无须赘述。

 

**【实验源码】**

（此项由学生自己完成）

\1.   输入两个矩阵，计算两个矩阵相乘，矩阵为int[][]或者double[][]都可以。声明一个方法，该方法接受参数，并返回计算的结果。

源码：

  **package** **com.haut.iot.assassin****;**     ***/\**\***   ***\* 1\******、输入两个矩阵，计算两个矩阵相乘，矩阵为\******int[][]\******或者\******double[][]\******都可以。\***   ***\**** ***声明一个方法，该方法接受参数，并返回计算的结果。\***   ***\*/\***     **//import java.util.Arrays; //****配合****Arrays.deepToString**  **import** **java.util.Scanner****;**        **public class** **TestDemo01 {**    **//main**    **public static void** **main****(String[] args) {**         **//boolean count = false; //****判断一下是创建矩阵****A****还是矩阵****B**      **int****[][] matrixA****;** **//new****一个矩阵****A****对象**      **int****[][] matrixB****;** **//new****一个矩阵****B****对象**      **int****[][] matrixRet****;** **//new****一个矩阵****result****对象**         **matrixA = \*createMatrix\*()****;**  **//****让****matrixA****指向创建好的对象**      **matrixB = \*createMatrix\*()****;**  **//****让****matrixB****指向创建好的对象**      **matrixRet = \*multiplyMatrix\*(matrixA****,** **matrixB)****;** **// //****让****matrixRet****指向相乘结果的对象**         **System.*****out\*****.println(****"The value of the matrix multiplied> "****)****;**      **//System.out.println(Arrays.deepToString(matrixRet));**      **//****可以直接调用****Arrays****类的****deepToString****函数直接打印**      **assert** **matrixRet !=** **null;** **//****断言 如果是空对象直接抛空指针异常**      ***printMatrix\*****(matrixRet)****;**       **}**       **//****构造函数，构造矩阵**    **public static int****[][]** **createMatrix****() {**         **Scanner scan =** **new** **Scanner(System.*****in\*****)****;**      **System.*****out\*****.println(****"please enter the row of the matrix> "****)****;** **//****输入行数**      **int** **row = scan.nextInt()****;** **//****行**      **System.*****out\*****.println(****"please enter the column of the matrix> "****)****;** **//****输入列数**      **int** **col = scan.nextInt()****;** **//****列**      **int****[][] matrixTemp =** **new int****[row][col]****;**      **System.*****out\*****.println(****"please enter the values of the matrix> "****)****;** **//****输入矩阵的值**         **for** **(****int** **i =** **0****;** **i < row****;** **i++) {** **//****给矩阵赋值**        **for** **(****int** **j =** **0****;** **j < col****;** **j++) {**          **matrixTemp[i][j] =  scan.nextInt()****;**        **}**      **}**       **return** **matrixTemp****;**    **}**       **//****乘法函数，矩阵相乘**    **public static int****[][]** **multiplyMatrix****(****int****[][] matrixA****, int****[][] matrixB) {**      **if** **(matrixA[****0****].****length** **!=  matrixB.****length****) {**        **System.*****out\*****.println(****"Your input is wrong> "****)****;** **//****输入的矩阵****A****的行不等于矩阵****B****的列，无法进行乘法计算**        **return null;** **//****返回****null****对象**      **}** **else** **{**        **int****[][] matrixRet =** **new int****[matrixA.****length****][matrixB[****0****].****length****]****;**        **//****矩阵****A****的第****i****行与矩阵****B****的每一列相乘，最外层矩阵****A****总共走的次数，也就是矩阵****A****的行数**        **for** **(****int** **i =** **0****;** **i < matrixA.****length****;** **i++) {**           **//****矩阵****A****的每一行都要依次跟矩阵****B****的每一列相乘，走矩阵****B****的列数次**          **for** **(****int** **j =** **0****;** **j < matrixB[****0****].****length****;** **j++) {**            **for** **(****int** **k =** **0****;** **k < matrixA[****0****].****length****;** **k++) {** **//****每次相乘完都要把结果相加**              **//** **矩阵****A****有多少行（矩阵****B****有多少列）就加多少次**              **matrixRet[i][j] += matrixA[i][k] \* matrixB[k][j]****;**            **}**          **}**        **}**        **return** **matrixRet****;**      **}**    **}**       **//****打印函数****,****范围****for/for each**    **public static void** **printMatrix****(****int****[][] matrix) {** **//****增强****for****循环 打印出****ret****矩阵结果**       **for** **(****int****[] ints  : matrix) {**        **for** **(****int** **anInt :  ints) {**           **System.*****out\*****.print(anInt  +** **"****\t****"****)****;**        **}**        **System.*****out\*****.println()****;**      **}**    **}**  **}**     

\2.   声明一个类，定义一个方法以计算一维数组中的最大值并返回该值，参数为int[]或double[]。在main方法中调用该方法，传递不同长度的数组，得到返回值并输出。

源码：

  **package** **com.haut.iot.assassin****;**     ***/\**\***   ***\* 2\******、声明一个类，定义一个方法以计算一维数组中的最大值并返回该值，参数为\******int[]\******或\******double[]\******。\***   ***\**** ***在\******main\******方法中调用该方法，传递不同长度的数组，得到返回值并输出\***   ***\*/\***     **public class** **TestDemo02 {**    **public static void** **main****(String[] args) {**      **double****[] arr1 = {****1.0****,** **2.0****,** **3.0****,** **4.0****,** **5.0****}****;** **//****定义一个数组**      **double** **maxNum = \*getMax\*(arr1)****;**      **System.*****out\*****.println(****"****第一个数组的最大值为：****"** **+ maxNum)****;****//****打印最大值**         **double****[] arr2 = {-****2.4****,** **2.0****,** **3.0****,** **7.7****,** **5.0****,** **12.3****}****;****//****再定义一个不同长度的数组进行对照**      **maxNum = \*getMax\*(arr2)****;**      **System.*****out\*****.println(****"****第二个数组的最大值为：****"** **+  maxNum)****;****//****打印最大值**       **}**    **public static double** **getMax****(****double****[] arr) {**      **double** **max = arr[****0****]****;** **//****默认数组的第一个元素为最大值**      **for** **(****int** **i =** **1****;** **i < arr.****length****;** **i++) {** **//****从数组的第二个数开始遍历**        **if** **(max < arr[i]) {** **//****如果数组中有数大于****max****，就将这个数赋值给****max**           **max = arr[i]****;**        **}**      **}**      **//****退出循环后****max****便是数组的最大值**      **return** **max****;** **//****返回数组的最大值**    **}**  **}**     

 

\3.   声明一个Circle类有radius（double类型）属性，area方法返回圆面积。

源码：

  **package** **com.haut.iot.assassin****;**     ***/\**\***   ***\* 3\******、声明一个\******Circle\******类有\******radius\******（\******double\******类型）属性，\***   ***\* area\******方法返回圆面积。\***   ***\*/\***  **class** **Circle {**    **double** **radius****;****//****半径属性**       **public** **Circle****(****double** **radius) {** **//****构造方法，初始化****radius**      **this****.****radius** **= radius****;**    **}**       **public double** **area****() {** **//****调用****Math****类的****PI****计算面积**      **return** **Math.*****PI\*** ***** **radius** ***** **radius****;** **//****返回面积**    **}**  **}**  **//****测试类**  **public class** **TestDemo03 {**    **public static void** **main****(String[] args) {**      **Circle circle =** **new** **Circle(****2.0****)****;****//new****一个****Circle****对象**      **double** **areaRet =  circle.area()****;****//****调用****area****方法获取面积**      **System.*****out\*****.printf(****"****圆的面积是：****%.4f"****,****areaRet)****;****//****类似于****C/C++****的控制格式输出**    **}**     **}**  

\4.   设计一个人类Person，包含姓名，年龄，性别基本信息，修饰为私有的；定义构造方法，用来初始化基本信息；定义方法show，用来显示基本信息值。测试该类。（必做）

源码：

  **package** **com.haut.iot.assassin****;**     ***/\**\***   ***\* 4\******、设计一个人类\******Person\******，包含姓名，年龄，性别基本信息，修饰为私有的；\***   ***\**** ***定义构造方法，用来初始化基本信息；定义方法\******show\******，用来显示基本信息值。\***   ***\**** ***测试该类。（必做）\***   ***\*/\***     **class** **Person {**    **private** **String** **name****;** **//****姓名**    **private int** **age****;** **//****年龄**    **private** **String** **sex****;** **//****性别**       **public** **Person****() {** **//****习惯性的保留一个空参构造**      **//*****TODO\*** ***空参构造\***    **}**       **public** **Person****(String name****, int** **age****,** **String sex) {****//****构造方法进行属性的初始化**      **this****.****name** **= name****;**      **this****.****age** **= age****;**      **this****.****sex** **= sex****;**    **}**       **public void** **show****() {** **//show****方法打印出对象信息**      **System.*****out\*****.println(****"-----------------****\n****基本信息如下：****"****)****;**      **System.*****out\*****.println(****"****姓名：****"** **+** **this****.****name****)****;**      **System.*****out\*****.println(****"****年龄：****"** **+** **this****.****age****)****;**      **System.*****out\*****.println(****"****性别：****"** **+** **this****.****sex****)****;**    **}**  **}**     **public class** **TestDemo04 {**    **public static void** **main****(String[] args) {**      **Person person =** **new** **Person(****"****王源****"****,** **20****,** **"****男****"****)****;****//new****一个****Person****对象**      **person.show()****;****//****对象调用****show****方法显示信息**    **}**  **}**  

\5.   设计一个个人银行账号类，包含账户名、账户号码、所属银行属性，及存钱、取钱、查询余额方法，改写equals方法，当账户号码相等时返回TRUE。测试该类及其中的所有方法。（必做）

源码：

  **package** **com.haut.iot.assassin****;**     **import** **java.util.Objects****;**     ***/\**\***   ***\* 5\******、设计一个个人银行账号类，包含账户名、账户号码、所属银行属性，\***   ***\**** ***及存钱、取钱、查询余额方法，改写\******equals\******方法，当账户号码相等时返回\******TRUE\******。\***   ***\**** ***测试该类及其中的所有方法。（必做）\***   ***\*/\***     **class** **BankAccount {**    **private** **String** **countName****;** **//****账户名**    **private** **String** **countNum****;** **//****账户号码**    **private** **String** **countOwned****;** **//****所属银行**       **//****构造方法，初始化属性**    **public** **BankAccount****(String countName****,** **String countNum****,** **String countOwned)  {**      **this****.****countName** **= countName****;**      **this****.****countNum** **= countNum****;**      **this****.****countOwned** **= countOwned****;**    **}**       **public void** **saving****() {** **//****存钱方法**      **System.*****out\*****.println(****"hi,****这里是存钱****!"****)****;**    **}**       **public void** **takeOut****() {****//****取钱方法**      **System.*****out\*****.println(****"hi,****这里是取钱****!"****)****;**    **}**       **public void** **checkOut****() {****//****查询方法**      **System.*****out\*****.println(****"hi,****这里是查询余额****!"****)****;**    **}**       **@Override**    **public boolean** **equals****(Object obj) {****//****重写****Object****的****equals****方法**      **if** **(****this** **== obj)  {****//****如果是同一个对象直接返回****true****，提高效率**         **return true;**      **}**      **//****如果传进来的对象为****null****或者****obj****对象不是****BankAccount****类的实例，直接返回****false**      **if** **(obj ==** **null** **|| !(obj**  **instanceof** **BankAccount)) {**        **return false;**      **}**      **BankAccount bankAccount =  (BankAccount) obj****;****//****向下转型**      **//****调用****String****的****equals****方法判断账户号码是否相同，相同返回****true****，不同返回****false**      **return** **countNum****.equals(bankAccount.****countNum****)****;**    **}**       **@Override**    **public int** **hashCode****() {** **//****重写****hashCode(),****相同对象****hashCode****必须相同**      **return** **Objects.\*hash\*(****countNum****)****;**    **}**  **}**        **public class** **TestDemo05 {**    **public static void** **main****(String[] args) {**      **BankAccount bankAccount1 =** **new** **BankAccount(****"****王源****"****,****"666666"****,****"****工商银行****"****)****;**        **BankAccount bankAccount2 =** **new** **BankAccount(****"****王源****"****,****"666666"****,****"****工商银行****"****)****;**         **System.*****out\*****.println(****"=============****方法调用****=============="****)****;**      **bankAccount1.saving()****;**      **bankAccount1.takeOut()****;**      **bankAccount1.checkOut()****;**         **System.*****out\*****.println(****"============equals()****重写****=========="****)****;**      **System.*****out\*****.println(****"bankAccount1** **对比** **bankAccount2** **：****"** **+ bankAccount1.equals(bankAccount2))****;**      **System.*****out\*****.println(****"============hashCode()============"****)****;**      **System.*****out\*****.println(bankAccount1.hashCode())****;**      **System.*****out\*****.println(bankAccount2.hashCode())****;**          **}**  **}**  

 

\6.   实现简单的计算器。定义名为Number的类其中有两个整型数据成员n1和n2应声明为私有。编写构造方法赋予n1和n2初始值再为该类定义加、减、乘、除等公有成员方法分别对两个成员变量执行加、减、乘、除的运算。在main方法中创建Number类的对象调用各个方法并显示计算结果。（选做）

源码：

  **package** **com.haut.iot.assassin****;**     ***/\**\***   ***\* 6\******、实现简单的计算器。定义名为\******Number\******的类其中有两个整型数据成员\******n1\******和\******n2\******应声明为私有。\***   ***\**** ***编写构造方法赋予\******n1\******和\******n2\******初始值再为该类定义加、减、乘、除等公有成员方法\***   ***\**** ***分别对两个成员变量执行加、减、乘、除的运算。\***   ***\**** ***在\******main\******方法中创建\******Number\******类的对象调用各个方法并显示计算结果。（选做）\***   ***\*/\***  **class** **Number {**    **private int** **n1****;** **//****整型变量**    **private int** **n2****;**       **public** **Number****(****int** **n1****, int** **n2) {** **//****构造方法，初始化属性**      **this****.****n1** **= n1****;**      **this****.****n2** **= n2****;**    **}**       **public int** **add****() {** **//****加法**      **return this****.****n1** **+** **this****.****n2****;**     **}**    **public int** **sub****() {** **//****减法**      **return this****.****n1** **-** **this****.****n2****;**    **}**    **public int** **mul****() {** **//****乘法**      **return this****.****n1** ***** **this****.****n2****;**    **}**    **public int** **div****() {** **//****除法**      **return this****.****n1** **/** **this****.****n2****;**    **}**  **}**     **public class** **TestDemo06 {**    **public static void** **main****(String[] args) {**      **Number number =** **new** **Number(****10****,** **5****)****;** **//new****一个****number****对象**      **System.*****out\*****.println(****"****加法：****"** **+  number.add())****;****//****加**      **System.*****out\*****.println(****"****减法：****"** **+  number.sub())****;****//****减**      **System.*****out\*****.println(****"****乘法：****"** **+  number.mul())****;****//****乘**      **System.*****out\*****.println(****"****除法：****"** **+  number.div())****;****//****除**    **}**  **}**  

\7.   定义一个Comment类，包括成员变量：int sex和int salary；方法void manOrWorman()：根据sex的值显示“man”(sex==1)或者“women”(sex==0)；方法void employeed()：根据salary的值显示“no job”(salary==0)或者“job”(salary!=0)。测试该类。（必做）

源码：

  **package** **com.haut.iot.assassin****;**     ***/\**\***   ***\* 7\******、定义一个\******Comment\******类，包括成员变量：\******int sex\******和\******int salary\******；方法\******void manOrWoman()\******：\***   ***\**** ***根据\******sex\******的值显示\******“man”(sex==1)\******或者\******“women”(sex==0)\******；\***   ***\**** ***方法\******void employed()\******：根据\******salary\******的值显示\******“no job”(salary==0)\******或者\******“job”(salary!=0)\******。\***   ***\**** ***测试该类。（必做）\***   ***\*/\***     **class** **Comment {**    **private int** **sex****;** **//****性别**    **private int** **salary****;** **//****薪水**       **public** **Comment****(****int** **sex****, int** **salary) {** **//****构造方法，初始化属性**      **setSex(sex)****;**      **setSalary(salary)****;**    **}**       **public void** **setSex****(****int** **sex) {** **//set** **性别**      **this****.****sex** **= sex****;**    **}**       **public void** **setSalary****(****int** **salary) {** **//set** **薪水**      **this****.****salary** **= salary****;**    **}**       **public void** **manOrWoman****() {** **//****判断男或女**      **if** **(****sex** **==** **1****) {**        **System.*****out\*****.println(****"man"****)****;**       **}** **else if** **(****sex** **==** **0****) {**        **System.*****out\*****.println(****"woman"****)****;**      **}**    **}**    **public void** **employed****() {** **//****判断有无工作**      **if** **(****salary** **==** **0****) {**        **System.*****out\*****.println(****"no job"****)****;**      **}** **else** **{**        **System.*****out\*****.println(****"job"****)****;**      **}**    **}**  **}**     **public class** **TestDemo07 {**    **public static void** **main****(String[] args) {**      **Comment comment =** **new** **Comment(****1****,** **100****)****;** **//new****一个****comment****对象**         **//****调用****manOrWoman****判断男或女**      **comment.manOrWoman()****;**      **//****调用****employed****方法判断有无工作**       **comment.employed()****;**       **}**  **}**  

\8.   定义Book类，包括属性title（书名）、price（价格）及pub（出版社），pub的默认值是“在路上出版社”，并在该类中定义方法getInfo（），来显示三个属性的值。再定义一个公共类BookPress，其内包括主方法。在主方法中，定义3个Book类的实例b1，b2和b3，分别调用各个对象的getInfo（）方法，如果“在路上出版社”改为“天天向上出版社”，请在程序中实现b1，b2和b3的pub改名操作。完成功能后，思考:如果book类的实例众多，如何优化这样的批量改名操作？（选做）

源码：

  **package** **com.haut.iot.assassin****;**     ***/\**\***   ***\* 8\******、定义\******Book\******类，包括属性\******title\******（书名）、\******price\******（价格）及\******pub\******（出版社），\***   ***\* pub\******的默认值是\******“\******在路上出版社\******”\******，并在该类中定义方法\******getInfo\******（），来显示三个属性的值。\***   ***\**** ***再定义一个公共类\******BookPress\******，其内包括主方法。\***   ***\**** ***在主方法中，定义\******3\******个\******Book\******类的实例\******b1\******，\******b2\******和\******b3\******，分别调用各个对象的\******getInfo\******（）方法，\***   ***\**** ***如果\******“\******在路上出版社\******”\******改为\******“\******天天向上出版社\******”\******，请在程序中实现\******b1\******，\******b2\******和\******b3\******的\******pub\******改名操作。\***   ***\**** ***完成功能后，思考\******:\******如果\******book\******类的实例众多，如何优化这样的批量改名操作？（选做）\***   ***\*/\***        **class** **Book {**    **private** **String** **title****;**    **private double** **price****;**    **private** **String** **pub** **=** **"****在路上出版社****"****;**       **public** **Book****() {** **//****习惯性的给一个无参构造**      **//*****TODO\*** ***无参构造\***    **}**       **//****有参构造，初始化属性**    **public** **Book****(String title****, double** **price) {**      **setTitle(title)****;**      **setPrice(price)****;**    **}**       **public void** **getInfo****() {** **//****获取属性**      **System.*****out\*****.println(****"****书名：****"** **+** **title****)****;**      **System.*****out\*****.println(****"****价格：****"** **+** **price****)****;**      **System.*****out\*****.println(****"****出版社：****"** **+** **pub****)****;**    **}**       **public** **String** **getTitle****() {** **//get title**      **return** **title****;**    **}**       **public void** **setTitle****(String title) {** **//set title**      **this****.****title** **= title****;**    **}**       **public double** **getPrice****() {** **//get price**      **return** **price****;**    **}**       **public void** **setPrice****(****double** **price) {** **//set price**      **this****.****price** **= price****;**    **}**       **public** **String** **getPub****() {** **//get pub**      **return** **pub****;**    **}**       **public void** **setPub****(String pub) {** **//set pub**      **this****.****pub** **= pub****;**    **}**        **}**     **public class** **BookPress {**    **public static void** **main****(String[] args) {**      **Book book1 =** **new** **Book(****"****西游记****"****,****30.0****)****;** **//****对象****1**      **Book book2 =** **new** **Book(****"****红楼梦****"****,****55.9****)****;** **//****对象****2**      **Book book3 =** **new** **Book(****"****三国演义****"****,****62.5****)****;** **//****对象****3**         **//show** **属性**      **book1.getInfo()****;**      **System.*****out\*****.println(****"--------------"****)****;**         **book2.getInfo()****;**      **System.*****out\*****.println(****"--------------"****)****;**         **book3.getInfo()****;**         **System.*****out\*****.println(****"****\n****======****测试改出版社****======"****)****;**      **//****改出版社，以****book1****为例**      **book1.setPub(****"****天天向上出版社****"****)****;**      **book1.getInfo()****;**         **System.*****out\*****.println(****"---------------"****)****;**         **book2.setPub(****"****天天向上出版社****"****)****;**      **book2.getInfo()****;**         **System.*****out\*****.println(****"---------------"****)****;**         **book3.setPub(****"****天天向上出版社****"****)****;**      **book3.getInfo()****;**    **}**  **}**  

\9.   定义一个交通工具(Vehicle)的类，有：属性速度(speed)体积(size)等等，方法移动(move())设置速度(setSpeed(int speed))加速speedUp(),减速speedDown()等等，并在测试类Vehicle中的main()中实例化一个交通工具对象并通过方法给它初始化speed，size的值并且通过打印出来。调用加速减速的方法改变其速度。（选做）

源码：

  **package** **com.haut.iot.assassin****;**     ***/\**\***   ***\* 9\******、定义一个交通工具\******(Vehicle)\******的类，有：属性速度\******(speed)\******体积\******(size)\******等等，\***   ***\**** ***方法移动\******(move())\******设置速度\******(setSpeed(int speed))\******加速\******speedUp(),\***   ***\**** ***减速\******speedDown()\******等等，并在测试类\******Vehicle\******中的\******main()\******中实例化一个交通工具对象\***   ***\**** ***并通过方法给它初始化\******speed\******，\******size\******的值并且通过打印出来。\***   ***\**** ***调用加速减速的方法改变其速度。（选做）\***   ***\*/\***     **class** **Vehicle {**    **private int** **speed****;**    **private double** **size****;**    **private double** **weight****;**       **public void** **move****() {** **//move****方法**      **System.*****out\*****.println(****"****我正在****move~"****)****;**    **}**       **public void** **setSpeed****(****int** **speed) {** **//****初始化设置****speed**      **this****.****speed** **= speed****;**    **}**       **public void** **setSize****(****double** **size) {** **//****初始化****size**      **this****.****size** **= size****;**    **}**       **public void** **speedUp****() {** **//****加速方法**      **this****.****speed** **+=** **5****;**       **}**       **public void** **speedDown****() {** **//****减速方法**      **this****.****speed** **-=** **5****;**    **}**       **public void** **showAll****() {**      **System.*****out\*****.println(****"speed: "** **+** **speed****)****;**      **System.*****out\*****.println(****"size: "** **+** **size****)****;**    **}**  **}**     **public class** **TestDemo09 {**    **public static void** **main****(String[] args) {**        **Vehicle vehicle =** **new** **Vehicle()****;**      **//****初始化属性**      **vehicle.setSize(****100****)****;**      **vehicle.setSpeed(****10****)****;**      **//****打印属性信息**      **vehicle.showAll()****;**         **System.*****out\*****.println(****"----------"****)****;**         **vehicle.speedUp()****;****//****加速****5**      **System.*****out\*****.println(****"****加速后：****"****)****;**         **//****打印属性信息**      **vehicle.showAll()****;**         **System.*****out\*****.println(****"----------"****)****;**         **System.*****out\*****.println(****"****减速后：****"****)****;**         **vehicle.speedDown()****;****//****减速****5**      **//****打印属性信息**      **vehicle.showAll()****;**       **}**  **}**  

 

**【实验结果】**

（截图给出实验结果）

\1.   输入两个矩阵，计算两个矩阵相乘，矩阵为int[][]或者double[][]都可以。声明一个方法，该方法接受参数，并返回计算的结果。

**代码概览：**

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image002.jpg)

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image004.jpg)

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image006.jpg)

\2.   声明一个类，定义一个方法以计算一维数组中的最大值并返回该值，参数为int[]或double[]。在main方法中调用该方法，传递不同长度的数组，得到返回值并输出

代码概览：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image008.jpg)

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image010.jpg)

\3.   声明一个Circle类有radius（double类型）属性，area方法返回圆面积。

代码概览：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image012.jpg)

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image014.jpg)

\4.   设计一个人类Person，包含姓名，年龄，性别基本信息，修饰为私有的；定义构造方法，用来初始化基本信息；定义方法show，用来显示基本信息值。测试该类。（必做）

代码概览：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image016.jpg)

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image018.jpg)

\5.   设计一个个人银行账号类，包含账户名、账户号码、所属银行属性，及存钱、取钱、查询余额方法，改写equals方法，当账户号码相等时返回TRUE。测试该类及其中的所有方法。（必做）

代码概览：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image020.jpg)

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image022.jpg)

运行结果：

账户号码不同时：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image024.jpg)

账户号码相同时：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image026.jpg)

 

\6.   实现简单的计算器。定义名为Number的类其中有两个整型数据成员n1和n2应声明为私有。编写构造方法赋予n1和n2初始值再为该类定义加、减、乘、除等公有成员方法分别对两个成员变量执行加、减、乘、除的运算。在main方法中创建Number类的对象调用各个方法并显示计算结果。（选做）

代码概览：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image028.jpg)

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image030.jpg)

\7.   定义一个Comment类，包括成员变量：int sex和int salary；方法void manOrWorman()：根据sex的值显示“man”(sex==1)或者“women”(sex==0)；方法void employeed()：根据salary的值显示“no job”(salary==0)或者“job”(salary!=0)。测试该类。（必做）

代码概览：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image032.jpg)

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image034.jpg)

\8.   定义Book类，包括属性title（书名）、price（价格）及pub（出版社），pub的默认值是“在路上出版社”，并在该类中定义方法getInfo（），来显示三个属性的值。再定义一个公共类BookPress，其内包括主方法。在主方法中，定义3个Book类的实例b1，b2和b3，分别调用各个对象的getInfo（）方法，如果“在路上出版社”改为“天天向上出版社”，请在程序中实现b1，b2和b3的pub改名操作。完成功能后，思考:如果book类的实例众多，如何优化这样的批量改名操作？（选做）

代码概览：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image036.jpg)

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image038.jpg)

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image040.jpg)

改出版社后：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image042.jpg)

思考：

如果想批量修改，实例对象用对象数组，批量修改用for循环语句就可以了。

\9.   定义一个交通工具(Vehicle)的类，有：属性速度(speed)体积(size)等等，方法移动(move())设置速度(setSpeed(int speed))加速speedUp(),减速speedDown()等等，并在测试类Vehicle中的main()中实例化一个交通工具对象并通过方法给它初始化speed，size的值并且通过打印出来。调用加速减速的方法改变其速度。（选做）

代码概览：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image044.jpg)

 

 

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image046.jpg)

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image048.jpg)

 

 

 

 

 

 

**【实验体会】**

（至少150字）

\1.   第1题是让我们计算两个矩阵相乘的结果，我们可以把它推广为由我们控制的矩阵相乘，也就是不一定是3*3，可以两个矩阵能相乘，任意两个都能计算。

首先在main方法里new三个对象指向null，一个用来表示矩阵A，一个用来表示矩阵B，另一个用来表示相乘过后的矩阵。自己实现矩阵构造的方法，将构造初始化过后的对象地址返回给main方法的两个引用类型的变量。自己还需实现一个矩阵乘法的方法，将结果的地址返回给表示相乘的矩阵，这里需要注意的是，两个矩阵必须是可以相乘的，如果不满足条件直接return null；具体的矩阵乘法步骤可以看代码里的注释，这里不再展开。最后就是实现打印方法进行结果的打印就行了。

\2.   此题让我们找出一个数组的最大值并返回，思路很简单，我们先定义一个

maxNum变量，让它等于数组的第一个元素，随后从第二个数开始遍历数组，如果有出现比maxNum大的元素，就把maxNum更新为此数，最终返回的就是数组的最大值。

可以考虑一下当数组的输入不规范，例如出现空数组时的情况，这时我们可以用一个if else来判断一下，提高代码的健壮性。

 

\3.   此题是让我们求圆面积，要求定义一个area方法，这是非常常规的，直接在area方法中return Math.PI * radius * radius就行了，在测试类中new一个对象来调用area方法即可。

 

\4.   此题是考察基本的构造方法的定义，基本上没有什么值得分析的，就是如实描述出来，依据题意写一个构造方法来对属性进行初始化，随后在show方法中打印出属性，最后就是在测试类中new一个对象调用show方法打印信息。

\5.   本题主要考察equals方法的重写，equals方法时Object类的方法，当我们自己要使用时，通常是对其重写已达到我们自己想要的功能。需要注意的是，对equals方法重写的同时，需要重写hashCode方法，以满足hashCode的特性，此题较为基础。

 

\6.   本题主要考察我们属性应该定义为私有，让外界调用公有的方法得到想要的结果，非常基础，无须赘述。

\7.   本题考察分支语句，if else if，如实描述即可，完全按照要求做就行了。

\8.   本题也是一样非常的基础，如实描述，跟着题目要求走，不需要额外的思考，实例化三个对象然后分别调用setPub改出版社，最后再逐个调用getInfo打印信息。

\9.   本题依旧是面向过程的基础，考察我们对方法的定义和在另一个类里面实例化对象，无须赘述。

 

总的来说，比较基础，重点是考察面向对象的基本语法。

 

 



**实验四** **Java****继承、常用类的应用**

实验时间：  2021/10/13  

**【实验目的】**

掌握Java继承及常用类的应用。

**【实验环境】**

JDK、IntelliJ IDEA

**【实验内容】**

\1. 设计Shape表示图形类，有面积属性area、周长属性per，颜色属性color，有两个构造方法（一个是默认的、一个是为颜色赋值的），还有3个抽象方法，分别是：getArea计算面积、getPer计算周长、showAll输出所有信息，还有一个求颜色的方法getColor。

（1）设计2个子类：一个Rectangle表示矩形类，增加两个属性，Width表示长度、height表示宽度，重写getPer、getArea和showAll三个方法，另外又增加一个构造方法（一个是默认的、一个是为高度、宽度、颜色赋值的）。一个Circle表示圆类，增加1个属性，radius表示半径，重写getPer、getArea和showAll三个方法，另外又增加两个构造方法（为半径、颜色赋值的）。

（2）在main方法中，声明创建每个子类的对象，并调用2个子类的showAll方法。

2.描述Object类的功能及在java类中的位置；改写Object类的equals方法，判断创建的学生类（包含学号、姓名、年龄、性别属性及学习方法）创建的对象是否为同一个人，熟悉Object类中的toString（）方法，并对其功能进行测试，

3.选择Random类中的合适方法生成4位随机码（包括数字和英文字符）。并实现输入随机码，验证输入的验证码的正确与否。（要求生成随机码的功能用类中的方法实现）

4.定义两个数组，并输入数据，比较两个数组是否相等，并对数组进行排序，将第一个数组的部分数据拷贝到另一个数组中。

5.选择合适类的合适功能，制作个性化日历，显示当前日期格式为：yyyy-mm-dd，今天是星期*，上午/下午：hh-mm（时-分），距离毕业还有**天。

6.制作自己的三角函数计算器，包括：正弦、余弦、正切函数及它们的反函数。

**【详细分析】**

（此项由学生自己完成）

\1. 设计Shape表示图形类，有面积属性area、周长属性per，颜色属性color，有两个构造方法（一个是默认的、一个是为颜色赋值的），还有3个抽象方法，分别是：getArea计算面积、getPer计算周长、showAll输出所有信息，还有一个求颜色的方法getColor。

（1）设计2个子类：一个Rectangle表示矩形类，增加两个属性，Width表示长度、height表示宽度，重写getPer、getArea和showAll三个方法，另外又增加一个构造方法（一个是默认的、一个是为高度、宽度、颜色赋值的）。一个Circle表示圆类，增加1个属性，radius表示半径，重写getPer、getArea和showAll三个方法，另外又增加两个构造方法（为半径、颜色赋值的）。

（2）在main方法中，声明创建每个子类的对象，并调用2个子类的showAll方法。

本题主要考察继承和抽象类的编写。父类是Shape类，定义有area属性，per属性和color属性，在其中提供两个构造方法和三个抽象方法，有Rectangle和Circle两个子类继承并实现父类的抽象方法。本题很简单，如实描述即可。需要熟悉的是抽象类的细节，当一个类中写了抽象方法时，这个类也会相应地变成抽象类，而一个抽象类中不一定有抽象方法。

 

2.描述Object类的功能及在java类中的位置；改写Object类的equals方法，判断创建的学生类（包含学号、姓名、年龄、性别属性及学习方法）创建的对象是否为同一个人，熟悉Object类中的toString（）方法，并对其功能进行测试，

本题考察Object类对于java其他类的意义，我们知道Object类是所有类的父类。需要注意的是，重写Object类的equals方法的同时，需要重写hashCode方法，hashCode方法必须遵守的原则是同一个对象的哈希码相同。本题没有让我们重写toString方法，只是探究toString方法输出的结果，后面会谈到其输出的值为对象的全类名+@+哈希码的十六进制表示形式。

3.选择Random类中的合适方法生成4位随机码（包括数字和英文字符）。并实现输入随机码，验证输入的验证码的正确与否。（要求生成随机码的功能用类中的方法实现）

此题考察Random类的基本使用，生成四位随机码可以用三个for循环完成，开辟一个字符数组可以存储62个字符，分别是26个大写字母，26个小写字母加上10个数字，最后在for循环中用StringBuffer或者StringBuild进行拼接，形成四位随机码。验证随机码的逻辑可以直接调用String的equals方法或者自己实现一个可以忽略大小写的方法（这样会更贴切验证码的实际情况），后面会详细提到。

4.定义两个数组，并输入数据，比较两个数组是否相等，并对数组进行排序，将第一个数组的部分数据拷贝到另一个数组中。

本题主要目的是考察我们对Arrays类的内置方法的掌握情况，比如sort方法和copyOf方法等，只要我们熟悉其使用就能很快地解决此问题，自己实现方法的话完全没有必要，这也是Java相比于C语言的优势所在，不需要造轮子。

5.选择合适类的合适功能，制作个性化日历，显示当前日期格式为：yyyy-mm-dd，今天是星期*，上午/下午：hh-mm（时-分），距离毕业还有**天。

本题主要是考察Date很Calendar两个类的使用，具体实现细节见实验结果展示。

值得注意的是，计算毕业剩余时间需要将时间格式化一下，格式化成天数最为直观。

6.制作自己的三角函数计算器，包括：正弦、余弦、正切函数及它们的反函数。

本题主要是考察我们对Math类中的三角函数方法掌握程度，我们可以直接调用Math类的各种方法来计算相应的三角函数，这极大地便捷了我们的日常使用，我这里稍微地对功能做了一些封装，让代码功能看起来更像一个计算器。

**【实验源码】**

（此项由学生自己完成）

\1. 设计Shape表示图形类，有面积属性area、周长属性per，颜色属性color，有两个构造方法（一个是默认的、一个是为颜色赋值的），还有3个抽象方法，分别是：getArea计算面积、getPer计算周长、showAll输出所有信息，还有一个求颜色的方法getColor。

（1）设计2个子类：一个Rectangle表示矩形类，增加两个属性，Width表示长度、height表示宽度，重写getPer、getArea和showAll三个方法，另外又增加一个构造方法（一个是默认的、一个是为高度、宽度、颜色赋值的）。一个Circle表示圆类，增加1个属性，radius表示半径，重写getPer、getArea和showAll三个方法，另外又增加两个构造方法（为半径、颜色赋值的）。

（2）在main方法中，声明创建每个子类的对象，并调用2个子类的showAll方法。

源码：Shape.java

  **package** **com.haut.iot.ninghai****;**     **public abstract class** **Shape {**    **protected double** **area****;** **//****面积**    **protected double** **per****;** **//****周长**    **private** **String** **color****;** **//****颜色**       **public** **Shape****() {****//****习惯性的加上空参构造**      **//*****TODO\*** ***空参构造\***    **}**       **public** **Shape****(String color) {****//****构造方法，初始化****color**      **this****.****color** **= color****;**    **}**       **public** **String** **getColor****() {****//****获取颜色信息**      **return** **color****;**    **}**       **//****三个抽象方法**    **public abstract double** **getArea****()****;** **//****子类实现****getArea**       **public abstract double** **getPer****()****;** **//****子类实现****getPer**       **public abstract void** **showAll****()****;** **//****子类实现****showAll**  **}**     

Rectangle.java

  **package** **com.haut.iot.ninghai****;**     **public class** **Rectangle** **extends** **Shape {**    **private double** **width****;** **//****宽**    **private double** **height****;** **//****长**       **public** **Rectangle****() {** **//****空参构造**      **//*****TODO\*** ***空参构造\***     **}**       **public** **Rectangle****(String color****, double** **width****, double** **height) {** **//****初始化高度，宽度和颜色**      **super****(color)****;**      **this****.****width** **= width****;**      **this****.****height** **= height****;**    **}**       **public double** **getArea****() {** **//****获取面积**      **area** **=** **width** ***** **height****;**      **return** **area****;**    **}**    **public double** **getPer****() {** **//****获取周长**      **per** **=** **2** *** (****width** **+** **height****)****;**      **return** **per****;**    **}**    **public void** **showAll****() {** **//****打印长方形基本信息**      **System.*****out\*****.println(****"****长方形的长：****"** **+** **this****.****height****)****;**      **System.*****out\*****.println(****"****长方形的宽：****"** **+** **this****.****width****)****;**       **System.*****out\*****.println(****"****长方形的颜色：****"** **+** **this****.getColor())****;**      **System.*****out\*****.println(****"****长方形的面积：****"** **+** **this****.getArea())****;**      **System.*****out\*****.println(****"****长方形的周长：****"** **+** **this****.getPer())****;**    **}**  **}**  

Circle.java

  **package** **com.haut.iot.ninghai****;**     **public class** **Circle** **extends** **Shape {**    **private double** **radius****;** **//****半径属性**       **public** **Circle****() {** **//****习惯性的加上空参构造**      **//*****TODO\*** ***空参构造\***    **}**       **public** **Circle****(String color****, double** **radius) {****//****构造方法初始化颜色和半径**      **super****(color)****;**      **this****.****radius** **= radius****;**    **}**       **public double** **getArea****() {** **//****获取面积**       **area** **= Math.*****PI\*** ***** **radius** ***** **radius****;**      **return** **area****;**    **}**    **public double** **getPer****() {** **//****获取周长**      **per** **=** **2** *** Math.*****PI\*** ***** **radius****;**      **return** **per****;**    **}**    **public void** **showAll****() {** **//****打印圆形基本信息**      **System.*****out\*****.println(****"****圆形的半径：****"** **+** **this****.****radius****)****;**       **System.*****out\*****.println(****"****圆形的颜色：****"** **+** **this****.getColor())****;**      **System.*****out\*****.printf(****"****圆形的的面积：****%.4f****\n****"****, this****.getArea())****;**      **System.*****out\*****.printf(****"****圆形的的周长：****%.4f"****, this****.getPer())****;**    **}**  **}**  

TestDemo01.java

| **package** **com.haut.iot.ninghai****;**     ***/\**\***   ***\* 1.\*** ***设计\******Shape\******表示图形类，有面积属性\******area\******、周长属性\******per\******，颜色属性\******color\******，\***   ***\**** ***有两个构造方法（一个是默认的、一个是为颜色赋值的），还有\******3\******个抽象方法，\***   ***\**** ***分别是：\******getArea\******计算面积、\******getPer\******计算周长、\******showAll\******输出所有信息，\***   ***\**** ***还有一个求颜色的方法\******getColor\******。\***   ***\**** ***（\******1\******）设计\******2\******个子类：一个\******Rectangle\******表示矩形类，增加两个属性，\***   ***\* Width\******表示长度、\******height\******表示宽度，重写\******getPer\******、\******getArea\******和\******showAll\******三个方法，\***   ***\**** ***另外又增加一个构造方法（一个是默认的、一个是为高度、宽度、颜色赋值的）。\***   ***\**** ***一个\******Circle\******表示圆类，增加\******1\******个属性，\******radius\******表示半径，重写\******getPer\******、\******getArea\******和\******showAll\******三个方法，\***   ***\**** ***另外又增加两个构造方法（为半径、颜色赋值的）。\***   ***\**** ***（\******2\******）在\******main\******方法中，声明创建每个子类的对象，并调用\******2\******个子类的\******showAll\******方法。\***   ***\*/\***     **public class** **TestDemo01 {**    **public static void** **main****(String[] args) {**      **Rectangle rectangle =** **new** **Rectangle(****"red"****,** **2.0****,** **3.0****)****;****//****长方形对象**      **rectangle.showAll()****;** **//****调用****showAll****打印信息**         **System.*****out\*****.println(****"==================================="****)****;****//****分割线**         **Circle circle =** **new** **Circle(****"blue"****,** **3.0****)****;** **//****圆形对象**      **circle.showAll()****;** **//****调用****showAll****打印信息**    **}**  **}** |
| ------------------------------------------------------------ |
|                                                              |

 

2.描述Object类的功能及在java类中的位置；改写Object类的equals方法，判断创建的学生类（包含学号、姓名、年龄、性别属性及学习方法）创建的对象是否为同一个人，熟悉Object类中的toString（）方法，并对其功能进行测试，

源代码：

  **package** **com.haut.iot.ninghai****;**     **import** **java.util.Objects****;**     ***/\**\***   ***\* 2.\******描述\******Object\******类的功能及在\******java\******类中的位置；\***   ***\**** ***改写\******Object\******类的\******equals\******方法，判断创建的学生类\***   ***\**** ***（包含学号、姓名、年龄、性别属性及学习方法）创建的对象是否为同一个人，\***   ***\**** ***熟悉\******Object\******类中的\******toString\******（）方法，并对其功能进行测试，\***   ***\*/\***     **//Object****类是所有类的父类**     **class** **Student {**    **private int** **numId****;** **//****学号**    **private** **String** **name****;** **//****姓名**    **private int** **age****;** **//****年级**    **private** **String** **sex****;** **//****性别**       **//****构造方法，初始化属性**    **public** **Student****(****int** **numId****,** **String name****, int** **age****,** **String sex) {**      **this****.****numId** **= numId****;**      **this****.****name** **= name****;**      **this****.****age** **= age****;**       **this****.****sex** **= sex****;**    **}**       **//****学习方法函数**    **public void** **studyMethod****() {**      **System.*****out\*****.println(****"Interest in Learning to stay!"****)****;**    **}**       **@Override**    **public boolean** **equals****(Object obj) {****//****重写****Object****的****equals****方法**      **if** **(****this** **== obj)  {** **//****如果是同一个对象直接返回****true****，提高效率**        **return true;**      **}**         **//****如果传进来的对象为****null****或者****obj****对象不是****Student****类的实例，直接返回****false**      **if** **(obj ==** **null** **|| !(obj**  **instanceof** **Student)) {**        **return false;**      **}**  **//**    **用****getClass****代替****instanceof****效果会更好**  **//    if (obj == null || (getClass() !=  obj.getClass())) {**  **//      return false;**  **//    }**      **Student student = (Student) obj****;** **//****向下转型**      **//****如果属性都为****true****则返回****true****，有一个不为****true****则返回****false**      **return** **numId** **== student.****numId** **&&** **age** **==  student.****age** **&&**           **name****.equals(student.****name****)  &&** **sex****.equals(student.****sex****)****;**    **}**       **@Override**    **public int** **hashCode****() {** **//****重写****hashCode(),****相同对象****hashCode****必须相同**      **return** **Objects.\*hash\*(****numId****,** **name****,** **age****,** **sex****)****;**    **}**     **}**     **public class** **TestDemo02 {**    **public static void** **main****(String[] args) {**      **Student student1 =** **new** **Student(****16****,** **"****王源****"****,** **20****,** **"****男****"****)****;****//new****一个对象**      **Student student2 =** **new** **Student(****16****,** **"****王源****"****,** **20****,** **"****男****"****)****;****//new****另一个对象**            **//****结果为****true**      **System.*****out\*****.println(****"student1** **对比** **student2 : "** **+ student1.equals(student2))****;**         **System.*****out\*****.println(****"=================================="****)****;****//****分割线**         **System.*****out\*****.println(student1)****;****//****这条语句相当于****student.toString()**      **//****由此可见，****Object****类的****toString()****输出的是全类名****+ @ +** **十六进制的哈希码**       **}**     **}**  

 

3.选择Random类中的合适方法生成4位随机码（包括数字和英文字符）。并实现输入随机码，验证输入的验证码的正确与否。（要求生成随机码的功能用类中的方法实现）

源代码：

  **package** **com.haut.iot.ninghai****;**     **import** **java.util.Random****;**  **import** **java.util.Scanner****;**     ***/\**\***   ***\* 3.\******选择\******Random\******类中的合适方法生成\******4\******位随机码（包括数字和英文字符）。\***   ***\**** ***并实现输入随机码，验证输入的验证码的正确与否。\***   ***\**** ***（要求生成随机码的功能用类中的方法实现）\***   ***\*/\***     **class** **Func {**    **public** **StringBuilder** **identifyCode****(****char****[] arr) {**      **for** **(****int** **i =** **0****;** **i <** **26****;** **i++) {** **//****存储****26****个大写字母**        **arr[i] = (****char****)(****'A'** **+ i)****;**      **}**       **for** **(****int** **i =** **0****;** **i <** **26****;** **i++) {** **//****存储****26****个小写字母**        **arr[i +** **26****] = (****char****)(****'a'** **+ i)****;**      **}**      **for** **(****int** **i =** **0****;** **i <** **10****;** **i++) {** **//****存储****10****个数字**        **arr[i +** **52****] = (****char****)(****48** **+ i)****;**      **}**      **Random random =** **new** **Random()****;** **//new****一个****Random****对象**         **StringBuilder str =** **new** **StringBuilder()****;** **//****利用****StringBuilder****对象来实现字符串拼接**         **for** **(****int** **i =** **0****;** **i <** **4****;** **i++) {**        **str.append(arr[random.nextInt(****62****)])****;** **//****调用****append****方法循环四次实现拼接**      **}**      **return** **str****;**    **}**       **public boolean** **compare****(String ret****,** **StringBuilder str) {** **//****验证两字符串**      **char****[] arr1 = ret.toCharArray()****;**      **char****[] arr2 = str.toString().toCharArray()****;**      **int** **i =** **0****;****//****计数器**      **while** **(i < arr1.****length** **&&  ((arr1[i] == arr2[i]) || Math.\*abs\*(arr1[i] - arr2[i]) ==** **32****)) {**         **i++****;** **//****如果字符相同或者互为大小写，****i++**      **}**      **if** **(i != arr1.****length****) {** **//****如果****i****没有原数组的长度，说明两数组不相同**        **return false;**       **}** **else** **{**        **return true;**      **}**    **}**  **}**     **public class** **TestDemo03 {**    **public static void** **main****(String[] args) {**         **char****[] arr =** **new char****[****62****]****;** **//****大小字母****+****数字** **26 + 26 + 10**      **StringBuilder str =** **new** **StringBuilder()****;** **//****利用****StringBuilder****对象来实现字符串拼接**         **Func func =** **new** **Func()****;** **//new****一个对象**      **str = func.identifyCode(arr)****;** **//****生成随机码**      **System.*****out\*****.println(****"****验证码：****"** **+ str)****;**         **System.*****out\*****.println(****"Please input the identifying code:>"****)****;**      **Scanner scanner =** **new** **Scanner(System.*****in\*****)****;**      **String ret = scanner.nextLine()****;**         **if** **(func.compare(ret****,** **str)) {** **//****验证随机码的正确性**        **System.*****out\*****.println(****"Verification Successful!"****)****;**      **}** **else** **{**        **System.*****out\*****.println(****"You are wrong!"****)****;** **//****输入正确或错误都给出相应的提示**      **}**       **}**  **}**  

 

 

 

4.定义两个数组，并输入数据，比较两个数组是否相等，并对数组进行排序，将第一个数组的部分数据拷贝到另一个数组中。

源代码：

| **package** **com.haut.iot.ninghai****;**     **import** **java.util.Arrays****;**  **import** **java.util.Scanner****;**     ***/\**\***   ***\* 4.\******定义两个数组，并输入数据，比较两个数组是否相等，并对数组进行排序，\***   ***\**** ***将第一个数组的部分数据拷贝到另一个数组中。\***   ***\*/\***     **public class** **TestDemo04 {**    **public static void** **main****(String[] args) {**         **Scanner scanner =** **new** **Scanner(System.*****in\*****)****;** **//****扫描器**         **int****[] arr1 =** **new int****[****5****]****;** **//****五个元素的数组**      **System.*****out\*****.println(****"****请输入数组****1****的五个数****"****)****;**      **for** **(****int** **i =** **0****;** **i < arr1.****length****;** **i++) {**           **arr1[i] = scanner.nextInt()****;****//****赋值**         **}**      **int****[] arr2 =** **new int****[****5****]****;** **//****五个元素的数组**      **System.*****out\*****.println(****"****请输入数组****2****的五个数****"****)****;**      **for** **(****int** **i =** **0****;** **i < arr1.****length****;** **i++) {**           **arr2[i] = scanner.nextInt()****;** **//****赋值**         **}**      **//****调用****Arrays****的****equals****方法**      **System.*****out\*****.println(****"****数组****1****和数组****2****对比：****"** **+ Arrays.\*equals\*(arr1****,****arr2))****;**         **//****对两个无序数组排序**       **System.*****out\*****.println(****"****排序后：****>"****)****;**         **System.*****out\*****.print(****"****数组****1****：****> "****)****;**      **Arrays.\*sort\*(arr1)****;** **//****调用****Arrays****类的****sort****方法排序**      **System.*****out\*****.println(Arrays.\*toString\*(arr1))****;**         **System.*****out\*****.println()****;****//****换行**         **System.*****out\*****.print(****"****数组****2****：****> "****)****;**      **Arrays.\*sort\*(arr2)****;** **//****调用****Arrays****类的****sort****方法排序**      **System.*****out\*****.println(Arrays.\*toString\*(arr2))****;**         **//****将数组****1****的三个数拷贝到数组****2**      **System.*****out\*****.println(****"****将数组****1****的前三个数拷贝到数组****2****：****>"****)****;**      **arr2 = Arrays.\*copyOf\*(arr1****,****3****)****;****//****调用****copyOf****方法实现部分数据拷贝**         **System.*****out\*****.println(Arrays.\*toString\*(arr2))****;****//****最后调用****Arrays****类的****toString****方法打印**       **}**  **}** |
| ------------------------------------------------------------ |
|                                                              |

 

5.选择合适类的合适功能，制作个性化日历，显示当前日期格式为：yyyy-mm-dd，今天是星期*，上午/下午：hh-mm（时-分），距离毕业还有**天。

源代码：

  **package** **com.haut.iot.ninghai****;**     **import** **java.text.SimpleDateFormat****;**  **import** **java.util.Calendar****;**  **import** **java.util.Date****;**     ***/\**\***   ***\* 5.\******选择合适类的合适功能，制作个性化日历，显示当前日期格式为：\******yyyy-mm-dd\******，\***   ***\**** ***今天是星期\******\*******，上午\******/\******下午：\******hh-mm\******（时\******-\******分），距离毕业还有\******\**\******天。\***   ***\*/\***     **public class** **TestDemo05 {**    **public static void** **main****(String[] args) {**      **Date date =** **new** **Date()****;****//new****一个****date****对象**      **SimpleDateFormat sdf =** **new** **SimpleDateFormat(****"****当前时间为：****"** **+** **"yyyy-MM-dd"** **+**          **"** **今天是****"** **+** **"E"** **+** **"** **时间是****:"** **+** **"hh-mm"****)****;** **//****格式化时间信息**      **Calendar cal = Calendar.\*getInstance\*()****;** **//new****一个****cal****对象**         **cal.set(****2023****,** **Calendar.*****JULY\*****,** **18****)****;** **//****设置一个目标时间**         **long** **graduateTime =  cal.getTimeInMillis()****;** **//****把这个时间转换为毫秒**         **//****将目标时间和当前时间相减，并转换格式**      **long** **remainDays = (graduateTime  - System.\*currentTimeMillis\*()) / (****1000** ***** **60** ***** **60** ***** **24****)****;**         **//****格式化**      **System.*****out\*****.println(sdf.format(date))****;**      **//****打印剩余天数**      **System.*****out\*****.println(****"****距离毕业还有****"** **+  remainDays +** **"****天****"****)****;**    **}**  **}**  

6.制作自己的三角函数计算器，包括：正弦、余弦、正切函数及它们的反函数。

源代码：

  **package** **com.haut.iot.ninghai****;**     **import** **java.util.Scanner****;**     ***/\**\***   ***\* 6.\******制作自己的三角函数计算器，包括：正弦、余弦、正切函数及它们的反函数。\***   ***\*/\***     **//****计算器类**  **class** **Calculator {**    **public void** **showUi****() {** **//show IU**      **System.*****out\*****.println(****"===================="****)****;**      **System.*****out\*****.println(****"1.****正弦**  **2.****反正弦****"****)****;**      **System.*****out\*****.println(****"3.****余弦**  **4.****反余弦****"****)****;**      **System.*****out\*****.println(****"5.****正切**  **6.****反正切****"****)****;**      **System.*****out\*****.println(****"===================="****)****;**    **}**       **public void** **compute****() {**      **Scanner scanner =** **new** **Scanner(System.*****in\*****)****;** **//****扫描器**      **System.*****out\*****.println(****"****请输入您要计算的角度，如****90"****)****;****//****提示输入**      **double** **ret =  scanner.nextDouble()****;** **//****接受一个****double****值**      **double** **radians = Math.\*toRadians\*(ret)****;** **//****将接收到的数转化为弧度**         **System.*****out\*****.println(****"****请输入您的选择：****>"****)****;**      **int** **choice = scanner.nextInt()****;**         **switch** **(choice) {** **//****分支判断**        **case** **1****:**          **System.*****out\*****.println(****"****正弦：****"** **+ Math.\*sin\*(radians))****;**          **break;**        **case** **2****:**          **System.*****out\*****.println(****"****反正弦：****"** **+ Math.\*asin\*(radians))****;**          **break;**        **case** **3****:**          **System.*****out\*****.println(****"****余弦：****"** **+ Math.\*cos\*(radians))****;**          **break;**        **case** **4****:**           **System.*****out\*****.println(****"****反余弦：****"** **+ Math.\*acos\*(radians))****;**          **break;**        **case** **5****:**          **System.*****out\*****.println(****"****正切：****"** **+ Math.\*tan\*(radians))****;**          **break;**        **case** **6****:**          **System.*****out\*****.println(****"****反正切：****"** **+ Math.\*atan\*(radians))****;**          **break;**        **default****:**          **System.*****out\*****.println(****"****您的输入有误，程序退出！****"****)****;**           **break;**      **}**       **}**  **}**        **public class** **TestDemo06 {**    **public static void** **main****(String[] args) {**         **Calculator calculator =** **new** **Calculator()****;** **//new****一个对象**         **calculator.showUi()****;** **//****调用****showUi****打印信息**      **calculator.compute()****;** **//****计算三角函数**       **}**  **}**  

 

**【实验结果】**

\1. 设计Shape表示图形类，有面积属性area、周长属性per，颜色属性color，有两个构造方法（一个是默认的、一个是为颜色赋值的），还有3个抽象方法，分别是：getArea计算面积、getPer计算周长、showAll输出所有信息，还有一个求颜色的方法getColor。

（1）设计2个子类：一个Rectangle表示矩形类，增加两个属性，Width表示长度、height表示宽度，重写getPer、getArea和showAll三个方法，另外又增加一个构造方法（一个是默认的、一个是为高度、宽度、颜色赋值的）。一个Circle表示圆类，增加1个属性，radius表示半径，重写getPer、getArea和showAll三个方法，另外又增加两个构造方法（为半径、颜色赋值的）。

（2）在main方法中，声明创建每个子类的对象，并调用2个子类的showAll方法。

**代码概览：**

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image050.jpg)

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image052.jpg)

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image054.jpg)![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image056.jpg)

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image058.jpg)

2.描述Object类的功能及在java类中的位置；改写Object类的equals方法，判断创建的学生类（包含学号、姓名、年龄、性别属性及学习方法）创建的对象是否为同一个人，熟悉Object类中的toString（）方法，并对其功能进行测试，

Object源码：Object类是所有类的父类

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image060.jpg)

 

 

 

 

Object类的toString()输出的是全类名+@+十六进制的哈希码

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image062.jpg)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

**代码概览：**

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image064.jpg)

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image066.jpg)

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image068.jpg)

3.选择Random类中的合适方法生成4位随机码（包括数字和英文字符）。并实现输入随机码，验证输入的验证码的正确与否。（要求生成随机码的功能用类中的方法实现）

 

**代码概览：**

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image070.jpg)

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image072.jpg)

运行结果：

正确：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image074.jpg)

错误：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image076.jpg)

（截图给出实验结果）

4.定义两个数组，并输入数据，比较两个数组是否相等，并对数组进行排序，将第一个数组的部分数据拷贝到另一个数组中。

 

代码概览：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image078.jpg)

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image080.jpg)

5.选择合适类的合适功能，制作个性化日历，显示当前日期格式为：yyyy-mm-dd，今天是星期*，上午/下午：hh-mm（时-分），距离毕业还有**天。

代码概览：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image082.jpg)

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image084.jpg)

 

6.制作自己的三角函数计算器，包括：正弦、余弦、正切函数及它们的反函数。

代码概览：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image086.jpg)

 

 

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image088.jpg)

运行结果：

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image090.jpg)

![img](file:///C:/Users/王源/AppData/Local/Temp/msohtmlclip1/01/clip_image092.jpg)

注：这里只测试了正弦和余弦，其他功能这里不再测试

 

 

**【实验体会】**

（至少150字）

\1.   本题主要考察继承和抽象类的编写。父类是Shape类，定义有area属性，per属性和color属性，在其中提供两个构造方法和三个抽象方法，有Rectangle和Circle两个子类继承并实现父类的抽象方法。本题很简单，如实描述即可。需要熟悉的是抽象类的细节，当一个类中写了抽象方法时，这个类也会相应地变成抽象类，而一个抽象类中不一定有抽象方法。

\2.   本题考察Object类对于java其他类的意义，我们知道Object类是所有类的父类。需要注意的是，重写Object类的equals方法的同时，需要重写hashCode方法，hashCode方法必须遵守的原则是同一个对象的哈希码相同。本题没有让我们重写toString方法，只是探究toString方法输出的结果，后面会谈到其输出的值为对象的全类名+@+哈希码的十六进制表示形式。

\3. 此题考察Random类的基本使用，生成四位随机码可以用三个for循环完成，开辟一个字符数组可以存储62个字符，分别是26个大写字母，26个小写字母加上10个数字，最后在for循环中用StringBuffer或者StringBuild进行拼接，形成四位随机码。验证随机码的逻辑可以直接调用String的equals方法或者自己实现一个可以忽略大小写的方法（这样会更贴切验证码的实际情况），后面会详细提到。

\4. 本题主要目的是考察我们对Arrays类的内置方法的掌握情况，比如sort方法和copyOf方法等，只要我们熟悉其使用就能很快地解决此问题，自己实现方法的话完全没有必要，这也是Java相比于C语言的优势所在，不需要造轮子。

\5. 本题主要是考察Date很Calendar两个类的使用，具体实现细节见实验结果展示。值得注意的是，计算毕业剩余时间需要将时间格式化一下，格式化成天数最为直观。

\6. 本题主要是考察我们对Math类中的三角函数方法掌握程度，我们可以直接调用Math类的各种方法来计算相应的三角函数，这极大地便捷了我们的日常使用， 我这里稍微地对功能做了一些封装，让代码功能看起来更像一个计算器。

总的来说，考察的比较细致，个人认为面向对象的三大特性多态都考查到了，受益匪浅。