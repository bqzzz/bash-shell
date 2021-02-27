<p align="center">
  <img src="https://cloud.githubusercontent.com/assets/2059754/24601246/753a7f36-1858-11e7-9d6b-7a0e64fb27f7.png" width="200px" height="200px" alt="bash logo"/>
</p>

## Contents

- [文件管理](#文件管理)
- [文本处理](#文本处理)
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
      <td><a href="#11重定向>">></a></td>
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


### 2.`cd`

切换目录，可使用**相对路径**或**绝对路径**

```bash
$ cd	#切换到当前用户的主目录(/home/用户目录)
$ cd ~	#切换到当前用户的主目录(/home/用户目录)
$ cd .	#保持在当前目录不变
$ cd ..	#切换到上级目录
$ cd -	#可以在最近两次工作目录之间来回切换
```


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

### 4.`touch`

创建文件或修改文件修改时间

- 如果文件 **不存在**，可以创建一个空白文件
- 如果文件 **已经存在**，可以修改文件的末次修改日期


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


### 6.`rmdir`

删除一个空的目录


### 7.`rm`

删除文件或目录（删除后不能恢复）

- **-f** ：强制删除，忽略不存在的文件，无需提示
- **-r** ：递归地删除目录下的内容，**删除文件夹** 时必须加此参数

### 8.`tree`

以树状图列出文件目录结构

- **-d**：只显示目录

示例：

```bash
$ tree  				#显示当前目录结构树
$ tree ./Desktop/myprj	#显示指定目录结构树
```

### 9.`cp`

复制文件或目录

- **-i**： 覆盖文件前提示
- **-r**： 若给出的源文件是目录文件，则 cp 将递归复制该目录下的所有子目录和文件，目标文件必须为一个目录名

示例：

```bash
$ cp -r  myprojects test
```


### 10.`mv`

移动文件或目录，可以覆盖自己用来重命名

- **-i** 覆盖文件前提示

### 11.重定向`>`

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
      <td><a href="#4grep">grep</a></td>
      <td><a href="#5echo">echo</a></td>
      <td><a href="#6管道|">|</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
   </tr>
</table>


### 1、`cat`

由第一行开始显示文件内容，cat 会一次显示所有的内容，适合查看**内容较少**的文本文件

- **-b**：对非空输出行编号
- **-n**：对输出的所有行编号


### 2、`tac`

从最后一行开始显示，可以看出 tac 是 cat 的倒着写！

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

### 4.`grep`

用于过滤/搜索的**关键字**，可使用**正则表达式**搜索文本，并把匹配的行打印出来。

- **-n** ：显示匹配行及行号
- **-v** ：显示不包含匹配文本的所有行（相当于求反
-  **-i** ：忽略大小写

```bash
$ grep -n 'time' test.py		# 搜索time关键字所在的行（关键字带空格或括号时，必须加引号）
$ grep -n ^def fake.py			# 搜索以def开头的行
$ grep -n '()$' fake.py			# 搜索以()结尾的行
```

### 5.`echo`

在终端中显示参数指定的文字，类似print函数

### 6.管道`|`

将 **一个命令的输出** 可以**通过管道** 做为 **另一个命令的输入**

示例：

```bash
$ ls -al | more				# 把所有文件详情列表分屏显示
$ ls -al | grep hello.py	# 在文件详情列表中搜索hello.py文件
```

