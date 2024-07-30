# Github-Commands

## Configuration

| Command                                             | Description                                                                   |
| --------------------------------------------------- | ----------------------------------------------------------------------------- |
| `git config --global user.name "John Doe"`          | Define the author name to be used for all commits in the current repository.  |
| `git config --global user.email example@gmail.com ` | Define the author email to be used for all commits in the current repository. |
| `git config --global color.ui auto`                 | Enable some colorization of Git output.                                       |
| `git config --global core.editor code`              | Define the text editor used by commands like `git commit`.                    |
| `git config --global --list`                        | List all the configurations.                                                  |

## Basic Commands

| Command                           | Description                                                     |
| --------------------------------- | --------------------------------------------------------------- |
| `git init`                        | Initialize a local Git repository                               |
| `git status`                      | List all new or modified files                                  |
| `git diff`                        | Show file differences that have not been staged                 |
| `git add <file>`                  | Add a file to the staging area                                  |
| `git diff --staged`               | Show file differences between staging and the last file version |
| `git commit -m "message"`         | Commit changes to head                                          |
| `git commit -a`                   | Commit any files that have been added with `git add`            |
| `git clone <url>`                 | Clone a repository into a new directory                         |
| `git log`                         | View changes made in the repository                             |
| `git log --oneline`               | View changes made in the repository in one line                 |
| `git log --graph --oneline --all` | View changes made in the repository in one line with graph      |
| `git log --oneline --graph`       | View changes made in the repository in one line with graph      |
| `git show <commit>`               | Show the changes made in the commit                             |
| `git show`                        | Show the changes made in the last commit                        |
| `git show HEAD`                   | Show the changes made in the last commit                        |
| `git show HEAD~1`                 | Show the changes made in the commit before the last commit      |
| `git reset HEAD <file>`           | Unstage a file                                                  |
| `git reset HEAD`                  | Unstage all files                                               |
| `git checkout -- <file>`          | Discard changes in the working directory                        |
| `git checkout <commit> -- <file>` | Discard changes in the working directory to the commit          |
| `git reset --hard`                | Discard all changes in the working directory                    |

## Branches

| Command                             | Description                                                                |
| ----------------------------------- | -------------------------------------------------------------------------- |
| `git branch`                        | List all the branches in the repository                                    |
| `git branch <branch>`               | Create a new branch                                                        |
| `git checkout <branch>`             | Switch to a branch                                                         |
| `git checkout -b <branch>`          | Create a new branch and switch to it                                       |
| `git merge <branch>`                | Merge a branch into the active branch                                      |
| `git branch -d <branch>`            | Delete a branch                                                            |
| `git push`                          | Push the changes to the remote repository                                  |
| `git push origin --delete <branch>` | Delete a branch in the remote repository                                   |
| `git push origin <branch>`          | Push the branch to the remote repository                                   |
| `git pull`                          | Update the local repository with changes from the remote repository        |
| `git pull origin <branch>`          | Update the local repository with changes from the remote repository branch |
| `git fetch`                         | Download objects and refs from another repository                          |
| `git fetch origin`                  | Download objects and refs from the remote repository                       |
| `git remote -v`                     | List all the remote repositories                                           |
| `git remote add <name> <url>`       | Add a new remote repository                                                |
| `git remote remove <name>`          | Remove a remote repository                                                 |

## Tags

| Command         | Description                         |
| --------------- | ----------------------------------- |
| `git tag`       | List all the tags in the repository |
| `git tag <tag>` | Create a new tag                    |

## Stash

| Command                   | Description                                |
| ------------------------- | ------------------------------------------ |
| `git stash`               | Stash changes in a dirty working directory |
| `git stash list`          | List all the stashes                       |
| `git stash apply`         | Apply the last stash                       |
| `git stash apply <stash>` | Apply a specific stash                     |
| `git stash drop`          | Remove the last stash                      |

## Rebase

| Command                 | Description                               |
| ----------------------- | ----------------------------------------- |
| `git rebase <branch>`   | Rebase the current branch with the branch |
| `git rebase --continue` | Continue the rebase process               |
| `git rebase --abort`    | Abort the rebase process                  |

## Gitignore

```bash
# Ignore all .a files
*.a
# But do track lib.a, even though you're ignoring .a files above
!lib.a
# Ignore all files in the build/ directory
build/
# Ignore doc/notes.txt, but not doc/server/arch.txt
doc/*.txt
# Ignore all .pdf files in the doc/ directory
doc/**/*.pdf

# etc...
```

## Aditional Resources

- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [Git Handbook](https://guides.github.com/introduction/git-handbook/)
