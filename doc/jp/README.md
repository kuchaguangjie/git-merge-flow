# git-merge-flow (日本語)

[English](../../README.md) |
[中文](../cn/README.md)

git のさまざまなマージ プロセスをテストします。

## マージ 方法
- `git merge <commit>`
  - If there are conflict, need to resolve by hand, or reset by hand.
- `git cherry-pick <commit>`
  - If there are conflict, could choose resolve by hand and continue, or auto abroad.
- `git rebase <upstream>`
  - If there are conflict, could choose resolve by hand and continue, or auto abroad.
  - It avoid unneeded commits on merge, thus may get a neat commit history.

## 例
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

## コミット変更グラフ
[graph - commit change](../graph-commit-change.md)

## 例でコミットを再作成する方法:
[re-create commits](../re-create-commits.md)

## 提案
[suggestion](../suggestion.md)

## 参考文献
- [SO - merge & cherry-pick & rebase](https://stackoverflow.com/a/1241829)
- 公文書:
    - [git merge](https://git-scm.com/docs/git-merge)
    - [git cherry-pick](https://git-scm.com/docs/git-cherry-pick)
    - [git rebase](https://git-scm.com/docs/git-rebase)

## 参考文献
- [SO - merge & cherry-pick & rebase](https://stackoverflow.com/a/1241829)
- 公文書:
    - [git merge](https://git-scm.com/docs/git-merge)
    - [git cherry-pick](https://git-scm.com/docs/git-cherry-pick)
    - [git rebase](https://git-scm.com/docs/git-rebase)
- チュートリアル (Bitbucket):
    - [git merge - strategies](https://www.atlassian.com/git/tutorials/using-branches/merge-strategy)
    - [git merge - conflict](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts)
    - [cherry-pick - with graph](https://www.atlassian.com/git/tutorials/cherry-pick)
- 他の:
    - [merge strategy](https://blog.mergify.com/whats-the-best-git-merge-strategy) (from mergify.com)

## TODOs
- さまざまなマージ方法をさらに比較します。
