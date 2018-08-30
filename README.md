# Branch and Merge Practice 

## The Problem

KU Cafe has a separate Breakfast menu and regular menu.  The Cafe owner is an SKE graduate who used git branches for the two menus:

| Branch       | Menu   |
|--------------|--------|
| `master`     | regular (day) menu |
| `breakfast`  | breakfast menu |

Now, KU Cafe wants to combine the two into a single menu.

Do the following.  Please perform all the steps below.  
If your repository doesn't contain the "merges" described here you won't learn anything. You won't get credit, either.

## Reference

[Basic Branching and Merging](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging) in online [Git Book](https://git-scm.com/book/en/v2).

## Exercises

> **Caution:**  You will be working on different branches. If you edit this README file on different branches, you will need to be careful.  It is easier to either a) edit README.md on master after you finish step 13, or b) edit a copy of README outside of the repo, then copy it back into `master` before final commit.

1. Clone the repository from Github. Clone both `master` and `breakfast` branches as tracking branches.  There are a few ways to do this.

2. Check that you have both branches and they track the remote.  

3. On the master branch, view file `menu.md`.  Then checkout the "breakfast" branch and view `menu.md`.  What are the differences?  
> Can you view differences between branches visually using a GUI tool or Github?    
> This is something to explore on your own.

4. Create a feature branch off of master for creating the new, unified menu.  First switch to `master`. Then create a new branch named `dev-one-menu` and switch to it.  What is(are) the command(s) for this?
```
cmd> git branch dev-one-menu
cmd> git checkout dev-one-menu
```

5. (Optional) Are you tired of typing "git checkout xxxx"?  Create an alias "co" so you can just type "git co branchname" (Subersion has this alias):
```
cmd> git config --global alias.co checkout
cmd> git co master
cmd> git co dev-one-menu
```

6. Check the `menu.md` file. It should be exactly same as the file on master.  You want to combine this file with `menu.md` in the "breakfast" branch, so try merging branch "breakfast" into this branch:
```
cmd> git merge breakfast
```

7. What did git do?  What is in `menu.md` now?

8. If you don't like the results of a merge, you can undo it.  The best command for this is:
```
cmd> git reset --merge
```
> There are two commands that work: `git reset --hard HEAD` and and `get reset --merge`. `reset --merge` keeps local changes that have not been commited or staged.  See [git help reset](https://git-scm.com/docs/git-reset).

9. Do the merge again.  This time, you will "resolve" the conflicts manually.  After you merge, edit `menu.md` with a text editor to see what has changed.  There are several "diffs" in the file.
```shell
cmd> git merge breakfast
cmd> edit menu.md  (use any text editor you like)
```
> As a programmer, you'll need a good text editor.  
> Something better than the Windows Notepad or Wordpad.    
> A visual "diff" tool is also useful (if your editor doesn't have one).    
> For code, Eclipse EGit has a good built-in merge tool.

10. To manually "resolve" the conflicts in this file you can use an editor or a GUI merge tool.
    * The important thing is to know how to read the "diffs" in the file.  This is explained in class.
    * Demo how to merge conflicts in class.
    * Instructor will use `git mergetool` for visual merging

11. After you have successfully fixed the conflicts, you should test the result.
    * In a software project you would run *unit tests*. 
    * For this project, we can just preview the menu, using a Markdown preview tool.

12. Commit your revised `menu.md`. Write a good, descriptive commit message since you merged conflicting files.

13. Switch back to "master" and merge the `dev-one-menu` branch.  This time the merge is easy.  Wny?
    * After that, make changes to README.md on `master` and commit it.
  
14. Push the updated `master` branch to Github.

15. Should you push the `dev-one-menu` branch?
    * On a team project you would, so that you can issue a "pull request" before merging into master.
    * On an individual project its your preference. Some people delete feature branches after merging them, so no need to "push" it.


