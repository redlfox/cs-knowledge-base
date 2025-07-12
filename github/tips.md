# Github Tips

github default branch master main

* https://docs.github.com/en/search-github/github-code-search/understanding-github-code-search-syntax
* https://docs.github.com/en/get-started/accessibility/keyboard-shortcuts
## utilities
* https://onlineminitools.com/github-repo-size-checker
* https://git-bit.netlify.app/
### Rollback revert commit
https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository

git-filter-repo

[Manual Rollback Action · Actions · GitHub Marketplace](https://github.com/marketplace/actions/manual-rollback-action)

https://stackoverflow.com/questions/448919/how-can-i-remove-a-commit-on-github
```
git reset --soft HEAD^
#git reset --hard HEAD~1
git push origin +branchName --force
```
```
git push -f origin HEAD^:master
```
