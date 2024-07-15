# Shell？

> *Linux操作系统核心和外部应用程序的一个接口。是一个命令行解释器，接收应用程序/用户命令，然后调用操作系统内核。*

## 一、入门

### 1、脚本格式

脚本以**#! /bin/bash**开头（指定解析器）

### 2、第一个Shell脚本

1. 需求：创建一个Shell脚本，输出helloworld

2. 案例实操：

   1. ![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=M2I4MmQ5MzFkMjExMGUxYjg3MTA5MWNmMDgzODE1YzlfN0RPazluUlJIWlhQQ2NZb1N3b3p2aGcwemxZRFd1dkpfVG9rZW46T0p6ZGJmVjV4b1JTTUt4VFRWRGN4UlkxbjhiXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)

   2. ```Bash
      #！bin/bash
      echo "helloworld"
      ```

3. 脚本的常用执行方式

   1. 第一种：采用bash或sh+脚本的相对路径或绝对路径（不用赋予脚本+x权限）
      -   sh+脚本的相对路径
      - ![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=MDE4NDJjZGVkMzkxOWRiZTgwMDQzYjBjNTliMTdjNmVfTEpWS3NicU5OU0h4VnRlNlhMS0xvVE4xZ1F4dUhPZmNfVG9rZW46WWFlZ2JmYkdpb3Z6UmZ4b3RBSWM2RFBYbkRoXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)
      -   sh+脚本的绝对路径
      - ![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=MmU4ZTlmNjI1YjYzYmFjNTI1NzllYWUxYWU0ZmQwN2VfeUZTcjdRaHk4a2x4aXRDRlZ0WG9ibW9VejhsT0l5SWJfVG9rZW46QlBvVmJoTmVob2hjU3d4Q1Q4cWNaZUxabkhlXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)
      -   bash+相对路径
      - ![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=Y2ZjZDkxOTZiYjk3YzI2MTI2M2ZmZTA4ZGMzZWZkZjBfRGc4M0dOWXVhblBlVEdUaXkzMlN4RjBQRU0zWmlZempfVG9rZW46WHBwTGJzSWlvb3ZuRHF4dXM4U2NTa1FGbmVnXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)
      -   bash+绝对路径
      - ![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=OTFlMjQxNTk4MTExOGNjMjc1OWZlNzZmZDg2MzQwZmFfb0lPaDVQYUYxQnFtWVlWOTJNYXdTTGppSEtUUnVtY2JfVG9rZW46R0owdWJnd2VJb0FUaEl4QVd1VmNMU2UzbjNkXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)
   2. 第二种：采用输入脚本的绝对路径或相对路径执行脚本（**必须具有可执行权限+x**）
      - 首先要赋予hell0world.sh脚本的+x权限
        - ![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=NGNjZGE0MzJiZGQ3YmVlN2VmNzkyYzU4ZjdjNDc1NDJfZHhPVndRd24zdE5kMzJNSjhvZU01NkZzUFZnRzM1NU9fVG9rZW46RENlN2JrRnpob1Jwdld4TTJFTGNpSGVtbmFoXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)
      - 执行脚本
        - 相对路径
          - ![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=MTZmMDJlZjlhMmMyMmFmOWVjMGY1YTVmY2UxODU4MWZfeHVaU0lXYldxeTFHUThpekZuWDhXNk5lSzRPbktaa3ZfVG9rZW46WTJGOGIyY3Rqb002ZVR4ejFpQmN6NlpHbnBoXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)
        - 绝对路径
          - ![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=OGU1ZTZjMzU0YmEyYTI4M2U3MDJkZDExMTM4NjQyMWFfd2g0bXdxcTJZY1BXSDgzQ1luSUw4bVdpaWJ1YWdoc29fVG9rZW46U0pUSWIyallvb0VyUGZ4V3BjUWN2V3FWbktiXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)
   3.  注意：第一种执行方法，本质是bash解析器帮你执行脚本，所以脚本本身不需要执行权限。第二种执行方法，本质是脚本需要自己执行，所以需要执行权限。
   4. 第三种（了解）
   5.  在脚本的路径前加上“.”或者source
   6.  原因：
      - 前两种方式都是在当前Shell中打开一个子Shell来执行脚本内容，当脚本内容结束，则子Shell关闭，会到父Shell中。
      - 第三种，可以使脚本内容在当前Shell里执行，而无需打开子Shell，这也就是为什么我们每次修改完/etc/profile文件以后，需要source一下的原因。

### 3、变量

#### 3.1、系统定义变量

1. 常用系统变量

$HOME、$PWD、$USER

