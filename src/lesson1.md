github 创建好一个项目后 使用git clone 克隆到本地

git log 查看提交信息 q退出

git status 查看工作目录当前工作指令

如果有本地有改动 git status会告诉你modify的文件

上传：
1 git add <file>   //单个文件可以直接写文件名 n个文件可以用.

2 git commit 会打开一个vim 按i 进入编辑模式 Add "文件名" esc=>连按两次大写Z退出

两步完成 代码成功暂存到本地仓库

3 这个时候输入git status 可以看到你本地的仓库已经领先远程仓库n个版本的提示信息 让你git push 照做后本地仓库代码成功上传到远端仓库

```总结：
1 git status 好东西 随时查看当前状态
2 git log 查看你的提交记录
3 提交三部曲  git add . => git commit => git push  （完整的从本地到远端的命令）
4 加油！`````
