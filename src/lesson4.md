push其实就是把本地暂存的推到远端

但是有几个注意点 git push 只能用在你当初从远端git clone下来的branch 上

比如说 你git clone的项目只有一个master 当你在本地的master 分支处于head状态时 git push 就ok的
但是如果你本地新建了一个分支 就不能直接用git push了  为什么？ 因为远端没有啊 傻不傻！那要怎么办 ？
2个办法

1，git push origin <分支名>

2，或者改一下git config的设置 把push.config的值设置成current 这样就自动推向远端仓库的同名分支，easy！

我是懒人 直接 git config --global push.default current 了 。



进阶之 merge

merge 顾名思义 合并 之前b1 b2 分支上开发完成了 

我现在要把 b1 b2 上的东西合并到master 怎么搞？

首先 git checkout master 检出到你想要合并到的分支上

然后 git merge b1
    git merge b2
    
   
   这样 就会生成2次新的commit  一次是master合并了b1 后新的commit 一次是新的commit 合并了b2后更加新的commit
   
   
思考：这个时候有两个问题

    1，n个分支只能这样一条一条的去合并吗 应该有简单方法
    2，合并后 b1 b2理论上完成使命了 这个时候是不是需要手动git branch -d b1 b2 去删除对这两个分支的引用从而让git的垃圾回收机制回收


merge中的特殊情况

   1，改了同一段代码会出现冲突 这个时候手动改一下就好啦 如果不想手动改 直接 git merge --abort 放弃解决冲突 取消merge
   

其他特殊情况都不算特殊 反正原则就是 最后都到最新的commit上 所以不用管

思考：现在还有个需要解决的问题 merge后 我远端的b1 b2 怎么删除？

git branch -d <仓库名> 删除本地的仓库  git push origin -d <仓库名> 删除远端的仓库

这个延伸出了pull request 

这个其实就是把分支提交的独立出来 这样别的同事直接去上面看 所有你分支上做的改动别人都能看到 然后觉得ok了
就可以一键merge 和一键删除远端分支仓库 最后你只要本地再git pull一下 然后本地删除分支 ok！一次轮回达成！


//b4 test pullrequest
//再加点东西
