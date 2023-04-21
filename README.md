# LearnGit
## 1. Introduction Sequence
1. These commands are used for saving the changes made to the repository as commits, as a set of changes from one version of the repository to the next, like recording snapshots of the project.
   ```
   git commit
   git commit
    ```

2. This command is used for creating a new branch and moving into it at the same time.
   ```
   git checkout -b bugFix
   ```

3. These commands create a special commit that has two unique parents that contains all the work made in both branches, by merging them.
   ```
   git checkout -b bugFix
   git commit
   git checkout main
   git commit
   git merge bugFix
   ```

4. These commands take a set of commits and make a linear sequence of them, looking like these two features were developed sequentially, when in reality they were developed in parallel.
   ```
   git checkout -b bugFix
   git commit
   git checkout main
   git commit
   git checkout bugFix
   git rebase main
   ```

## 2. Ramping Up
1. This command allows to detach HEAD from the branch and attach it to the commit.
   ```
   git checkout C4
   ```

2. This command allows to detach HEAD from the branch and attach it to the parent commit of the branch, using relative refs.
   ```
   git checkout bugFix^
   ```

3. These commands move by force the branches to the commits I want.
   ```
   git checkout HEAD^
   git branch -f main C6
   git branch -f bugFix C0
   ```

4. These commands reverse changes by moving a branch reference backwards in time to an older commit, using reset for local branches and revert for remote branches.
   ```
   git reset HEAD^
   git checkout pushed
   git revert pushed
   ```

## 3. Moving Work Around
1. This command allows to copy a series of commits I desire below the current location.
   ```
   git cherry-pick C3 C4 C7
   ```

2. This command allows to relocate a series of commits in the order and picking the specific commits I want. It is useful when I don't know which commits I want.
   ```
   git rebase -i HEAD~4
   ```

https://learngitbranching.js.org/
