# Shell
shell脚本学习

## 第一行：

#!/bin/bash

此行称为 shebang（就是 sharp (#) + bang (!) 的意思），会指引操作系统使用接下来指定的程序运行此文件。此处 /bin/bash 执行我们的文件。

## 变量

使用变量无需声明，以字母和下划线开头。等号左右不能有空格

Shell 变量默认都是字符串。bash 里面可以用 (( )) 执行 C 风格的算术表达式。

## 流程控制

### if语句

if 
  判断命令，可以有很多个，真假取最后的返回值
then
  如果前述为真做什么
[ # 方括号代表可选，别真打进去了！
elif
  可以再来个判断，如果签名为假继续尝试这里
then
  如果前述为真做什么 ]
else
  如果全都不行做什么
fi # 结束，就是倒写的 if 啦。

大多数情况下，可以使用测试命令来对条件进行测试，比如可以比较字符串、判断文件是否存在及是否可读等等

-f "filename"
判断是否是一个文件
-x "/bin/ls"
判断/bin/ls是否存在并有可执行权限
-n "$var"
判断 $var 变量是否有值
"$a" == "$b"
判断$a和$b是否相等

使用&& 和 || 操作符可以替代if语句

### cae语句

case ... in
   ...) do something here 
   ;;
esac

## select语句

echo "What is your favourite OS?"
select var in "Linux" "Gnu Hurd" "Free BSD" "Other"; do
  break;
done
echo "You have selected $var"

### while/for 循环

while ...; do
   ....
done

for var in ....; do
   ....
done

## Shell里的函数

#别笑，bash 里面函数名的确可以这样……
#(POSIX sh 函数名倒是和变量名要求差不多)
我是一个函数() {
  #函数里面 $1 $2 对应函数所接受到的第一、第二……个参数。
  这里有很多命令
}

## 命令行参数

$0 $1 $2 ........
$# $@ $*






















