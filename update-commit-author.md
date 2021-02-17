## Steps to change committer details 

- Make a alias command to search and replace in the commit:

```
git config --global alias.change-commits '!'"f() { VAR=\$1; OLD=\$2; NEW=\$3; shift 3; git filter-branch --env-filter \"if [[ \\\"\$\`echo \$VAR\`\\\" = '\$OLD' ]]; then export \$VAR='\$NEW'; fi\" \$@; }; f"
```
- Change the author name:

```
git change-commits GIT_AUTHOR_NAME "old name" "new name"
```

-- Change the author email: 

```
git change-commits GIT_AUTHOR_EMAIL "old@email.com" "new@email.com"
```