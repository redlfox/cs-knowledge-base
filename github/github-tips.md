# Github Tips

github default branch master main

[Managing the default branch name for your repositories - GitHub Docs](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-user-account-settings/managing-the-default-branch-name-for-your-repositories)

https://stackoverflow.com/questions/64781462/github-actions-default-branch-variable

* https://docs.github.com/en/search-github/github-code-search/understanding-github-code-search-syntax
* https://docs.github.com/en/get-started/accessibility/keyboard-shortcuts
## utilities
[👨‍💻 Developer Tools · fmhy/FMHY Wiki](https://github.com/fmhy/edit/blob/main/docs/devtools.md) [2](https://fmhy.net/devtools)

* [GitHub-Userscripts](https://github.com/Mottie/GitHub-userscripts) - GitHub Userscripts
* [Awesome Actions](https://github.com/sdras/awesome-actions) - Curated List of Github Actions
* [ActionServerless](https://github.com/gitx-io/ActionServerless) - Create Serverless Service
* [GitKraken](https://www.gitkraken.com/) or [Sourcetree](https://www.sourcetreeapp.com/) - Git GUI
* [lazygit](https://github.com/jesseduffield/lazygit) or [gitui](https://github.com/Extrawurst/gitui) - Git TUI
* [Codeberg](https://codeberg.org/), [git.sr.ht](https://git.sr.ht/), [Giters](https://www.giters.com/) or [GitGud](https://gitgud.io/) - Git Hosting
* [Snipli](https://www.snipli.xyz/) - Convert Localfiles to Gist
* [Git / Github Guide](https://www.notion.so/Git-GitHub-61bc81766b2e4c7d9a346db3078ce833)
* [GitBook](https://www.gitbook.com/) - Document Collaboration
* [Refined GitHub](https://github.com/sindresorhus/refined-github) - Simplifies GitHub Interface & Adds Features
* https://onlineminitools.com/github-repo-size-checker
* https://git-bit.netlify.app/
### Rollback revert commit
https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository

[newren/git-filter-repo: Quickly rewrite git repository history (filter-branch replacement)](https://github.com/newren/git-filter-repo) Quickly rewrite git repository history (filter-branch replacement)

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
