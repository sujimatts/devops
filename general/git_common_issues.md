## The source branch is X commits behind the target branch

If your branch is behind by master then do:

```
git checkout master (you are switching your branch to master)
git pull 
git checkout yourBranch (switch back to your branch)
git merge master
```
After merging it, check if there is a conflict or not.
If there is NO CONFLICT then:

```git push```

If there is a conflict then fix your file(s), then:

```git add yourFile(s)
git commit -m 'updating my branch'
git push```

https://stackoverflow.com/questions/34118404/what-i-can-do-to-resolve-1-commit-behind-master
