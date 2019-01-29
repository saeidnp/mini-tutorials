// Reference: [here](https://gist.github.com/mandiwise/5954bbb2e95c011885ff) and [here](https://gist.github.com/niksumeiko/8972566).
## Transferring `master` branch

```
$ cd <repo-directory>
$ git remote rename origin bitbucket
$ git remote add origin <github-url>
$ git push origin master

$ git remote rm bitbucket
// Bitbucket (or any other VC host) repo can be deleted.
```

## Transferring all branches

```
$ cd <repo-directory>

// Fetching all remote branches

$ git fetch origin

// View all branches
$ git branch -a
// If some of the remotes/ branches doesn't have a local copy, checkout to create a local copy of the missing ones:
$ git checkout -b <branch> origin/<branch>
// Now we have all branches locally.

// Make sure all local branches are up-to-date. You can checkout to the branches one by one and pull.
// Or if you have "tig" installed, you can do the following:
$ tig --all
// It will show all the local and remote branches. Checkout to the ones that have local fell behind and pull.

// Add the new remote
$ git remote rename origin bitbucket
$ git remote add origin <github-url>

// Push all branches to the new remote
$ git push --all origin

// Push all tags to the new remote
$ git push --tags origin

// Delete the old origin
$ git remote rm bitbucket
```