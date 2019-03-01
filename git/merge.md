Thanks to [this answer](https://stackoverflow.com/a/14168817) on stackoverflow, this is how I merge branches:
```
(on branch development)$ git merge master
(resolve any merge conflicts if there are any)
git checkout master
git merge --no-ff development (there won't be any conflicts now)
```

Doing merge in this way, causes master to remain clean and any possible mess will be in development branch. Also, it's essential to use `no-ff` option since it prevents git from doing fast-forward and makes a new commit for this merge anyways.