1. 案例实操
   1. 查看系统变量的值
      1. ![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=ZjNhMGE1YzJhNWE5ZWY2N2M3YmEwMmJlYzFkZjQyMDNfS3N0Yktac2d5RGtnVjNibmpNWFdzRHZjYUp0MDhwVG1fVG9rZW46QXh6SmJERW9yb0JJckt4bDhlMWNybFRFbjhnXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)
   2. 显示当前Shell中所有变量
      1. ![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=ZjgwODZlODNiNGRlZWY0Njg3NDUyNDU2NzBjODZjM2VfT2tqSWdneDhIWXdpWU5NbEpzQjRhWFFCRVhSNWFoM3hfVG9rZW46RHhxd2JRRk5Gb0hQVHJ4M0hIOGNNZUFRbkVmXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)

#### 3.2、自定义变量

1. 基本语法
   1. 定义变量：变量名=变量值，注意，=号前后不能有空格
   2. 撤销变量：unset变量名
   3. 声明静态变量：readonly变量，注意：不能unset
2. 变量定义规则
   1. 变量名称可以由字母、数字、下划线组成，但是不能以数字开头，环境变量名建议大写。
   2. 等号两侧不能有空格。
   3. 在bash中，变量默认类型都是字符串类型，无法直接进行数值运算。
   4. 变量的值如果有空格，需要使用双引号或单引号括起来。
3. 实操...

#### 3.3、特殊变量

1. $n
   1.  n为数字，$0代表该脚本名称，$1-$9代表第一到第九个参数，10以上的参数，需要用大括号包含，如${10}。
2. $#
   1.  功能描述：获取 所有输入参数个数，常用于循环，判断参数的个数是否正确以及加强脚本的健壮性。
3. $*、$@
   1. 基本用法
      1. $*：这个变量代表命令行中所有的参数，$*把所有的参数看成一个整体。
      2. $@：这个变量代表命令行中所有的参数，不过$@把每个参数区分对待。
   2. 案例...

以上案例实操：

```Shell
#!/bin/bash
echo '======$n======'
echo script name:$0
echo 1st paramater:$1
echo 2nd parameter:$2
echo '======$#======'
echo parameter numbers:$#
echo '======$*======'
echo $*
echo '======$@======'
echo $@
```

**结果：**

![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=MmIzZDQ5NmUxNjg1MzM1MzEzMWFlZjUyNmZlY2I3NzZfRUtSOHg5dUZkWWlCN2RhU1I4dFRiVE1NT3ZEUTlMRnhfVG9rZW46UHNsYWI4a1Zub0ltVkJ4WGtXUGNtMXlqbkpjXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)

1. $?
   1. 基本用法
      1. 最后一次执行的命令的返回状态，如果这个变量的值为0，证明上一个命令正确执行；如果这个变量的值为非0（具体是哪个数，由命令自己来决定），则证明上一个命令执行不正确了。
   2. 案例...

### 4、运算符

1. 基本语法

   1. “$((运算式))”或“$[运算式]”

2. 案例：

   1. 计算(2+3)*4的值

      1. ![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=NGZiOGNkY2E2ODkzMjlhOWY0OWQ2ODY3NDg3MmU1OTlfMFB2RzVyZjZpVHozNlYzbE9wem0zMkMxU09qRmZrWFBfVG9rZW46Wnh5bWJYSlBmb3o5NFp4VHZzRmM0Qk1abjJqXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)

      2. 写一个两数相加

         1. ```Shell
            #!/bin/bash
            sum=$[$1+$2]
            echo sum=$sum
            ```

         2. ![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=N2FjZDMyYmU1MzQ3NjdjOWUyMWU1NzU4YTM4ZTU0MjRfQldrM2M2elRsQmx5WnBCdTVVbFQ0bHE0RmUwSGZlT21fVG9rZW46UjJOdmJNTFVXb09PanZ4c2ZYaWNpZkxGbnFiXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)

### 5、条件判断

1. 基本语法
   1.  test [condition]
   2. [ condition ]  **前后都有空格**
2. 常用判断条件
   1. 两个整数之间比较
      1. -ep等于（equal）
      2. -ne不等于（not equal）
      3. -lt小于（less than）
      4. -le小于等于（less equal）
      5. -gt大于（greater than）
      6. -ge大于等于（greater equal）
   2.  注：如果是字符串之间的比较，用等号“=”判断相等，用“!=”判断不等
   3. 按照文件权限进行判断
      1. -r 有读的权限
      2. -w 有写的权限
      3. -x 有执行的权限
   4. 按照文件类型进行判断
      1. -e 文件存在（existence）
      2. -f 文件存在并且是一个常规的文件
      3. -d 文件存在并且是一个目录
3. 案例...

### 6、流程控制

