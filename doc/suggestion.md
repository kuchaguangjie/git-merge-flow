# Suggestion

[Readme](../README.md)

## Which to use?
- Each method has its advantage & disadvantage, choose one according to the requirement & commit status.
  - All methods may reach the same final content, though the commit history might be different.
- Reduce possible conflicts, could be at least as important as which method to use.
  - If there are too much conflicts, it may be messy & difficult despite which method is chosen.

## To reduce conflict:
- Merge early, pull often.
- Split tasks among multiple developers, in ways that might create fewer conflicts.
- Organize code structures, in ways that might create fewer conflicts.

## On merge:
- Could optionally merge in some kind of newly created tmp branch, if succeeded, then merge to shared common branches (e.g `dev`, `master`).
  - So that if code get messy after merge, you may always easily discard it by discarding the tmp branch.
