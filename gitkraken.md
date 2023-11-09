# gitkraken,团队开发利器（代码的pull和push）
对于一个项目的团队开发，我们经常使用一些工具进行代码的pull与push，从而对一段代码进行团队协作的编写与修改。
对此我们经常用到某些工具，例如**Git Bush**,以及带有Git Bush功能的编译器(例如vs code)。
## 1.Git Bash
 ![Git Bush](./../image/Git%20Bush.png)

但是Git Bush页面简陋,不好上手操作,难以理解，指令复杂难懂。关于它的用法和指令此篇文章中不会详细展开。
### 2.vs code
![Git Bush](./../image/vs%20code.png)
此处Git Bush成为vs code的一个功能，但具体操作方法与Git相同，此处不重点介绍。
#### 3.GitKraken
接下来将主要介绍一款软件**GitKraken**，有效的减少了传输代码的难度，且能更加清晰的看到团队协作的流程。在GitKraken上，我们可以直接在软件中对于拉到本地的文件进行修改，直接push到远端仓库,后**发起PR**。使流程更加简便易懂。
![Git Bush](./../image/GitKraken.png)
下载网址https://www.gitkraken.com/

1.在github上fork目标仓库。
2.进入GitKraken并克隆仓库。(clone a repo)
![Git Bush](./../image/zhuyemian.png)
 填写需要克隆的地址（本地文件夹）以及fork后的仓库URL
![Git Bush](./../image/clone.png)
3.进入repo
![Git Bush](./../image/仓库.png)
进入后可直观的看到其他团队成员对于目标仓库的PR流程，分支等信息。
4.在页面右侧单击需要修改的文件,单击file view进行修改。
![Git Bush](./../image/修改.png)
5修改好后点击Diff View，右侧页面改变
![Git Bush](./../image/change.png)
6.点击Stage all changes
![Git Bush](,/../../image/after.png)
可在commit message中填写相关备注。
7.在仓库页面中新建分支
![Git Bush](./../image/new.png)
8.push 文件到自己的远端仓库
![Git Bush](./../image/push.png)
9.在自己github上发起PR，等待审核。

相对于前两种方法，GitKraken更加方便快捷，将指令转化为具体操作，对团队新手较为友好。
