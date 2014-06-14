###### cd(目录)
* “.”表示当前目录。
* "/"目录间隔。
* ”~”表示主目录
* ".."表示上一级目录。

###### ps(进程)	
* "exec"进程切换。
* "-a"所有的进程信息。
* “exit”退出进程。
* "-l"长格式
* "-e"所有的进程
* "-f"显示完整的命令

###### jobs(查看后台任务)

###### fg(执行后台带"+"的任务)
示例:

* "fg 6"
* "fg"

###### bg(执行后台带"+"的任务,后台执行)
示例:

* "bg 6"
* "bg"

###### kill(杀死某个进程)
示例:

* "kill 1185"
* "kill %1"(先jobs看id)
###### telnet(远程连接)
`telnet 192.168.1.10`

###### ls(文件查询)
“*”表示通配符(匹配一个或者多个),"?"表示通配符(匹配一个字符),"[]"匹配范围。

- “-F”显示目录下的所有内容，结尾描述:
	- “/”文件夹。
	- “@”链接(Windows中的快捷方式)。
	- “\*”可执行文件。
	- “|”管道。
- “-a”显示目录下的所有内容(包括隐藏文件),以”.”开头的文件为隐藏文件。
- “-A”显示目录下的所有内容(包括隐藏文件，但不包括”.”和”..”)。
- “-R”列出目录下的目录树。
- “-r”倒序显示。
- "-d"文件夹。
- “-l”显示当前目录下文件的详细信息。每一行会有类似”drwxr-xr-x@“的前缀,其中”d(文件夹)r(读取)w(写入)x(执行)r-x**同组**r-x**外组**@“。前缀描述:
	- “-”普通文件。
	- “p”管道。
	- “l”软链接(可以理解为Windows下的超链接)。
	- “d”文件夹。

###### ln(链接)
- 软链接`ln -s /bin/sleep bs`。
- 硬链接`ln /bin/zsh zzzsh`。

###### cp(复制)
- “-r”拷贝目录
- ”-i“交互(当文件或目录存在时给予提示)
示例:
1. `cp /etc/ip6addrctl.conf \~/Desktop/ `,复制ip6addrctl.conf到桌面。
2. cp -ri List README.md  girl

###### rm(删除)
- “-r”删除目录
`rm zzzsh`

###### chmod(修改权限)
- “u”自己。
- “g”组内成员。
- “o”其他人。
- “a”表示所有人。

示例:
- 删除其他人ip6addrctl.conf文件的读取权限，`chmod o-r ip6addrctl.conf`，结果”-rw-r-----   1 XiaoXiang  staff        304  6  7 12:41 ip6addrctl.conf”。
- 增加其他人ip6addrctl.conf 文件的读取和写入权限，`chmod o+rw ip6addrctl.conf`，结果”-rw-r--rw-   1 XiaoXiang  staff        304  6  7 12:41 ip6addrctl.conf”。
权限对应的数字:
- “r”—4
- “w”—2
- “x”—1
- “-”—0	
其它:
	chmod o=rwx ip6addrctl.conf
	chmod o=- ip6addrctl.conf
	chmod u-w,o+r,g+w ip6addrctl.conf
	chmod 755 ip6addrctl.conf
	chmod 0755 ip6addrctl.conf("0"表示8进制)
	chmod ugo+x ip6addrctl.conf
	chmod a-x ip6addrctl.conf

###### mkdir(创建目录)
- “-p”表示路径。
示例:
1. mkdir 范冰冰(在当前目录下，创建”范冰冰“这个文件夹)。
2. mkdir -p 美女/范冰冰(在当前目录下，创建”美女“这个文件夹，然后再”美女“文件夹下面，创建”范冰冰“这个文件夹)。

###### mkdir(创建文件)
示例:

1. touch wxx
2. touch wxk hx qy
3. touch 美女/wxx 美女/范冰冰/fbb

其它:

1. date\>xyz(\>输出重定向)
2. date\>\>xyz(\>\>追加)

###### cat/less/more/head/tail/wc/grep(显示文件内容)
示例:
1. cat xyz2. 
2. less xyz(支持上下翻页浏览)
3. more xyz
4. head -5 xyz
5. tail -6 xyz
6. head xyz
7. wc xyz(支持“-l”,“-w”,“-c”)
8. grep root /etc/passwd("-i"忽略大小写，“-v”查找不含指定字符的行)
9. grep -i 1 /etc/passwd | more("|"管道)

###### cal(日历)
示例:

1. cal
2. cal 2013
3. cal 11 2013

###### echo(输出输入的内容)
示例:

1. echo wxx
2. echo “wxx wxk                hx”
2. echo wxx\>\>xyz
3. echo wxx\>\>xyz;cat xyz
“/dev/tty”这个文件代表终端, “/dev/null”空文件，无论写入什么都会消失。

###### mv(移动)
示例:

1. mv 1.jpg  美女/范冰冰
2. mv 美女/范冰冰/1.jpg  美女/fbb.png
3. mv 美女 girl(改名)

###### rmdir(删除目录)
###### VI
* "i","a","o"插入
* "I","A","O"插入
* "x"删除光标处的字符
* "u"恢复
* "p"粘贴
* "0"行首
* "$"行尾
* "H"屏幕最前面
* "M"屏幕中间
* "L"屏幕的最后面
* "ctrl+b"、"ctrl+f",上一页、下一页。
* "w"把光标移到下一个单词开头
* "b"把光标移到上一个单词开头
* "e"把光标移到单词末尾
* ":set nu"设置行号
* ":set nonu"不显示行号
* "ctrl+z" 挂起状态

示例:
* "8 G"
* ": 8"
* "5 x"
* "2 x"

###### sleep(睡眠)
* "&"后台执行
##### find(搜索)
"find 目录 条件 [处理命令]"
* "-name"名称搜索
* "-exec"命令
示例:
1. "find / Yosemite"
2. "find . -name "*.md" -exec cp {} Desktop/test/"
3. "find  Desktop/test -name "*.md" -exec rm -i {} \;"
