## (Git是目前世界上最先进的分布式版本控制系统)
### 1、常用命令行工具:

``` bash
  (1)cmd            (2)powershell           (3)git bash
```

### 2、命令行常用命令（在git bash上生效，部分在cmd无用）

``` bash
    -mkdir(make directory) 创建文件夹
    
    -rmdir(remove directory)删除文件夹（只能删除空文件夹，不常用）

    -touch 创建文件
    
    -rm(remove) 删除文件，-rm -rf 文件夹（循环递进删除文件夹）
    
    -mv(move) 移动文件或重命名

    -cp(copy) 复制文件

    -pwd (print working directory) 查看当前所在路径--绝对路径

    -cd(change directory) 切换目标

    -ls(list) 查看当前目录下的内容

    -cat 查看文件内容（一次性将内容全部显示）

    -less 查看文件内容（显示部分信息）--再次输入‘回车’一行一行显示，‘空格’一页一页显示 ，‘b’一次向上走一页

    -echo ‘内容’ > 文件名 （输出内容到文件中，每次输入都是覆盖原来的文件）

    -echo ‘内容’ >>文件名（输出内容到文件中，每次输入都是追加新内容）
    
    -clear 清屏

    -q 退出
```

### 3、Git介绍:

``` bash
  Git版本管理工具，有三大区域：

    (1)工作目录 -----存放项目代码的目录

    (2)暂存区   -----存放工作中更改的文件，避免项目代码丢失。

    (3)代码仓库 -----当开发功能足够成为一个版本时，提交到仓库。其实就是将暂存区中代码复制一份存储到代码仓库中。
```
<br>

``` bash
Git常用命令

(1)配置git用户名和密码

    git  config  --global user.name sun

    git  config  --global user.email  sun@qq.com

(2)查看当前git的配置

    git  config --list

(3)初始化git 仓库

    git  init

(4)查看当前仓库的状态

    git  status

(5)将工作目录中的文件添加到暂存区

    git  add a.txt b.txt    git add  . 

(6)将暂存区中的代码提交到本地仓库，形成一个版本

    git  commit -m 'first commit'

(7)查看本地仓库中的历史提交版本

    git  log

(8)将暂存区中文件删除

    git  rm --cached 文件名

(9)用暂存区中的文件覆盖工作目录中的文件

    git  checkout -- 文件名

(10)回滚到本地仓库中特定版本

    git  reset --hard HEAD^ 回退到上一个版本(HEAD^^回退两个版本，HEAD~100回退100个版本)
    git  reset --hard 1094a 回退到对应的ID版本
    git  push origin HEAD --force 回滚之后强推到远程
```
<br>

``` bash
分支相关命令：

(1)查看分支  

    git  branch (显示结果中 有* 代表当前所在分支)

(2)创建分支

    git  branch 分支名称

(3)切换分支  

    git  checkout 分支名称

(4)创建并切换分支 

    git  checkout -b 分支名称

(5)删除分支 （如果分支没有被合并不允许删除）

    git  branch -d 分支名称

(6)删除分支（强制删除分支）

    git  branch  -D 分支名称

(7)合并分支

    git  merge 来源分支（意思：当前目录到主分支，将来源分支合并到主分支上。合并后来源分支仍然存在）
    
(8)打标签

    git tag					查看所有标签
    git tag v1.0		    给当前版本打标签
    git tag v2.0 f52c633	给对应版本打标签
    git tag -d v1.0			删除标签

```
### 4、github 相关命令介绍
``` bash
4.1 模拟一个公共代码仓库

(1)先初始化   git  init --bare  sun.git （注意：此时公共代码仓库的文件夹必须以.git为后缀名）

　 4.2  github仓库

    (1)为远程仓库地址创建别名

        git  remote add origin  https://github.com/sun766/Programming-art.git（此处举例）

    (2)查看远程地址的详细信息

        git  remote -v

    (3)查看当前别名所对应的远程仓库地址

        git  remote show origin

    (4)从远程仓库获取代码（拉取所有版本到本地）

        git clone  origin 

    (5)从远程仓库拉取代码（拉取最新版本到本地，开发过程中使用）

        git pull origin master

    (6)向远程仓库推送代码

        git  push origin master

    (7)删除当前别名所对应的远程仓库地址

        git  remote remove origin 
```
