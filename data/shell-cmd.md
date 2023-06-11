# :neckbeard: shell常用操作

## :credit_card: 文本数组
+ 遍历数组
```shell
list1=(d f 3 5 t a)
for element in ${list1[@]}
do
  echo $element
done
```
+ 读取文本内容并执行命令

***for do done***
```shell
#!/bin/bash
for url in $(cat url.log); do
  ping -n -D -c 2 "$url"
done
```
***xargs***
```shell
#< url.log将url.log文件的内容作为输入提供给xargs命令，然后xargs命令将逐行读取该输入，并将每行内容作为参数传递给后续的ping命令进行执行。
xargs -I {} ping -n -D -c 2 {} < url.log
```
---
## :tshirt: shell变量
+ [[ ]]  # 针对数学比较表达式
+ (( ))  # 字符串表达式的加强版
+ $#	传给脚本的参数个数
+ $0	脚本本身的名字
+ $1	传递给该shell脚本的第一个参数
+ $2	传递给该shell脚本的第二个参数
+ $@	传给脚本的所有参数的列表
+ $*	以一个单字符串显示所有向脚本传递的参数,与位置变量不同,参数可超过9个
+ $$	脚本运行的当前进程ID号
+ $?	显示最后命令的退出状态,0表示没有错误,其他表示有错误 

***shell举例：*** ```for i in m h z; do echo "my name is ${i}test";done```

---

## :green_apple: awk用法

***逻辑运算：*** ```awk 'BEGIN {num = 5; if (num >= 0 && num <= 7)  printf "%d is in 0 ~ 7\n", num }'```

***算术运算：*** ```awk 'BEGIN { cnt=10; cnt += 99; print "Counter =", cnt }'```

---

## :watermelon: 网络

```shell
netstat -n | awk '/^tcp/ {++S[$NF]} END {for (a in S) print a,S[a]}'
```
---

## :apple: 简单实例

***循环打印时间：*** ```shell i=0; while true; do echo "$i: $(date)"; i=$((i+1)); sleep 1; done```
