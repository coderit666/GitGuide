> 1. **介绍**：**GitGuide** 致力于打造最易懂的 Git 版本控制入门教程，`让天下没有难学的 Git 版本控制`
> 2. **转载须知** ：以下所有文章与视频教程皆为我的原创，转载请联系我们，如发现恶意抄袭/搬运，会动用法律武器维护自己的权益，让我们一起维护一个良好的技术创作环境！
> 3. **Star/Fork 支持**：开源不易，如果开源项目帮助你打开 Git  学习大门，希望你能 **Star** 支持我们，你的支持就是我们持续更新的动力。

<p align="center">
  <a href="https://mp.weixin.qq.com/s/PpeblHk6Ml4w8iNrrw8UAA"><img src="https://img.shields.io/badge/%E5%9C%A8%E7%BA%BF%E9%98%85%E8%AF%BB-read-brightgreen" alt="在线阅读"></a>
  <a href="#公众号"><img src="https://img.shields.io/badge/%E5%BE%AE%E4%BF%A1%E5%85%AC%E4%BC%97%E5%8F%B7-%E4%BB%A3%E7%A0%81%E6%83%85%E7%BC%98-orange" alt="公众号"></a>
  <a href="#公众号"><img src="https://img.shields.io/badge/PDF-Git%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6-yellowgreen" alt="PDF"></a>
  <a href="#联系我"><img src="https://img.shields.io/badge/%E8%81%94%E7%B3%BB%E6%88%91%E4%BB%AC-weChat-orange" alt="联系我"></a>
</p>



## 给我一个 Star！ ⭐

如果您喜欢或者打算使用这个项目来学习或者来开始你的 `Git 版本控制`学习之路，给我一个 `Star`，谢谢！



## 版本控制的起源

- 现在的软件项目通常是由一个研发小组共同分析、设计、编码、维护以及测试的
- 针对团队开发需要解决以下问题：
  + 备份多个版本，费空间，费时间
  + 难于恢复至以前正确版本
  + 难以解决代码冲突困难
  + 难于追溯问题代码的修改人和修改时间
  + 无法进行权限控制
  + 项目版本发布困难
- 源代码管理工具就是为了解决上述问题应运而生的
---
## 版本控制(Revision Control)

 + 是维护工程蓝图的标准做法，能追踪工程蓝图从诞生一直到定案的过程。是一种记录若干文件内容变化，以便将来查阅特定版本修订情况的系统
    + 如果是团队开发，使用版本控制是强制性的！
    + 如果是单人开发，也强烈建议现在就开始使用版本控制!
- 使用版本控制可以：
  + 不会对现有工作造成任何损害
  + 不会增加工作量
  + 添加新的功能拓展时，会变得更加容易
---
## 常见版本控制工具

  + CVS	开启版本控制之门
	+ CVS 1990年诞生，远古时代的主流源代码管理工具
  + SVN	集中式版本控制之王者
	+ SVN:又称subversion，是CVS的接班人，是一款`集中式`源代码管理工具。曾经是绝大多数开源软件的代码管理工具(google code)，前几年在国内软件企业使用最为普遍
  + GIT	分布式版本控制之伟大作品
	+ GIT:一款`分布式`源代码管理工具，目前国内企业几乎都已经完成了从SVN到GIT的转换
