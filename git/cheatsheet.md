# Branches
## Rename a local branch
```
$ git branch -m <old_name> <new_name>
```
Or if you want to rename the branch you are on:
```
$ git branch -m <new_name>
```
## Delete a branch
### Local
```
$ git branch -d <branch>

// Force delete the branch
$ git branch -D <branch>
```

### Remote
```
$ git push <remote> --delete <branch>
```

## Create a new remote branch
Assuming that `<new-branch>` exists locally,
```
$ git push <remote> <new-branch>
```
This newly created is not being tracked by any local branches. The following command sets the current branch's upstream.
```
$ git push origin -u <new-branch>
```
We can also delete a remote branch and create a new one in one command:
```
$ git push origin :<old-branch> <new-branch>
```

# Miscellaneous
## Stop tracking a certain file
It is particularly useful for machine-specific files (like some of config files):
```
$ git update-index --assume-unchanged <path>
```
