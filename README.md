# git-merge-flow

[中文](doc/cn/README.md) |
[日本語](doc/jp/README.md)

Test various git merge flows.

## merge methods
- `git merge <commit>`
  - If there are conflicts, need to resolve by hand, or reset by hand.
- `git cherry-pick <commit>`
  - If there are conflicts, could choose to resolve by hand and continue, or auto abort.
- `git rebase <upstream>`
  - If there are conflicts, could choose to resolve by hand and continue, or auto abort.
  - It avoids unneeded commits on merge, thus may get a neat commit history.

## Example
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

## How commits change
  [graph - commit change](doc/graph-commit-change.md)

## How to re-create commits in the example:
[re-create commits](doc/re-create-commits.md)

## Suggestions
[suggestion](doc/suggestion.md)

## References
- [SO - merge & cherry-pick & rebase](https://stackoverflow.com/a/1241829)
- Official doc:
    - [git merge](https://git-scm.com/docs/git-merge)
    - [git cherry-pick](https://git-scm.com/docs/git-cherry-pick)
    - [git rebase](https://git-scm.com/docs/git-rebase)
- Tutorial (from Bitbucket):
  - [git merge - strategies](https://www.atlassian.com/git/tutorials/using-branches/merge-strategy)
  - [git merge - conflict](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts)
  - [cherry-pick - with graph](https://www.atlassian.com/git/tutorials/cherry-pick)
- More:
  - [merge strategy](https://blog.mergify.com/whats-the-best-git-merge-strategy) (from mergify.com)

## TODOs
- Do more comparison on various merge methods.
