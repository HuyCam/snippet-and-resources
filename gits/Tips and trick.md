## [Untrack files already tracked by git repos in .gitignore](http://www.codeblocq.com/2016/01/Untrack-files-already-added-to-git-repository-based-on-gitignore/)

1. Commit all your changes
2. Remove everything from the repos
``` git rm -r --cached```
3. Re add everything
``` git add . ```
4. Commit and push it to remote repos.
``` git commit -m ".gitignore fix"```
5. Push it to the remote repos:```git push origin master```
