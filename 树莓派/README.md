# 树莓派笔记

## 1. 安装opencv踩的坑

我用的树莓派3B+的内存只有1G，在编译一些源码的时候会出现内存被耗尽，编译中断的情况，比如编译opencv时，经常98% 99%的时候卡住；
以下是解决方法

我用的是树莓派系统32位，可以去以下网站下载opencv4.5.x版本安装脚本，
[OpenCV4.5.x安装系列脚本](https://github.com/Qengineering/Install-OpenCV-Raspberry-Pi-32-bits)


**安装开始前设置swap memory**
```shell
sudo vi /sbin/dphys-swapfile #将CONF_SWAPSIZE和CONF_MAXSWAP都改成4096
sudo reboot #重启

cd /var
sudo swapoff /var/swap #先关闭swap
sudo dd if=/dev/zero of=swap bs=1M count=4096 #重新设置大小1M*4096=4G
sudo mkswap /var/swap #格式化
sudo swapon /var/swap #开启
swapon -s #查看当前已生效的swap
free -m #查看当前swap使用情况
```

以上设置完后，
```shell
sudo chmod 777 ./OpenCV-4-5-3.sh
./OpenCV-4-5-3.sh
```
等待安装完成即可，大概需要一个多小时。

其他需要注意的坑：
 - 安装前需要sudo apt-get update一下
 - OpenCV-4-5-3.sh脚本中的sudo make -j4改成sudo make不要-j4不需要多线程，可能会卡
 - 安装完后把dphys-swapfile改回来
 
安装完opencv可以通过以下方法测试：
 - python的话可以直接import cv2看下
 - c++的话可以先去https://github.com/wxlscm/raspberry_tutorial该网站下载代码，然后进到文件夹ch8_test_OpenCV
```shell
mkdir build
cd build
cmake ../
cmake --build .
./sample1
#运行以上代码即可看到一张彩色图和转换后的灰度图，表明opencv安装成功！
```

## 2. 树莓派安装ubuntu mate 18.04

[在树莓派3B+上安装ubuntu mate 18.04](http://t.zoukankan.com/Biiigwang-p-11735890.html)<br>
[树莓派3b+ ubuntu 18.04添加SSH服务](https://blog.csdn.net/stephanezhang/article/details/104651185)<br>
[树莓派ubuntu18.04 mate 安装VNC](https://blog.csdn.net/chenzz444/article/details/119016938)<br>



