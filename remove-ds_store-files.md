## Remove existing files from the repository

```
find . -name .DS_Store -print0 | xargs -0 git rm -f --ignore-unmatch
echo .DS_Store >> .gitignore
git add .
git commit -m '.DS_Store banished!'
```