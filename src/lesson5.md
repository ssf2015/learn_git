补充一些git的命令


git log -p

-p 是 --patch 的缩写，通过 -p 参数，你可以看到具体每个 commit 的改动细节

git log --stat

如果你只想大致看一下改动内容，但并不想深入每一行的细节，那么可以把选项换成 --stat


如果你想看某个具体的 commit 的改动内容，可以用 show

git show 直接查看当前的commit 或者后面加sha-1码 前4位就ok 如果是指定的文件 在后面再加上文件名就ok
```
diff (1工作区，2暂存区，3上一条commit)

如果是1和2对比 用git diff

如果是1和3对比 用git diff HEAD

如果是2和3对比 用git diff --staged
```


还有个gitk  图形化界面 不过mac上不是很清楚 从头看到尾
