# Shell编程
## 一般命令
+ `set` 初始化位置参数，把参数的值赋予位置参数
+ `shift` 向左移动所有的参数
+ `local` 声明局部变量，仅限函数内部使用

## 内置命令
### type
显示命令的相关信息
### read
接收用户的输入，一般使用`-p`获取用户输入  
未指定接收变量时输入被`REPLY`变量接收  
同时输入多个参数时，多余的参数全被赋予最后一个变量

## 扩展级别
`'  '` 不执行任何扩展  
`"  "` 只执行变量扩展  
`  `（不加引号）可执行变量替换  

## 特殊结构
+ `>` 输出重定向
+ `<` 输入重定向
+ `&&` 控制操作符，首先执行前面的命令，成功执行则执行之后的命令
+ `$0` 保存调用程序的名称
+ `$1`-`$n`/`${n}` 位置参数，n大于一个字符时`{}`必须加上
+ `$*` 表示所有的位置参数，所有的参数合并成一个参数
+ `$@` 表示所有的位置参数，所有的参数仍然是单独的参数
+ `$#` 保存命令行参数的个数
+ `$$` 保存shell进程的PID编号
+ `$!` 在后台运行的最后一个进程的PID编号
+ `$?` 返回上一个命令的退出状态，未在exit时指定状态时，0表示成功执行，1表示没有成功执行
+ `$-` 单字符bash选项标识字符串
+ `$_` 前一条已执行命令的最后一个参数
+ `:-` 如果变量为空或者没有赋值则用后面的值进行扩展替换，但是不改变变量的值
+ `:=` 同`:-`但是改变变量的值
+ `:(空)` 放置在开头，计算命令行其余部分符号的值，一般后面利用`:=`进行未赋值变量的值
+ `:?` 如果变量没有被赋值则直接返回后面的错误信息发送到标准错误

## 控制结构
### if...then
```bash
if test-command
    then
        commands
fi
```
### if...then...else
```bash
if test-command
    then
        commands
    else
        commands
fi
```
### if...then...elif
```bash
if test-command
    then
        commands
    elif test-commands
        then
            commands
    ...
    else
        commands
    fi
```
### for...in
```bash
for loop-index in argument-list
    do
        commands
    done
```
### for
```bash
for loop-index
    do
        commands
    done
```
### while
```bash
while test-command
    do
        commands
    done
```
### until
```bash
until test-command
    do
        commands
    done
```
### `break`
结束本层循环，把控制权交给`done`后面的语句，从而跳出循环
### `continue`
结束本次循环，把控制权交给`done`语句，继续执行循环
### case
```bash
case test-string in
    pattern-1)
        commands-1
        ;;
    pattern-2)
        commands-2
        ;;
    pattern-3)
        commands-3
        ;;
    ...
    esac
```

### select
```bash
select varname [in arg...]
    do
        commands
    done
```
### here文档
```bash
grep "$1" <<+
...
...
+
```
## 文件描述符
## 参数
