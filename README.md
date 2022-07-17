# rebase-preserve-merge

## with the feature branch (!)

### intial state

![initial repo state](./doc/INITIAL_REPO_STATE.PNG?raw=true)

### simple rebase

Git will rewrite (rebase) these 4 commits (without the merge commit):

![simple rebase detail](./doc/SIMPLE_REBASE_DETAIL.PNG?raw=true)

Git will keep the commits leading to the `feature/a` branch.

```
git checkout project/p1
git rebase master
```

![after simple rebase](./doc/SIMPLE_REBASE.PNG?raw=true)

### rebase --preserve-merges

Git will rewrite (rebase) all the 5 commits (including the merge commit):

![preserve-merges detail](./doc/PRESERVE_MERGES_WITH_FEATURE_BRANCH_DETAIL.PNG?raw=true)

Git will keep the commits leading to the `feature/a` branch.

```
git checkout project/p1
git rebase --preserve-merges master
warning: git rebase --preserve-merges is deprecated. Use --rebase-merges instead.
Successfully rebased and updated refs/heads/project/p1.
```

![after preserve-merges with feature branch](./doc/PRESERVE_MERGES_WITH_FEATURE_BRANCH.PNG)

## without the feature branch

### intial state

![initial repo state 2](./doc/INITIAL_REPO_STATE_2.PNG?raw=true)

### simple rebase

Git will rewrite (rebase) these 4 commits (without the merge commit):

![simple rebase detail](./doc/SIMPLE_REBASE_DETAIL_2.PNG?raw=true)

```
git checkout project/p1
git rebase master
```

![after simple rebase 2](./doc/SIMPLE_REBASE_2.PNG?raw=true)

### rebase --preserve-merges

Git will rewrite (rebase) all the 5 commits (including the merge commit):

![preserve-merges detail 2](./doc/PRESERVE_MERGES_WITHOUT_FEATURE_BRANCH_DETAIL.PNG?raw=true)

```
git checkout project/p1
git rebase --preserve-merges master
warning: git rebase --preserve-merges is deprecated. Use --rebase-merges instead.
Successfully rebased and updated refs/heads/project/p1.
```

![after preserve-merges without feature branch 2](./doc/PRESERVE_MERGES_WITHOUT_FEATURE_BRANCH.PNG)

### rebase --rebase-merges

Git will also rewrite (rebase) all the 5 commits (including the merge commit).

```
git checkout project/p1
git rebase --rebase-merges master
```

![after rebase-merges without feature branch](./doc/REBASE_MERGES_WITHOUT_FEATURE_BRANCH.PNG)