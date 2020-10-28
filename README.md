### Revert Uncommit codes

```

git checkout .

git checkout -- FILE

```


### Stash 

```

git stash save

git stash pop

```


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


### Remove files from history commit ; Reduce Size

```
git filter-branch --tree-filter "rm -rf A/B/C/D.zip" --prune-empty HEAD

git reflog expire --all --expire=now

git gc --prune=now --aggressive

git push origin --force --all

```


### Merge Branch Into Master with 1 commit

1. you have a branch called feature/A
2. feature/A has many commits
3. You want to merge feature/A branch into master with 1 commit.


```sh
git checkout master
git pull

git checkout -b merge/A
git merge --squash  feature/A
git commit # without -m ; remove all contents, then add new content ;

# merge to master
git checkout master
git merge merge/A
git log
git push
```




### Move file and keep history


```sh 
git filter-branch -f --tree-filter ' `if [ -f "A.txt" ]; then  git mv A.txt  C.txt  ; fi  ` ' HEAD 
```

