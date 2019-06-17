# shell编程

## shell 及shell脚本介绍

![1560593359897](C:\Users\shanwujun\AppData\Roaming\Typora\typora-user-images\1560593359897.png)



![1560593704967](C:\Users\shanwujun\AppData\Roaming\Typora\typora-user-images\1560593704967.png)

### 批量注释文件

```properties
在vim模式下，按 Ctrl + shift +v ,出现VISUAL BLOCK 

选中需要注释的行

按shift + i

在第一行的开头写注释符号#

按Esc
```

```properties
:<<EOF
需要注释的代码
EOF
```

### 执行shell

```shell
1、bash script-name 或者 sh script-name (脚本有无执行权限都可)
2、path/script-name 或者 ./script-name(脚本必须有权限)
3、source script-name或者 . script-name
4、sh < script-name 或者 cat script-name | sh
```



### shell脚本编写规范

```shell
1、开头加脚本解释器
2、附带作者及版权信息
3、脚本扩展名为 *.sh
4、脚本存放在固定目录下
5、脚本中不用中文
6、成对的符号一次书写完成
7、循环格式一次性输入完成
```

### 定义环境变量(全局变量)

```shell
1、export 变量名=变量值
2、定义变量，在导出
   DONGQING=shan
   export DONGQING
3、declare
help declare 查看命令
declare -x name=value
注：配置在/etc/profile 下的环境变量，也是全局的

```

### 取消环境变量

```shell
unset name
```



### 环境变量文件

```shell
1、全局文件
/etc/profile
/etc/bashrc
2、用户环境变量
~/.bashrc
~/.bash_profile
环境变量初始化与对应文件生效顺序
/etc/sysconfig/i18n->/etc/profile.d/*.sh->/etc/bashrc->~/.bashrc->~/.bash_profile->/etc/profile

```



### 普通变量

```shell
# 当前用户或者脚本中生效
# 1、字符串变量
变量名=value
变量名='value'
变量名="value"
2、变量名
字母、数字、下划线3者组合，以字母开头

```

### 命令变量

```shell
变量名=`ls`
变量名=$(ls)

```

### 特殊位置变量

```shell
1、$0 #获取脚本名字
2、$n 
   $1  # 表示脚本后的第一个参数
   $2  # 表示脚本后的第二个参数
       # 如果 n>9，则需要${n} 取值
3、$#  # 脚本后面所有参数的个数
4、$*  # 获取脚本后的所有参数,结果作为一个字符串
5、$@  # 获取脚本后的所有参数,结果作为多个字符串
```





