# Github更新方法

## 1. 初始化

```
git init
```

## 2. 添加本地项目

```
git add *
```

## 3. 添加注释说明

```
git commit -m 'Update'
```

## 4. 推送并更新

```
git push -u origin main
```

## 拉取项目或者修改本地仓库的位置时，总是要先初始化，并且链接远程仓库，如果本地项目被删掉了一些文件导致与远程仓库不一致，需要重新创建文件夹把仓库放在新文件夹位置

```
git init
git remote add origin https://github.com/vvision0/Github-Using-Method.git
git pull --rebase origin main
```

## 如果要上传新文件，首先将文件添加到缓存区，然后将缓存区的文件添加到本地仓库，然后将本地仓库推送到远程仓库

```
git add xx.xx // 添加到缓存区
git commit -m "备注" // 添加到本地仓库
git push -u origin master // 推送到远程仓库
```

