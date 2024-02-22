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

## `git revert`

[`git revert`使用以及理解](https://blog.csdn.net/allanGold/article/details/111372750)

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

## todo

- [`git fetch`](https://www.yiibai.com/git/git_fetch.html)
- [`git cherry-pick`](https://www.ruanyifeng.com/blog/2020/04/git-cherry-pick.html)
- [Git删除远程某个历史提交记录](https://www.jianshu.com/p/18b5cbc3e702)
- [`git rebase`](https://lvan-zhang.blog.csdn.net/article/details/128848133?spm=1001.2101.3001.6650.2&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-2-128848133-blog-106479779.235%5Ev43%5Epc_blog_bottom_relevance_base9&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-2-128848133-blog-106479779.235%5Ev43%5Epc_blog_bottom_relevance_base9&utm_relevant_index=1)
- [冲突解决](https://www.kingname.info/2020/09/13/how-to-reslove-conflict/)和[github实验](https://learn.microsoft.com/zh-cn/training/modules/resolve-merge-conflicts-github/?WT.mc_id=DT-MVP-5003916)