# Git

## `git pull` & `git pull --rebase`

在dev分支上执行操作

```
git pull
git push

# 等价于
git fetch
git merge origin/dev
git push
```

```
git pull --rebase
git push

# 等价于
git fetch
git rebase --origin/dev
git push
```

## git reset

1. `git reset --hard` (暂存区和工作区的东西都会舍弃)
2. `git reset --soft` (暂存区和工作区保持不变，reset导致的差异转到暂存区)
3. `git reset --mixed` (default) (暂存区、工作区、reset导致的差异通通转到工作区.效果看起来就是原节点和Reset节点之间的所有差异都会放到工作目录中)

## indetermination

main分支 / dev分支

- 个人在本地仓库新建一个dev_xx分支，并在上面开发，开发完成后合并到本地dev上，然后push到云端dev分支上
- 如果push成功，结束；如果push失败，可能是其他开发者在云端dev分支上增加了新内容，此时为了云端dev分支的美观，可以使用`git pull --rebase`命令同步到本地，然后再push

```
git checkout -b dev_xx
git commit
git checkout dev
git merge dev_xx
git push

# success 结束

# fail 
git pull --rebase
git push
git checkout dev_xx
git reset --hard dev
# 继续开发
```