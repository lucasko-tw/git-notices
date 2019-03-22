
### Migrate Code from Sub Directory of Repo A to Repo B


```sh
git clone https://github.com/lucasko-tw/repo-A.git 

cd repo-A

git filter-branch --prune-empty --subdirectory-filter  ./the/sub_folder/you/want  master

git config --get remote.origin.url

git remote -v

git remote show

git remote set-url origin  https://github.com/lucasko-tw/repo-A.git 

git remote -v
```
