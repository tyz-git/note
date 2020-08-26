## 配置git

```java
//git全局配置
git  config  --global  user.name  "tongyazhou"

//git非全局配置
git  config   user.name  "tongyazhou"		-- 在项目中使用此命令，会在项目中出现  .git/config文件，代表当前项目的配置
```







## git本地仓库的创建

#### 从已有的git仓库clone

```java
//把整个远程仓库克隆下来
git clone https://github.com/shiyanlou/gitproject

//克隆远程仓库中的某个分支
git clone -b [某个分支] [仓库地址]
```

#### 新建一个本地仓库

新建一个git仓库，把未进行版本控制的文件进行版本控制，切换到项目的目录下使用git  init，让他置于git的版本控制管理之下

```
git  init
```







## git的工作流程

1. 使用git add将文件提交到本地暂存区

   ```java
   git  add /  git  add  .  是把本地的所有文件提交到暂存区
   ```

2. 使用git  commit命令将暂存区中的代码提交到本地代码库

   ```java
   git  commit  -m "注释的内容"
   ```

3. 使用git  push 推送到远程仓库

   ```
   git  push
   ```







## git本地连接远程仓库

#### 添加远程主机，让本地仓库和远程仓库建立联系

```java
git remote add origin(主机名) https://github.com/kinglion580/shiyanlou.git(git地址)
```

#### 将本地仓库同步到远程服务器

```java
git push origin master
```







## 分支与合并

```java
//创建分支
git  branch  分支名
    
//查看分支
git  branch
    
//切换分支
git checkout  分支名
    
//删除分支
git branch -d 分支名   -- 这个命令只能删除已经被当前分支合并完的分支
git branch -D 分支名	-- 强制删除分支
    
//撤销一个合并
git reset --hard HEAD^	-- 感觉合并后一团乱麻，想要回到合并前的版本，使用后续命令完成
```







## 比较提交的内容

#### 比较当前分支的内容

```java
//本地工作区查看
git   diff

//暂存区查看
git  diff   --cached

commit提交到本地仓库后上两个命令输入完什么都不会返回
```

#### 比较不同分支的内容

commit后，使用(git  diff   dev  master)会显示两个分支的内容不同的地方，展示的是第一视角的文件内容

```
git diff dev (第一视角) master
```









## 同步代码

#### 拉取最新的代码

```
git  pull
```

#### 拉取别的仓库代码

```
git pull  其他仓库地址
```







## 遇到的问题

首次提交的时候推送到远程仓库会被远程仓库拒绝，错误如下：
error: failed to push some refs to 'https://github.com/tyz-git/MyTest.git'