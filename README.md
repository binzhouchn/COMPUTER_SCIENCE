# 目录

[1. **leetcode笔记借鉴**](leetcode)

[2. **linux操作命令**](linux)

[3. **windows相关**](windows)

[4. **github相关**](github)

---

## 计算机原理

**1. 数据结构/算法**

见[lintcode](https://github.com/binzhouchn/algor)或[leetcode](leetcode/)

**2. 计算机网络**

[HTTP/TCP协议基础](https://www.cnblogs.com/sunshine-blog/p/8393264.html)<br>
[计算机网络基础知识总结](https://www.runoob.com/w3cnote/summary-of-network.html)<br>
[计算机网络基础知识整理](https://blog.csdn.net/m0_37568814/article/details/81018769?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-2.channel_param&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-2.channel_param)<br>

**3. 操作系统原理**

[你当初是如何学会操作系统这门课程的？(知乎)](https://www.zhihu.com/question/270998611/answer/360930889)<br>
[哈工大李治军老师的OS(视频)](https://www.bilibili.com/video/BV1d4411v7u7?p=1)<br>

**4. 其他**

 - 4.1 RSA加密过程<br>
 I. 找出质数p,q<br>
 II. n = p*q<br>
 III. fi(n) = (p-1)*(q-1) 即欧拉函数<br>
 IV. 公钥e，1<e<fi(n);e和fi(n)互质;私钥d，e*d除以fi(n)余数为1<br>
 V. 加密：m^e除以n求余数C，将C传输；解密：C^d除以n求余数得到m<br>