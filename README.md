
### Migrate Code from Sub Directory of Repo A to Repo B


```sh
git clone https://github.com/lucasko-tw/repo-A.git 

cd repo-A

git filter-branch --prune-empty --subdirectory-filter  ./the/sub_folder/you/want  master

git config --get remote.origin.url

git remote -v
#origin	https://github.com/lucasko-tw/repo-A.git  (fetch)
#origin	https://github.com/lucasko-tw/repo-A.git  (push)


git remote show

git remote set-url origin  https://github.com/lucasko-tw/repo-B.git 

git remote -v
#origin	https://github.com/lucasko-tw/repo-B.git  (fetch)
#origin	https://github.com/lucasko-tw/repo-B.git  (push)

git add .

git commit -m "migration"

git push
```
