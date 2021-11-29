#  CentOS 7升级GCC
```bash
正文开始@Assassin
```
@[TOC](目录：)


我们在**centos**下默认的**gcc**版本是**gcc4.8.5**，版本比较低，默认是支持编译**c++98**的，若在**C++**程序中直接使用到**c++11**的特性，则会报错。
**解决方案：** 在编译时加上`-std=c++11`即可，如`g++ test.cpp -o run -std=c++11`

在bash下直接下载 : 
```bash
yum install -y gcc gcc-c++
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/ade1e1f9fc0a40748de77e751a37b021.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5a6B5rW35rKh5pyJ5LiD5Y-35YWs5Zut,size_20,color_FFFFFF,t_70,g_se,x_16)
查看一下版本号：

```bash
gcc --version
g++ --version
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/4a3ec349aa2c4cef9649ad8100ce3ead.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5a6B5rW35rKh5pyJ5LiD5Y-35YWs5Zut,size_20,color_FFFFFF,t_70,g_se,x_16)

##  基本执行步骤：
###  1. 切换用户：
输入以下命令行切换到root用户，此时需要输入你对应的root密码
```bash
su - root
```
如下图所示：
![在这里插入图片描述](https://img-blog.csdnimg.cn/066750ccdcca44a6af5d4441637f9057.png)
###  2. 安装centos-release-scl：
```bash
sudo yum install -y http://mirror.centos.org/centos/7/extras/x86_64/Packages/centos-release-scl-rh-2-3.el7.centos.noarch.rpm
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/8057347f3a8e454d8298fdaa6cd5dddb.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5a6B5rW35rKh5pyJ5LiD5Y-35YWs5Zut,size_20,color_FFFFFF,t_70,g_se,x_16)
```bash
sudo yum install -y http://mirror.centos.org/centos/7/extras/x86_64/Packages/centos-release-scl-2-3.el7.centos.noarch.rpm
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/793ed270cd374f0889a6222c1e89d6b2.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5a6B5rW35rKh5pyJ5LiD5Y-35YWs5Zut,size_20,color_FFFFFF,t_70,g_se,x_16)
###  3. 安装devtoolset：
这里需要注意一下，如果想安装7.版本的，就改成`devtoolset-7-gcc`，以此类推

```bash
sudo yum install devtoolset-9-gcc-c++
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/ced5fce63b1b42e5a783ef722c9af64e.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5a6B5rW35rKh5pyJ5LiD5Y-35YWs5Zut,size_20,color_FFFFFF,t_70,g_se,x_16)
###  4. 激活对应的devtoolset:
按理来说你可以一次安装多个版本的**devtoolset**，需要的时候用下面这条命令切换到对应的版本

```bash
scl enable devtoolset-9 bash
```
**此条命令行也同样适用**
```bash
source /opt/rh/devtoolset-9/enable
```
###  5. 查看gcc版本号：

```bash
gcc --version
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/e71a4628ce844b8986e8cf369325335c.png)

```bash
g++ --version
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/0f293af50a494f13bd15892c73091208.png)
###  6. 一些issue:
**注意**：这条`scl enable devtoolset-9 bash
`激活命令只对本次会话有效，重启会话或者切换用户后还是会变回原来的**4.8.5**版本，因为安装的`devtoolset`是在`/opt/rh`目录下的，如图所示：
![在这里插入图片描述](https://img-blog.csdnimg.cn/25692394d31a4e77b46f06e1b9c61ddd.png)
每个版本的目录下面都有个**enable**文件：
![在这里插入图片描述](https://img-blog.csdnimg.cn/2ebeffb7ac21492fa1db8a53077a593e.png)
如果需要启用某个版本，只需要执行命令行：
```bash
source ./enable
```
所以要想切换到某个版本，只需要执行：
```bash
source /opt/rh/devtoolset-*/enable
```
可以将对应版本的切换命令写个**shell脚本**放在配置了环境变量的目录下，需要时随时切换，或者开机自启。**但是经过我自己的实践，不推荐上述方法。**

---
最直截了当的方法是**直接替换旧版本的gcc**

> 旧版本gcc运行的在`/usr/bin/gcc`，所以将该目录下的`gcc/g++`替换为安装的新版本gcc软连接，省去了每次都要enable，简洁明了

**依次执行以下命令：**
```bash
mv /usr/bin/gcc /usr/bin/gcc-4.8.5
ln -s /opt/rh/devtoolset-9/root/bin/gcc /usr/bin/gcc
```
现在就算是**永久性地启动指定版本的gcc**，这种方式适用于长期使用该版本进行编译，**切换bash依然有效**

切换到**Assassin**用户查看一下：
```bash
[root@Ninghai ~]# su - Assassin
Last login: Fri Nov 26 22:20:43 CST 2021 from 182.118.236.53 on pts/1
[Assassin@Ninghai ~]$ g++ --version
g++ (GCC) 9.3.1 20200408 (Red Hat 9.3.1-2)
Copyright (C) 2019 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/6bbdc4c1cf3741f3affb38288bff23a3.png)
到这里就ok了~~