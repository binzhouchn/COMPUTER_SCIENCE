1. [windows gcc安装](http://blog.csdn.net/yunxian_19/article/details/46799339)<br>

2. [VMware Workstation与Hyper-V不兼容问题](https://blog.csdn.net/Becivells/article/details/51755399?utm_source=blogxgwz4)<br>
`VMware Workstation 与 Hyper-V 不兼容。请先从系统中移除 Hyper-V 角色，然后再运行 VMware Workstation。`
 - win+r输入qiy，把Hyper-V取消勾选
 - 使用Win + X键调出快捷菜单，点击“命令提示符（管理员）”
 - 在命令提示符窗口中输入以下命令 ```bcdedit /copy {current} /d “Windows 10 (关闭 Hyper-V)”``` 运行后会提示你已经创建了另外一个启动菜单项，记下 { } 中的那串代码。
 - 然后继续输入并运行以下命令 ```bcdedit /set {你记下的那串代码} hypervisorlaunchtype OFF```

如果需要开启的话，把Hyper-V勾选，然后输入```bcdedit /set {你记下的那串代码} hypervisorlaunchtype auto```

3. [win10开机默认启动系统有多个win10系统怎么办](https://jingyan.baidu.com/article/d8072ac4b849cdec94cefd51.html)<br>

4. [VMware12安装Ubuntu 16.04(图文教程)](https://blog.csdn.net/colin_lisicong/article/details/70193539?depth_1-utm_source=distribute.pc_relevant.none-task&utm_source=distribute.pc_relevant.none-task)<br>

5. xx

