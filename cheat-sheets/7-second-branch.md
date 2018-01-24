# Working with Branches

First, we need to create a new branch:

```
git update-ref refs/heads/feature <commit-SHA>
```

Now that the branch exists, we need to check out to that branch:

```
git symbolic-ref HEAD refs/heads/feature
```

For time sake, let's create a few porcelain commits:

```
touch file1.md file2.md
git add file1.md
git commit -m "add file 1"
git add file2.md
git commit -m "add file 2"
```

How does Git know how to merge?

```
git merge-base master feature
```
