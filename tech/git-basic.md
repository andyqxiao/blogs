# Git基本概念
## 摘要
* 工作区、仓库区与暂存区
* 工作区、仓库区与暂存区的转换
* 工作区、仓库区与暂存区的文件比较

### 工作区、仓库区与暂存区

工作区：当前目录。

仓库区：.git目录所代表的本地仓库及远程仓库。

暂存区：下一次提交的改动。

#### 工作区、仓库区与暂存区的转换

工作区到暂存区 `git add <file>`

暂存区到工作区 `git reset -- <file>`

暂存区到仓库区 `git commit`

仓库区到暂存区 `git reset --soft <commit>`

工作区到仓库区 `git commit -a`

仓库区到工作区 `git checkout <commit>`



#### 工作区、仓库区与暂存区的文件比较

工作区与暂存区比较 `git diff`

暂存区与仓库区(HEAD)比较 `git diff --cached`

工作区与仓库区(HEAD)比较 `git diff HEAD`

### branch/tag的管理

#### 删除

查看远程分支 `git branch -a`
删除远程分支和标签 `git push origin --delete <name>`
`git push origin :<name>`

`git tag -d <name>`
`git push origin :refs/tags/<name>`

`git fetch origin tag <name>`

#### 删除未被跟踪的文件 (git clean)

删除目录 `git clean -fd`

删除忽略文件 `git clean -fX`

此命令删除忽略文件，在重新构建项目时特别有用，可以保留新建的文件。

删除所有文件 `git clean -fx`
