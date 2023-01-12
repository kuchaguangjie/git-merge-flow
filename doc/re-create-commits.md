# Re-create commits

[Readme](../README.md)

This shows how to create the commits in a new git project, and do various merges.  
Though the commit hash will be different when you re-run the steps.

## Steps:
```
* feature a and b,
  commit: d0c4776bf
  tag:    v0.1
*
* team 1 start to work on v2 of feature a and b,
  branch: feat-ab_v2 (start from v0.1),
*
* at the sametime, team 2 continue to work on feature c, and also does a project-wide refactor, that also effect feature a and b,
  commits: 27104ba5, 1338ff4b2,
  tag:    v0.2
*
* team 1 commit v2 of feature a and b,
  commit: 51dd133e81
  branch: feat-ab_v2
*
* release-admin merge commits in feat-ab_v2 branch into master, (there are conflicts in files),
  ways:
    * git merge <commit>
      branch:     rl-v0.3_via_merge (start from v0.2)
      commit: de329db2
      tag:    v0.3

      sub steps:
        * if there are conflict, need resolve by hand,
        * then commit again,
        * then can merge rl-v0.3_via_merge into master, without conflict,
        * after test, can delete branch rl-v0.3_via_merge,
        *
    * git cherry-pick <commit>
      branch:     rl-v0.3_via_cherry_pick (start from v0.2)
      commit: de329db2
      tag:    v0.3_via_cherry_pick

      sub steps:
        * if there are conflict, need resolve by hand first,
        * git add <files..>
        * then run:
          git cherry-pick --continue
          // edit commit comment, and save,
        *
        * then can merge rl-v0.3_via_cherry_pick into master, without conflict,
          tips: if already merged to master in another way, then can skip this step,
        * after test, can delete branch rl-v0.3_via_cherry_pick,
        *
    * git rebase <upstream>
      branch:     rl-v0.3_via_rebase
      commit:
    *

  tips:
    * if more than 2 ways are used, their final result should be the same,
      // this shows no difference,
      git diff rl-v0.3_via_cherry_pick rl-v0.3_via_merge
    *
*
```

