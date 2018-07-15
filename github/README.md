## pycharm连接github

1. 在pycharm，default setting中配置github和git，<br>
注意github中勾选clone git repositories using ssh<br>
git中选择完git的所在位置，ssh executable选择native

2. 在终端输入 <br>
```bash
ssh-keygen -t rsa -C "your_email@example.com"
```
三次回车，如有看到The key's randomart image is，代表你的SSH Key生成成功了。<br>
```bash
cat ~/.ssh/id_rsa.pub
```
然后将一长串SSH Key粘贴到自己的git账户上。在github,settings,ssh and GPG keys中添加新ssh key就行

3. 在终端或git Bash中输入以下代码
```bash
ssh -T git@github.com
```
