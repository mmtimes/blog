# git使用
## git服务器搭建
1. 安装git ssh 等软件
```bash
sudo apt-get install git ssh
```
2. 新橧用户git并设置密码
```bash
sudo useradd git
sudo password git
sudo groupadd git
sudo usermod -G git git
sudo mkdir /home/git/.ssh
sudo chown git:git /home/git/.ssh
sudo chown git:git /home/git/.ssh/authorizedkeys
sudo vim /etc/passwd
    /bin/sh ==> /bit/git-shell
```
3. 初始化git仓库
```bash
sudo mkdir /code
sudo git --bare init test.git
sudo chown -R git:git /code/test.git
```
4. 测试服务器是否搭建成功
```bash
git clone git@server'ip:/code/test.git
```
## git客户端使用
1. 初始化git配置
```bash
git int 'path'
```
2. 把项目中的文件添加到本地版本库中
```bash
git add .
```
3.提交说明commit填写
```bash
git commit -m "说明文字“
```
4. 关联到远程仓库
```bash
git remote add origin git@server'sip:/code/test.git
git remote rm origin git@server'sip:/code/test.git
```
5. 将本地代码推送到远程仓库
```bash
git push -u origin master
```
6. 用远程仓库同步本地代码
```bash
git pull --rebase origin master //远程仓库非空需要做此操作
git pull origin master  --allow-unrelated-histories //忽略版本强行合并
```
7. 再次推送
```bash
git push origin master
```
8. 提交方式
```bash
git add -A //提交所有变化
git add -u 提交被修改和被删除的文件，不包括新文件 
git add . 提交新文件 和被修改的文件，不包括被删除文件
```