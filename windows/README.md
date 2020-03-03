1. [windows gcc安装](http://blog.csdn.net/yunxian_19/article/details/46799339)<br>

2. [VMware Workstation与Hyper-V不兼容问题](https://blog.csdn.net/Becivells/article/details/51755399?utm_source=blogxgwz4)<br>
`VMware Workstation 与 Hyper-V 不兼容。请先从系统中移除 Hyper-V 角色，然后再运行 VMware Workstation。`
 - 使用Win + X键调出快捷菜单，点击“命令提示符（管理员）”
 - 在命令提示符窗口中输入以下命令 ```shell  bcdedit /copy {current} /d “Windows 10 (关闭 Hyper-V)”``` 运行后会提示你已经创建了另外一个启动菜单项，记下 { } 中的那串代码。
 - 然后继续输入并运行以下命令 ```shell bcdedit /set {你记下的那串代码} hypervisorlaunchtype OFF```

3. xx


