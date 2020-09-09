查看电脑gcc版本 cat /proc/version<br>
查看电脑cpu iostat<br>

查看cpu相关情况<br>
 - 查看CPU信息（型号） ```cat /proc/cpuinfo | grep name | cut -f2 -d: | uniq -c```
 - 查看物理CPU个数 ```cat /proc/cpuinfo| grep "physical id"| sort| uniq| wc -l```
 - 查看每个物理CPU中core的个数(即核数) ```cat /proc/cpuinfo| grep "cpu cores"| uniq```
 - 查看逻辑CPU的个数 ```cat /proc/cpuinfo| grep "processor"| wc -l```
 
查看电脑内存 vmstat<br>
查看电脑内存 free<br>

查看电脑存储情况 df -h<br>
查看各文件夹大小:du -h --max-depth=1<br>

---
查看进程 ps -ef或者 ps -ef |grep xx<br>
查看进程比如我起了python flask_test.py想杀死的话那就<br>
ps -ef | grep flask*<br>
查看端口可用netstat -antlp|grep 5000或者lsof -i:5000

---

创建用户 adduser xxx<br>
给用户创建密码 passwd xxx 然后输入密码<br>
删除用户 userdel xxx 然后 groupdel xxx<br>

进入文件夹 cd<br>
打印列表 ls或者ll或者ll -h可以查看文件MB大小<br>
创建文件夹 mkdir<br>
创建文件 vi或者nano<br>
删除文件/文件夹 rm xxx.csv / rm -rf xxx<br>

重命名用户和用户组重命名为root(root下) chown root:root xxx.csv <br>
查看历史和删除历史 history / history -c <br>

启动flask_test.py的python脚本然后nohup(日志进入test.log)：
```shell
#! /bin/sh
nohup python flask_test.py > ./test.log  2>&1 &
```
两台电脑(ip)如果能ping通的话，拷贝文件操作;登录ip1然后把ip1中的egg文件拷到ip2<br>
scp -r ChatterBot-0.8.7-py3.5.egg/ zhoubin@ip2:/opt/anaconda3/lib/python3.5/site-packages

centos解压rpm文件：<br>
把所有的rpm包放在一个目录下一起解压：rpm -Uvh --force --nodeps *rpm<br>
解压单个rpm：rpm -ivh xx.rpm


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

[tar文件压缩和解压](https://www.cnblogs.com/Confusedren/p/11150709.html)<br>

7z命令：<br>
解压
```bash
7za x phpMyAdmin-3.3.8.1-all-languages.7z -r -o./
参数含义：
x  代表解压缩文件，并且是按原始目录树解压（还有个参数 e 也是解压缩文件，但其会将所有文件都解压到根下，而不是自己原有的文件夹下）
phpMyAdmin-3.3.8.1-all-languages.7z  是压缩文件，这里我用phpadmin做测试。这里默认使用当前目录下的phpMyAdmin-3.3.8.1-all-languages.7z
-r 表示递归解压缩所有的子文件夹
-o 是指定解压到的目录，-o后是没有空格的，直接接目录。这一点需要注意。
```
压缩
```bash
7za a -t7z -r Mytest.7z /opt/phpMyAdmin-3.3.8.1-all-languages/*
参数含义：
a  代表添加文件／文件夹到压缩包
-t 是指定压缩类型，这里定为7z，可不指定，因为7za默认压缩类型就是7z。
-r 表示递归所有的子文件夹
Mytest.7z 是压缩好后的压缩包名
/opt/phpMyAdmin-3.3.8.1-all-languages/*：是压缩目标。
注意：7za不仅仅支持.7z压缩格式，还支持.tar.bz2等压缩类型的。如上所述，用-t指定即可。
```

软连接
```shell
# 以gcc软连接为例
sudo ln -s  /usr/local/Cellar/gcc/9.1.0/bin/c++-7 /usr/bin/c++
sudo ln -s  /usr/local/Cellar/gcc/9.1.0/bin/g++-7 /usr/bin/g++
sudo ln -s  /usr/local/Cellar/gcc/9.1.0/bin/gcc-7 /usr/bin/gcc
sudo ln -s  /usr/local/Cellar/gcc/9.1.0/bin/gcc-7 /usr/bin/cc
```

cp拷贝(默认会覆盖原有的文件，以下是不覆盖的方法)
```shell
cp -vnpr
```

[运行shell脚本时报错"\[\[ : not found"解决方法](https://blog.csdn.net/lc250123/article/details/90747798?depth_1-utm_source=distribute.pc_relevant.none-task&utm_source=distribute.pc_relevant.none-task)<br>
```
sh命令无法识别"[[]]"表达式。

解决办法：bash与sh是有区别的，两者是不同的命令，且bash是sh的增强版，而"[[]]"是bash脚本中的命令，因此在执行时，使用sh命令会报错，将sh替换为bash命令即可。
```

### 安装cuda10.1及驱动

[Ubuntu：安装 cuda10.1 驱动](https://blog.csdn.net/sss_369/article/details/94591280)<br>
[NVIDIA CUDA各版本下载链接（更新至2019-12-11，包含最新10.2版本）](https://blog.csdn.net/discoverer100/article/details/86696311?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromBaidu-1&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromBaidu-1)<br>

```shell
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-10.1/lib64
export PATH=$PATH:/usr/local/cuda-10.1/bin
export CUDA_HOME=$CUDA_HOME:/usr/local/cuda-10.1
```

### Could not load dynamic library 'libnvinfer.so.6'

[链接](https://stackoverflow.com/questions/60368298/could-not-load-dynamic-library-libnvinfer-so-6)<br>

```shell
# Add NVIDIA package repositories
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/cuda-repo-ubuntu1804_10.1.243-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu1804_10.1.243-1_amd64.deb
sudo apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/7fa2af80.pub
sudo apt-get update
wget http://developer.download.nvidia.com/compute/machine-learning/repos/ubuntu1804/x86_64/nvidia-machine-learning-repo-ubuntu1804_1.0.0-1_amd64.deb
sudo apt install ./nvidia-machine-learning-repo-ubuntu1804_1.0.0-1_amd64.deb
sudo apt-get update

# Install NVIDIA driver
sudo apt-get install --no-install-recommends nvidia-driver-430
# Reboot. Check that GPUs are visible using the command: nvidia-smi

# Install development and runtime libraries (~4GB)
sudo apt-get install --no-install-recommends \
    cuda-10-1 \
    libcudnn7=7.6.4.38-1+cuda10.1  \
    libcudnn7-dev=7.6.4.38-1+cuda10.1


# Install TensorRT. Requires that libcudnn7 is installed above.
sudo apt-get install -y --no-install-recommends libnvinfer6=6.0.1-1+cuda10.1 \
    libnvinfer-dev=6.0.1-1+cuda10.1 \
    libnvinfer-plugin6=6.0.1-1+cuda10.1
```

### 解决linux下vim显示乱码

编辑~/.vimrc文件，加上如下几行：

set fileencodings=utf-8,ucs-bom,gb18030,gbk,gb2312,cp936<br>
set termencoding=utf-8<br>
set encoding=utf-8<br>

### docsify使用

[简书](https://www.jianshu.com/p/4883e95aa903)<br>
```shell
# 安装
npm i docsify-cli -g
# 初始化项目，md文件可以放到docs文件夹下
docsify init docs
# 启动
docsify serve docs
```
