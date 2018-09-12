查看电脑gcc版本 cat /proc/version <br>
查看电脑cpu iostat <br>

查看cpu相关情况<br>
 - 查看CPU信息（型号） ```cat /proc/cpuinfo | grep name | cut -f2 -d: | uniq -c```
 - 查看物理CPU个数 ```cat /proc/cpuinfo| grep "physical id"| sort| uniq| wc -l```
 - 查看每个物理CPU中core的个数(即核数) ```cat /proc/cpuinfo| grep "cpu cores"| uniq```
 - 查看逻辑CPU的个数 ```cat /proc/cpuinfo| grep "processor"| wc -l```
 
查看电脑内存 vmstat <br>
查看电脑内存 free<br>

查看电脑存储情况 df -h <br>

---
查看进程 ps -ef或者 ps -ef |grep xx<br>
查看进程比如我起了python flask_test.py想杀死的话那就<br>
ps -ef | grep flask*<br>
查看端口可用netstat -antlp|grep 5000或者lsof -i:5000

---

创建用户 adduser xxx <br>
给用户创建密码 passwd xxx 然后输入密码 <br>
删除用户 userdel xxx 然后 groupdel xxx <br>

进入文件夹 cd <br>
打印列表 ls或者ll或者ll -h可以查看文件MB大小<br>
创建文件夹 mkdir <br>
创建文件 vi或者nano <br>
删除文件/文件夹 rm xxx.csv / rm -rf xxx <br>

重命名用户和用户组重命名为root(root下) chown root:root xxx.csv <br>
查看历史和删除历史 history / history -c <br>

启动flask_test.py的python脚本然后nohup(日志进入test.log)：
```python
#! /bin/sh
nohup python flask_test.py > ./test.log  2>&1 &
```
两台电脑(ip)如果能ping通的话，拷贝文件操作;登录ip1然后把ip1中的egg文件拷到ip2<br>
scp -r ChatterBot-0.8.7-py3.5.egg/ zhoubin@ip2:/opt/anaconda3/lib/python3.5/site-packages

压缩：
```bash
tar  -czvf  sysconfig.tar.gz /etc/sysconfig/ 
```
命令解释：将目录/etc/sysconfig/打包成一个tar文件包，通过使用-z参数来调用gzip程序，对目录/etc/sysconfig/进行压缩，
压缩成文件sysconfig.tar.gz，并且将压缩成的文件放在当前文件夹内。参数解释如下：
-z 调用gzip程序来压缩文件，压缩后的文件名称以.gz结尾。
解压：
```bash
tar -xzvf sysconfig.tar.gz
```
命令解释：这条命令是将上一条命令解压