# Attach the Commit to a Branch

Git isn't truly happy until our commit is attached to a branch:

```
git update-ref refs/heads/master <commit-SHA>
```

Let's inspect it:

```
cat .git/refs/heads/master
```

A branch with a single commit is no fun. Let's do it again:

```
echo "some content" > another.md
git hash-object -w another.md
git update-index --add another.md
git write-tree
echo "a second commit" | git commit-tree <tree-SHA> -p <parent-commit-SHA>
git update-ref refs/heads/master <commit-SHA>
```

### Jump to [Next Exercise](6-make-pack.md)
