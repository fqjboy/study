### git的bug分支

---

1. 在master分支上建立dev分支，然后此时dev分支做了一些改动。此时发现master分支有bug，这个bug当然也体现在dev分支上，此时git stash保存dev分支状态；
2. 然后切换到master分支，建立一个临时分支issue-1，在这个临时分之上对bug进行修改，改好后提交。
3. 切换回master分支，合并issue-1的分支；
4. 合并后，切换到dev分支，git stash pop恢复状态，同时删除stash状态，可用git stash list查看；
5. 查看在issue-1分支提交时的版本号，然后用命令git cherry-pick  <版本号>修复dev分支的bug，此时会提示有冲突，但实际上代码已经修改，只要提交就可以了；