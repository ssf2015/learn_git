多人协同开发时

第n个人（n>=2）,需要：

1 git clone

2 修改文件后 先git pull 拉取远端最新代码

3 然后git 三部曲 git add ./ git commit /git push



_总结：多人开发时 懒人方法： 先按照git三部曲提交数据，如果最后一步push失败 先pull再push
（git pull其实就是把本地仓库的提交和中央仓库的提交进行合并）_


小知识：**git commit -m '' 和git commit -am ''**
区别： 修改文件后 后者不需要git add 也就是后者不需要文件暂存 就可以直接提交 而前者如果不先git add 暂存一下 提交的就是空

实际开发中 如果有文件增加 还是需要git add把文件改成跟踪状态的
如果只是修改 只需要git commit -am '' 和 git push 两步就ok了