#### 6.1、if判断

1. 基本语法

   1. 单分支

      1. ```Shell
         if [ 条件判断式 ]; then
            程序
         fi
         或者
         if [ 条件判断式 ]
         then
            程序
         fi
         ```

   2. 多分支

      1. ```Shell
         if [ 条件判断式 ]
         then
            程序
         elif [条件判断式]
         then
            程序
         else
            程序
         fi
         ```

#### 6.2、case语句

1. 基本语法

   1. ```Shell
      case $变量名 in
      "值1")
          如果变量的值等于值1，则执行程序1
      ;;
      "值2")
          如果变量的值等于值2，则执行程序2
      ;;
      ...省略其他分支...
      *)
          如果变量的值都不是以上的值，则执行此程序
      ;;
      esac
      ```

注意：

1. case行尾必须为单词“in”，每一个模式匹配必须以右括号“)”结束。
2. 双分号“;;”表示命令序列结束，相当于C++中的break。
3. 最后的“*)”表示默认模式，相当于C++中的default。

1. 案例

#### 6.3、for循环

1. 基本语法1

   1. ```Shell
      for (( 初始值；循环控制条件；变量变化))
      do
          程序
      done
      ```

2. 案例

   1. ```Shell
      #!/bin/bash
      
      sum=0
      for (( i=0;i<=$1;i++ ))
      do
              sum=$[$sum+$i]
      done
      echo $sum
      ```

结果：

![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=YmJjNTg4ZTY1NjE4OTAxYzFhYjE0NzBmYmMwY2M4YmJfM3VQVlE4RjBnTU1GUFZXMWVCY0hFdDd4MXVueDNmaXZfVG9rZW46S1JuamJ6MTZUb1VybmZ4YVcxOGN0UzBDbnliXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)

1. 基本语法2

   1. ```Shell
      for 变量 in 值1 值2 值3...
      do
          程序
      done
      ```

2. 案例

   1. ![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=Mjg0NjUwYWIyZjgyYmY5Yjk5ZjIwNzFiMjNmMDE4MGFfVW81ZXFIa2diUGRqMkZ4bkZveTVyMzJtSkoyeTFFbG5fVG9rZW46WHBQOWJZem5ub2hkWnV4Q2VUbWNtWHJsbnlnXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)

#### 6.4、while循环

1. 基本语法

   1. ```Shell
      while [ 条件判断式 ]
      do
          程序
      done
      ```

2. 案例

   1. ```Shell
      a=1
      while [ $a -le $1 ]
      do
      #        sum2=$[ $sum2 + $a]
      #        a=$[$a + 1]
               let sum2+=a
               let a++
      done
      echo $sum
      ```

### 7、read读取控制台输入

1. 基本语法
   1. read (选项) (参数)
      1. 选项：
         1.    -p：指定读取值时的提示符
         2.    -t：指定读取值时等待的时间（秒）如果-t不加表示一直等待
      2. 参数
         1.    变量：指定读取值的变量名

### 8、函数

#### 8.1、系统函数

##### 8.1.1、basename

1. 基本语法

   1. ```Shell
      basename[string/pathname][suffix] 
      ```

功能描述：basename命令会删掉所有的前缀包括最后一个（‘/’）字符，然后将字符串显示出来。 basename可以理解为取路径里的文件名称 选项：suffix为后缀，如果suffix被指定了，basename会将pathname或string中的suffix去掉。

1. 案例
   1. ![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=ODZmZWEyM2U2NTBhNmQzZDRjYjU1MGY4MDU1MDAzN2NfNXhwSERpdzhpTUIxSU1KVUhRcVFrOWJIY09xWkROeTBfVG9rZW46TG16YmJDMXpsbzNoVlV4REtNc2N1YjBlbnliXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)

##### 8.1.2、dirname

1. 基本语法

   1. ```Shell
      dirname 文件绝对路径
      ```

功能描述：从给定的包含绝对路径的文件名中去除文件名（非目录的部分），然后返回剩下的路径（目录的部分）。

Dirname 可以理解为取文件路径的绝对路径名称。

1. 案例
   1.  获取qint.txt文件的路径
   2. ![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=ZDBkMjc1MWY5YjI5MWMyNDUzM2Y4M2ZjYWNkMjlkZGFfTjBUY0xieXpjWElzSWlsTkVUVTF6c2tVcVBKUzVyTkJfVG9rZW46Qm95N2JHaUs0b0RNOUt4dXFnU2N6WVpybmViXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)

#### 8.2、自定义函数

1. 基本语法

   1. ```Shell
      [ function ] funname[()]
      {
          Action;
          [return int;]
      }
      ```

