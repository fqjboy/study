### git删除操作

---

1. 工作区新建文件后，如果没有git add以及git commit时，删除工作区此文件后无法恢复；
2. 工作区新建文件后，git add或者git add及git commit了，那么此时删除工作区文件后，可以通过git checkout恢复文件；
3. 新建文件git add或者git add及git commit了之后，如果git rm了此文件，那么工作区文件删除后无法恢复，因为此时暂存区或者版本库里的此文件都被删除；