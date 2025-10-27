# practice-rebase-demo

## What is merge?
Purpose:
Combines changes from one branch into another, keeping both branches’ history.

Type:
Can be either a fast-forward merge or a three-way merge depending on history.

## Example: fast-forward merge
### You’re on main
git checkout main

### Bring in changes from feature (which is ahead of main)
git merge feature

Result:
A---B---C---D  (main, feature)
main just “fast-forwards” to the same commit as feature.
No new merge commit is created.


## Example: Three-way merge
#### main has commits A-B-C
#### feature branched off at B and added D and E

```` 
git checkout main
git merge feature

History before merge:
A---B---C           (main)
     \
      D---E         (feature)

History after merge (three-way merge:
A---B---C-------F (main)
     \         /
      D-------E (feature)

Git creates a new merge commit (F) that combines the changes from both sides.
````

## What is rebase?

### Purpose:
Moves or “replays” commits from one branch on top of another to create a linear history.
It doesn’t create a merge commit (unless conflicts appear).

```` 
git checkout feature
git rebase main

Before rebasing: 
A---B---C (main)
     \
      D---E (feature)

After rebasing: 
A---B---C---D'---E' (feature)
````

## Other examples