---
- 集中式源代码管理
![](https://upload-images.jianshu.io/upload_images/647982-0038292fc7901b3c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 分布式源代码管理
![](https://upload-images.jianshu.io/upload_images/647982-b32b9194c125ecbf.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 分布式和集中式的最大区别在于：
  + 在集中式下, 开发者只能将代码提交到服务器, 在分布式下, 开发者可以本地提交
  + 在集中式下, 只有远程服务器上有代码数据库,  在分布式下,  每个开发者机器上都有一个代码数据库

- SVN(集中式)
![](https://upload-images.jianshu.io/upload_images/647982-04a8ecee2ca8e5c4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- GIT(分布式)
  ![](https://upload-images.jianshu.io/upload_images/647982-6a9d0974b77621bc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## Git和 SVN 的简单对比

- 速度
    + 在很多情况下，git的速度远远比SVN快
- 结构
    + SVN是集中式管理，git是分布式管理
- 其他
    + SVN使用分支比较笨拙，git可以轻松拥有无限个分支
    + SVN必须联网才能正常工作，git支持本地版本控制工作
    + 旧版本的SVN会在每一个目录置放一个.svn，git只会在根目录拥有一个.git
---
## GIT简介

- GIT是一款自由和开源的`分布式`版本控制系统，用于`敏捷高效`地处理任何或小或大的项目
- 在世界上所有的分布式版本控制工具中，git是最快、最简单、最流行的
- 是Linux之父李纳斯的第二个伟大作品
  + 2005年由于BitKeeper软件公司对Linux社区停止了免费使用权。
  + Linus为了辅助Linux内核的开发(管理源代码),迫不得己自己开发了一个分布式版本控制工具，从而Git诞生了

---
## GIT工作原理

- 如果想学好GIT必须先了解GIT的工作原理
- **工作区(Working Directory):** 仓库文件夹里面, 除了`.git目录`以外的内容
- **版本库(Repository):**.git目录, 用于存储记录版本信息
  - 版本库中的**暂缓区(staga):**
  - 版本库中的**分支(master):** git自动创建的第一个分支
  - 版本库中的**HEAD指针:**用于指向当前分支

---
- git add和git commit命名作用
  + git add: 把文件修改添加到暂缓区
  + ![](https://upload-images.jianshu.io/upload_images/647982-143ae6cdb18d3212.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
  + git commit: 把暂缓区的所有内容提交到当前HEAD指针指向的分支
  + ![](https://upload-images.jianshu.io/upload_images/647982-55c339632d9e540f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> GIT自学网站推荐: https://backlog.com/git-tutorial/cn/
---
## GIT使用环境

- 多人开发时需要一个`共享版本库`, 单人开发初始化一个`本地库`即可
- 共享版本库的形式:
  + 本地共享库: 文件夹/U盘/硬盘
  + 远程共享库: 自己搭建git服务器/托管到第三方平台(github/oschina等)
- 无论是单人开发还是多人开发, 客户端都可以使用命令行或者图形化界面使用git
---
## GIT命令-个人开发

- `git help` ：git指令帮助手册
  
  + 查看其他指令的做法：git help 其他指令
- `git init`  : 仓库初始化(个人仓库)
  + 仓库文件目录
  ```
  HEAD:	指向当前分支的一个提交
  description:	项目的描述信息
  config:	项目的配置信息
  info/:	里面有一个exclude文件，指定本项目要忽略的文件
  objects/:	Git对象库(commit/tree/blob/tag)
  refs/:	标识每个分支指向哪个提交
  hooks/:	默认的hook脚本
  ```
- GIT设置配置信息
  + 配置用户名：`git config user.name "用户名"`（用于跟踪修改记录）
  + 配置邮箱：`git config user.email "邮箱"`（用于多人开发间的沟通）
  + `git config -l` :	查看配置信息
  + `git config -e` :	编辑配置信息

- `git status` ：查文件的状态
  + 查看某个文件的状态：`git status 文件名`
  + 查看当前路径所有文件的状态：`git status`

- `git add` ：将工作区的文件保存到暂缓区
  + 保存某个文件到暂缓区：`git add 文件名`
  + 保存当前路径的所有文件到暂缓区：`git add .`（注意，最后是一个点 . ）

- `git commit`：将暂缓区的文件提交到当前分支
  + 提交某个文件到分支：`git commit -m ”注释” 文件名`
  + 保存当前路径的所有文件到分支：`git commit -m ”注释” `

- `git log` ：查看文件的修改日志
  + 查看某个文件的修改日志：`git log 文件名`
  + 查看当前路径所有文件的修改日志：`git log`
  + 用一行的方式查看简单的日志信息：`git log ––pretty=oneline`
  + 查看最近的N次修改：`git log –N`（N是一个整数）

- `git diff` ：查看文件最新改动的地方
  + 查看某个文件的最新改动的地方：`git diff 文件名`
  + 查看当前路径所有文件最新改动的地方：`git diff`

- `git reflog` ：查看分支引用记录（能够查看所有的版本号）

- `git rm`：删除文件（删完之后要进行commit操作，才能同步到版本库）

- `git reset `：版本回退（建议加上––hard参数，git支持无限次后悔）
  + 回退到上一个版本：`git reset ––hard HEAD^`
  + 回退到上上一个版本：`git reset ––hard HEAD^^`
  + 回退到上N个版本：`git reset ––hard HEAD~N（N是一个整数）`
  + 回退到任意一个版本：`git reset ––hard 版本号（版本号用7位即可）`

- Git忽略提交规则 - .gitignore配置
  + 别看了, 你想要的都在这[企业开发专用链接](https://github.com/github/gitignore)
```c
#               表示此为注释,将被Git忽略
*.a             表示忽略所有 .a 结尾的文件
!lib.a          表示但lib.a除外
/TODO           表示仅仅忽略项目根目录下的 TODO 文件，不包括 subdir/TODO
build/          表示忽略 build/目录下的所有文件，过滤整个build文件夹；
doc/*.txt       表示会忽略doc/notes.txt但不包括 doc/server/arch.txt
 
bin/:           表示忽略当前路径下的bin文件夹，该文件夹下的所有内容都会被忽略，不忽略 bin 文件
/bin:           表示忽略根目录下的bin文件
/*.c:           表示忽略cat.c，不忽略 build/cat.c
debug/*.obj:    表示忽略debug/io.obj，不忽略 debug/common/io.obj和tools/debug/io.obj
**/foo:         表示忽略/foo,a/foo,a/b/foo等
a/**/b:         表示忽略a/b, a/x/b,a/x/y/b等
!/bin/run.sh    表示不忽略bin目录下的run.sh文件
*.log:          表示忽略所有 .log 文件
config.php:     表示忽略当前路径的 config.php 文件
 
/mtk/           表示过滤整个文件夹
*.zip           表示过滤所有.zip文件
/mtk/do.c       表示过滤某个具体文件
 
被过滤掉的文件就不会出现在git仓库中（gitlab或github）了，当然本地库中还有，只是push的时候不会上传。
 
需要注意的是，gitignore还可以指定要将哪些文件添加到版本管理中，如下：
!*.zip
!/mtk/one.txt
 
唯一的区别就是规则开头多了一个感叹号，Git会将满足这类规则的文件添加到版本管理中。为什么要有两种规则呢？
想象一个场景：假如我们只需要管理/mtk/目录中的one.txt文件，这个目录中的其他文件都不需要管理，那么.gitignore规则应写为：：
/mtk/*
!/mtk/one.txt
 
假设我们只有过滤规则，而没有添加规则，那么我们就需要把/mtk/目录下除了one.txt以外的所有文件都写出来！
注意上面的/mtk/*不能写为/mtk/，否则父目录被前面的规则排除掉了，one.txt文件虽然加了!过滤规则，也不会生效！
 
----------------------------------------------------------------------------------
还有一些规则如下：
fd1/*
说明：忽略目录 fd1 下的全部内容；注意，不管是根目录下的 /fd1/ 目录，还是某个子目录 /child/fd1/ 目录，都会被忽略；
 
/fd1/*
说明：忽略根目录下的 /fd1/ 目录的全部内容；
 
/*
!.gitignore
!/fw/ 
/fw/*
!/fw/bin/
!/fw/sf/
说明：忽略全部内容，但是不忽略 .gitignore 文件、根目录下的 /fw/bin/ 和 /fw/sf/ 目录；注意要先对bin/的父目录使用!规则，使其不被排除。
```
---
## GIT命令-团队开发

- `git init --bare`  : 仓库初始化(共享仓库)
  + 注意: 不要直接在共享仓库中编写代码
- `git clone`：下载远程仓库到本地
  + 下载远程仓库到当前路径：git clone 仓库的URL
  + 下载远程仓库到特定路径：git clone 仓库的URL 存放仓库的路径
- `git pull`：下载远程仓库的最新信息到本地仓库
- `git push`：将本地的仓库信息推送到远程仓库
  + 提交时如果远程仓库有其它人提交的最新代码, 必须先pull, 再提交
- 冲突解决:
  + 当多个人同时修改了同一个文件时, 后提交的需要先从服务器pull代码到问题, 手动解决完冲突之后再push到远程服务器
```c
<<<<<<< HEAD
	你本地的新增的代码
=======
	服务器上和你冲突的代码
>>>>>>> e9609de28b65bf97539f94c6458cdebdf2711c9f
```
---
## GIT经典协同模型

- 中心仓库：包含master和develop两个分支
- 分支分类
  + 主要分支：master和develop分支
  + 支持性分支：特性分支，发布分支，热补丁分支
- 对于商业级项目，真正开发过程中都是基于develop分支进行的，develop分支是开发主线！
- master分支中，只存放相对稳定的分支，例如：0.1版本, 0.2版本
- 在实际产品开发中，需要“规划版本”，例如：将100个功能规划到5个不同的版本上
- 发现bug，要基于“上一个最稳定的版本”进行修复，这是热补丁分支存在的意义！
- 理解清楚版本管理分支的特性，是迭代式开发的重要基础！
![](https://upload-images.jianshu.io/upload_images/647982-96602fa3be91e763.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


- `git branch` : 查看所有分支
-  `git branch 分支名称` : 创建分支
  + 新创建的分支中的内容和master分支中的内容一样
- `git checkout 分支名称` : 切换到指定分支
- `git merge 分支名称` : 合并分支
  + 将当前所在分支和指定名称分支进行合并
-  `git branch -d 分支名称` : 删除指定分支
  + 不能在当前分支中删除自己

---
## 使用GIT我们应该

- 经常更新：降低冲突的可能性
- 提交前需在本机测试通过：降低将问题代码传到版本库
- 提交时一定写备注：方便其他员工查看和自己以后回顾
- 对于不需要提交的文件不要提交到版本库

>提示:
>- 每次提交之前先更新
>- 每天下班前提交当天编译通过的代码
>- 每天上班第一件事情更新前一天的代码

---
## GITHUB使用

- 1.注册GitHub账号
  + ![](https://upload-images.jianshu.io/upload_images/647982-48e94a59e7c767ae.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 2.登录GitHub
  + ![](https://upload-images.jianshu.io/upload_images/647982-97283b621f1aa762.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 3.点击你的仓库
  + ![](https://upload-images.jianshu.io/upload_images/647982-f25a114a2f4e2169.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 4.创建一个新的仓库
  + ![](https://upload-images.jianshu.io/upload_images/647982-12af8262b377bf13.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 5.新建的仓库可以下载, 但是提交需要账号密码
- 6.配置SSH Key
  + 6.1打开git 命令行工具
  + 输入指令``` ssh-keygen -t rsa -b 4096 -C "your_email@example.com"```
  + ![](https://upload-images.jianshu.io/upload_images/647982-cae44742691c8689.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
  + 6.2复制刚才生成的公钥
  + ![](https://upload-images.jianshu.io/upload_images/647982-7642e9233046be82.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
  + ![](https://upload-images.jianshu.io/upload_images/647982-de4e0d7d4a1a5c9d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
  + 6.3将生成好的SSH Key 添加到GitHub
  + ![](https://upload-images.jianshu.io/upload_images/647982-05b20bf92a0589e0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
  + ![](https://upload-images.jianshu.io/upload_images/647982-a30df50503d30337.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
  + ![](https://upload-images.jianshu.io/upload_images/647982-5e7e96e09c110ef1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
  + 6.4测试是否配置成功 ```ssh -T git@github.com```
  + 如果后面出现 : Hi ****! You've successfully authenticated, but GitHub does not provide shell access.证明成功
- 7.利用SSH Key操作GitHub
  + ![](https://upload-images.jianshu.io/upload_images/647982-3cafc31917484655.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

---
## oschina使用

- 和 GitHub 方法相同

## 编程常见问题汇总

1. [如何学习编程？](https://mp.weixin.qq.com/s/sb9n8dFe96XR6pRxEpZx0Q)
2. [如何选择一门编程语言？](https://mp.weixin.qq.com/s/8JeSy0fUYKVa2PrGRk8t-Q)
3. [如何做好离职交接工作？](https://mp.weixin.qq.com/s/HprdWcnNyWonwuaI74vOTw)
4. [学习编程的算法网站有哪些？](https://mp.weixin.qq.com/s/BM_osU-LX_JqELpahA59bQ)
5. 持续更新 ing

---

## 其他

### 联系我

### 编程语言学习路线

![各种技术的学习路线](https://cdn.nlark.com/yuque/0/2021/png/12653647/1636202999693-10aed6a8-00f0-476b-bc71-31ea47f477ba.png?x-oss-process=image%2Fresize%2Cw_1500%2Climit_0)

整理了一份各个技术的学习路线，需要的小伙伴加我微信：“**leader_fengy** ”备注“ **学习路线**” 即可！

![](https://cdn.nlark.com/yuque/0/2021/png/12653647/1635664638743-b3515c4e-842f-4a65-8240-bb330e3fe554.png)

### 公众号

如果大家想要实时关注我们更新的文章以及分享的干货的话，可以关注我们的微信公众号“**代码情缘**”。

**《C语言保姆级教程》:**《**Go语言保姆级教程**》《**Git版本控制**》PDF 版本在[微信公众号](#公众号)后台回复 **"书籍"** 即可免费领取！

![我的公众号](https://cdn.nlark.com/yuque/0/2021/jpeg/12653647/1635665327539-b1156e20-fe8c-430b-9c24-1f3b834942ac.jpeg)
