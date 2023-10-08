# Git

## linux的基本命令

![1696750883383](D:\桌面\git\1696750883383.jpg)

> linux的基本命令

~~~c++
cd //切换目录
cd .. //回到上一级目录
pwd //当前的目录
clear //清屏
touch //在当前目录下创建一个文件
rm //删除文件
mkdir //创建一个目录\文件夹
rm -r //删除一个目录, rm -rf / 删除所有文件,格式化切勿使用
mv 123.xlsx 123 //把当前目录的123.xlsx移动到当前目录的123文件夹中
reset //重置终端,和clear差不多
history //从开始到现在都使用了哪些指令
exit//退出
~~~

## Git配置

`所有的配置文件都保存在本地！`

~~~c++
git config -l //查看git的配置
git config --system --list //查看系统给配置的什么
```git config --global --list``` //查看自己配置的什么

//在自己的配置中,必须要有user.name和user.email
//必须要配置的
git config --global user.name "yike"
git config --global user.email "yk991202"    

linuxx的系统配置文件都是在etc中
而本地的配置都在c盘中的用户中gitconfig中
~~~

## Git核心

![1696755668921](D:\桌面\git\1696755668921.jpg)

有三个区域,工作区，本地仓库，远程仓库，
写的代码是在工作区,你要放到缓存区就 git add ，git add . 就是添加目录的所有文件到缓存区中,缓存区使用git commit 就把缓存区中的文件添加到本地仓库中,再使用push就添加到远程仓库中

## git操作

~~~c++
git init //创建一个本地仓库

git clone [url] //克隆一个别人的远程仓库到自己的本地仓库
    
~~~

>文件状态

~~~c++
untracked //本地的文件就是这种状态,未跟踪的状态,通过 git add ,状态就变为 staged
unmodify //文件入库但是没有修改,如果被修改了他就是modify状态,或者使用 git rm 移出本库他就是untracked状态
modified //文件修改,通过git add 就变为staged状态,而使用 git checkout 就是丢弃修改,返回到unmoidfy状态,也就是本地库中取出文件,覆盖掉当前修改
staged //使用 git commit 修改同步到库中,此时本地文件和库中的文件一致,
~~~

~~~c++
提交:
本地文件(工作区中的文件)就是(untracked), 使用git add 就把该文件添加到缓存区中[staged],使用git commit就是把缓存区中的文件同步到本地仓库中
    
拉取:
如果想从远程仓库中到本地仓库中就是git clone[url],如果是想从远程仓库直接到工作区中就是git pull。
而从远程到本地过程中clone,获得的文件是unmoidfy的状态,如果想对文件修改他就是modified的状态,如果想把它在库里删除 git rm 。
修改后的文件[在库],通过git add,和 git commit 保存到库中,如果修改了,感觉错了要回档,就是通过git checkout就把修改后的文件回滚到未修改的状态,也就是刚获取的时候
~~~

~~~c
git status //是查看文件的状态
git add //添加所有文件到暂存区
git commit -m " " //提交暂存区的文件到本地仓库, -m是提交信息 
~~~

## 忽略文件

![1696760104508](D:\桌面\git\1696760104508.jpg)

## 生成公钥

~~~c
在目录下 git ssh-keygen -t rsa, 生成公钥 -t rsa是加密方式
    
 
~~~

## git传到远程仓库的流程

~~~c
1. git init //创建本地仓库
2. git remote add origin <远程仓库地址>
3. git add . <文件>
4. git commit -m "info"
5. git push -u origin master
~~~

