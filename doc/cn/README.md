# git-merge-flow (中文)

[English](/readme.md) | [日本語](/doc/jp/readme.md)

测试 git 的 多种 合并 流程.

## 合并 方法
- `git merge <commit>`
  - If there are conflict, need to resolve by hand, or reset by hand.
- `git cherry-pick <commit>`
  - If there are conflict, could choose resolve by hand and continue, or auto abroad.
- `git rebase <upstream>`
  - If there are conflict, could choose resolve by hand and continue, or auto abroad.
  - It avoid unneeded commits on merge, thus may get a neat commit history.

## 例子
### branches:
  - `rl-v0.3_via_merge`, merge via `git merge`.
  - `rl-v0.3_via_cherry_pick`, merge via `git cherry-pick`.
  - `rl-v0.3_via_rebase`, merge via `git rebase`.
###  master
  - Though `master` merged with `rl-v0.3_via_merge`.
  - But all 3 `rl-v0.3_via<xxx>` branches has the same final content, you may verify via:
    - `git diff v0.3 rl-v0.3_via_merge`
    - `git diff v0.3 rl-v0.3_via_cherry_pick`
    - `git diff v0.3 rl-v0.3_via_rebase`
### tags
  - v0.1
  - v0.2
  - v0.3 (this is the merged release on master)

## 如何 重新 创建 例子中的 commits:
  [re-create commits](../re-create-commits.md)

## 参考资料
- [SO - merge & cherry-pick & rebase](https://stackoverflow.com/a/1241829)
- 官方文档:
    - [git merge](https://git-scm.com/docs/git-merge)
    - [git cherry-pick](https://git-scm.com/docs/git-cherry-pick)
    - [git rebase](https://git-scm.com/docs/git-rebase)
