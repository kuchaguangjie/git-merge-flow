# git-merge-flow

Test various git merge flow.

## merge methods
- `git merge <commit>`
  - If there are conflict, need to resolve by hand, or reset by hand.
- `git cherry-pick <commit>`
  - If there are conflict, could choose resolve by hand and continue, or auto abroad.
- `git rebase <upstream>`
  - If there are conflict, could choose resolve by hand and continue, or auto abroad.
  - It avoid unneeded commits on merge, thus may get a neat commit history.

## Example
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

## How to re-create commits in the example:
  [re-create commits](doc/re-create-commits.md)
