



## Git 概述

Git 是一个免费的、开源的分布式版本控制系统，可以快速高效地处理从小型到大型的各种项目。

Git 易于学习，占地面积小，性能极快。 

它具有廉价的本地库，方便的暂存区域和多个工作流分支等特性。其性能优于 Subversion、CVS、Perforce 和 ClearCase 等版本控制工具。



### **1.1** **何为版本控制**

版本控制是一种记录文件内容变化，以便将来查阅特定版本修订情况的系统。

版本控制其实最重要的是可以记录文件修改历史记录，从而让用户能够查看历史版本，方便版本切换。![批注 2022-03-30 145715](C:\Users\Administrator\Pictures\git\批注 2022-03-30 145715.png)

### **1.2** **为什么需要版本控制**

个人开发过渡到团队协作

![批注 2022-03-30 150059](C:\Users\Administrator\Pictures\git\批注 2022-03-30 150059.png)



像Git这种分布式版本控制工具，客户端提取的不是最新版本的文件快照，而是把代码

仓库完整地镜像下来（本地库）。这样任何一处协同工作用的文件发生故障，事后都可以用

其他客户端的本地仓库进行恢复。因为每个客户端的每一次文件提取操作，实际上都是一次

对整个文件仓库的完整备份。



**分布式的版本控制系统出现之后,解决了集中式版本控制系统的缺陷:**

1.服务器断网的情况下也可以进行开发（因为版本控制是在本地进行的）

2.每个客户端保存的也都是整个完整的项目（包含历史记录，更加安全）



## 常用命令

### 查看 git 版本

```
 git --version
```

### 查看目录

```
ll   或者 ll -a
```



### 设置用户签名。

Git 首次安装必须设置一下用户签名，否则无法提交代码。

**※注意：**这里设置用户签名和将来登录 GitHub（或其他代码托管中心）的账号没有任何关系

```
git config --global user.name 用户名 

git config --global user.email 邮箱 
```

### 初始化本地库

```
git init 
```

### 查看本地库状态

```
git status 
```

### 添加到暂存区

```
git add 文件名 
```

### 提交到本地库

```
git commit -m "日志信息" 文件名 
第一次提交：git commit -m "frint commit" 文件名 
第二次提交：git commit -m "second commit" 文件名 
第三次提交：git commit -m "third commit" 文件名 
```

### 查看历史记录

```
git reflog 
```

### 版本穿梭

```
git reset --hard 版本号 
```

```
--首先查看当前的历史记录，可以看到当前是在 087a1a7 这个版本

Layne@LAPTOP-Layne MINGW64 /d/Git-Space/SH0720 (master)

$ **git reflog**

087a1a7 (HEAD -> master) HEAD@{0}: commit: my third commit

ca8ded6 HEAD@{1}: commit: my second commit

86366fa HEAD@{2}: commit (initial): my first commit

--切换到 86366fa 版本，也就是我们第一次提交的版本

Layne@LAPTOP-Layne MINGW64 /d/Git-Space/SH0720 (master)

$ **git reset --hard 86366fa**

HEAD is now at 86366fa my first commit

--切换完毕之后再查看历史记录，当前成功切换到了 86366fa 版本

Layne@LAPTOP-Layne MINGW64 /d/Git-Space/SH0720 (master)

$ **git reflog**

86366fa (HEAD -> master) HEAD@{0}: reset: moving to 86366fa

087a1a7 HEAD@{1}: commit: my third commit

ca8ded6 HEAD@{2}: commit: my second commit

86366fa (HEAD -> master) HEAD@{3}: commit (initial): my first commit

--然后查看文件 hello.txt，发现文件内容已经变化

$ cat hello.txt

hello git! hello atguigu!

hello git! hello atguigu!

hello git! hello atguigu!

hello git! hello atguigu!

hello git! hello atguigu!

hello git! hello atguigu!

hello git! hello atguigu!


```

## **Git** **分支操作**

![批注 2022-03-31 155007](C:\Users\Administrator\Pictures\git\批注 2022-03-31 155007.png)



### **什么是分支**

在版本控制过程中，同时推进多个任务，为每个任务，我们就可以创建每个任务的单独分支。使用分支意味着程序员可以把自己的工作从开发主线上分离开来，开发自己分支的时候，不会影响主线分支的运行。对于初学者而言，分支可以简单理解为副本，一个分支就是

一个单独的副本。（分支底层其实也是指针的引用）![批注 2022-03-31 155138](C:\Users\Administrator\Pictures\git\批注 2022-03-31 155138.png)



### **分支的好处**

同时并行推进多个功能开发，提高开发效率。

各个分支在开发过程中，如果某一个分支开发失败，不会对其他分支有任何影响。失败的分支删除重新开始即可



### **分支的操作命令**

#### 创建分支

```
git branch 分支名 
```

#### 查看分支

```
git branch -v 
```

#### 切换分支

```
git checkout 分支名 
```

把指定的分支合并到当前分支上

```
git merge 分支名 
```



## GitHub 操作

####  查看当前所有远程地址别名

```
git remote -v
```

#### 创建远程仓库别名

```
git remote add 别名 远程地址
```

