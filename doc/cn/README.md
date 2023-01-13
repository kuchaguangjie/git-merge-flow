# git-merge-flow (中文)

[English](../../README.md) |
[日本語](../jp/README.md)

测试 git 的 多种 合并 流程.

## 合并 方法
- `git merge <commit>`
  - If there are conflicts, need to resolve by hand, or reset by hand.
- `git cherry-pick <commit>`
  - If there are conflicts, could choose to resolve by hand and continue, or auto abort.
- `git rebase <upstream>`
  - If there are conflicts, could choose to resolve by hand and continue, or auto abort.
  - It avoids unneeded commits on merge, thus may get a neat commit history.

## 例子
### branches:
  - `rl-v0.3_via_merge`, is merged via `git merge`.
  - `rl-v0.3_via_cherry_pick`, is merged via `git cherry-pick`.
  - `rl-v0.3_via_rebase`, is merged via `git rebase`.
###  master
  - Though `master` is merged with `rl-v0.3_via_merge`.
  - But all 3 `rl-v0.3_via<xxx>` branches have the same final content, you may verify via:
    - `git diff v0.3 rl-v0.3_via_merge`
    - `git diff v0.3 rl-v0.3_via_cherry_pick`
    - `git diff v0.3 rl-v0.3_via_rebase`
### tags
  - v0.1
  - v0.2
  - v0.3 (this is the merged release on master)

## Commit 变化图
[graph - commit change](../graph-commit-change.md)

## 如何 重新 创建 例子中的 commits:
[re-create commits](../re-create-commits.md)

## 建议
[suggestion](../suggestion.md)

- [SO - merge & cherry-pick & rebase](https://stackoverflow.com/a/1241829)
- 官方文档:
    - [git merge](https://git-scm.com/docs/git-merge)
    - [git cherry-pick](https://git-scm.com/docs/git-cherry-pick)
    - [git rebase](https://git-scm.com/docs/git-rebase)

## 参考资料
- [SO - merge & cherry-pick & rebase](https://stackoverflow.com/a/1241829)
- 官方文档:
    - [git merge](https://git-scm.com/docs/git-merge)
    - [git cherry-pick](https://git-scm.com/docs/git-cherry-pick)
    - [git rebase](https://git-scm.com/docs/git-rebase)
- 教程 (Bitbucket):
    - [git merge - strategies](https://www.atlassian.com/git/tutorials/using-branches/merge-strategy)
    - [git merge - conflict](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts)
    - [cherry-pick - with graph](https://www.atlassian.com/git/tutorials/cherry-pick)
- 其他:
    - [merge strategy](https://blog.mergify.com/whats-the-best-git-merge-strategy) (from mergify.com)

## TODOs
- 对不同 merge 方法 做更多 比较.
