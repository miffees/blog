CentOS开机后网卡默认不启动：
	先启动下网卡，方便Xshell链接：	ifup eth0 
	使用命令修改文件：
		vim /etc/sysconfig/network-scripts/ifcfg-eth0
	将文件内容中的ONBOOT=YES   （原本是NO）
	使用setup命令将服务器ip地址修改为静态：
	配置完成后输入命令：service network restart
	将网卡重启。
	至此，网络配置完成，以后每次重启都可以完成网卡自启。
	
	
	为什么每次启动都是默认进图形界面？
这是因为在/etc/inittab文件中配置的默认运行级别为5，可以将它改为3，以后启动就自动进入命令行运行级别了。
[root@localhost ~]# vim /etc/inittab
改为3后，保存；重启。便改为每次启动进入命令行运行级别了


用户信息存储位置
账户信息存储于/etc/passwd
密码信息存储于/etc/shadow
创建用户的同时，默认还会为用户创建一个同名的组，组信息保存在/etc/group中