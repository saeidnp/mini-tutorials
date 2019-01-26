// Reference: https://gist.github.com/mandiwise/5954bbb2e95c011885ff

$ cd <repo-directory>
$ git remote rename origin bitbucket
$ git remote add origin <github-url>
$ git push origin master

$ git remote rm bitbucket
// Bitbucket (or any other VC host) repo can be deleted.
