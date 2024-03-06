# 克隆
- 直接复制文件夹
- 用VMware克隆，**虚拟机必须处于关机状态**
# 虚拟机快照
- 虚拟机能够通过之前拍好的快照，在文件损坏之后回到快照的时候
# 安装VMtools
1. 安装后，可以在Windows下更好的管理vm虚拟机
2. 可以设置Windows和centOs的<font color = red>共享文件夹</font>
![[安装vmtools步骤.png]]
# 目录结构
## 基本介绍
1. linux的文件系统采用<font color = red>级层式的树状目录结构</font>，在此结构中的最上层<font color = red>根目录"/"</font>，然后在此目录下再创建其他的目录
2. 在Linux中，<font color = red>一切皆文件</font>
## 具体的目录结构
![[目录结构.png]]
![[具体目录结构.png]]
![[具体目录.png]]
![[目录结构 1.png]]
# 远程操控
## 远程连接Xshell
### 下载地址
![[xshell-xftp下载地址.png]]
1. 终端输入ifconfig，并找到ens33下的ip地址
![[找ip.png]]
2. 在win的cmd中去pingcentOS的IP地址
![[pingIP地址.png]]
3. 在xshell中连接
![[xshell中连接.png]]
## 远程上传下载文件-Xftp6
- 操作与连接xshell大致相同
### 如果遇到乱码
- 将编码改为UTF-8
![[xftp遇乱码.png]]
# vi vim快速入门
1. Linux系统中会内置vi文本编辑器
2. vim具有程序编辑能力，可以看作是vi的增强版，主动的以字体颜色辨别语法正确性，方便程序设计。代码补完、编译及错误跳转等方便编辑的功能特别丰富
## vim的三种模式
### 正常模式
- 以vim打开一个档案就直接进入一般模式。在这个模式中，你可以使用【上下左右】按键来移动光标，可以使用【删除字符】||【删除整行】来处理内容等
- 输入`vim hello.java`，创建一个Java文件
![[正常模式.png]]
### 插入模式
- 按下i，I，o，O，a，A，r，R等任意字母之后进入<font color = red>编辑模式</font>，一般按i即可
- 插入模式下编写的helloworld
![[插入模式下编写.png]]
### 命令行模式
- 按esc，再输入:或者/即可变为命令行模式
- 在这个模式中，可以提供你的相关指令，==完成读取、存盘、替换、离开vim、显示行号==等动作
- 按下esc，并输入==`：wq`==写入并保存即可
## 各种模式的相互切换
![[模式切换.png]]
## vi&vim的快捷键（常用）
1. <font color = red>一般模式下</font>,拷贝当前行：==`yy`==，拷贝当前行向下的5行(包括当前行)：==`5yy`==,粘贴：==`p`==
2. <font color = red>一般模式下</font>，删除当前行：==`dd`==，删除当前行向下的5行(包括当前行)：==`5dd`==
3. 再文件中查找某个单词，在<font color = red>命令模式</font>下输入==`/+关键字`==，回车查找，输入==`n`==查找下一个，再次输入/可以重新查找新的关键字
4. <font color = red>命令行模式下</font>设置文件行号，输入==`:set nu`==,取消文件行号==`set nonu`==
5. <font color = red>一般模式</font>，到文档最末行：==`G`==，到文档首行：==`gg`==
6. <font color = red>一般模式下</font>，撤销动作：==`u`==
7. <font color = red>一般模式下</font>，快速移动光标：==`数字+shift+g`==
