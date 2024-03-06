# 关机&重启命令
## 基本命令
1. 立刻关机：
<table><tr><td bgcolor = green>shutdown -h now</td></tr></table>
3. 一分钟后关机：
<table><tr><td bgcolor = green>shutdown -h 1</td></tr></table>
3. 重新启动计算机
<table><tr><td bgcolor = green>shut down -r now</td></tr></table>
4. 关机，与上面作用一样
<table><tr><td bgcolor = green>halt</td></tr></table>
5. 重新启动计算机
<table><tr><td bgcolor = green>reboot</td></tr></table>
6. 把<font color = red>内存数据同步到磁盘</font>
<table><tr><td bgcolor = green>sync</td></tr></table>
## 注意
- ==不管重启还是关闭系统，首先运行sync命令==，把内存中的数据写入到磁盘中
- 目前shutdown/reboot/halt等命令虽然已经在关机前运行了sync，但为了以防万一