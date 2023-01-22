# Github上传至仓库方法

## 1. 拥有Github账户

## 2. 安装Git(一路默认，最好把Git Bash添加到terminal那项勾上)

## 3. 在Github创建仓库(远程仓库)，并获得仓库的http地址

## 4. 在本地创建新文件夹(本地仓库)，并在里面空白处右键Git Bash Here

### (1) 设置邮箱名和账户名

```
$ git config --global user.email "xxx@xxx.xxx"
$ git config --global user.name "xxx"
```

### (2) 设置代理

即使使用了VPN或SSR可以连接Github，也可能存在往远程仓库文件时无法走代理的问题，因此需要自己设置代理

*(这是由于我自己直接推送代码一直不成功才返回来设置代理，如果跳过该步骤可以直接推送说明你推送代码已经走了代理，如果你也是跟我一样走到最后一步不成功，返回来设置代理，那么设置完可以直接Push)*

#### 两种情况:

**自己有VPN/SSR：**网页可以打开Github，说明命令行在拉取或推送代码时没有通过VPN/SSR进行代理

**自己没有VPN/SSR：**网页不能打开Github，此时可以自己去网上寻找代理IP和Port

#### http代理

```
git config --global http.proxy 127.0.0.1:7890
git config --global https.proxy 127.0.0.1:7890
```

#### socks5代理

```
git config --global http.proxy socks5 127.0.0.1:7890
git config --global https.proxy socks5 127.0.0.1:7890
```

#### 注意：

**命令中的主机号（127.0.0.1）**是使用的代理的主机号(自己电脑有vpn那么本机可看做访问github的代理主机)，即填入127.0.0.1即可，否则填入代理主机 ip(就是网上找的那个ip)
**命令中的端口号（7890）**为代理软件(代理软件不显示端口的话，就去Windows中的代理服务器设置中查看)或代理主机的监听IP，可以从代理服务器配置中获得，否则填入网上找的那个端口port 

*(clash可以直接在软件界面中看到，当然也可以自己到**设置-->网络和Internet-->代理**中看到主机号和端口号)*

### (3) 检查设置

```
git config --list
```

### (4) 配置密钥

```
ssh-keygen -t rsa -C "xxx@xxx.xxx"
```

然后到**C盘-->用户-->当前用户(名字是你自己起的，如果没起就是默认的Administrator)-->.ssh文件夹**下找到**id_rsa.pub**文件，用记事本打开，复制里面的所有内容

接着回到Github账户中，找到设置-->SSH and GPG keys，新建SSH keys，名字随便取，把上面在**id_rsa.pub**文件中复制的内容粘贴到密钥中，然后创建，此时就完成了密钥的配置

## 5. 复制和推送本地仓库文件

### (1) 初始化

```
git init
```

### (2) 添加文件

*为添加所有文件

```
git add *
```

### (3) 添加注释

```
git commit -m "first commit"
```

### (4) 设置分支

```
git branch -M main
```

### (5) 添加远程仓库

```
git remote add origin https://github.com/vvision0/Github-Using-Method.git
```

### (6) 推送

```
git push -u origin main
```

