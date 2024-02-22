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

## `git reset`

[`git reset`三种模式](https://www.jianshu.com/p/c2ec5f06cf1a)

1. `git reset --hard` (暂存区和工作区的东西都会舍弃)
2. `git reset --soft` (暂存区和工作区保持不变，reset导致的差异转到暂存区)
3. `git reset --mixed` (default) (暂存区、工作区、reset导致的差异通通转到工作区.效果看起来就是原节点和Reset节点之间的所有差异都会放到工作目录中)

## indetermination

main分支 / dev分支

```
git checkout -b dev_xx
# 在dev_xx分支上
git commit
git fetch origin dev
git merge dev  # 需要的话解决冲突

# 在dev分支上
git merge dev_xx
git push
```

## `git revert`

[`git revert`使用以及理解](https://blog.csdn.net/allanGold/article/details/111372750)