2. 技巧

   1. 必须在调用函数地方之前，先声明函数，Shell脚本时逐行运行，不会像其他语言一样先编译。
   2. 函数返回值，只能通过$?系统变量获得，可以显示加：return 返回，如果不加，将以最后一条命令运行结果，作为返回值。return后跟数值n（0-255）

3. 案例

### 9、正则表达式

使用单个字符串来描述、匹配一系列符合某个语法规则的字符串。

#### 9.1、常规匹配

一串不包含特殊字符的正则表达式匹配它自己，

![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=ODg3ZGZhNDlhZTI5YTZmOGQxZGZkNGYzMWNlYjgzODRfWU5YeDEya3YyWWRrQ2xJVkNqdTF0d05VY3U0aVBsUkhfVG9rZW46S3BGSWJidDlKb3BSUWV4TkFUWmNQVGFvbkRjXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)

就会匹配所有包含root的行。

#### 9.2、常用特殊字符

1. 特殊字符：^
   1.  ^ 匹配一行的开头，
   2. ![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=MWNkYzEwYjFkYzFmOGQyZWRjNjEyM2RkNjViM2QwZDRfUTNIUWQ4VnZIZGlHeWl6bzVmWjdPeTVRTFlQdFJvQ3dfVG9rZW46WUNRbWJMTG5ab1JUcWF4Z0t6eGNnSFFMbkloXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)
   3.  会匹配出所有以r开头的行。
2. 特殊字符：$

$ 匹配一行的结束，

![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=YzUyZWU0MTkxNmEwYTZmN2EzN2UyMWY4NzBjMDIwODhfbkhvWXRrQlNVejU3Nlp3MlpmMDV3RGJHT09FbEg3UlBfVG9rZW46SDN2TmJxWVY1bzdnTTh4VVExb2N4T29xbjBlXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)

​     会匹配出所有以n结尾的行。

1. 特殊字符：**.**

. 匹配一个任意的字符，

![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=ZTRiY2ZiOTc0MmFkOTkxMjhkNTM0MmU4OWI5OTg0MmRfUUxaYU9wT015SjJTUzZjWW1xVjBEQ0ZCWnhheGhINm9fVG9rZW46VWNucWJwM2lWb3RORzh4MnlneGNTcG5ZbmJjXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)

会匹配r..t的所有行。

1. 特殊字符：*

不单独使用，它和上一个字符连用，表示匹配上一个字符0次或多次，

![img](https://vnkshn64w3.feishu.cn/space/api/box/stream/download/asynccode/?code=ZGI5NWJiZmYxODIzNjMzNTQwNDVjMjQyZTVjMjBiMWNfTzVCVUlRRkRPTmVpWmkzaXNwMmtWalhvREdGUWdCOWNfVG9rZW46Sk1ONWJtSGxYb2p0aW14cEJnV2N2M2tmbk9jXzE3MDI5MjA0NTc6MTcwMjkyNDA1N19WNA)

会匹配rt，rot，root等所有行。

1. 字符区间（中括号）：[]
   1.   [] 表示匹配某个范围内的一个字符，例如：
   2.  [6,8]   匹配6或者8，
   3.  [0-9]  匹配一个0-9的数字
   4.  [0-9]*   匹配任意长度的数字字符串
   5.  [a,z]   匹配一个a-z之间的字符
   6.  [a-z]   匹配任意长度的字母字符串
   7.  [a-c, e-f]  匹配a-c或者e-f之间的任意字符
2. 特殊字符：\

\表示转义，并不会单独使用，由于所有特殊字符都有其特定匹配模式，当我们想匹配某一特殊字符本身时，就会碰到困难。此时我们就要将转义字符和特殊字符连用，来表示特殊字符本身。

### 10、文本处理工具

#### 10.1、cut

在文件中负责剪切数据用的，cut命令从文件的每一行剪切字节、字符和字段并将这些字节、字符、字段输出。

1. 基本用法

   1. ```Shell
      cut [选项参数] filename
      ```

2. 选项参数说明

   1. -f  列号，提取第几列
   2. -d  分隔符，按照指定分隔符分隔列，默认时制表符“\t”
   3. -c   按字符进行切割，后加n表示取第几列

3. 案例

#### 10.2、awk

把文件逐行读入，以空格为默认分隔符将每行切片，切开的部分再进行分析处理。

1. 基本用法

   1. ```Shell
      awk [选项参数] '/pattern1{action1} /pattern2/{action2}...' filename
      pattern  表示awk在数据中查找的内容，就是匹配模式
      action   在找到匹配内容时所执行的一系列命令
      ```

2. 选项参数说明

   1. -F  指定输入文件分隔符
   2. -v  赋值一个用户定义变量