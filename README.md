<p align="center">
  <img src="https://cloud.githubusercontent.com/assets/2059754/24601246/753a7f36-1858-11e7-9d6b-7a0e64fb27f7.png" width="200px" height="200px" alt="bash logo"/>
</p>


## Contents

- [文件管理](#文件管理)
- [文本处理](#文本处理)
- [网络管理](#网络管理)
- [远程操作](#远程操作)
- [系统信息](#系统信息)
- [包管理工具](#包管理工具)
    <br/>

## 文件管理

<table>
   <tr>
      <td><a href="#1pwd">pwd</a></td>
      <td><a href="#2cd">cd</a></td>
      <td><a href="#3ls">ls</a></td>
      <td><a href="#4touch">touch</a></td>
      <td><a href="#5mkdir">mkdir</a></td>
      <td><a href="#6rmdir">rmdir</a></td>
      <td><a href="#7rm">rm</a></td>
      <td><a href="#8tree">tree</a></td>
      <td><a href="#9cp">cp</a></td>
      <td><a href="#10mv">mv</a></td>
   </tr>
   <tr>
      <td><a href="#11>">></a></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
   </tr>
</table>




### 1.`pwd`

显示当前所在目录

- **-P** ：显示出确实的路径，而非使用连结 (link) 路径

<br/>

### 2.`cd`

切换目录，可使用**相对路径**或**绝对路径**

```bash
$ cd	#切换到当前用户的主目录(/home/用户目录)
$ cd ~	#切换到当前用户的主目录(/home/用户目录)
$ cd .	#保持在当前目录不变
$ cd ..	#切换到上级目录
$ cd -	#可以在最近两次工作目录之间来回切换
```

<br/>

### 3.`ls`

列出目录及文件名。

- **-a** ：显示指定目录下所有子目录与文件，包括隐藏文件
- **-l** ：以列表方式显示文件的详细信息
- **-h** ：配合 -l 以人性化的方式显示文件大小
- 使用正则表达式筛选结果

示例：

```bash
ls *1.txt #列出以.txt结尾的文件
```

<br/>

### 4.`touch`

创建文件或修改文件修改时间

- 如果文件 **不存在**，可以创建一个空白文件
- 如果文件 **已经存在**，可以修改文件的末次修改日期

<br/>

### 5.`mkdir`

创建一个新的目录

- **-p**：可以创建多个目录

示例：

```bash
$ ls
myprojects  sub1  test
$ mkdir sub2 -p sub3 sub4
$ ls
myprojects  sub1  sub2  sub3  sub4  test
```

<br/>

### 6.`rmdir`

删除一个空的目录

<br/>

### 7.`rm`

删除文件或目录（删除后不能恢复）

- **-f** ：强制删除，忽略不存在的文件，无需提示
- **-r** ：递归地删除目录下的内容，**删除文件夹** 时必须加此参数

<br/>

### 8.`tree`

以树状图列出文件目录结构

- **-d**：只显示目录

示例：

```bash
$ tree  				#显示当前目录结构树
$ tree ./Desktop/myprj	#显示指定目录结构树
```

<br/>

### 9.`cp`

复制文件或目录

- **-i**： 覆盖文件前提示
- **-r**： 若给出的源文件是目录文件，则 cp 将递归复制该目录下的所有子目录和文件，目标文件必须为一个目录名

示例：

```bash
$ cp -r  myprojects test
```

<br/>

### 10.`mv`

移动文件或目录，可以覆盖自己用来重命名

- **-i** 覆盖文件前提示



### 11.`>`

将本应显示在**终端上的内容** **输出／追加** 到**指定文件中**

- `>` 表示输出，会覆盖文件原有的内容
- `>>` 表示追加，会将内容追加到已有文件的末尾

示例：

```bash
$ ifconfig > ifconfig.txt
$ ls > ls.txt
$ echo hello > hello.txt
```

<br/>

## 文本处理

<table>
   <tr>
      <td><a href="#1cat">cat</a></td>
      <td><a href="#2tac">tac</a></td>
      <td><a href="#3more">more</a></td>
      <td><a href="#4head">head</a></td>
      <td><a href="#5tail">tail</a></td>
      <td><a href="#6grep">grep</a></td>
      <td><a href="#7echo">echo</a></td>
      <td><a href="#8|">|</a></td>
      <td></td>
      <td></td>
   </tr>
</table>



### 1.`cat`

由第一行开始显示文件内容，cat 会一次显示所有的内容，适合查看**内容较少**的文本文件

- **-b**：对非空输出行编号
- **-n**：对输出的所有行编号

<br/>

### 2.`tac`

从最后一行开始显示，可以看出 tac 是 cat 的倒着写！

<br/>

### 3.`more`

用于分屏显示文件内容，每次只显示一页内容，适合于查看**内容较多**的文本文件

| 操作键   | 功能                 |
| :------- | :------------------- |
| 空格键   | 显示手册页的下一屏   |
| Enter 键 | 一次滚动手册页的一行 |
| b        | 回滚一屏             |
| f        | 前滚一屏             |
| q        | 退出                 |
| /word    | 搜索 **word** 字符串 |

<br/>

### 4.`head`

只看头几行



### 5.`tail`

只看尾巴几行



### 6.`grep`

用于过滤/搜索的**关键字**，可使用**正则表达式**搜索文本，并把匹配的行打印出来。

- **-n** ：显示匹配行及行号
- **-v** ：显示不包含匹配文本的所有行（相当于求反
- **-i** ：忽略大小写

```bash
$ grep -n 'time' test.py		# 搜索time关键字所在的行（关键字带空格或括号时，必须加引号）
$ grep -n ^def fake.py			# 搜索以def开头的行
$ grep -n '()$' fake.py			# 搜索以()结尾的行
```

<br/>

### 7.`echo`

在终端中显示参数指定的文字，类似print函数




### 8.`|`

将 **一个命令的输出** 可以**通过管道** 做为 **另一个命令的输入**

示例：

```bash
$ ls -al | more				# 把所有文件详情列表分屏显示
$ ls -al | grep hello.py	# 在文件详情列表中搜索hello.py文件
```



## 网络管理

<table>
   <tr>
      <td><a href="#1ifconfig">ifconfig</a></td>
      <td><a href="#2ping">ping</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
   </tr>
</table>


### 1.`ifconfig`

查看/配置计算机当前的网卡配置信息
<br/>

### 2.`ping`

检测到目标 ip地址 的连接是否正常
<br/>

## 远程操作

<table>
   <tr>
      <td><a href="#1ssh">ssh</a></td>
      <td><a href="#2scp">scp</a></td>
      <td><a href="#3shutdown">shutdown</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
   </tr>
</table>


### 1.`ssh`

远程登录：`ssh [-p port] user@remote`（SSH默认端口为22）

退出登录：`exit`

免密登录：

1. `ssh-keygen` 在`~/.ssh`目录下生成 SSH 钥匙


2. `ssh-copy-id -p port user@remote` 可以让远程服务器记住我们的公钥


3. 配置别名（可选）：在 `~/.ssh/config` 里面追加以下内容：

```
Host mac
    HostName ip地址
    User itheima
    Port 22
```

> 保存之后，即可用 ssh mac 实现远程登录了，scp 同样可以使用

<br/>

### 2.`scp`

远程拷贝文件：拷贝本地文件到一个远程主机、拷贝一个远程主机文件到本地、拷贝一台远程主机的文件到另一台远程主机。

- **-r** 若给出的源文件是目录文件，则 scp 将递归复制该目录下的所有子目录和文件，目标文件必须为一个目录名
- **-P** 若远程 SSH 服务器的端口不是 22，需要使用大写字母 -P 选项指定端口
    示例：

```bash
# 把本地当前目录下的 01.py 文件 复制到 远程 家目录下的 Desktop/01.py
# 注意：`:` 后面的路径如果不是绝对路径，则以用户的家目录作为参照路径
scp -P port 01.py user@remote:Desktop/01.py

# 把远程 家目录下的 Desktop/01.py 文件 复制到 本地当前目录下的 01.py
scp -P port user@remote:Desktop/01.py 01.py

# 加上 -r 选项可以传送文件夹
# 把当前目录下的 demo 文件夹 复制到 远程 家目录下的 Desktop
scp -r demo user@remote:Desktop

# 把远程 家目录下的 Desktop 复制到 当前目录下的 demo 文件夹
scp -r user@remote:Desktop demo
```

<br/>

### 3.`shutdown`

安全关闭 或者 重新启动系统

- `-r`:重新启动

- 默认表示1分钟之后关闭电脑，可指定关闭时间

示例：

```bazaar
# 重新启动操作系统，其中 now 表示现在
$ shutdown -r now

# 立刻关机，其中 now 表示现在
$ shutdown now

# 系统在今天的 20:25 会关机
$ shutdown 20:25

# 系统再过十分钟后自动关机
$ shutdown +10

# 取消之前指定的关机计划
$ shutdown -c
```

<br/>

## 系统信息

<table>
   <tr>
      <td><a href="#1date">date</a></td>
      <td><a href="#2cal">cal</a></td>
      <td><a href="#3df">df</a></td>
      <td><a href="#4du">du</a></td>
      <td><a href="#5ps">ps</a></td>
      <td><a href="#6top">top</a></td>
      <td><a href="#7kill">kill</a></td>
      <td></td>
      <td></td>
      <td></td>
   </tr>
</table>


<br/>

### 1.`date`

查看系统时间

### 2.`cal`

calendar 查看日历

- `-y` 选项可以查看一年的日历


### 3.`df`

disk free 检查文件系统的磁盘空间占用情况。可以利用该命令来获取**硬盘**被占用了多少空间，目前还剩下多少空间等信息

```
df [-ahikHTm] [目录或文件名]
```

- `-a` ：列出所有的文件系统，包括系统特有的 /proc 等文件系统；
- `-k` ：以 KBytes 的容量显示各文件系统；
- `-m` ：以 MBytes 的容量显示各文件系统；
- `-h` ：以人们较易阅读的 GBytes, MBytes, KBytes 等格式自行显示；
- `-H` ：以 M=1000K 取代 M=1024K 的进位方式；
- `-T` ：显示文件系统类型, 连同该 partition 的 filesystem 名称 (例如 ext3) 也列出；
- `-i` ：不用硬盘容量，而以 inode 的数量来显示

### 4.`du`

du命令也是查看使用空间的，但是与df命令不同的是Linux du命令是对**文件和目录**使用的空间的查看

```
du [-ahskm] 文件或目录名称
```

- `-a` ：列出所有的文件与目录容量，因为默认仅统计目录底下的文件量而已。
- `-h` ：以人们较易读的容量格式 (G/M) 显示；
- `-s` ：列出总量而已，而不列出每个各别的目录占用容量；
- `-S` ：不包括子目录下的总计，与 -s 有点差别。
- `-k` ：以 KBytes 列出容量显示；
- `-m` ：以 MBytes 列出容量显示；

### 5.`ps`

process status 查看进程的详细状况

- `-a`：显示终端上的所有进程，包括其他用户的进程
- `-u`：显示进程的详细状态
- `-x`：显示没有控制终端的进程

### 6.`top`

动态显示运行中的进程并且排序

> 输入 q 退出 top

### 7.`kill`

`kill [-9] 进程代号`：终止指定代号的进程-9 表示强行终止

<br/>

## 包管理工具

### 1.`yum`

yum是一个在 Fedora 和 RedHat 以及 SUSE 中的 Shell 前端软件包管理器。

#### 常用命令

- 列出所有可更新的软件清单命令：yum check-update

- 更新所有软件命令：yum update

- 仅安装指定的软件命令：**yum install <package_name>**

- 仅更新指定的软件命令：yum update <package_name>

- 列出所有可安装的软件清单命令：yum list [正则表达式]

- 删除软件包命令：yum remove <package_name>

- 查找软件包命令：yum search <keyword>

- 清除缓存命令:

    + yum clean packages: 清除缓存目录下的软件包
    + yum clean headers: 清除缓存目录下的 headers
    + yum clean oldheaders: 清除缓存目录下旧的 headers
    + yum clean, yum clean all (= yum clean packages; yum clean oldheaders) :清除缓存目录下的软件包及旧的 headers


### 2.`apt`

apt是一个在 Debian 和 Ubuntu 中的 Shell 前端软件包管理器。

#### 常用命令

- 列出所有可更新的软件清单命令：sudo apt update

- 升级软件包：sudo apt upgrade

- 列出可更新的软件包及版本信息：apt list --upgradeable

- 升级软件包，升级前先删除需要更新软件包：sudo apt full-upgrade

- 安装指定的软件命令：**sudo apt install <package_name>**

- 安装多个软件包：sudo apt install <package_1> <package_2> <package_3>

- 更新指定的软件命令：sudo apt update <package_name>

- 显示软件包具体信息,例如：版本号，安装大小，依赖关系等等：sudo apt show <package_name>

- 删除软件包命令：sudo apt remove <package_name>

- 清理不再使用的依赖和库文件: sudo apt autoremove

- 移除软件包及配置文件: sudo apt purge <package_name>

- 查找软件包命令： sudo apt search <keyword>

- 列出所有已安装的包：apt list --installed

- 列出所有已安装的包的版本信息：apt list --all-versions
