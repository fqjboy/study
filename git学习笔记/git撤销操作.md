### git撤销操作

---

1. 工作区某文件修改之后，没有git add时，此时手动删除或者git checkout -- filename均可恢复至修改前的内容；
2. 工作区某文件修改之后，git add到了暂存区，然后此时工作区又做了修改，此时git checkout -- filename会将内容恢复至暂存区的状态；所以，git checkout命令就是将文件状态恢复至最新一次git add 或者git commit时的状态。比如在工作区某文件改动了两次，那么git checkout之后这两次修改都会撤销，因为这两次修改后没有git add 或者git commit，而如果工作区修改某文件后git add 了，之后再修改文件，这时git checkout会将文件恢复至git add的状态；
3. 工作区某文件修改后，git add到了暂存区，此时想要撤销git add这一步，用命令git reset HEAD filename，这个命令撤销了暂存区的内容，但并没有对工作区内容进行撤销，如果想接着撤销工作区内容，需要执行git checkout命令；
4. 如果工作区文件修改后，git add并git commit了，那么想要撤销修改就要版本回退了，既git reset --hard HEAD^或者git reset --hard <版本号>；