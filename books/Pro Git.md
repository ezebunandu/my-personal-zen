# Pro Git
- Remember that each file in your working directory can be in one of two states: tracked or untracked. Tracked files are files that were in the last snapshot; they can be unmodified, modified, or staged. In short, tracked files are files that Git knows about
- To stage it, you
- git add is a multipurpose command — you use it to begin tracking new files, to stage files, and to do other things like marking merge-conflicted files as resolved. It may be helpful to think of it more as “add precisely this content to the next commit” rather than “add this file to the project”
- The git add command takes a path name for either a file or a directory; if it’s a directory, the command adds all the files in that directory recursively.
- If you modify a file after you run git add, you have to run git add again to stage the latest version of the file: $ git add CONTRIBUTING.md $ git status On branch master Your branch is up-to-date with 'origin/master'.
- more time: $ vim CONTRIBUTING.md $ git status On branch master Your branch is up-to-date with 'origin/master'. Changes to be committed: (use "git reset HEAD <file>..." to unstage) new file: README modified: CONTRIBUTING.md Changes not staged for commit: (use "git add <file>..." to update what will be committed) (use "git checkout -- <file>..." to discard changes in working directory) modified: CONTRIBUTING.md What the heck? Now CONTRIBUTING.md is listed as both staged and unstaged. How is that possible? It turns out that Git stages a file exactly as it is when you run the git add command. If you commit now, the version of CONTRIBUTING.md as it was when you last ran the git add command is how it will go into the commit, not the version of the file as it looks in your working directory when you run git commit. If
- If you modify a file after you run git add, you have to run git add again to stage the latest version of the file: $ git add CONTRIBUTING.md $ git status On branch master Your branch is up-to-date with 'origin/master'.
- If you modify a file after you run git add, you have to run git add again to stage
- If you modify a file after you run git add, you have to run git add again to stage
- If you modify a file after you run git add, you have to run git add again to stage
- more time: $ vim CONTRIBUTING.md $ git status On branch master Your branch is up-to-date with 'origin/master'. Changes to be committed: (use "git reset HEAD <file>..." to unstage) new file: README modified: CONTRIBUTING.md Changes not staged for commit: (use "git add <file>..." to update what will be committed) (use "git checkout -- <file>..." to discard changes in working directory) modified: CONTRIBUTING.md What the heck? Now CONTRIBUTING.md is listed as both staged and unstaged. How is that possible? It turns out that Git stages a file exactly as it is when you run the git add command. If you commit now, the version of CONTRIBUTING.md as it was when you last ran the git add command is how it will go into the commit, not the version of the file as it looks in your working directory when you run git commit. If
