# Graph - how commits change

[Readme](../README.md)

---
## git merge
- Command:
  > git checkout master  
  > git merge topic
- From
```
  	  A---B---C topic
	 /
    D---E---F---G master
```
- To
```
	  A---B---C topic
	 /         \
    D---E---F---G---H master (contains all changes in topic)
```

---
## git cherry-pick
- Command:
  > git checkout master  
  > git cherry-pick F
- From
```
    A - B - C - D   master
         \
           E - F - G topic
```
- To
```
    A - B - C - D - F   master (contains changes in commit F)
         \
           E - F - G topic
```

---
## git rebase
- Command:
  > git checkout topic  
  > // Tip: merge master into topic.   
  > git rebase master
- From
```
          A---B---C topic
         /
    D---E---F---G master
```
- To
```
                  A'--B'--C' topic (contains changes in master)
                 /
    D---E---F---G master
```
