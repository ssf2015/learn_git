前面比较基础 后面开始进阶内容

进阶之head master branch


head通俗点说是"当前commit"的引用，永远永远永远指向当前的commit，所以你永远可以用 head 来操作当前 commit。
master 其实就是默认的branch  其有两个特点:

1新创建的 repository（仓库）是没有任何 commit 的。但在它创建第一个 commit 时，会把 master 指向它，并把 HEAD 指向 master。

2当有人使用 git clone 时，除了从远程仓库把 .git 这个仓库目录下载到工作目录中，还会 checkout （签出） master
（checkout 的意思就是把某个 commit 作为当前 commit，把 HEAD 移动过去，并把工作目录的文件内容替换成这个 commit 所对应的内容）。


如何创建分支并切换过去（切换过去的意思其实就是改变head指向）

1 git branch <分支名> 

2 git checkout <分支名>

或者直接 git checkout -b <分支名>

这个时候你来回切换并且提交的话 分叉就真的出现了！

删除branch 直接git branch -d <分支名> 不过要注意如果head指向当前的分支是不能删除的（其实很容易理解假设head指向的是处于激活状态的分支，
那这时可以删除的只能是未被激活的，这时可以先用git checkout 改变head指向 再删除就可以啦，嘿嘿嘿）

那么问题来了 删除branch 到底删除的是什么呢

其实branch也仅仅是一个引用 删除branch不会删除任何commit 只是删除对这个commit的引用，然后如果在一定的时间内没有任何branch
会回溯到这个commit上 这些在分支上的commit就会被git的垃圾回收机制收回！！！nice！


git branch -a 查看所有'branch'以及当前处于激活状态的分支

再次总结：

HEAD 是指向当前 commit 的引用，它具有唯一性，每个仓库中只有一个 HEAD。在每次提交时它都会自动向前移动到最新的 commit 。

branch 是一类引用。HEAD 除了直接指向 commit，也可以通过指向某个 branch 来间接指向 commit。当 HEAD 指向一个 branch 时，
commit 发生时，HEAD 会带着它所指向的 branch 一起移动。

master 是 Git 中的默认 branch，它和其它 branch 的区别在于：

新建的仓库中的第一个 commit 会被 master 自动指向；

在 git clone 时，会自动 checkout 出 master。

branch 的创建、切换和删除：

创建 branch 的方式是 git branch 名称 或 git checkout -b 名称（创建后自动切换）；

切换的方式是 git checkout 名称；

删除的方式是 git branch -d 名称。 

强制删除git branch -D 名称  

当你在分支上commit了内容 后面又用不到时可以用（慎用，删除后可能会引起不可回溯，也就是彻底死翘翘）
